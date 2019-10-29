---
title: Android および iOS での OpenGL ES アプリケーションのビルド | Microsoft Docs
ms.custom: ''
ms.date: 10/09/2019
ms.technology: vs-ide-mobile
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 76a67886-df57-4a81-accb-2e3c2eaf607b
author: corob-msft
ms.author: corob
manager: jillfra
ms.workload:
- xplat-cplusplus
ms.openlocfilehash: a15902278e9a73488b315729a2db6e8fb5d53935
ms.sourcegitcommit: 8a96a65676fd7a2a03b0803d7eceae65f3fa142b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72588916"
---
# <a name="build-an-opengl-es-application-on-android-and-ios"></a>Android および iOS での OpenGL ES アプリケーションのビルド

共通コードを共有する iOS アプリ用および Android アプリ用の Visual Studio ソリューションおよびプロジェクトを作成できます。 この記事では、単純な iOS アプリと Android Native Activity アプリの両方を作成するソリューション テンプレートについて説明します。 これらのアプリには、OpenGL ES を使用して各プラットフォームで同じアニメーション回転キューブを表示する共通の C++ コードがあります。 OpenGL ES (OpenGL for Embedded Systems または GLES) は、多くのモバイル デバイスでサポートされている 2D および 3D グラフィックス API です。

## <a name="requirements"></a>必要条件

iOS 用および Android 用 OpenGL ES アプリを作成するには、その前にすべてのシステム要件を満たしていることを確認してください。 C++ によるモバイル開発ワークロードをまたインストールしていない場合は、Visual Studio インストーラーにインストールします。 OpenGL ES テンプレートを取得し、iOS 用にビルドするには、オプションの C++ iOS 開発ツールを含めます。 Android 用にビルドするには、C++ Android 開発ツールと、必要な以下のサードパーティ ツールをインストールします。Android NDK、Apache Ant、Google Android Emulator。 Intel プラットフォームでエミュレーターのパフォーマンスを向上させるには、Intel Hardware Accelerated Execution Manager (HAXM) もインストールすることをお勧めします。 次に、システムでの実行に向けて Intel HAXM と Android Emulator を構成します。 詳細情報と詳細な手順については、「[C++ によるクロスプラットフォーム モバイル開発をインストールする](../cross-platform/install-visual-cpp-for-cross-platform-mobile-development.md)」をご覧ください。

iOS アプリをビルドしてテストするには、インストール手順に従って設定されている Mac コンピューターが必要になります。 iOS 開発の設定方法について詳しくは、[iOS を使用してビルドするためのツールのインストールと構成](../cross-platform/install-and-configure-tools-to-build-using-ios.md)に関するページをご覧ください。

## <a name="create-a-new-opengles-application-project"></a>新しい OpenGLES アプリケーション プロジェクトの作成

このチュートリアルでは、まず新しい OpenGL ES アプリケーション プロジェクトを作成します。 その後、Android Emulator で既定のアプリをビルドして実行します。 次に、iOS 用アプリをビルドし、iOS デバイスでアプリを実行します。

::: moniker range="vs-2017"

1. Visual Studio で、 **[ファイル]** > **[新規作成]** > **[プロジェクト]** の順に選択します。

1. **[新しいプロジェクト]** ダイアログ ボックスの **[テンプレート]** で **[Visual C++]** > **[クロス プラットフォーム]** の順に選択し、 **[OpenGLES アプリケーション (Android, iOS)]** テンプレートを選択します。

1. アプリに *MyOpenGLESApp* などの名前を付け、 **[OK]** を選択します。

   ![新しい OpenGLES アプリケーション プロジェクト](../cross-platform/media/cppmdd_opengles_newproj.PNG "CPPMDD_OpenGLES_NewProj")

   Visual Studio は新しいソリューションを作成し、ソリューション エクスプローラーを開きます。

   ![ソリューション エクスプローラーの MyOpenGLESApp](../cross-platform/media/cppmdd_opengles_solexpl.PNG "CPPMDD_OpenGLES_SolExpl")

