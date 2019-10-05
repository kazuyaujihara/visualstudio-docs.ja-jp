---
title: または VB C#プロジェクトのリモートデバッグ |Microsoft Docs
ms.custom:
- remotedebugging"=
- seodec18
ms.date: 08/14/2018
ms.topic: conceptual
dev_langs:
- C++
- FSharp
- CSharp
- JScript
- VB
helpviewer_keywords:
- remote debugging, setup
ms.assetid: a9753fbb-e7f4-47f0-9dbe-9de90c6c8457
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 3490cab7c902dcdf1a7d0095eb69dd44de47a727
ms.sourcegitcommit: ea182703e922c74725045afc251bcebac305068a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71211120"
---
# <a name="remote-debugging-a-c-or-visual-basic-project-in-visual-studio"></a>Visual Studio でC#のまたは Visual Basic プロジェクトのリモートデバッグ
別のコンピューターに配置されている Visual Studio アプリケーションをデバッグするには、アプリを配置したコンピューターにリモートツールをインストールして実行し、Visual Studio からリモートコンピューターに接続するようにプロジェクトを構成してから、アプリを実行します。

![リモートデバッガーコンポーネント](../debugger/media/remote-debugger-client-apps.png "Remote_debugger_components")

ユニバーサル Windows アプリ (UWP) のリモートデバッグの詳細については、「[インストールされているアプリパッケージのデバッグ](debug-installed-app-package.md)」を参照してください。

## <a name="requirements"></a>要件

