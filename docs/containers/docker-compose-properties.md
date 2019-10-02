---
title: Visual Studio コンテナー ツール Docker Compose ビルド設定
author: ghogen
description: コンテナー ツールのビルド プロセスの概要
ms.author: ghogen
ms.date: 08/12/2019
ms.technology: vs-azure
ms.topic: conceptual
ms.openlocfilehash: 06a1c5b637ca2ed9306162ee1960c60d103e5843
ms.sourcegitcommit: 88f576ac32af31613c1a10c1548275e1ce029f4f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2019
ms.locfileid: "71185980"
---
# <a name="docker-compose-build-properties"></a>Docker Compose のビルド プロパティ

「[コンテナー ツールのビルド プロパティ](container-msbuild-properties.md)」で説明している、個々の Docker プロジェクトを制御するプロパティに加え、ソリューション構築のために MSBuild で使用される Docker Compose プロパティを設定することで、Visual Studio による Docker Compose プロジェクトのビルド方法をカスタマイズすることもできます。 Docker Compose 構成ファイルでファイル ラベルを設定することで、Visual Studio デバッガーによる Docker Compose アプリの実行方法を制御することもできます。

## <a name="how-to-set-the-msbuild-properties"></a>MSBuild プロパティの設定方法

プロパティの値を設定するには、プロジェクト ファイルを編集します。 Docker Compose プロパティの場合、このプロジェクトファイルは、次のセクションの表で特に指定されていない限り、拡張子が .dcproj のプロジェクト ファイルです。 たとえば、デバッグを開始するときにブラウザーを起動するように指定するとします。 次のように、.dcproj プロジェクト ファイル内で `DockerLaunchAction` プロパティを設定できます。

```xml
<PropertyGroup>
   <DockerLaunchAction>LaunchBrowser</DockerLaunchAction>
</PropertyGroup>
```

プロパティ設定を既存の `PropertyGroup` 要素に追加できます。存在しない場合は、新しい `PropertyGroup` 要素を作成できます。

## <a name="docker-compose-msbuild-properties"></a>Docker Compose MSBuild のプロパティ

次の表は、Docker Compose プロジェクトで使用できる MSBuild プロパティを示しています。

| プロパティ名 | 場所 | 説明 | 既定値  |
|---------------|----------|-------------|----------------|
|DockerComposeBuildArguments|dcproj|`docker-compose build` コマンドに渡す追加のパラメーターを指定します。 たとえば、`--parallel --pull` |
|DockerComposeDownArguments|dcproj|`docker-compose down` コマンドに渡す追加のパラメーターを指定します。 たとえば、`--timeout 500`|-|  
|DockerComposeProjectPath|csproj または vbproj|docker-compose プロジェクト (dcproj) ファイルの相対パス。 docker-compose.yml ファイルに格納されている関連イメージ ビルド設定を見つける目的で、サービス プロジェクトの公開時にこのプロパティを設定します。|-|
|DockerComposeUpArguments|dcproj|`docker-compose up` コマンドに渡す追加のパラメーターを指定します。 たとえば、`--timeout 500`|-|
|DockerLaunchAction| dcproj | F5 または Ctrl + F5 キーで実行する起動アクションを指定します。  指定できる値には、None、LaunchBrowser、LaunchWCFTestClient があります。|なし|
|DockerLaunchBrowser| dcproj | ブラウザーを起動するかどうかを示します。 DockerLaunchAction が指定されている場合は無視されます。 | False |
|DockerServiceName| dcproj|DockerLaunchAction または DockerLaunchBrowser が指定されている場合、DockerServiceName は、起動する必要があるサービスの名前です。  docker-compose 構成ファイルで参照できるプロジェクトはたくさん存在する可能性があります。そのうちのどれを起動するかをこのプロパティを使用して決定します。|-|
|DockerServiceUrl| dcproj | ブラウザーを起動するときに使用される URL。  有効な置換トークンには、"{ServiceIPAddress}"、"{ServicePort}"、"{Scheme}" があります。  例: {Scheme}://{ServiceIPAddress}:{ServicePort}|-|
|DockerTargetOS| dcproj | Docker イメージをビルドするときに使用されるターゲット OS。|-|

> [!NOTE]
> Visual Studio 2019 バージョン 16.3 Preview 3 では、DockerComposeBuildArguments、DockerComposeDownArguments、DockerComposeUpArguments が新しく追加されています。

## <a name="docker-compose-file-labels"></a>Docker Compose ファイル ラベル

*docker-compose.yml* ファイルと同じディレクトリに *docker-compose.vs.debug.yml* という名前のファイル (**デバッグ**構成の場合) または *docker-compose.vs.release.yml* という名前のファイル (**リリース**構成の場合) を置くことで一部の設定をオーバーライドすることもできます。  このファイルでは、次のように設定を指定できます。

```yml
services:
  webapplication1:
    labels:
      com.microsoft.visualstudio.debuggee.workingdirectory: "C:\\my_app_folder"
```

前の例のように値を二重引用符で囲み、パスでバックスラッシュのエスケープ文字としてバックスラッシュを使用します。

|ラベル名|説明|
|----------|-----------|
|com.microsoft.visualstudio.debuggee.arguments|デバッグの開始時にプログラムに渡される引数。 .NET Core アプリの場合、通常、これらの引数は NuGet パッケージの追加検索パスであり、これにプロジェクトの出力アセンブリのパスが続きます。|
|com.microsoft.visualstudio.debuggee.killprogram|このコマンドは、(必要なときに) コンテナー内で実行されているデバッグ対象プログラムを停止する目的で使用されます。|
|com.microsoft.visualstudio.debuggee.program|デバッグの開始時に起動するプログラム。 .NET Core アプリの場合、この設定は通常、**dotnet** です。|
|com.microsoft.visualstudio.debuggee.workingdirectory|デバッグの開始時に開始ディレクトリとして使用されるディレクトリ。 この設定は通常、Linux コンテナーの場合は */app*、Windows コンテナーの場合は *C:\app* になります。|

## <a name="next-steps"></a>次の手順

MSBuild プロパティの一般情報については、[MSBuild プロパティ](../msbuild/msbuild-properties.md)を参照してください。

## <a name="see-also"></a>関連項目

[コンテナー ツールのビルド プロパティ](container-msbuild-properties.md)

[コンテナー ツールの起動設定](container-launch-settings.md)

[MSBuild の予約済みおよび既知のプロパティ](../msbuild/msbuild-reserved-and-well-known-properties.md)