::: moniker-end

::: moniker range=">=vs-2019"

1. Visual Studio で、 **[ファイル]** > **[新規作成]** > **[プロジェクト]** の順に選択します。

1. **[新しいプロジェクトの作成]** ダイアログ ボックスで、 **[OpenGLES アプリケーション (Android, iOS)]** テンプレートを選択し、 **[次へ]** を選択します。

1. **[新しいプロジェクトの構成]** ダイアログ ボックスで、**プロジェクト名**に *MyOpenGLESApp* のような名前を入力し、 **[作成]** を選択します。

   Visual Studio は新しいソリューションを作成し、ソリューション エクスプローラーを開きます。

   ![ソリューション エクスプローラーの MyOpenGLESApp](../cross-platform/media/cppmdd_opengles_solexpl.PNG "CPPMDD_OpenGLES_SolExpl")

::: moniker-end

新しい OpenGL ES アプリケーション ソリューションには、次の 3 つのライブラリ プロジェクトと 2 つのアプリケーション プロジェクトが含まれています。 ライブラリ フォルダーには、共有コード プロジェクトと共有コードを参照する 2 つのプラットフォーム固有のプロジェクトが含まれています。

- `MyOpenGLESApp.Android.NativeActivity` には、Android 上の Native Activity としてアプリを実装する参照とグルー コードが含まれています。 グルー コードからのエントリ ポイントは、*main.cpp* に実装され、これには `MyOpenGLESApp.Shared` に共通の共有コードが含まれています。 プリコンパイル済みヘッダーは *pch.h* にあります。 この Native Activity アプリ プロジェクトは、共有ライブラリ ( *.so*) ファイルにコンパイルされ、`MyOpenGLESApp.Android.Packaging` プロジェクトで使用されます。

- `MyOpenGLESApp.iOS.StaticLibrary` は、`MyOpenGLESApp.Shared` に共有コードが含まれている iOS スタティック ライブラリ ( *.a*) ファイルを作成します。 それは `MyOpenGLESApp.iOS.Application` プロジェクトで作成されたアプリにリンクされます。

- `MyOpenGLESApp.Shared` には、プラットフォーム間で機能する共有コードが含まれています。 プラットフォーム固有のコードの条件付きコンパイルにプリプロセッサ マクロを使用します。 共有コードは、`MyOpenGLESApp.Android.NativeActivity` と `MyOpenGLESApp.iOS.StaticLibrary` の両方のプロジェクト参照によって使用されます。

ソリューションには、Android および iOS プラットフォーム用のアプリを構築するための 2 つのプロジェクトがあります。

- `MyOpenGLESApp.Android.Packaging` は、Android デバイスまたはエミュレーターに配置する *.apk* ファイルを作成します。 このファイルには、リソースと、マニフェスト プロパティを設定した AndroidManifest.xml ファイルが含まれています。 Ant のビルド プロセスを制御する *build.xml* ファイルも含まれています。 それは既定でスタートアップ プロジェクトとして設定されているため、Visual Studio から直接、配置して実行できます。

- `MyOpenGLESApp.iOS.Application` には、`MyOpenGLESApp.iOS.StaticLibrary` で C++ スタティック ライブラリ コードにリンクする iOS アプリを作成するためのリソースと Objective-C グルー コードが含まれています。 このプロジェクトは、Visual Studio およびリモート エージェントによってご使用の Mac に転送されるビルド パッケージを作成します。 このプロジェクトをビルドする場合、Visual Studio はファイルとコマンドを送信して、アプリを Mac でビルドおよび配置します。

## <a name="build-and-run-the-android-app"></a>Android アプリのビルドと実行

