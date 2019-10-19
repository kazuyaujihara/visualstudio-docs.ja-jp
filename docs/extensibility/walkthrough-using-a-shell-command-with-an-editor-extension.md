---
title: 'チュートリアル: エディター拡張機能でシェルコマンドを使用する |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], new - add a menu command
ms.assetid: 08526848-a442-4cd4-afa1-b2eac2005adb
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 08c3acb26fe6eed1918dd1f9bb9e84b260defa5e
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72632498"
---
# <a name="walkthrough-use-a-shell-command-with-an-editor-extension"></a>チュートリアル: エディター拡張機能でシェルコマンドを使用する
VSPackage から、メニューコマンドなどの機能をエディターに追加できます。 このチュートリアルでは、メニューコマンドを呼び出して、エディターのテキストビューに表示要素を追加する方法について説明します。

 このチュートリアルでは、Managed Extensibility Framework (MEF) コンポーネントパーツと共に VSPackage を使用する方法について説明します。 VSPackage を使用して、メニューコマンドを Visual Studio シェルに登録する必要があります。 また、コマンドを使用して、MEF コンポーネントの部分にアクセスすることもできます。

## <a name="prerequisites"></a>必要条件
 Visual Studio 2015 以降では、ダウンロードセンターから Visual Studio SDK をインストールしません。 これは、Visual Studio セットアップでオプション機能として含まれています。 VS SDK は、後でインストールすることもできます。 詳細については、「 [Visual STUDIO SDK のインストール](../extensibility/installing-the-visual-studio-sdk.md)」を参照してください。

## <a name="create-an-extension-with-a-menu-command"></a>メニューコマンドを使用して拡張機能を作成する
 **[ツール]** メニューに **[装飾要素の追加]** という名前のメニューコマンドを配置する VSPackage を作成します。

1. @No__t_1 とC#いう名前の VSIX プロジェクトを作成し、カスタムコマンド項目テンプレート名**addadornment**を追加します。 詳細については、「[メニューコマンドを使用して拡張機能を作成](../extensibility/creating-an-extension-with-a-menu-command.md)する」を参照してください。

2. MenuCommandTest という名前のソリューションが開きます。 MenuCommandTestPackage ファイルには、メニューコマンドを作成し、 **[ツール]** メニューに配置するコードが含まれています。 この時点で、コマンドによってメッセージボックスが表示されます。 後の手順では、これを変更してコメントの表示要素を表示する方法を示します。

3. VSIX マニフェストエディターで*source.extension.vsixmanifest*ファイルを開きます。 [@No__t_0] タブには、MenuCommandTest という名前の VsPackage の行が必要です。

4. *Source.extension.vsixmanifest*ファイルを保存して閉じます。

## <a name="add-a-mef-extension-to-the-command-extension"></a>コマンド拡張機能に MEF 拡張機能を追加する

