---
title: Visual Studio 2017 の機能拡張における重大な変更
titleSuffix: ''
ms.date: 11/09/2016
ms.topic: conceptual
ms.assetid: 54d5af60-0b44-4ae1-aa57-45aa03f89f3d
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a1a12470530589c8d19a088428bc265c530b55f0
ms.sourcegitcommit: e98db44f3a33529b0ba188d24390efd09e548191
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2019
ms.locfileid: "71252317"
---
# <a name="changes-in-visual-studio-2017-extensibility"></a>Visual Studio 2017 の拡張機能の変更点

Visual studio 2017 では、[より高速で軽量な Visual studio インストールエクスペリエンス](https://devblogs.microsoft.com/visualstudio/faster-leaner-visual-studio-installer)が提供されます。これにより、ユーザーは、インストールされているワークロードと機能に対してより多くの選択肢を提供できるだけではありません。 これらの機能強化をサポートするために、いくつかの重大な変更を含め、拡張モデルを変更しました。 この記事では、これらの変更の技術的な詳細と、それらに対処するために実行できる操作について説明します。

> [!NOTE]
> 一部の情報は、特定の時点の実装の詳細であり、後で変更される可能性があります。

## <a name="changes-affecting-vsix-format-and-installation"></a>VSIX の形式とインストールに影響を与える変更

Visual Studio 2017 では、ライトウェイトインストールエクスペリエンスをサポートするために、VSIX v3 (バージョン 3) 形式が導入されました。

VSIX 形式における変更は次のとおりです:

* セットアップの前提条件の宣言。 Visual Studio の軽量で、高速なインストールを実現するため、 インストーラーはより多くの構成オプションをユーザーへ提供するようになりました。 そのため、拡張機能に必要な機能とコンポーネントがインストールされていることを確認するには、拡張機能に依存関係を宣言する必要があります。

  * Visual Studio 2017 インストーラーでは、拡張機能のインストールの一環として、ユーザーに必要なコンポーネントを取得してインストールするように自動的に提供されます。
  * 新しい VSIX v3 形式を使用してビルドされていない拡張機能をインストールしようとすると、ユーザーにも警告が表示されます。これは、バージョン15.0 のターゲットとしてマニフェストでマークされている場合でも同様です。

* VSIX 形式の機能を強化します。 サイド バイ サイド インストールをもサポートする Visual Studio の[影響の少ないインストール](https://devblogs.microsoft.com/visualstudio/anatomy-of-a-low-impact-visual-studio-install)で提供するため、ほとんどの構成データはシステム レジストリに保存されなくなり、Visual Studio 固有のアセンブリが GAC から取り除かれました。 また VSIX 形式と VSIX インストールエンジンの機能が強化されたため、一部のインストールの種類においては、MSI や EXE の代わりにそれらの機能を使用して拡張機能をインストールできるようになりました。

新しい機能は次のとおりです。

* 指定した Visual Studio インスタンスへの登録。
* [拡張フォルダー](set-install-root.md)外部でのインストール。
* プロセッサ アーキテクチャの検出。
* 言語で区切られた言語パックの依存関係。
* [NGEN サポート](ngen-support.md)を使用したインストール。

## <a name="build-an-extension-for-visual-studio-2017"></a>Visual Studio 2017 の拡張機能をビルドする

新しい VSIX v3 マニフェスト形式を作成するためのデザイナーツールは、Visual Studio 2017 で使用できます。 付属のドキュメント[を参照してください。デザイナーツールの使用、または](how-to-migrate-extensibility-projects-to-visual-studio-2017.md)プロジェクトとマニフェストへの手動更新を行って VSIX v3 拡張機能を開発する方法の詳細については、「機能拡張プロジェクトを Visual Studio 2017 に移行する」をご確認ください。

## <a name="change-visual-studio-user-data-path"></a>変更Visual Studio ユーザーデータパス

これまで Visual Studio の各メジャー リリースは 1 つのコンピューターにつき 1 つまでしかインストールすることができませんでした。 Visual Studio 2017 ではサイド バイ サイド インストールをサポートするために、複数の Visual Studio ユーザー データ パスをユーザーのコンピューターに存在させることができます。

Visual studio のプロセス内で実行されているコードは、Visual Studio の設定マネージャーを使用するように更新する必要があります。 Visual Studio プロセスの外部で実行されているコードは[このガイダンスに従って](locating-visual-studio.md)特定の Visual Studio インストールのユーザー パスを検索することができます。

## <a name="change-global-assembly-cache-gac"></a>変更グローバルアセンブリキャッシュ (GAC)

ほとんどの Visual Studio コアアセンブリは、GAC にインストールされなくなりました。 次の変更は、Visual Studio プロセスで実行されるコードが実行時に必要なアセンブリを見つけることができるようにするために行われました。

> [!NOTE]
> 下の [INSTALLDIR] は、Visual Studio のインストールルートディレクトリを示しています。 *VSIXInstaller*によって自動的に設定されますが、カスタムデプロイコードを記述するには、「 [Visual Studio の検索](locating-visual-studio.md)」を参照してください。

* GAC にのみインストールされたアセンブリ:

  これらのアセンブリは<em>、\*[INSTALLDIR] \Common7\IDE、* [INSTALLDIR] \Common7\IDE\PublicAssemblies</em>または *[INSTALLDIR] \Common7\IDE\PrivateAssemblies*の下にインストールされるようになりました。 これらのフォルダーは、Visual Studio プロセスのプローブパスの一部です。

* 非プローブパスと GAC にインストールされたアセンブリ:

  * GAC のコピーがセットアップから削除されました。
  * アセンブリのコードベースエントリを指定するために、 *pkgdef*ファイルが追加されました。

    次に例を示します。

    ```
    [$RootKey$\RuntimeConfiguration\dependentAssembly\codeBase\{UniqueGUID}]
    "name"="AssemblyName" "codeBase"="$PackageFolder$\AssemblyName.dll"
    "publicKeyToken"="Public Key Token"
    "culture"="neutral"
    "version"=15.0.0.0
    ```

    実行時に、visual studio .pkgdef サブシステムは、これらのエントリを要素として[`<codeBase>`](/dotnet/framework/configure-apps/file-schema/runtime/codebase-element) visual studio プロセスのランタイム構成ファイル ( *[vsappdata] \devenv.exe.config*の下) にマージします。 これは、Visual Studio プロセスでアセンブリを検索するために推奨される方法です。プローブパスの検索が回避されるためです。

### <a name="reacting-to-this-breaking-change"></a>この重大な変更への対応

* 拡張機能が Visual Studio プロセス内で実行されている場合:

  * コードでは、Visual Studio のコアアセンブリを見つけることができます。
  * 必要に応じて、 *pkgdef*ファイルを使用してアセンブリへのパスを指定することを検討してください。

* 拡張機能が Visual Studio プロセス外で実行されている場合:

  構成ファイルまたはアセンブリを使用して<em>、[INSTALLDIR\*] \Common7\IDE、* [INSTALLDIR] \Common7\IDE\PublicAssemblies</em>または *[INSTALLDIR] \Common7\IDE\PrivateAssemblies*の下で Visual Studio コアアセンブリを検索することを検討してくださいアーティクル.

## <a name="change-reduce-registry-impact"></a>変更レジストリへの影響を軽減する

### <a name="global-com-registration"></a>グローバル COM 登録

* 以前は、Visual Studio では、ネイティブ COM 登録をサポートするために、HKEY_CLASSES_ROOT および HKEY_LOCAL_MACHINE ハイブに多くのレジストリキーがインストールされていました。 この影響を避けるために、Visual Studio では、 [COM コンポーネントの登録を不要にしたアクティベーション](https://msdn.microsoft.com/library/ms973913.aspx)が使用されるようになりました。
* その結果、既定では、Visual Studio によって、% ProgramFiles (x86)% \ Common .OLB v の下にあるほとんどの TLB//DLL ファイルがインストールされなくなりました。 これらのファイルは、Visual Studio ホストプロセスによって使用される、対応する登録不要の COM マニフェストと共に [INSTALLDIR] の下にインストールされるようになりました。
* その結果、Visual Studio COM インターフェイスのグローバル COM 登録に依存する外部コードは、これらの登録を見つけることができなくなります。 Visual Studio プロセス内で実行されているコードに違いはありません。

### <a name="visual-studio-registry"></a>Visual Studio レジストリ

* 以前は、visual Studio では、Visual Studio 固有のキーの下に、システムの**HKEY_LOCAL_MACHINE**および**HKEY_CURRENT_USER**ハイブに多くのレジストリキーがインストールされていました。

  * **HKLM\Software\Microsoft\VisualStudio\{Version}** :MSI インストーラーおよびコンピューターごとの拡張機能によって作成されたレジストリキー。
  * **HKCU\Software\Microsoft\VisualStudio\{Version}** :ユーザー固有の設定を格納するために Visual Studio によって作成されたレジストリキー。
  * **HKCU\Software\Microsoft\VisualStudio\{バージョン} 構成 (_c)** :上の Visual Studio HKLM キーのコピーと、拡張子によって、 *pkgdef*ファイルからマージされたレジストリキー。

* レジストリへの影響を軽減するために、Visual Studio では、 [Regloadappkey](/windows/desktop/api/winreg/nf-winreg-regloadappkeya)関数を使用して、レジストリキーを *[vsappdata] \privateregistry.bin*の下のプライベートバイナリファイルに格納するようになりました。 システムレジストリに含まれる Visual Studio 固有のキーの数はごくわずかです。
* Visual Studio プロセス内で実行されている既存のコードは影響を受けません。 Visual Studio は、HKCU Visual Studio 固有のキーの下にあるすべてのレジストリ操作をプライベートレジストリにリダイレクトします。 他のレジストリの場所の読み取りと書き込みでは、システムレジストリが引き続き使用されます。
* 外部コードは、Visual Studio レジストリエントリのためにこのファイルの読み込みと読み取りを行う必要があります。

### <a name="react-to-this-breaking-change"></a>この重大な変更に対処する

* 外部コードは、COM コンポーネントの登録を必要としないアクティベーションを使用するように変換する必要があります。
* 外部コンポーネントは、[こちらのガイダンスに従って](https://devblogs.microsoft.com/setup/changes-to-visual-studio-15-setup)Visual Studio の場所を見つけることができます。
* 外部コンポーネントでは、Visual Studio レジストリキーを直接読み書きするのではなく、[外部設定マネージャー](/dotnet/api/microsoft.visualstudio.settings.externalsettingsmanager)を使用することをお勧めします。
* 拡張機能が使用しているコンポーネントが、別の登録手法を実装していないかどうかを確認します。 たとえば、デバッガー拡張機能では、新しい[MSVSMON JSON ファイル COM 登録](migrate-debugger-COM-registration.md)を利用できます。
