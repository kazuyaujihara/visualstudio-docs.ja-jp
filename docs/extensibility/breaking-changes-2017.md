---
title: Visual Studio 2017 の拡張機能における重大な変更
titleSuffix: ''
ms.date: 11/09/2016
ms.topic: conceptual
ms.assetid: 54d5af60-0b44-4ae1-aa57-45aa03f89f3d
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 589f5eddb2b1e2a8fd61eea2a205f12d2d9c0742
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66321356"
---
# <a name="changes-in-visual-studio-2017-extensibility"></a>Visual Studio 2017 の機能拡張の変更

Visual Studio 2017 の提供、[高速、軽量な Visual Studio のインストール エクスペリエンス](https://devblogs.microsoft.com/visualstudio/faster-leaner-visual-studio-installer)ワークロードとは機能経由でユーザーより多くの選択肢を提供中に Visual Studio のユーザーのシステムへの影響を減らすインストールされています。 これらの機能強化をサポートするには、いくつかの重大な変更を含む、機能拡張モデルに変更を行いましたしました。 この記事では、これらの変更と対処に何ができる技術的な詳細について説明します。

> [!NOTE]
> いくつかの情報は、特定の時点の実装の詳細についてし、後で変更することがあります。

## <a name="changes-affecting-vsix-format-and-installation"></a>VSIX 形式とインストールに影響する変更

Visual Studio 2017 には、VSIX v3 が導入された、軽量なインストール エクスペリエンスをサポートするために (バージョン 3) の形式。

VSIX 形式における変更は次のとおりです:

* セットアップの前提条件の宣言。 Visual Studio の軽量で、高速なインストールを実現するため、 インストーラーはより多くの構成オプションをユーザーへ提供するようになりました。 その結果、機能と拡張機能に必要なコンポーネントがインストールされているためには、拡張機能がその依存関係を宣言する必要があります。

  * Visual Studio 2017 インストーラーを入手し、拡張機能のインストールの一環として、ユーザーに必要なコンポーネントをインストールする自動的に提供します。
  * ユーザーは、拡張機能が組み込まれていない新しい VSIX v3 形式を使用してバージョン 15.0 をターゲットとすると、マニフェストでマークされている場合でもをインストールしようとするときにも警告されます。

* VSIX 形式の機能を強化します。 サイド バイ サイド インストールをもサポートする Visual Studio の[影響の少ないインストール](https://devblogs.microsoft.com/visualstudio/anatomy-of-a-low-impact-visual-studio-install)で提供するため、ほとんどの構成データはシステム レジストリに保存されなくなり、Visual Studio 固有のアセンブリが GAC から取り除かれました。 また VSIX 形式と VSIX インストールエンジンの機能が強化されたため、一部のインストールの種類においては、MSI や EXE の代わりにそれらの機能を使用して拡張機能をインストールできるようになりました。

新しい機能は次のとおりです。

* 指定した Visual Studio インスタンスへの登録。
* [拡張フォルダー](set-install-root.md)外部でのインストール。
* プロセッサ アーキテクチャの検出。
* 言語で区切られた言語パックの依存関係。
* [NGEN サポート](ngen-support.md)を使用したインストール。

## <a name="build-an-extension-for-visual-studio-2017"></a>Visual Studio 2017 の拡張機能をビルドします。

デザイナーの新しいオーサリング ツールは VSIX v3 マニフェスト形式では、Visual Studio 2017 で使用できます。 付属のドキュメントを参照してください。[方法。機能拡張プロジェクトを Visual Studio 2017 に移行](how-to-migrate-extensibility-projects-to-visual-studio-2017.md)デザイナー ツールを使用して、または、プロジェクトを手動で更新したことの詳細とマニフェスト v3 の VSIX 拡張機能を開発します。

## <a name="change-visual-studio-user-data-path"></a>変更:Visual Studio のユーザー データ パス

これまで Visual Studio の各メジャー リリースは 1 つのコンピューターにつき 1 つまでしかインストールすることができませんでした。 Visual Studio 2017 ではサイド バイ サイド インストールをサポートするために、複数の Visual Studio ユーザー データ パスをユーザーのコンピューターに存在させることができます。

Visual Studio プロセス内で実行されているコードは、Visual Studio の設定マネージャーを使用して更新する必要があります。 Visual Studio プロセスの外部で実行されているコードは[このガイダンスに従って](locating-visual-studio.md)特定の Visual Studio インストールのユーザー パスを検索することができます。

## <a name="change-global-assembly-cache-gac"></a>変更:グローバル アセンブリ キャッシュ (GAC)

ほとんどの Visual Studio のコア アセンブリは GAC にインストールされません。 Visual Studio のプロセスで実行されるコードは引き続き実行時に必要なアセンブリを検出できるように、次の変更が行われました。

> [!NOTE]
> [INSTALLDIR] Visual Studio のインストールのルート ディレクトリに以下を参照します。 *VSIXInstaller.exe* 、これを自動的に設定されますが、カスタム展開コードを記述することをお読みください[Visual Studio の検出](locating-visual-studio.md)します。

* アセンブリを GAC にインストールされただけの:

   これらのアセンブリがインストールされた<em>[INSTALLDIR] \Common7\IDE\*、* [INSTALLDIR] \Common7\IDE\PublicAssemblies</em>または *[INSTALLDIR] \Common7\IDE\PrivateAssemblies*します。 これらのフォルダーは、Visual Studio プロセスのプローブ パスの一部です。

* 非プローブのパスと、GAC にインストールされたアセンブリの場合:

   * GAC 内のコピーは、セットアップから削除されました。
   * A *.pkgdef*アセンブリのコード ベースのエントリを指定するファイルが追加されました。

      例:

      ```xml
      [$RootKey$\RuntimeConfiguration\dependentAssembly\codeBase\{UniqueGUID}]
      "name"="AssemblyName" "codeBase"="$PackageFolder$\AssemblyName.dll"
      "publicKeyToken"="Public Key Token"
      "culture"="neutral"
      "version"=15.0.0.0
      ```

      Visual Studio の pkgdef サブシステムは、実行時に、Visual Studio プロセスのランタイム構成ファイルにこれらのエントリをマージ ( *[VSAPPDATA]\devenv.exe.config*) として[ `<codeBase>` ](/dotnet/framework/configure-apps/file-schema/runtime/codebase-element)要素。 これは、プローブ パスから検索を回避するので、独自のアセンブリを検索する Visual Studio のプロセスをできるようにすることをお勧めの方法です。

### <a name="reacting-to-this-breaking-change"></a>この重大な変更に反応します。

* 拡張機能は、Visual Studio プロセス内で実行している: 場合

   * コードは Visual Studio のコア アセンブリを検索することになります。
   * 使用を検討して、 *.pkgdef*ファイルに必要な場合に、アセンブリへのパスを指定します。

* 拡張機能は Visual Studio プロセスの外部で実行されている: 場合

   Visual Studio のコア アセンブリを探して検討<em>[INSTALLDIR] \Common7\IDE\*、* [INSTALLDIR] \Common7\IDE\PublicAssemblies</em>または *[INSTALLDIR] \Common7\IDE\PrivateAssemblies*構成ファイルまたはアセンブリ リゾルバーを使用します。

## <a name="change-reduce-registry-impact"></a>変更:レジストリへの影響を減らす

### <a name="global-com-registration"></a>グローバルの COM 登録

* 以前は、Visual Studio では、ネイティブの COM 登録をサポートするために HKEY_CLASSES_ROOT と HKEY_LOCAL_MACHINE ハイブに多くのレジストリ キーをインストールします。 この影響を排除するために Visual Studio を今すぐ使用して[COM コンポーネントの登録を必要としないアクティベーション](https://msdn.microsoft.com/library/ms973913.aspx)します。
* その結果、ほとんど TLB/OLB % %programfiles (x86) %\Common files \microsoft Shared\MSEnv の DLL ファイルが Visual Studio によって既定でインストールされなく/。 Visual Studio のホスト プロセスによって使用される Registration-free COM マニフェストの対応するには、[INSTALLDIR] の下でこれらのファイルはインストールされました。
* その結果、Visual Studio COM インターフェイスの COM 登録をグローバルに依存する外部のコードは不要になったこれらの登録を検索します。 Visual Studio プロセス内で実行されているコードでは、違いが見られない。

### <a name="visual-studio-registry"></a>Visual Studio レジストリ

* Visual Studio が、システムに多くのレジストリ キーをインストールする以前は、 **HKEY_LOCAL_MACHINE**と**HKEY_CURRENT_USER**ハイブ Visual Studio に固有のキーの下。

  * **Hklm \software\microsoft\visualstudio\{バージョン}** :MSI インストーラーとコンピューター単位の拡張機能によって作成されたレジストリ キー。
  * **Hkcu \software\microsoft\visualstudio\{バージョン}** :ユーザーに固有の設定を格納する Visual Studio によって作成されたレジストリ キーです。
  * **Hkcu \software\microsoft\visualstudio\{バージョン} _Config**:上の Visual Studio HKLM キーとレジストリ キーのコピーにマージされた *.pkgdef*拡張機能によってファイル。

* レジストリへの影響を減らすためには、Visual Studio を今すぐ使用して、 [RegLoadAppKey](/windows/desktop/api/winreg/nf-winreg-regloadappkeya)プライベート バイナリ ファイルの下にレジストリ キーを格納する関数 *[VSAPPDATA]\privateregistry.bin*します。 Visual Studio 固有のキーの数が非常に小さいだけは、システム レジストリに残ります。
* Visual Studio プロセス内で実行されている既存のコードは影響はありません。 Visual Studio は、HKCU Visual Studio に固有のキーの下のすべてのレジストリ操作をプライベート レジストリにリダイレクトされます。 その他のレジストリの場所に対する読み取りと書き込みは、システム レジストリを使用して続けます。
* 外部コードを読み込むし、Visual Studio のレジストリ エントリには、このファイルから読み取る必要があります。

### <a name="react-to-this-breaking-change"></a>この重大な変更に対応します。

* 同様に COM コンポーネントの登録なしのアクティベーションを使用する外部コードを変換する必要があります。
* 外部コンポーネントは、Visual Studio の場所を見つけることができます[こちらのガイダンスに従って](https://devblogs.microsoft.com/setup/changes-to-visual-studio-15-setup)します。
* 外部コンポーネントが使用することをお勧め、[外部設定マネージャー](/dotnet/api/microsoft.visualstudio.settings.externalsettingsmanager) Visual Studio のレジストリ キーに直接読み取り/書き込みの代わりにします。
* 登録のための別の手法は、拡張機能を使用して、コンポーネントに実装がかどうかを確認します。 たとえば、デバッガーの拡張機能が新しい利用することが可能性があります[msvsmon JSON ファイルの COM 登録](migrate-debugger-COM-registration.md)します。