テンプレートで作成したソリューションは、既定のプロジェクトとして、Android アプリを設定します。  インストールとセットアップを確認するために、このアプリをビルドおよび実行できます。 初期テストでは、Android 用エミュレーターによってインストールされているデバイス プロファイルのいずれかでアプリを実行します。 別の対象でアプリをテストする場合は、対象のエミュレーターを読み込むか、デバイスをコンピューターに接続してください。

### <a name="to-build-and-run-the-android-native-activity-app"></a>Android Native Activity アプリをビルドして実行するには

1. まだ選択されていない場合は、 **[ソリューション プラットフォーム]** ドロップダウン リストから **[x86]** を選択します。

   ![ソリューション プラットフォームを x86 に設定する](../cross-platform/media/cppmdd_opengles_solutionplat.png "CPPMDD_OpenGLES_SolutionPlat")

   x86 を使用してエミュレーターを対象とします。 デバイスを対象とするには、デバイス プロセッサに基づいてソリューション プラットフォームを選択します。 **[ソリューション プラットフォーム]** リストが表示されない場合は、 **[ボタンの追加と削除]** リストから **[ソリューション プラットフォーム]** を選択してから、使用するプラットフォームを選択します。

1. **ソリューション エクスプローラー**で `MyOpenGLESApp.Android.Packaging` プロジェクトのショートカット メニューを開き、 **[ビルド]** を選択します。

   ![Android パッケージ化プロジェクトのビルド](../cross-platform/media/cppmdd_opengles_andbuild.png "CPPMDD_OpenGLES_AndBuild")

   Android 共有ライブラリと Android アプリ用のビルド プロセスの出力が [出力] ウィンドウに表示されます。

   ![Android プロジェクト用の出力のビルド](../cross-platform/media/cppmdd_opengles_andoutput.png "CPPMDD_OpenGLES_AndOutput")

1. 配置ターゲットとして、いずれかのエミュレートされた Android デバイス プロファイルを選択します。

   ![配置ターゲットの選択](../cross-platform/media/cppmdd_opengles_pickemulator.png "CPPMDD_OpenGLES_PickEmulator")

   別のエミュレーターをインストールしてあるか、Android デバイスを接続してある場合は、配置対象のドロップダウン リストからそれらを選択できます。 アプリを実行するには、ビルドしたソリューション プラットフォームが、ターゲット デバイスのプラットフォームと一致している必要があります。

1. **F5** キーを押してデバッグを開始するか、**Shift** + **F5** キーを押してデバッグなしで開始します。

   Visual Studio によってエミュレーターが起動されます。コードを読み込んで配置するのに数秒かかります。 エミュレーターでアプリがどのように表示されるかを次に示します。

   ![Android Emulator で実行されているアプリ](../cross-platform/media/cppmdd_opengles_andemulator.png "CPPMDD_OpenGLES_AndEmulator")

   アプリが開始されると、ブレークポイントの設定や、デバッガーを使用したステップ実行、ローカルの確認、値のウォッチができるようになります。