1. **ソリューションエクスプローラー**で、ソリューションノードを右クリックし、 **[追加]** をクリックして、 **[新しいプロジェクト]** をクリックします。 **[新しいプロジェクトの追加]** ダイアログボックスで、 **[ビジュアルC# ]** の **[拡張機能]** 、 **[VSIX プロジェクト]** の順にクリックします。 プロジェクトに `CommentAdornmentTest` という名前を付けます。

2. このプロジェクトは、厳密な名前が付けられた VSPackage アセンブリと対話するため、アセンブリに署名する必要があります。 VSPackage アセンブリ用に既に作成されているキーファイルを再利用することができます。

    1. プロジェクトのプロパティを開き、 **[署名]** タブを選択します。

    2. **[アセンブリの署名]** を選択します。

    3. [**厳密な名前のキーファイルを選択し**てください] で、MenuCommandTest アセンブリ用に生成された*キー .snk*ファイルを選択します。

## <a name="refer-to-the-mef-extension-in-the-vspackage-project"></a>VSPackage プロジェクトの MEF 拡張機能を参照してください。
 MEF コンポーネントを VSPackage に追加するため、マニフェストで両方の種類のアセットを指定する必要があります。

> [!NOTE]
> MEF の詳細については、「 [Managed Extensibility Framework (mef)](/dotnet/framework/mef/index)」を参照してください。

### <a name="to-refer-to-the-mef-component-in-the-vspackage-project"></a>VSPackage プロジェクトで MEF コンポーネントを参照するには

1. MenuCommandTest プロジェクトで、VSIX マニフェストエディターの*source.extension.vsixmanifest*ファイルを開きます。

2. **[アセット]** タブで、 **[新規]** をクリックします。

3. **[種類]** ボックスの一覧で、 **[VisualStudio]** を選択します。

4. **[ソース]** ボックスの一覧で、**現在のソリューション内のプロジェクト**を選択します。

5. **[プロジェクト]** ボックスの一覧で **[CommentAdornmentTest]** を選択します。

6. *Source.extension.vsixmanifest*ファイルを保存して閉じます。

7. MenuCommandTest プロジェクトに CommentAdornmentTest プロジェクトへの参照があることを確認します。

8. CommentAdornmentTest プロジェクトで、アセンブリを生成するようにプロジェクトを設定します。 **ソリューションエクスプローラー**でプロジェクトを選択し、 **[プロパティ]** ウィンドウで **[ビルド出力を outputdirectory にコピー]** プロパティを確認し、 **[true]** に設定します。

## <a name="define-a-comment-adornment"></a>コメントの装飾を定義する
 コメントの表示項目は、選択したテキストを追跡する <xref:Microsoft.VisualStudio.Text.ITrackingSpan> と、作成者とその説明を表す文字列で構成されます。

#### <a name="to-define-a-comment-adornment"></a>コメントの装飾を定義するには

1. CommentAdornmentTest プロジェクトで、新しいクラスファイルを追加し、`CommentAdornment` という名前を指定します。

2. 次の参照を追加します。

    1. VisualStudio. CoreUtility

    2. VisualStudio のデータ

    3. VisualStudio. Logic

    4. VisualStudio. UI

    5. VisualStudio (Microsoft. UI)

    6. System.ComponentModel.Composition

    7. PresentationCore

    8. PresentationFramework

    9. WindowsBase

3. 次の `using` ディレクティブを追加します。

    ```csharp
    using Microsoft.VisualStudio.Text;
    ```

4. このファイルには、`CommentAdornment` という名前のクラスが含まれている必要があります。

    ```csharp
    internal class CommentAdornment
    ```

5. @No__t_1、作成者、および説明のために、`CommentAdornment` クラスに3つのフィールドを追加します。

    ```csharp
    public readonly ITrackingSpan Span;
    public readonly string Author;
    public readonly string Text;
    ```

6. フィールドを初期化するコンストラクターを追加します。

    ```csharp
    public CommentAdornment(SnapshotSpan span, string author, string text)
    {
        this.Span = span.Snapshot.CreateTrackingSpan(span, SpanTrackingMode.EdgeExclusive);
        this.Author = author;
        this.Text = text;
    }
    ```

## <a name="create-a-visual-element-for-the-adornment"></a>表示要素のビジュアル要素を作成する
 表示項目のビジュアル要素を定義します。 このチュートリアルでは、<xref:System.Windows.Controls.Canvas> Windows Presentation Foundation (WPF) クラスから継承するコントロールを定義します。

1. CommentAdornmentTest プロジェクトにクラスを作成し、`CommentBlock` という名前を指定します。

2. 次の `using` ディレクティブを追加します。

    ```csharp
    using Microsoft.VisualStudio.Text;
    using System;
    using System.Windows;
    using System.Windows.Controls;
    using System.Windows.Media;
    using System.Windows.Shapes;
    using System.ComponentModel.Composition;
    using Microsoft.VisualStudio.Text.Editor;
    using Microsoft.VisualStudio.Utilities;
    ```

3. @No__t_0 クラスが <xref:System.Windows.Controls.Canvas> から継承されるようにします。

    ```csharp
    internal class CommentBlock : Canvas
    { }
    ```

4. いくつかのプライベートフィールドを追加して、表示要素の視覚的な側面を定義します。

    ```csharp
    private Geometry textGeometry;
    private Grid commentGrid;
    private static Brush brush;
    private static Pen solidPen;
    private static Pen dashPen;
    ```

5. コメントの表示要素を定義するコンストラクターを追加し、関連するテキストを追加します。

    ```csharp
    public CommentBlock(double textRightEdge, double viewRightEdge,
            Geometry newTextGeometry, string author, string body)
    {
        if (brush == null)
        {
            brush = new SolidColorBrush(Color.FromArgb(0x20, 0x00, 0xff, 0x00));
            brush.Freeze();
            Brush penBrush = new SolidColorBrush(Colors.Green);
            penBrush.Freeze();
            solidPen = new Pen(penBrush, 0.5);
            solidPen.Freeze();
            dashPen = new Pen(penBrush, 0.5);
            dashPen.DashStyle = DashStyles.Dash;
            dashPen.Freeze();
        }

        this.textGeometry = newTextGeometry;

        TextBlock tb1 = new TextBlock();
        tb1.Text = author;
        TextBlock tb2 = new TextBlock();
        tb2.Text = body;

        const int MarginWidth = 8;
        this.commentGrid = new Grid();
        this.commentGrid.RowDefinitions.Add(new RowDefinition());
        this.commentGrid.RowDefinitions.Add(new RowDefinition());
        ColumnDefinition cEdge = new ColumnDefinition();
        cEdge.Width = new GridLength(MarginWidth);
        ColumnDefinition cEdge2 = new ColumnDefinition();
        cEdge2.Width = new GridLength(MarginWidth);
        this.commentGrid.ColumnDefinitions.Add(cEdge);
        this.commentGrid.ColumnDefinitions.Add(new ColumnDefinition());
        this.commentGrid.ColumnDefinitions.Add(cEdge2);

        System.Windows.Shapes.Rectangle rect = new System.Windows.Shapes.Rectangle();
        rect.RadiusX = 6;
        rect.RadiusY = 3;
        rect.Fill = brush;
        rect.Stroke = Brushes.Green;

            Size inf = new Size(double.PositiveInfinity, double.PositiveInfinity);
            tb1.Measure(inf);
            tb2.Measure(inf);
            double middleWidth = Math.Max(tb1.DesiredSize.Width, tb2.DesiredSize.Width);
            this.commentGrid.Width = middleWidth + 2 * MarginWidth;

        Grid.SetColumn(rect, 0);
        Grid.SetRow(rect, 0);
        Grid.SetRowSpan(rect, 2);
        Grid.SetColumnSpan(rect, 3);
        Grid.SetRow(tb1, 0);
        Grid.SetColumn(tb1, 1);
        Grid.SetRow(tb2, 1);
        Grid.SetColumn(tb2, 1);
        this.commentGrid.Children.Add(rect);
        this.commentGrid.Children.Add(tb1);
        this.commentGrid.Children.Add(tb2);

        Canvas.SetLeft(this.commentGrid, Math.Max(viewRightEdge - this.commentGrid.Width - 20.0, textRightEdge + 20.0));
        Canvas.SetTop(this.commentGrid, textGeometry.GetRenderBounds(solidPen).Top);

        this.Children.Add(this.commentGrid);
    }
    ```

6. また、装飾を描画する <xref:System.Windows.Controls.Panel.OnRender%2A> イベントハンドラーも実装します。

    ```csharp
    protected override void OnRender(DrawingContext dc)
    {
        base.OnRender(dc);
        if (this.textGeometry != null)
        {
            dc.DrawGeometry(brush, solidPen, this.textGeometry);
            Rect textBounds = this.textGeometry.GetRenderBounds(solidPen);
            Point p1 = new Point(textBounds.Right, textBounds.Bottom);
            Point p2 = new Point(Math.Max(Canvas.GetLeft(this.commentGrid) - 20.0, p1.X), p1.Y);
            Point p3 = new Point(Math.Max(Canvas.GetLeft(this.commentGrid), p1.X), (Canvas.GetTop(this.commentGrid) + p1.Y) * 0.5);
            dc.DrawLine(dashPen, p1, p2);
            dc.DrawLine(dashPen, p2, p3);
        }
    }
    ```

## <a name="add-an-iwpftextviewcreationlistener"></a>IWpfTextViewCreationListener を追加する
 @No__t_0 は、作成イベントの表示をリッスンするために使用できる MEF コンポーネント部分です。

1. CommentAdornmentTest プロジェクトにクラスファイルを追加し、`Connector` という名前を指定します。

2. 次の `using` ディレクティブを追加します。

    ```csharp
    using System.ComponentModel.Composition;
    using Microsoft.VisualStudio.Text.Editor;
    using Microsoft.VisualStudio.Utilities;
    ```

3. @No__t_0 を実装するクラスを宣言し、"text" の <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute> と <xref:Microsoft.VisualStudio.Text.Editor.PredefinedTextViewRoles.Document> の <xref:Microsoft.VisualStudio.Text.Editor.TextViewRoleAttribute> を使用してエクスポートします。 Content type 属性は、コンポーネントが適用されるコンテンツの種類を指定します。 テキスト型は、すべての非バイナリファイルの種類の基本型です。 このため、作成されるほとんどすべてのテキストビューがこの型になります。 Text view role 属性は、コンポーネントが適用されるテキストビューの種類を指定します。 ドキュメントテキストビューロールでは、通常、行で構成され、ファイルに格納されているテキストが表示されます。

     [!code-vb[VSSDKMenuCommandTest#11](../extensibility/codesnippet/VisualBasic/walkthrough-using-a-shell-command-with-an-editor-extension_1.vb)]
     [!code-csharp[VSSDKMenuCommandTest#11](../extensibility/codesnippet/CSharp/walkthrough-using-a-shell-command-with-an-editor-extension_1.cs)]

4. @No__t_0 メソッドを実装して、`CommentAdornmentManager` の静的 `Create()` イベントを呼び出すようにします。

    ```csharp
    public void TextViewCreated(IWpfTextView textView)
    {
        CommentAdornmentManager.Create(textView);
    }
    ```

5. コマンドを実行するために使用できるメソッドを追加します。

    ```csharp
    static public void Execute(IWpfTextViewHost host)
    {
        IWpfTextView view = host.TextView;
        //Add a comment on the selected text. 
        if (!view.Selection.IsEmpty)
        {
            //Get the provider for the comment adornments in the property bag of the view.
            CommentAdornmentProvider provider = view.Properties.GetProperty<CommentAdornmentProvider>(typeof(CommentAdornmentProvider));

            //Add some arbitrary author and comment text. 
            string author = System.Security.Principal.WindowsIdentity.GetCurrent().Name;
            string comment = "Four score....";

            //Add the comment adornment using the provider.
            provider.Add(view.Selection.SelectedSpans[0], author, comment);
        }
    }
    ```

## <a name="define-an-adornment-layer"></a>装飾レイヤーを定義する
 新しい表示要素を追加するには、表示要素レイヤーを定義する必要があります。

### <a name="to-define-an-adornment-layer"></a>装飾層を定義するには

1. @No__t_0 クラスで <xref:Microsoft.VisualStudio.Text.Editor.AdornmentLayerDefinition> 型のパブリックフィールドを宣言し、表示要素レイヤーの一意の名前を指定する <xref:Microsoft.VisualStudio.Utilities.NameAttribute> を使用してエクスポートします。また、この表示形式レイヤーと他のテキストビューレイヤーとの Z オーダー関係を定義する <xref:Microsoft.VisualStudio.Utilities.OrderAttribute> (テキスト、キャレット、および選択) を選択します。

    ```csharp
    [Export(typeof(AdornmentLayerDefinition))]
    [Name("CommentAdornmentLayer")]
    [Order(After = PredefinedAdornmentLayers.Selection, Before = PredefinedAdornmentLayers.Text)]
    public AdornmentLayerDefinition commentLayerDefinition;

    ```

## <a name="provide-comment-adornments"></a>コメントの修飾を指定する
 表示要素を定義するときは、コメント表示項目の表示プロバイダーとコメントの表示要素を実装することもできます。 コメントの表示要素は、コメントの表示要素の一覧を保持し、基になるテキストバッファーの <xref:Microsoft.VisualStudio.Text.ITextBuffer.Changed> イベントをリッスンし、基になるテキストが削除されたときにコメントの修飾を削除します。

1. CommentAdornmentTest プロジェクトに新しいクラスファイルを追加し、`CommentAdornmentProvider` という名前を指定します。

2. 次の `using` ディレクティブを追加します。

    ```csharp
    using System;
    using System.Collections.Generic;
    using System.Collections.ObjectModel;
    using Microsoft.VisualStudio.Text;
    using Microsoft.VisualStudio.Text.Editor;
    ```

3. @No__t_0 という名前のクラスを追加します。

    ```csharp
    internal class CommentAdornmentProvider
    {
    }
    ```

4. テキストバッファーのプライベートフィールドと、バッファーに関連付けられているコメントの表示要素の一覧を追加します。

    ```csharp
    private ITextBuffer buffer;
    private IList<CommentAdornment> comments = new List<CommentAdornment>();

    ```

5. @No__t_0 のコンストラクターを追加します。 プロバイダーは `Create()` メソッドによってインスタンス化されるため、このコンストラクターにはプライベートアクセスが必要です。 コンストラクターは、<xref:Microsoft.VisualStudio.Text.ITextBuffer.Changed> イベントに `OnBufferChanged` イベントハンドラーを追加します。

    ```csharp
    private CommentAdornmentProvider(ITextBuffer buffer)
    {
        this.buffer = buffer;
        //listen to the Changed event so we can react to deletions. 
        this.buffer.Changed += OnBufferChanged;
    }

    ```

6. `Create()` メソッドを追加します。

    ```csharp
    public static CommentAdornmentProvider Create(IWpfTextView view)
    {
        return view.Properties.GetOrCreateSingletonProperty<CommentAdornmentProvider>(delegate { return new CommentAdornmentProvider(view.TextBuffer); });
    }

    ```

7. `Detach()` メソッドを追加します。

    ```csharp
    public void Detach()
    {
        if (this.buffer != null)
        {
            //remove the Changed listener 
            this.buffer.Changed -= OnBufferChanged;
            this.buffer = null;
        }
    }
    ```

8. @No__t_0 イベントハンドラーを追加します。

     [!code-csharp[VSSDKMenuCommandTest#21](../extensibility/codesnippet/CSharp/walkthrough-using-a-shell-command-with-an-editor-extension_2.cs)]
     [!code-vb[VSSDKMenuCommandTest#21](../extensibility/codesnippet/VisualBasic/walkthrough-using-a-shell-command-with-an-editor-extension_2.vb)]

9. @No__t_0 イベントの宣言を追加します。

    ```csharp
    public event EventHandler<CommentsChangedEventArgs> CommentsChanged;
    ```

10. @No__t_0 メソッドを作成して、装飾を追加します。

    ```csharp
    public void Add(SnapshotSpan span, string author, string text)
    {
        if (span.Length == 0)
            throw new ArgumentOutOfRangeException("span");
        if (author == null)
            throw new ArgumentNullException("author");
        if (text == null)
            throw new ArgumentNullException("text");

        //Create a comment adornment given the span, author and text.
        CommentAdornment comment = new CommentAdornment(span, author, text);

        //Add it to the list of comments. 
        this.comments.Add(comment);

        //Raise the changed event.
        EventHandler<CommentsChangedEventArgs> commentsChanged = this.CommentsChanged;
        if (commentsChanged != null)
            commentsChanged(this, new CommentsChangedEventArgs(comment, null));
    }

    ```

11. @No__t_0 メソッドを追加します。

    ```csharp
    public void RemoveComments(SnapshotSpan span)
    {
        EventHandler<CommentsChangedEventArgs> commentsChanged = this.CommentsChanged;

        //Get a list of all the comments that are being kept
        IList<CommentAdornment> keptComments = new List<CommentAdornment>(this.comments.Count);

        foreach (CommentAdornment comment in this.comments)
        {
            //find out if the given span overlaps with the comment text span. If two spans are adjacent, they do not overlap. To consider adjacent spans, use IntersectsWith. 
            if (comment.Span.GetSpan(span.Snapshot).OverlapsWith(span))
            {
                //Raise the change event to delete this comment. 
                if (commentsChanged != null)
                    commentsChanged(this, new CommentsChangedEventArgs(null, comment));
            }
            else
                keptComments.Add(comment);
        }

        this.comments = keptComments;
    }
    ```

12. 指定されたスナップショットスパン内のすべてのコメントを返す `GetComments()` メソッドを追加します。

    ```csharp
    public Collection<CommentAdornment> GetComments(SnapshotSpan span)
    {
        IList<CommentAdornment> overlappingComments = new List<CommentAdornment>();
        foreach (CommentAdornment comment in this.comments)
        {
            if (comment.Span.GetSpan(span.Snapshot).OverlapsWith(span))
                overlappingComments.Add(comment);
        }

        return new Collection<CommentAdornment>(overlappingComments);
    }
    ```

13. 次のように、`CommentsChangedEventArgs` という名前のクラスを追加します。

    ```csharp
    internal class CommentsChangedEventArgs : EventArgs
    {
        public readonly CommentAdornment CommentAdded;

        public readonly CommentAdornment CommentRemoved;

        public CommentsChangedEventArgs(CommentAdornment added, CommentAdornment removed)
        {
            this.CommentAdded = added;
            this.CommentRemoved = removed;
        }
    }
    ```

## <a name="manage-comment-adornments"></a>コメントの修飾の管理
 コメントの装飾マネージャーは、装飾を作成し、それを装飾層に追加します。 @No__t_0 と <xref:Microsoft.VisualStudio.Text.Editor.ITextView.Closed> のイベントをリッスンして、装飾を移動または削除できるようにします。 また、コメントが追加または削除されたときに、コメントの装飾のプロバイダーによって発生する `CommentsChanged` イベントもリッスンします。

1. CommentAdornmentTest プロジェクトにクラスファイルを追加し、`CommentAdornmentManager` という名前を指定します。

2. 次の `using` ディレクティブを追加します。

    ```csharp
    using System;
    using System.Collections.Generic;
    using System.Windows.Media;
    using Microsoft.VisualStudio.Text;
    using Microsoft.VisualStudio.Text.Editor;
    using Microsoft.VisualStudio.Text.Formatting;
    ```

3. @No__t_0 という名前のクラスを追加します。

    ```csharp
    internal class CommentAdornmentManager
        {
        }
    ```

4. いくつかのプライベートフィールドを追加します。

    ```csharp
    private readonly IWpfTextView view;
    private readonly IAdornmentLayer layer;
    private readonly CommentAdornmentProvider provider;
    ```

5. マネージャーをサブスクライブするコンストラクターを追加して、<xref:Microsoft.VisualStudio.Text.Editor.ITextView.LayoutChanged> イベントと <xref:Microsoft.VisualStudio.Text.Editor.ITextView.Closed> イベントに加え、`CommentsChanged` イベントにも追加します。 このコンストラクターは、静的 `Create()` メソッドによってマネージャーがインスタンス化されるため、プライベートです。

    ```csharp
    private CommentAdornmentManager(IWpfTextView view)
    {
        this.view = view;
        this.view.LayoutChanged += OnLayoutChanged;
        this.view.Closed += OnClosed;

        this.layer = view.GetAdornmentLayer("CommentAdornmentLayer");

        this.provider = CommentAdornmentProvider.Create(view);
        this.provider.CommentsChanged += OnCommentsChanged;
    }
    ```

6. プロバイダーを取得する `Create()` メソッドを追加するか、必要に応じて作成します。

    ```csharp
    public static CommentAdornmentManager Create(IWpfTextView view)
    {
        return view.Properties.GetOrCreateSingletonProperty<CommentAdornmentManager>(delegate { return new CommentAdornmentManager(view); });
    }
    ```

7. @No__t_0 ハンドラーを追加します。

    ```csharp
    private void OnCommentsChanged(object sender, CommentsChangedEventArgs e)
    {
        //Remove the comment (when the adornment was added, the comment adornment was used as the tag). 
        if (e.CommentRemoved != null)
            this.layer.RemoveAdornmentsByTag(e.CommentRemoved);

        //Draw the newly added comment (this will appear immediately: the view does not need to do a layout). 
        if (e.CommentAdded != null)
            this.DrawComment(e.CommentAdded);
    }
    ```

8. @No__t_0 ハンドラーを追加します。

    ```csharp
    private void OnClosed(object sender, EventArgs e)
    {
        this.provider.Detach();
        this.view.LayoutChanged -= OnLayoutChanged;
        this.view.Closed -= OnClosed;
    }
    ```

9. @No__t_0 ハンドラーを追加します。

    ```csharp
    private void OnLayoutChanged(object sender, TextViewLayoutChangedEventArgs e)
    {
        //Get all of the comments that intersect any of the new or reformatted lines of text.
        List<CommentAdornment> newComments = new List<CommentAdornment>();

        //The event args contain a list of modified lines and a NormalizedSpanCollection of the spans of the modified lines.  
        //Use the latter to find the comments that intersect the new or reformatted lines of text. 
        foreach (Span span in e.NewOrReformattedSpans)
        {
            newComments.AddRange(this.provider.GetComments(new SnapshotSpan(this.view.TextSnapshot, span)));
        }

        //It is possible to get duplicates in this list if a comment spanned 3 lines, and the first and last lines were modified but the middle line was not. 
        //Sort the list and skip duplicates.
        newComments.Sort(delegate(CommentAdornment a, CommentAdornment b) { return a.GetHashCode().CompareTo(b.GetHashCode()); });

        CommentAdornment lastComment = null;
        foreach (CommentAdornment comment in newComments)
        {
            if (comment != lastComment)
            {
                lastComment = comment;
                this.DrawComment(comment);
            }
        }
    }
    ```

10. コメントを描画するプライベートメソッドを追加します。

     [!code-csharp[VSSDKMenuCommandTest#35](../extensibility/codesnippet/CSharp/walkthrough-using-a-shell-command-with-an-editor-extension_3.cs)]
     [!code-vb[VSSDKMenuCommandTest#35](../extensibility/codesnippet/VisualBasic/walkthrough-using-a-shell-command-with-an-editor-extension_3.vb)]

## <a name="use-the-menu-command-to-add-the-comment-adornment"></a>メニューコマンドを使用して、コメントの装飾を追加します。
 メニューコマンドを使用して、VSPackage の `MenuItemCallback` メソッドを実装することにより、コメントの表示要素を作成できます。

1. MenuCommandTest プロジェクトに次の参照を追加します。

    - VisualStudio。相互運用

    - VisualStudio

    - VisualStudio (Microsoft. UI)

2. *AddAdornment.cs*ファイルを開き、次の `using` ディレクティブを追加します。

    ```csharp
    using Microsoft.VisualStudio.TextManager.Interop;
    using Microsoft.VisualStudio.Text.Editor;
    using Microsoft.VisualStudio.Editor;
    using CommentAdornmentTest;
    ```

3. @No__t_0 メソッドを削除し、次のコマンドハンドラーを追加します。

    ```csharp
    private async void AddAdornmentHandler(object sender, EventArgs e)
    {
    }
    ```

4. アクティブなビューを取得するコードを追加します。 アクティブな `IVsTextView` を取得するには、Visual Studio シェルの `SVsTextManager` を取得する必要があります。

    ```csharp
    private async void AddAdornmentHandler(object sender, EventArgs e)
    {
        IVsTextManager txtMgr = (IVsTextManager) await ServiceProvider.GetServiceAsync(typeof(SVsTextManager));
        IVsTextView vTextView = null;
        int mustHaveFocus = 1;
        txtMgr.GetActiveView(mustHaveFocus, null, out vTextView);
    }
    ```

5. このテキストビューがエディターのテキストビューのインスタンスである場合は、それを <xref:Microsoft.VisualStudio.TextManager.Interop.IVsUserData> インターフェイスにキャストし、<xref:Microsoft.VisualStudio.Text.Editor.IWpfTextViewHost> とそれに関連付けられた <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextView> を取得できます。 @No__t_0 を使用して `Connector.Execute()` メソッドを呼び出します。このメソッドは、コメントの装飾の提供元を取得し、その装飾を追加します。 コマンドハンドラーは次のようになります。

    ```csharp
    private async void AddAdornmentHandler(object sender, EventArgs e)
    {
        IVsTextManager txtMgr = (IVsTextManager) await ServiceProvider.GetServiceAsync(typeof(SVsTextManager));
        IVsTextView vTextView = null;
        int mustHaveFocus = 1;
        txtMgr.GetActiveView(mustHaveFocus, null, out vTextView);
        IVsUserData userData = vTextView as IVsUserData;
         if (userData == null)
        {
            Console.WriteLine("No text view is currently open");
            return;
        }
        IWpfTextViewHost viewHost;
        object holder;
        Guid guidViewHost = DefGuidList.guidIWpfTextViewHost;
        userData.GetData(ref guidViewHost, out holder);
        viewHost = (IWpfTextViewHost)holder;
        Connector.Execute(viewHost);
    }
    ```

6. Addadornment コンストラクターの AddAdornment コマンドのハンドラーとして、このメソッドを設定します。

    ```csharp
    private AddAdornment(AsyncPackage package, OleMenuCommandService commandService)
    {
        this.package = package ?? throw new ArgumentNullException(nameof(package));
        commandService = commandService ?? throw new ArgumentNullException(nameof(commandService));

        var menuCommandID = new CommandID(CommandSet, CommandId);
        var menuItem = new MenuCommand(this.AddAdornmentHandler, menuCommandID);
        commandService.AddCommand(menuItem);
    }
    ```

## <a name="build-and-test-the-code"></a>コードをビルドしてテストする

1. ソリューションをビルドし、デバッグを開始します。 実験用インスタンスが表示されます。

2. テキスト ファイルを作成します。 テキストを入力して選択します。

3. **[ツール]** メニューの **[装飾の追加]** をクリックします。 バルーンはテキストウィンドウの右側に表示され、次のテキストのようなテキストが含まれている必要があります。

     ユーザー名

     4スコア...

## <a name="see-also"></a>関連項目
- [チュートリアル: コンテンツの種類をファイル名拡張子にリンクする](../extensibility/walkthrough-linking-a-content-type-to-a-file-name-extension.md)
