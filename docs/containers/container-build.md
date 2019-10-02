---
title: Visual Studio コンテナー ツールのビルド概要
author: ghogen
description: コンテナー ツールのビルド プロセスの概要
ms.author: ghogen
ms.date: 06/06/2019
ms.technology: vs-azure
ms.topic: conceptual
ms.openlocfilehash: edc4674e2468124ecb46b25a1411043ed4b66a2a
ms.sourcegitcommit: e98db44f3a33529b0ba188d24390efd09e548191
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2019
ms.locfileid: "71253112"
---
# <a name="building-containerized-apps-using-visual-studio-or-the-command-line"></a>Visual Studio またはコマンド ラインを使用してコンテナー化されたアプリをビルドする

Visual Studio IDE からビルドする場合でも、コマンド ライン ビルドを設定する場合でも、Visual Studio のビルドで Dockerfile を使用してプロジェクトがどのようにビルドされるかを知っておく必要があります。  パフォーマンス上の理由から、Visual Studio ではコンテナー化されたアプリの特別なプロセスに従います。 Visual Studio がプロジェクトをビルドする方法を理解することは、Dockerfile を変更してビルド プロセスをカスタマイズする場合に特に重要です。

Visual Studio では、Docker コンテナーを使用しないプロジェクトをビルドするときに、ローカル コンピューター上で MSBuild が呼び出され、ローカル ソリューション フォルダーの下のフォルダー (通常は `bin`) 内に出力ファイルが生成されます。 ただし、コンテナー化されたプロジェクトの場合、コンテナー化されたアプリをビルドするため、ビルド プロセスで Dockerfile の命令が考慮されます。 Visual Studio で使用される Dockerfile は、複数のステージに分割されます。 このプロセスは、Docker の*マルチステージ ビルド*機能に依存しています。

## <a name="multistage-build"></a>マルチステージ ビルド

マルチステージ ビルド機能を使用すると、コンテナーのビルド プロセスが効率化され、実行時にアプリに必要なビットしか含めないようにすることで、コンテナーのサイズを小さくすることができます。 マルチステージ ビルドは、.NET Framework プロジェクトではなく、.NET Core プロジェクトに使用されます。

マルチステージ ビルドを使用すると、中間イメージを生成するステージでコンテナー イメージを作成できます。 例として、Visual Studio によって生成される一般的な Dockerfile を考えてみます。最初のステージは `base` です。

```
FROM mcr.microsoft.com/dotnet/core/aspnet:2.2-stretch-slim AS base
WORKDIR /app
EXPOSE 80
EXPOSE 443
```

Dockerfile 内の行は、Microsoft Container Registry (mcr.microsoft.com) の Nanoserver イメージから始まり、ポート 80 および 443 を公開する中間イメージ `base` を作成し、作業ディレクトリを `/app` に設定します。

次のステージは `build` で、次のように表示されます。

```
FROM mcr.microsoft.com/dotnet/core/sdk:2.2-stretch AS build
WORKDIR /src
COPY ["WebApplication43/WebApplication43.csproj", "WebApplication43/"]
RUN dotnet restore "WebApplication43/WebApplication43.csproj"
COPY . .
WORKDIR "/src/WebApplication43"
RUN dotnet build "WebApplication43.csproj" -c Release -o /app
```

`build` のステージは、base からの続きではなく、レジストリ (`aspnet` ではなく `sdk`) からの別の、元のイメージから開始されることがわかります。  `sdk` のイメージにはすべてのビルド ツールがあるため、実行時コンポーネントのみを含む aspnet イメージよりもかなり大きくなります。 別のイメージを使用する理由は、Dockerfile の残りの部分を確認すると明確になります。

```
FROM build AS publish
RUN dotnet publish "WebApplication43.csproj" -c Release -o /app

FROM base AS final
WORKDIR /app
COPY --from=publish /app .
ENTRYPOINT ["dotnet", "WebApplication43.dll"]
```

最後のステージは、もう一度 `base` から始まります。発行された出力を最終イメージにコピーするための `COPY --from=publish` が含まれます。 このプロセスを使用すると、`sdk` イメージに含まれていたすべてのビルド ツールを含める必要がないため、最終的なイメージがかなり小さくなる可能性があります。

## <a name="faster-builds-for-the-debug-configuration"></a>デバッグ構成のためのビルドの高速化

Visual Studio では、コンテナー化されたプロジェクトのビルド プロセスのパフォーマンスを向上させるため、いくつかの最適化が行われています。 デバッグを開始 (F5) すると、可能な場合には、ビルド済みのイメージが再利用されます。 前のコンテナーを再利用しない場合は、Visual Studio で **Rebuild** または **Clean** コマンドを使用して、Visual Studio で新しいコンテナーを強制的に使用することができます。

