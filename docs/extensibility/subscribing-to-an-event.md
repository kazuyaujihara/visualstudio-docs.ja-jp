---
title: イベントへのサブスクライブ |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- running document table (RDT), responding to events
- running document table (RDT), subscribing to events
ms.assetid: e94a4fea-94df-488e-8560-9538413422bc
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: bd2933ee3e0e162740f0c7eb3f3c2307e17ec46d
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72647930"
---
# <a name="subscribing-to-an-event"></a>イベントのサブスクライブ
このチュートリアルでは、実行中のドキュメントテーブル (RDT) のイベントに応答するツールウィンドウを作成する方法について説明します。 ツールウィンドウは、<xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocTableEvents> を実装するユーザーコントロールをホストします。 @No__t_0 メソッドは、インターフェイスをイベントに接続します。

## <a name="prerequisites"></a>必要条件
 Visual Studio 2015 以降では、ダウンロードセンターから Visual Studio SDK をインストールしません。 これは、Visual Studio セットアップでオプション機能として含まれています。 VS SDK は、後でインストールすることもできます。 詳細については、「 [Visual STUDIO SDK のインストール](../extensibility/installing-the-visual-studio-sdk.md)」を参照してください。

## <a name="subscribing-to-rdt-events"></a>RDT イベントのサブスクライブ

#### <a name="to-create-an-extension-with-a-tool-window"></a>ツールウィンドウで拡張機能を作成するには

1. VSIX テンプレートを使用して**Rdtexplorer**という名前のプロジェクトを作成し、 **RDTExplorerWindow**という名前のカスタムツールウィンドウ項目テンプレートを追加します。

     ツールウィンドウを使用した拡張機能の作成の詳細については、「[ツールウィンドウを使用した拡張機能の作成](../extensibility/creating-an-extension-with-a-tool-window.md)」を参照してください。

#### <a name="to-subscribe-to-rdt-events"></a>RDT イベントをサブスクライブするには

1. RDTExplorerWindowControl ファイルを開き、`button1` という名前のボタンを削除します。 @No__t_0 コントロールを追加し、既定の名前をそのまま使用します。 Grid 要素は次のようになります。

    ```xml
    <Grid>
        <StackPanel Orientation="Vertical" Margin="-10,10,10,0">
            <TextBlock Margin="10" HorizontalAlignment="Center">RDTExplorerWindow</TextBlock>
            <ListBox x:Name="listBox" Height="100" />
        </StackPanel>
    </Grid>
    ```

2. コードビューで RDTExplorerWindow.cs ファイルを開きます。 次の using ディレクティブをファイルの先頭に追加します。

    ```csharp
    using Microsoft.VisualStudio;
    using Microsoft.VisualStudio.Shell;
    using Microsoft.VisualStudio.Shell.Interop;
    ```

3. @No__t_1 クラスから派生するだけでなく、<xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocTableEvents> インターフェイスを実装するように `RDTExplorerWindow` クラスを変更します。

    ```csharp
    public class RDTExplorerWindow : ToolWindowPane, IVsRunningDocTableEvents
    {. . .}
    ```

4. <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocTableEvents>を実装します。

    - インターフェイスを実装します。 IVsRunningDocTableEvents 名にカーソルを置きます。 左余白に電球が表示されます。 電球の右側にある下矢印をクリックし、 **[インターフェイスの実装]** を選択します。

5. インターフェイスの各メソッドで、`throw new NotImplementedException();` 行を次のコードに置き換えます。

    ```csharp
    return VSConstants.S_OK;
    ```

6. RDTExplorerWindow クラスに cookie フィールドを追加します。

    ```csharp
    private uint rdtCookie;
    ```

     これは、<xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.AdviseRunningDocTableEvents%2A> メソッドによって返されるクッキーを保持します。

7. RDTExplorerWindow の Initialize () メソッドをオーバーライドして、RDT イベントに登録します。 Createtoolwindow は toolwindowpane の Initialize () メソッドでは、常に、コンストラクターではなくサービスを取得する必要があります。

    ```csharp
    protected override void Initialize()
    {
        IVsRunningDocumentTable rdt = (IVsRunningDocumentTable)
        this.GetService(typeof(SVsRunningDocumentTable));
        rdt.AdviseRunningDocTableEvents(this, out rdtCookie);
    }
    ```

     @No__t_1 インターフェイスを取得するために、<xref:Microsoft.VisualStudio.Shell.Interop.SVsRunningDocumentTable> サービスが呼び出されます。 @No__t_0 メソッドは、RDT イベントを、<xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocTableEvents> (この場合は RDTExplorer オブジェクト) を実装するオブジェクトに接続します。

8. RDTExplorerWindow の Dispose () メソッドを更新します。

    ```csharp
    protected override void Dispose(bool disposing)
    {
        // Release the RDT cookie.
        IVsRunningDocumentTable rdt = (IVsRunningDocumentTable)
            Package.GetGlobalService(typeof(SVsRunningDocumentTable));
        rdt.UnadviseRunningDocTableEvents(rdtCookie);

        base.Dispose(disposing);
    }
    ```

     @No__t_0 メソッドは、`RDTExplorer` と RDT イベント通知の間の接続を削除します。

9. 次の行を <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocTableEvents.OnBeforeLastDocumentUnlock%2A> ハンドラーの本体の `return` ステートメントの直前に追加します。

    ```csharp
    public int OnBeforeLastDocumentUnlock(uint docCookie, uint dwRDTLockType, uint dwReadLocksRemaining, uint dwEditLocksRemaining)
    {
        ((RDTExplorerWindowControl)this.Content).listBox.Items.Add("Entering OnBeforeLastDocumentUnlock");
        return VSConstants.S_OK;
    }
    ```

10. @No__t_0 ハンドラーの本文と、リストボックスに表示するその他のイベントに同様の行を追加します。

    ```csharp
    public int OnAfterFirstDocumentLock(uint docCookie, uint dwRDTLockType, uint dwReadLocksRemaining, uint dwEditLocksRemaining)
    {
        ((RDTExplorerWindowControl)this.Content).listBox.Items.Add("Entering OnAfterFirstDocumentLock");
        return VSConstants.S_OK;
    }
    ```

11. プロジェクトをビルドし、デバッグを開始します。 Visual Studio の実験用インスタンスが表示されます。

12. **RDTExplorerWindow** (**ビュー/その他のウィンドウ/RDTExplorerWindow**) を開きます。

     **RDTExplorerWindow**ウィンドウが開き、空のイベント一覧が表示されます。

13. ソリューションを開くか、作成します。

     @No__t_0 と `OnAfterFirstDocument` イベントが発生すると、各イベントの通知がイベント一覧に表示されます。