リモートデバッガーは、windows 7 以降 (phone 以外) および windows server 2008 Service Pack 2 以降のバージョンでサポートされています。 要件の完全な一覧については、「[要件](../debugger/remote-debugging.md#requirements_msvsmon)」を参照してください。

> [!NOTE]
> プロキシ経由で接続されている2台のコンピューター間のデバッグはサポートされていません。 高待機時間接続または低帯域幅接続 (ダイヤルアップインターネットなど) またはインターネット経由でのデバッグは推奨されません。また、障害が発生する可能性があります。

## <a name="download-and-install-the-remote-tools"></a>リモート ツールのダウンロードおよびインストール

[!INCLUDE [remote-debugger-download](../debugger/includes/remote-debugger-download.md)]

> [!TIP]
> 場合によっては、ファイル共有からリモートデバッガーを実行する方が効率的な場合があります。 詳細については、「[ファイル共有からのリモートデバッガーの実行](../debugger/remote-debugging.md#fileshare_msvsmon)」を参照してください。

## <a name="BKMK_setup"></a> リモート デバッガーのセットアップ

[!INCLUDE [remote-debugger-configuration](../debugger/includes/remote-debugger-configuration.md)]

> [!NOTE]
> 追加のユーザーにアクセス許可を追加する必要がある場合、リモートデバッガーの認証モードまたはポート番号を変更するには、「[リモートデバッガーの構成](../debugger/remote-debugging.md#configure_msvsmon)」を参照してください。

## <a name="remote_csharp"></a>プロジェクトのリモートデバッグ
デバッガーでは、Visual C# または Visual Basic のデスクトップ アプリケーションをリモート コンピューターに配置できませんが、次のようにリモートからそれらのデスクトップ アプリケーションをデバッグすることはできます。 次の手順では、次の図に示すように、 **Mjo-DL**という名前のコンピューターでデバッグを行うことを前提としています。

1. **MyWpf** という名前の WPF プロジェクトを作成します。

2. ブレークポイントをコード内の達しやすい任意の箇所に設定します。

    たとえば、ブレークポイントをボタン ハンドラーに設定できます。 これを行うには、Mainwindow.xaml を開き、[ツールボックス] から Button コントロールを追加します。次に、ボタンをダブルクリックして、そのハンドラーを開きます。

3. ソリューション エクスプローラーでプロジェクトを右クリックし、 **[プロパティ]** を選択します。

4. **[プロパティ]** ページで、 **[デバッグ]** タブをクリックします。

    ![Remoteデバッガ csharp](../debugger/media/remotedebuggercsharp.png "Remoteデバッガ csharp")

5. **[作業ディレクトリ]** テキスト ボックスが空であることを確認してください。

6. **[リモートコンピューターを使用する]** を選択し、テキストボックスに「 **machinename: port** 」と入力します。 (ポート番号は [リモートデバッガー] ウィンドウに表示されます。 ポート番号は、Visual Studio の各バージョンで2ずつ増加します)。

    この例では、次のコードを使用します。
    ::: moniker range=">=vs-2019"
    **4024:** Visual Studio 2019 での
    ::: moniker-end
    ::: moniker range="vs-2017"
    **4022:** Visual Studio 2017 での
    ::: moniker-end

7. **[ネイティブ コードのデバッグを有効にする]** がオフであることを確認します。

8. プロジェクトをビルドします。

9. Visual Studio コンピューター上の **Debug** フォルダー ( **\<ソース パス>\MyWPF\MyWPF\bin\Debug**) と同じパスのフォルダーをリモート コンピューター上に作成します。

10. 上で作成した実行可能ファイルを、Visual Studio コンピューターから、リモート コンピューター上の新しく作成したフォルダーにコピーします。

    > [!CAUTION]
    > コードに変更を加えたりリビルドしたりしないでください (または、この手順を繰り返す必要があります)。 リモート コンピューターにコピーした実行可能ファイルは、ローカルのソースとシンボルに正確に一致している必要があります。

    プロジェクトは手動でコピーすることも、Xcopy、Robocopy、Powershell などのオプションを使用することもできます。

11. ターゲットコンピューターでリモートデバッガーが実行されていることを確認します (そうでない場合は、 **[スタート]** メニューで**リモートデバッガー**を検索します)。 リモートデバッガーウィンドウは次のようになります。

     ![Remoteデバッガウィンドウ](../debugger/media/remotedebuggerwindow.png "Remoteデバッガウィンドウ")

12. Visual Studio でデバッグを開始します ( **[デバッグ] > [デバッグの開始]** 、または **F5** キー)。

13. メッセージが表示されたら、リモートコンピューターに接続するためのネットワーク資格情報を入力します。

     必要な資格情報は、ネットワークのセキュリティ構成によって異なります。 たとえば、ドメインコンピューターでは、ドメイン名とパスワードを入力できます。 ドメイン以外のコンピューターでは、コンピューター名と有効なユーザーアカウント名<strong>MJO-DL\name@something.com</strong>(など) を正しいパスワードと共に入力できます。

     WPF アプリケーションのメイン ウィンドウがリモート コンピューター上で開いていることを確認できるはずです。

14. 必要に応じて、ブレークポイントにヒットするアクションを実行します。 ブレークポイントがアクティブになっていることを確認できるはずです。 ブレークポイントがアクティブでない場合、アプリケーションのシンボルが読み込まれていません。 もう一度お試しください。それでもうまくいかない場合は、シンボルの読み込みと、シンボル[ファイルと Visual Studio のシンボル設定](https://devblogs.microsoft.com/devops/understanding-symbol-files-and-visual-studios-symbol-settings/)についてのトラブルシューティングに関する情報を参照してください。

15. Visual Studio コンピューターで、実行がブレークポイントで停止したことを確認できるはずです。

    アプリケーションで使用する必要がある非コードファイルがある場合は、それらを Visual Studio プロジェクトに含める必要があります。 追加のファイル用のプロジェクト フォルダーを作成します (**ソリューション エクスプローラー**で、 **[追加] > [新しいフォルダー]** をクリックします)。 次にファイルをそのフォルダーに追加します (**ソリューション エクスプローラー**で、 **[追加] > [既存の項目]** の順にクリックしてからファイルを選択します)。 ファイルごとの **[プロパティ]** ページで、 **[出力ディレクトリにコピー]** を **[常にコピーする]** に設定します。

## <a name="set-up-debugging-with-remote-symbols"></a>リモート シンボルを使用したデバッグのセットアップ

[!INCLUDE [remote-debugger-symbols](../debugger/includes/remote-debugger-symbols.md)]

## <a name="see-also"></a>関連項目
- [Visual Studio でのデバッグ](../debugger/index.yml)
- [デバッガーでのはじめに](../debugger/debugger-feature-tour.md)
- [Windows ファイアウォールをリモート デバッグ用に構成する](../debugger/configure-the-windows-firewall-for-remote-debugging.md)
- [リモート デバッガーのポートの割り当て](../debugger/remote-debugger-port-assignments.md)
- [リモートの IIS コンピューター上の ASP.NET のリモート デバッグ](../debugger/remote-debugging-aspnet-on-a-remote-iis-computer.md)
- [リモート デバッグ エラーとトラブルシューティング](../debugger/remote-debugging-errors-and-troubleshooting.md)