また、パフォーマンスを向上させるには、コンテナー化されたアプリのビルド プロセスは、Dockerfile に記載されている手順に単に従うほど簡単ではありません。 コンテナーでのビルドは、ローカル コンピューターでのビルドよりもはるかに低速です。  そのため、**デバッグ**構成でビルドすると、Visual Studio によって実際にプロジェクトがローカル コンピューター上にビルドされてから、ボリューム マウントを使用して出力フォルダーがコンテナーに共有されます。 この最適化が有効になっているビルドは、*高速*モードのビルドと呼ばれます。

**高速**モードでは、Visual Studio により、`base` ステージのみをビルドするように Docker に指示する引数を指定して `docker build` が呼び出されます。  Visual Studio では、Dockerfile の内容に関係なく、プロセスの残りの部分が処理されます。 そのため、コンテナー環境をカスタマイズしたり、追加の依存関係をインストールしたりするために Dockerfile を変更する場合は、最初のステージで変更を加える必要があります。  Dockerfile の `build`、`publish`、`final` のいずれかのステージに配置されているカスタム ステップは実行されません。

このパフォーマンスの最適化は、**デバッグ**構成でビルドする場合にのみ発生します。 **リリース**構成では、Dockerfile で指定されているように、コンテナーでビルドが実行されます。

Dockerfile によって指定されているパフォーマンスの最適化とビルドを無効にする場合は、次のように、プロジェクト ファイルの **ContainerDevelopmentMode** プロパティを **Regular** に設定します。

```xml
<PropertyGroup>
   <ContainerDevelopmentMode>Regular</ContainerDevelopmentMode>
</PropertyGroup>
```

パフォーマンスの最適化を復元するには、プロジェクト ファイルからプロパティを削除します。

## <a name="building-from-the-command-line"></a>コマンド ラインからのビルド

`docker build` または `MSBuild` を使用すると、コマンド ラインからビルドできます。

### <a name="docker-build"></a>docker build

コマンド ラインからコンテナー化されたソリューションをビルドするには、通常、ソリューション内の各プロジェクトに対してコマンド `docker build <context>` を使用します。 *build context* 引数を指定します。 Dockerfile の *build context* は、イメージを生成する作業フォルダーとして使用されるローカル コンピューター上のフォルダーです。 たとえば、コンテナーにコピーするときにファイルをコピーするフォルダーです。  .NET Core プロジェクトでは、ソリューション ファイル (.sln) が格納されているフォルダーを使用します。  相対パスとして表されます。この引数は、通常、プロジェクト フォルダー内の Dockerfile とその親フォルダー内のソリューション ファイルに対しては ".." です。  .NET Framework プロジェクトの場合、build context はソリューション フォルダーではなく、プロジェクト フォルダーです。

```cmd
docker build -f Dockerfile ..
```

### <a name="msbuild"></a>MSBuild

Visual Studio によって .NET Framework プロジェクト用 (および Visual Studio 2017 Update 4 より前のバージョンの Visual Studio で作成された .NET Core プロジェクト用) に作成された Dockerfile は、マルチステージの Dockerfile ではありません。  これらの Dockerfile のステップでは、コードはコンパイルされません。  代わりに、Visual Studio では .NET Framework Dockerfile をビルドする際に、まず MSBuild を使用してプロジェクトがコンパイルされます。  これが成功すると、Visual Studio によって Dockerfile がビルドされます。これは単純に、MSBuild からのビルド出力が、生成された Docker イメージにコピーされます。  コードをコンパイルするステップは Dockerfile に含まれていないため、コマンド ラインから `docker build` を使用して .NET Framework Dockerfile をビルドすることはできません。 これらのプロジェクトをビルドするには、MSBuild を使用する必要があります。

単一の Docker コンテナー プロジェクトのイメージをビルドするには、MSBuild を `/t:ContainerBuild` コマンド オプションと共に使用します。 次に例を示します。

```cmd
MSBuild MyProject.csproj /t:ContainerBuild /p:Configuration=Release
```

Visual Studio IDE からソリューションをビルドすると、**出力**ウィンドウに表示されるような出力が表示されます。 Visual Studio でマルチステージ ビルドの最適化が使用されている場合は、**デバッグ**構成をビルドするときに得られる結果が想定どおりでない場合があるため、常に `/p:Configuration=Release` を使用します。

Docker Compose プロジェクトを使用している場合は、コマンドを使用してイメージをビルドします。

```cmd
msbuild /p:SolutionPath=<solution-name>.sln /p:Configuration=Release docker-compose.dcproj
```

## <a name="next-steps"></a>次の手順

プロジェクト ファイルで追加の MSBuild プロパティを設定して、ビルドをさらにカスタマイズする方法について学習します。 [コンテナーのプロジェクトの MSBuild プロパティ](container-msbuild-properties.md)に関するページを参照してください。

## <a name="see-also"></a>関連項目

[MSBuild](../msbuild/msbuild.md)
[Windows の Dockerfile](/virtualization/windowscontainers/manage-docker/manage-windows-dockerfile)
[Windows 上の Linux コンテナー](/virtualization/windowscontainers/deploy-containers/linux-containers)