1. **Shift** + **F5** キーを押してデバッグを停止します。

   エミュレーターは実行され続ける独立したプロセスです。 同じエミュレーターに対して、コードを何度も編集、コンパイル、配置できます。 アプリはエミュレーターのアプリ コレクションに表示され、そこから直接起動することができます。

   生成された Android Native Activity アプリとライブラリ プロジェクトは、Android プラットフォームとやり取りする "グルー" コードを含むダイナミック ライブラリに C++ 共有コードを配置します。 ほとんどのアプリ コードはライブラリに含まれ、マニフェスト、リソース、およびビルド手順は、パッケージ化するプロジェクトに含まれます。 共有コードは、NativeActivity プロジェクトの main.cpp から呼び出されます。 Android Native Activity をプログラムする方法の詳細については、Android NDK Developer の「 [Concepts](https://developer.android.com/ndk/guides/concepts.html) 」ページを参照してください。

   Visual Studio は、プラットフォーム ツールセットとして Clang を使用する Android NDK を使用して Android Native Activity プロジェクトをビルドします。 Visual Studio では、NativeActivity プロジェクトのプロパティが、ターゲット プラットフォームでコンパイル、リンク、デバッグするために使用されるオプションにマップされます。 詳細については、MyOpenGLESApp.Android.NativeActivity プロジェクトの **[プロパティ ページ]** ダイアログを参照してください。 コマンド ライン スイッチの詳細については、「[Clang Compiler User's Manual](http://clang.llvm.org/docs/UsersManual.html)」 (Clang コンパイラ ユーザーズ マニュアル) を参照してください。

## <a name="build-and-run-the-ios-app-on-an-ios-device"></a>iOS デバイスで iOS アプリをビルドして実行する

iOS アプリ プロジェクトの作成および編集は Visual Studio で行いますが、ライセンスの制限があるため、プロジェクトのビルドおよび配置は、Mac から行う必要があります。 Visual Studio は、Mac で実行するリモート エージェントと通信して、プロジェクト ファイルを転送し、ビルド、配置、デバッグのコマンドを実行します。 iOS アプリをビルドするには、その前に Mac と Visual Studio が通信できるように設定および構成します。 手順の詳細については、[iOS を使用してビルドするためのツールのインストールと構成](../cross-platform/install-and-configure-tools-to-build-using-ios.md)に関するページをご覧ください。 リモート エージェントを Mac で実行し、Visual Studio とペアリングすると、iOS アプリをビルドおよび実行して、インストールとセットアップを確認することができます。

iOS アプリを iOS デバイスに配置するには、Mac 上の Xcode への自動署名も設定する必要があります。 自動署名では、アプリの署名を自動的に管理し、プロビジョニング プロファイルを作成してアプリのビルドに署名します。

### <a name="to-set-up-automatic-signing-on-xcode"></a>Xcode の自動署名を設定するには

1. [Xcode](https://developer.apple.com/xcode/) をまだ Mac にインストールしていない場合は、インストールします。

1. Mac で Xcode アプリを開きます。

1. 新しい **Single View Application** Xcode プロジェクトを作成ます。 プロジェクトの作成中に、必須フィールドに入力します。 この値は、後でアプリのビルドに署名するために使用するプロビジョニング プロファイルの作成にのみ使用されるため、任意で指定できます。

1. [Apple Developer Program](https://developer.apple.com/programs/) アカウントに登録されている Apple ID を Xcode に追加します。 Apple ID は、アプリに署名するための署名 ID として使用されます。 Xcode で署名 ID を追加するには、 **[Xcode]** メニューを開き、 **[Preferences]\(環境設定\)** を選択します。 **[Accounts]\(アカウント\)** を選択し、[Add]\(追加\) ボタン (+) をクリックして Apple ID を追加します。 詳しい手順については、「[Add your Apple ID account](https://help.apple.com/xcode/mac/current/#/devaf282080a)」 (Apple ID アカウントを追加する) を参照してください。

1. Xcode プロジェクトの [General]\(全般\) 設定から、 **[Bundle Identifier]\(バンドル識別子\)** の値を `com.<NameOfVSProject>` に変更します。ここで、`<NameOfVSProject>` は作成した Visual Studio ソリューションのプロジェクトと同じ名前です。 たとえば、Visual Studio で `MyOpenGLESApp` という名前のプロジェクトを作成した場合、 **[Bundle Identifier]\(バンドル識別子\)** を `com.MyOpenGLESApp` に設定します。

   ![Xcode バンドル識別子](../cross-platform/media/cppmdd-opengles-iosxcodeid.png "CPPMDD_OpenGLES_iOSXcodeId")

1. 自動署名を有効にするには、 [Automatically manage signing**]\(署名の自動管理\) をオンにします。

   ![Xcode の自動署名](../cross-platform/media/cppmdd-opengles-iosxcodesign.png "CPPMDD_OpenGLES_iOSXcodeSign")

1. 開発**チーム**として追加した Apple ID のチーム名を選択します。

   ![Xcode チーム](../cross-platform/media/cppmdd-opengles-iosxcodeteam.png "CPPMDD_OpenGLES_iOSXcodeTeam")

### <a name="to-build-and-run-the-ios-app-on-an-ios-device"></a>iOS デバイスで iOS アプリをビルドして実行するには

1. Mac でリモート エージェントを実行し、Visual Studio がリモート エージェントとペアリングされていることを確認します。 リモート エージェントを開始するには、ターミナル アプリのウィンドウを開き、「 `vcremote`」を参照してください。 詳細については、「 [Visual Studio でリモート エージェントを構成する](../cross-platform/install-and-configure-tools-to-build-using-ios.md#ConfigureVS)」を参照してください。

   ![Vcremote が実行されている Mac ターミナル ウィンドウ](../cross-platform/media/cppmdd_common_vcremote.png "CPPMDD_common_vcremote")

1. iOS デバイスを Mac に接続します。 デバイスを初めてコンピューターに接続すると、アラートで、デバイスにアクセスするコンピューターを信頼するかどうかがたずねられます。 デバイスが Mac コンピューターを信頼するようにできます。

1. Visual Studio で、まだ選択されていない場合は、デバイス プロセッサに基づいて、 **[ソリューション プラットフォーム]** ドロップダウン リストから、ソリューション プラットフォームを選択します。 この例では、それは **ARM64** プロセッサになります。

   ![ソリューション プラットフォームを ARM64 に設定する](../cross-platform/media/cppmdd-opengles-pickplatformarm64.png "CPPMDD_OpenGLES_SolutionPlatARM64")

1. ソリューション エクスプローラーで、MyOpenGLESApp.iOS.Application プロジェクトのショートカット メニューを開き、 **[プロジェクトのアンロード]** を選択して、プロジェクトをアンロードします。

1. 再度、アンロードした MyOpenGLESApp.iOS.Application プロジェクトのショートカット メニューを開き、 **[Edit project.pbxproj]\(project.pbxproj の編集\)** を選択して、プロジェクト ファイルを編集します。 `project.pbxproj` ファイルで、`buildSettings` 属性を探し、Apple チーム ID を使用して、`DEVELOPMENT_TEAM` を追加します。 次のスクリーンショットに、Apple チーム ID の `123456ABC` の値の例を示します。 Xcode から Apple チーム ID の値を見つけることができます。 **[ビルド設定]** に移動し、開発チーム名にマウス ポインターを移動して、ヒントを表示します。 ヒントに、チーム ID が表示されます。

   ![開発チームを設定する](../cross-platform/media/cppmdd-opengles-iosdevelopmentteam.png "CPPMDD_OpenGLES_iOSDevelopmentTeam")

1. `project.pbxproj` ファイルを閉じてから、アンロードした MyOpenGLESApp.iOS.Application プロジェクトのショートカット メニューを開き、 **[プロジェクトの再読み込み]** を選択して、プロジェクトを再読み込みします。

1. ここで、プロジェクトのショートカット メニューを開き、 **[ビルド]** を選択して、MyOpenGLESApp.iOS.Application プロジェクトをビルドします。

   ![iOS アプリケーション プロジェクトのビルド](../cross-platform/media/cppmdd_opengles_iosbuild.png "CPPMDD_OpenGLES_iOSBuild")

   iOS スタティック ライブラリと iOS アプリ用のビルド プロセスの出力が [出力] ウィンドウに表示されます。 Mac でリモート エージェントを実行しているターミナル ウィンドウに、コマンドおよびファイル転送アクティビティが表示されます。

   Mac コンピューターで、codesign にキーチェーンへのアクセスを許可するように求められることがあります。 **[許可]** を選択して続行します。

1. ツールバーで、iOS デバイスを選択し、Mac に接続されているデバイスでアプリを実行します。 アプリが起動しない場合、デバイスによって、デプロイされたアプリケーションに、デバイス上で実行するためのアクセス許可が付与されていることを確認します。 このアクセス許可を設定するには、デバイスで **[Settings]\(設定\)**  >  **[General]\(全般\)**  >  **[Device Management]\(デバイス管理\)** に移動します。 デベロッパ APP のアカウントを選択し、アカウントを信頼して、アプリを確認します。 Visual Studio からアプリの再実行を試行します。

   ![iOS デバイス上の iOS アプリ](../cross-platform/media/cppmdd-opengles-iosdevice.png "CPPMDD_OpenGLES_iOSDevice")

   アプリが開始されたら、ブレークポイントを設定し、Visual Studio デバッガーを使用してローカルを確認したり、呼び出し履歴を確認したり、値を観察したりできます。

   ![iOS アプリのブレークポイントにあるデバッガー](../cross-platform/media/cppmdd_opengles_iosdebug.png "CPPMDD_OpenGLES_iOSDebug")

1. **Shift** + **F5** キーを押してデバッグを停止します。

   生成された iOS アプリとライブラリのプロジェクトは、共有コードのみを実装するスタティック ライブラリに C++ コードを配置します。 アプリケーション コードのほとんどは、`Application` プロジェクトに配置されます。 このテンプレート プロジェクトの共有ライブラリ コードへの呼び出しは、*GameViewController.m* ファイルで実行されます。 iOS アプリをビルドするために、Visual Studio は Xcode プラットフォーム ツールセットを使用します。これは、Mac で実行されるリモート クライアントと通信する必要があります。

   Visual Studio は、Xcode を使用してアプリをビルドするために、リモート クライアントに対してプロジェクト ファイルを転送し、コマンドを送信します。 リモート クライアントは、ビルドの状態情報を Visual Studio に返します。 アプリが正常にビルドされたら、Visual Studio を使用して、アプリを実行してデバッグするためのコマンドを送信できます。 Visual Studio のデバッガーによって、Mac に接続されている iOS デバイスで実行されているアプリが制御されます。 Visual Studio では、StaticLibrary プロジェクトのプロパティが、ターゲット iOS プラットフォームでコンパイル、リンク、およびデバッグするために使用されるオプションにマップされます。 コンパイラ コマンド ライン オプションの詳細については、MyOpenGLESApp.iOS.StaticLibrary プロジェクトの **[プロパティ ページ]** ダイアログを開いてください。

## <a name="customize-your-apps"></a>アプリのカスタマイズ

共通機能を追加または変更するために、共有 C++ コードを変更することができます。 一致するように `MyOpenGLESApp.Android.NativeActivity` および `MyOpenGLESApp.iOS.Application` プロジェクトの共有コードへの呼び出しを変更する必要があります。 プリプロセッサ マクロを使用して、共通コードにおけるプラットフォーム固有のセクションを指定することができます。 Android 用にビルドする場合は、プリプロセッサ マクロ `__ANDROID__` が事前に定義されます。 iOS 用にビルドする場合は、プリプロセッサ マクロ `__APPLE__` が事前に定義されます。

特定のプロジェクト プラットフォーム用の IntelliSense を表示するには、エディター ウィンドウの上部のナビゲーション バーにあるコンテキスト スイッチャーのドロップダウンでプロジェクトを選択します。

![エディターのプロジェクト コンテキスト スイッチャーのドロップダウン](../cross-platform/media/cppmdd_opengles_contextswitcher.png)

現在のプロジェクトで使用されているコードの IntelliSense の問題が、赤色の波線でマークされます。 他のプロジェクトでの問題については、紫色の波線でマークされます。 Visual Studio では、Java または Objective-C ファイルのコードの色付けや IntelliSense がサポートされていません。 ただし、アプリケーション名、アイコン、およびその他の実装の詳細を設定するために、ソース ファイルを変更したり、リソースを変更したりできます。
