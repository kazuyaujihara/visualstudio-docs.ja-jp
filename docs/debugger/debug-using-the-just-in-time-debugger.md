---
title: Just-in-time デバッガーを使用してデバッグする |Microsoft Docs
ms.date: 09/24/2018
ms.topic: conceptual
helpviewer_keywords:
- debugging [Visual Studio], Just-In-Time
- Just-In-Time debugging
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b842fa4ce7c75e061a58d980cefe5648094c2ef7
ms.sourcegitcommit: 40bd5b27f247a07c2e2514acb293b23d6ce03c29
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2019
ms.locfileid: "73188672"
---
# <a name="debug-using-the-just-in-time-debugger-in-visual-studio"></a>Visual Studio で Just-in-time デバッガーを使用してデバッグする

Just-in-time デバッグは、Visual Studio のエラーまたはクラッシュの外部で実行されているアプリを自動的に起動できます。 Just-in-time デバッグを使用すると、Visual Studio の外部でアプリをテストし、Visual Studio を開いて問題が発生したときにデバッグを開始できます。

Just-in-time デバッグは、Windows デスクトップアプリに対して機能します。 これは、ユニバーサル Windows アプリ、またはビジュアライザーなどのネイティブアプリケーションでホストされているマネージコードでは機能しません。

> [!TIP]
> [Just-in-time デバッガー] ダイアログボックスが表示されないようにするだけで、Visual Studio がインストールされていない場合は、「 [Just-in-time デバッガーを無効](../debugger/just-in-time-debugging-in-visual-studio.md)にする」を参照してください。 Visual Studio をインストールしたことがある場合は、 [Windows レジストリから just-in-time デバッグを無効](#disable-just-in-time-debugging-from-the-windows-registry)にすることが必要になる場合があります。

## <a name="BKMK_Enabling"></a>Visual Studio での Just-in-time デバッグを有効または無効にする

>[!NOTE]
>Just-in-time デバッグを有効または無効にするには、Visual Studio を管理者として実行している必要があります。 Just-in-time デバッグを有効または無効にすると、レジストリキーが設定され、そのキーを変更するために管理者特権が必要になる場合があります。 管理者として Visual Studio を開くには、Visual Studio アプリを右クリックし、 **[管理者として実行]** を選択します。

Just-in-time デバッグは、Visual Studio の [**ツール** > **オプション**] (または [**デバッグ** > **オプション**]) ダイアログボックスから構成できます。

**Just-In-Time デバッグの有効/無効を切り替えるには:**

1. **[ツール]** メニューまたは **[デバッグ]** メニューで、 **[オプション]** を選択して > **just-in-time** > **デバッグ**します。

   ![JIT デバッグを有効または無効にする](../debugger/media/dbg-jit-enable-or-disable.png "JIT デバッグを有効または無効にする")

1. **[次の種類のコードの just-in-time デバッグを有効]** にする ボックスで、 **[マネージ]** 、 **[ネイティブ]** 、または **[スクリプト]** のいずれかまたは両方のデバッグ対象の just-in-time デバッグを実行するコードの種類を選択します。

1. **[OK]** を選択します。

Just-in-time デバッガーを有効にしても、アプリがクラッシュしたときやエラーが発生しても開かない場合は、「 [just-in-time デバッグのトラブルシューティング](#jit_errors)」を参照してください。

## <a name="disable-just-in-time-debugging-from-the-windows-registry"></a>Windows レジストリから Just-in-time デバッグを無効にする

Visual Studio がコンピューターからアンインストールされた後でも、Just-In-Time デバッグが有効になっている場合があります。 Visual Studio がインストールされていない場合は、Windows レジストリを編集して Just-in-time デバッグを無効にすることができます。

**レジストリを編集して Just-In-Time デバッグを無効にするには:**

1. Windows の **[スタート]** メニューから、**レジストリエディター** (*regedit.exe*) を実行します。

2. **レジストリエディター**ウィンドウで、次のレジストリエントリを見つけて削除します。

    - **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\。Netframework\ dbgmanageddebugger**

    - **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\AeDebug\Debugger**

    ![JIT レジストリキー](../debugger/media/dbg-jit-registry.png "JIT レジストリキー")

3. コンピューターで64ビットのオペレーティングシステムが実行されている場合は、次のレジストリエントリも削除します。

    - **HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\\.NETFramework\DbgManagedDebugger**

    - **HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows NT\CurrentVersion\AeDebug\Debugger**

    他のレジストリキーを削除または変更しないようにしてください。

5. **レジストリエディター**ウィンドウを閉じます。

## <a name="enable-just-in-time-debugging-of-a-windows-form"></a>Windows フォームの Just-in-time デバッグを有効にする

既定では、Windows フォームアプリには最上位レベルの例外ハンドラーが用意されており、これを使用すると、回復可能な場合でもアプリを実行し続けることができます。 Windows フォームアプリがハンドルされない例外をスローすると、次のダイアログが表示されます。

![Windows フォームのハンドルされない例外](../debugger/media/windowsformsunhandledexception.png "Windows フォームのハンドルされない例外")

標準の Windows フォームエラー処理ではなく Just-in-time デバッグを有効にするには、次の設定を追加します。

- *Machine.config または* *\<アプリ名 > .exe*ファイルの `system.windows.forms` セクションで、`jitDebugging` の値を `true`に設定します。

    ```xml
    <configuration>
        <system.windows.forms jitDebugging="true" />
    </configuration>
    ```

- C++ Windows フォームアプリケーションでは、 *.config*ファイルまたはコード内で`true`するように`DebuggableAttribute`も設定します。 [/Zi](/cpp/build/reference/z7-zi-zi-debug-information-format) を使用し、[/Og](/cpp/build/reference/og-global-optimizations) は使用しないでコンパイルすると、コンパイラによってこの属性が設定されます。 ただし、最適化されていないリリースビルドをデバッグする場合は、アプリの*AssemblyInfo*ファイルに次の行を追加して、`DebuggableAttribute` を設定する必要があります。

   ```cpp
   [assembly:System::Diagnostics::DebuggableAttribute(true, true)];
   ```

   詳細については、「<xref:System.Diagnostics.DebuggableAttribute>」を参照してください。

## <a name="BKMK_Using_JIT"></a>Just-in-time デバッグを使用する
この例では、アプリがエラーをスローした場合の Just-in-time デバッグについて説明します。

- これらの手順を実行するには、Visual Studio がインストールされている必要があります。 Visual Studio をお持ちでない場合は、無料の[Visual Studio Community エディション](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=Community&rel=15)をダウンロードできます。

- Just-in-time**デバッグ >  > ** の [**ツール** > **オプション]** で [just-in-time デバッグ] が[有効になっ](#BKMK_Enabling)ていることを確認**します。**

この例では、 [NullReferenceException](/dotnet/api/system.nullreferenceexception)をスロー C#するコンソールアプリを Visual Studio で作成します。

1. Visual Studio で、 *ThrowsNullException*とC#いう名前のコンソールアプリ (**新しい** > **プロジェクト** > **Visual C#**  > **コンソールアプリケーション** > **ファイル**) を作成します。 Visual Studio でのプロジェクトの作成の詳細については、「[チュートリアル: 簡単なアプリケーションの作成](../get-started/csharp/tutorial-wpf.md)」を参照してください。

1. Visual Studio でプロジェクトを開くときに、 *Program.cs*ファイルを開きます。 Main () メソッドを次のコードに置き換えます。このコードは、コンソールに線を出力し、NullReferenceException をスローします。

   ```csharp
   static void Main(string[] args)
   {
       Console.WriteLine("we will now throw a NullReferenceException");
       throw new NullReferenceException("this is the exception thrown by the console app");
   }
   ```

1. ソリューションをビルドするには、 **[デバッグ]** (既定値) または **[リリース]** 構成 を選択し、[**ビルド** > **リビルド**] を選択します。

   > [!NOTE]
   > - 完全なデバッグエクスペリエンスを実現するには、[**デバッグ**構成] を選択します。
   > - [[リリース](../debugger/how-to-set-debug-and-release-configurations.md)構成] を選択した場合は、この手順が動作するように[マイコードのみ](../debugger/just-my-code.md)を無効にする必要があります。 [**ツール** > **オプション**] >  **[デバッグ]** の **[マイコードのみを有効にする]** をオフにします。

   ビルド構成の詳細については、「[ビルド構成について](../ide/understanding-build-configurations.md)」を参照してください。

1. ビルドしたアプリ*ThrowsNullException*をC#プロジェクトフォルダー ( *. ..\ThrowsNullException\ThrowsNullException\bin\Debug*または *..\ThrowsNullException\ThrowsNullException\bin\Release*) で開きます。

   次のコマンドウィンドウが表示されます。

   ![ThrowsNullExceptionConsole](../debugger/media/throwsnullexceptionconsole.png "ThrowsNullExceptionConsole")

1. **[Just-in-time デバッガーの選択]** ダイアログボックスが開きます。

   ![ジャストインタイムダイアログ](../debugger/media/justintimedialog.png "ジャストインタイムダイアログ")

   **[使用可能なデバッガー]** の下で、 **Visual Studio バージョン/エディション >** を選択していない場合は \<[の新しいインスタンス] を選択します。

1. **[OK]** を選択します。

   ThrowsNullException プロジェクトが Visual Studio の新しいインスタンスで開き、例外をスローした行で実行が停止します。

   ![Nulldinstance](../debugger/media/nullreferencesecondinstance.png "Nulldinstance")

この時点でデバッグを開始できます。 実際のアプリをデバッグしている場合は、コードが例外をスローしている理由を確認する必要があります。

> [!CAUTION]
> アプリに信頼できないコードが含まれている場合は、[セキュリティの警告] ダイアログボックスが表示され、デバッグを続行するかどうかを決定できます。 デバッグを続行する前に、コードを信頼するかどうかを決定します。 このコードは、自分で作成したコードですか。 アプリケーションをリモート コンピューター上で実行している場合、プロセスの名前を識別できますか。 アプリがローカルで実行されている場合は、コンピューターで悪意のあるコードが実行されている可能性を考慮してください。 コードが信頼できると判断した場合は、[ **OK]** を選択します。 それ以外の場合、 **[キャンセル]** を選択します。

## <a name="jit_errors"></a>Just-in-time デバッグのトラブルシューティング

アプリがクラッシュしたときに Just-in-time デバッグが開始されない場合は、Visual Studio で有効になっていても、次のようになります。

- コンピューターのエラー処理を Windows エラー報告可能性があります。

  この問題を解決するには、レジストリエディターを使用して、次のレジストリキーに**無効**な**DWORD 値**(**値データ** **1**) を追加します。

  - **HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\Windows エラー報告**

  - (64 ビットコンピューターの場合): **HKEY_LOCAL_MACHINE\Software\WOW6432Node\Microsoft\Windows\Windows エラー報告**

  詳細については、「」を参照してください[。WER の設定](/windows/desktop/wer/wer-settings)。

- 既知の Windows の問題により、Just-in-time デバッガーが失敗する可能性があります。

  この問題を解決するには、次のレジストリキーに**値 data** **1**を指定して**Auto**の**DWORD 値**を追加します。

  - **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\AeDebug**

  - (64 ビットコンピューターの場合): **HKEY_LOCAL_MACHINE\Software\WOW6432Node\Microsoft\Windows NT\CurrentVersion\AeDebug**

ジャストインタイムデバッグ中に、次のエラーメッセージが表示されることがあります。

- **クラッシュしたプロセスにアタッチできません。指定されたプログラムは、Windows または MS-DOS のプログラムではありません。**

    デバッガーは、別のユーザーで実行されているプロセスにアタッチしようとしました。

    この問題を回避するには、Visual Studio で **[デバッグ]** を開き >  **[プロセスにアタッチ]** をクリックし、 **[選択可能なプロセス]** ボックスの一覧でデバッグするプロセスを見つけます。 プロセスの名前がわからない場合は、 **Visual Studio の Just-in-time デバッガー**ダイアログでプロセス ID を見つけます。 選択 **[可能なプロセス]** ボックスの一覧でプロセスを選択し、 **[アタッチ]** を選択します。 **[いいえ]** を選択すると、just-in-time デバッガーダイアログボックスが閉じます。

- **ログオンしているユーザーがいないため、デバッガーを開始できませんでした。**

    コンソールにログオンしているユーザーは存在しないため、Just-in-time デバッグダイアログを表示するためのユーザーセッションはありません。

    この問題を解決するには、コンピューターにログオンします。

- **クラスは登録されていません。**

    デバッガーは、登録されていない COM クラスを作成しようとしました。インストールの問題が原因である可能性があります。

    この問題を解決するには、Visual Studio インストーラーを使用して、Visual Studio のインストールを再インストールまたは修復します。

## <a name="see-also"></a>関連項目

- [デバッガーのセキュリティ](../debugger/debugger-security.md)
- [デバッガーでのはじめに](../debugger/debugger-feature-tour.md)
- [[オプション]、[デバッグ]、[Just-in-time] ダイアログボックス](../debugger/just-in-time-debugging-options-dialog-box.md)
- [セキュリティ警告信頼されていないユーザーによって所有されているプロセスにアタッチすると、危険なことができます。以下の情報に関して疑わしい点がある場合や、不明な場合は、このプロセスにアタッチしないでください。](../debugger/security-warning-attaching-to-a-process-owned-by-an-untrusted-user.md)
