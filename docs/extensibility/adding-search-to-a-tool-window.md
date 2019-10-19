---
title: ツールウィンドウへの検索の追加 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- tool windows, adding search
ms.assetid: f78c4892-8060-49c4-8ecd-4360f1b4d133
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 4414f6d907424a1abb56bccd1d1b125444e7c716
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72648001"
---
# <a name="add-search-to-a-tool-window"></a>ツールウィンドウへの検索の追加
拡張機能でツールウィンドウを作成または更新するときに、Visual Studio の他の場所に表示されるのと同じ検索機能を追加できます。 この機能には、次の機能があります。

- ツールバーのカスタム領域に常に配置されている検索ボックス。

- 検索ボックス自体に重なっている進行状況インジケーター。

- 各文字を入力するとすぐに結果を表示する機能 (クイック検索)、または**enter**キー (要求時に検索) を選択した後にのみ結果を表示する機能。

- 最近検索した用語を示す一覧。

- 検索対象の特定のフィールドまたは要素によって検索をフィルター処理する機能。

このチュートリアルでは、次のタスクを実行する方法について説明します。

1. VSPackage プロジェクトを作成します。

2. 読み取り専用のテキストボックスを持つ UserControl を含むツールウィンドウを作成します。

3. ツールウィンドウに検索ボックスを追加します。

4. 検索の実装を追加します。

5. クイック検索を有効にし、進行状況バーを表示します。

6. [**大文字と小文字を区別**する] オプションを追加します。

7. **偶数行のみを検索**するフィルターを追加します。

## <a name="to-create-a-vsix-project"></a>VSIX プロジェクトを作成するには

1. **Testsearch**という名前のツールウィンドウを使用して、`TestToolWindowSearch` という名前の VSIX プロジェクトを作成します。 この操作について支援が必要な場合は、「[ツールウィンドウを使用した拡張機能の作成](../extensibility/creating-an-extension-with-a-tool-window.md)」を参照してください。

## <a name="to-create-a-tool-window"></a>ツールウィンドウを作成するには

1. @No__t_0 プロジェクトで、 *Testsearchcontrol .xaml*ファイルを開きます。

2. 既存の `<StackPanel>` ブロックを次のブロックに置き換えます。これにより、読み取り専用の <xref:System.Windows.Controls.TextBox> がツールウィンドウの <xref:System.Windows.Controls.UserControl> に追加されます。

    ```xaml
    <StackPanel Orientation="Vertical">
        <TextBox Name="resultsTextBox" Height="800.0"
            Width="800.0"
            IsReadOnly="True">
        </TextBox>
    </StackPanel>
    ```

3. *TestSearchControl.xaml.cs*ファイルで、次の using ディレクティブを追加します。

    ```csharp
    using System.Text;
    ```

4. @No__t_0 メソッドを削除します。

     **Testsearchcontrol**クラスに次のコードを追加します。

     このコードは、 **Searchresultstextbox**という名前のパブリック <xref:System.Windows.Controls.TextBox> プロパティと、 **searchcontent**という名前のパブリック文字列プロパティを追加します。 コンストラクターでは、SearchResultsTextBox がテキストボックスに設定され、SearchContent は、改行で区切られた一連の文字列に初期化されます。 テキストボックスの内容は、文字列のセットにも初期化されます。

     [!code-csharp[ToolWindowSearch#1](../extensibility/codesnippet/CSharp/adding-search-to-a-tool-window_1.cs)]
     [!code-vb[ToolWindowSearch#1](../extensibility/codesnippet/VisualBasic/adding-search-to-a-tool-window_1.vb)]

5. プロジェクトをビルドし、デバッグを開始します。 Visual Studio の実験用インスタンスが表示されます。

6. メニューバーで、[ > **その他のウィンドウ** > **Testsearch**を**表示**] を選択します。

     ツールウィンドウが表示されますが、検索コントロールはまだ表示されていません。

## <a name="to-add-a-search-box-to-the-tool-window"></a>ツールウィンドウに検索ボックスを追加するには

1. *TestSearch.cs*ファイルで、次のコードを `TestSearch` クラスに追加します。 このコードは、get アクセサーが `true` を返すように、<xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowSearch.SearchEnabled%2A> プロパティをオーバーライドします。

     検索を有効にするには、<xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowSearch.SearchEnabled%2A> プロパティをオーバーライドする必要があります。 @No__t_0 クラスは <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowSearch> を実装し、検索を有効にしない既定の実装を提供します。

    ```csharp
    public override bool SearchEnabled
    {
        get { return true; }
    }
    ```

2. プロジェクトをビルドし、デバッグを開始します。 実験用インスタンスが表示されます。

3. Visual Studio の実験用インスタンスで、 **Testsearch**を開きます。

     ツールウィンドウの上部に**は、検索ウォーターマーク**と虫眼鏡アイコンが表示されます。 ただし、検索プロセスが実装されていないため、検索はまだ機能しません。

## <a name="to-add-the-search-implementation"></a>検索の実装を追加するには
 前の手順のように、<xref:Microsoft.VisualStudio.Shell.ToolWindowPane> での検索を有効にすると、ツールウィンドウによって検索ホストが作成されます。 このホストは、常にバックグラウンドスレッドで実行される検索プロセスを設定および管理します。 @No__t_0 クラスは検索ホストの作成と検索の設定を管理するため、検索タスクを作成して検索方法を指定するだけで済みます。 検索プロセスはバックグラウンドスレッドで実行され、ツールウィンドウコントロールの呼び出しは UI スレッド上で発生します。 そのため、コントロールを処理するときに行う呼び出しを管理するには、 [Threadhelper. Invoke *](https://msdn.microsoft.com/data/ee197798(v=vs.85))メソッドを使用する必要があります。

1. *TestSearch.cs*ファイルで、次の `using` ディレクティブを追加します。

    ```csharp
    using System;
    using System.Collections.Generic;
    using System.Runtime.InteropServices;
    using System.Text;
    using System.Windows.Controls;
    using Microsoft.Internal.VisualStudio.PlatformUI;
    using Microsoft.VisualStudio;
    using Microsoft.VisualStudio.PlatformUI;
    using Microsoft.VisualStudio.Shell;
    using Microsoft.VisualStudio.Shell.Interop;
    ```

2. @No__t_0 クラスで、次のアクションを実行する次のコードを追加します。

    - @No__t_0 メソッドをオーバーライドして、検索タスクを作成します。

    - @No__t_0 メソッドをオーバーライドして、テキストボックスの状態を復元します。 このメソッドは、ユーザーが検索タスクをキャンセルしたときと、ユーザーがオプションやフィルターを設定または解除したときに呼び出されます。 UI スレッドで <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowSearch.CreateSearch%2A> と <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowSearch.ClearSearch%2A> の両方が呼び出されます。 したがって、 [Threadhelper. Invoke *](https://msdn.microsoft.com/data/ee197798(v=vs.85))メソッドを使用してテキストボックスにアクセスする必要はありません。

    - @No__t_1 から継承する `TestSearchTask` という名前のクラスを作成します。これにより、<xref:Microsoft.VisualStudio.Shell.Interop.IVsSearchTask> の既定の実装が提供されます。

         @No__t_0 では、コンストラクターは、ツールウィンドウを参照するプライベートフィールドを設定します。 検索メソッドを提供するには、<xref:Microsoft.VisualStudio.Shell.VsSearchTask.OnStartSearch%2A> および <xref:Microsoft.VisualStudio.Shell.VsSearchTask.OnStopSearch%2A> メソッドをオーバーライドします。 @No__t_0 方法では、検索プロセスを実装します。 このプロセスでは、検索の実行、テキストボックスへの検索結果の表示、およびこのメソッドの基本クラスの実装を呼び出して、検索が完了したことを報告します。

    ```csharp
    public override IVsSearchTask CreateSearch(uint dwCookie, IVsSearchQuery pSearchQuery, IVsSearchCallback pSearchCallback)
    {
        if (pSearchQuery == null || pSearchCallback == null)
            return null;
         return new TestSearchTask(dwCookie, pSearchQuery, pSearchCallback, this);
    }

    public override void ClearSearch()
    {
        TestSearchControl control = (TestSearchControl)this.Content;
        control.SearchResultsTextBox.Text = control.SearchContent;
    }

    internal class TestSearchTask : VsSearchTask
    {
        private TestSearch m_toolWindow;

        public TestSearchTask(uint dwCookie, IVsSearchQuery pSearchQuery, IVsSearchCallback pSearchCallback, TestSearch toolwindow)
            : base(dwCookie, pSearchQuery, pSearchCallback)
        {
            m_toolWindow = toolwindow;
        }

        protected override void OnStartSearch()
        {
            // Use the original content of the text box as the target of the search.
            var separator = new string[] { Environment.NewLine };
            TestSearchControl control = (TestSearchControl)m_toolWindow.Content;
            string[] contentArr = control.SearchContent.Split(separator, StringSplitOptions.None);

            // Get the search option.
            bool matchCase = false;
            // matchCase = m_toolWindow.MatchCaseOption.Value;

                // Set variables that are used in the finally block.
                StringBuilder sb = new StringBuilder("");
                uint resultCount = 0;
                this.ErrorCode = VSConstants.S_OK;

                try
                {
                    string searchString = this.SearchQuery.SearchString;

                    // Determine the results.
                    uint progress = 0;
                    foreach (string line in contentArr)
                    {
                        if (matchCase == true)
                        {
                            if (line.Contains(searchString))
                            {
                                sb.AppendLine(line);
                                resultCount++;
                            }
                        }
                        else
                            {
                                if (line.ToLower().Contains(searchString.ToLower()))
                                {
                                    sb.AppendLine(line);
                                    resultCount++;
                                }
                            }

                            // SearchCallback.ReportProgress(this, progress++, (uint)contentArr.GetLength(0));

                            // Uncomment the following line to demonstrate the progress bar.
                            // System.Threading.Thread.Sleep(100);
                        }
                    }
                    catch (Exception e)
                    {
                        this.ErrorCode = VSConstants.E_FAIL;
                    }
                    finally
                    {
                        ThreadHelper.Generic.Invoke(() =>
                        { ((TextBox)((TestSearchControl)m_toolWindow.Content).SearchResultsTextBox).Text = sb.ToString(); });

                        this.SearchResults = resultCount;
                    }

            // Call the implementation of this method in the base class.
            // This sets the task status to complete and reports task completion.
            base.OnStartSearch();
        }

        protected override void OnStopSearch()
        {
            this.SearchResults = 0;
        }
    }
    ```

3. 次の手順を実行して、検索の実装をテストします。

    1. プロジェクトをリビルドし、デバッグを開始します。

    2. Visual Studio の実験用インスタンスで、ツールウィンドウをもう一度開き、[検索] ウィンドウに検索テキストを入力して、 **Enter キー**を押します。

         正しい結果が表示されます。

## <a name="to-customize-the-search-behavior"></a>検索動作をカスタマイズするには
 検索設定を変更することで、検索コントロールの表示方法と検索方法にさまざまな変更を加えることができます。たとえば、透かし (検索ボックスに表示される既定のテキスト)、検索コントロールの最小および最大の幅、および進行状況バーを表示するかどうかを変更できます。 また、検索結果が表示される位置 (要求時またはクイック検索) と、最近検索した用語の一覧を表示するかどうかを変更することもできます。 設定の完全な一覧については、<xref:Microsoft.VisualStudio.PlatformUI.SearchSettingsDataSource> クラスを参照してください。

1. \* TestSearch.cs * ファイルで、次のコードを `TestSearch` クラスに追加します。 このコードは、オンデマンド検索ではなく、インスタント検索を有効にします (つまり、ユーザーは**ENTER キー**をクリックする必要はありません)。 このコードは、既定の設定を変更するために必要な、`TestSearch` クラスの `ProvideSearchSettings` メソッドをオーバーライドします。

    ```csharp
    public override void ProvideSearchSettings(IVsUIDataSource pSearchSettings)
    {
        Utilities.SetValue(pSearchSettings,
            SearchSettingsDataSource.SearchStartTypeProperty.Name,
            (uint)VSSEARCHSTARTTYPE.SST_INSTANT);}
    ```

2. ソリューションをリビルドし、デバッガーを再起動して、新しい設定をテストします。

     検索ボックスに文字を入力するたびに検索結果が表示されます。

3. @No__t_0 メソッドで、次の行を追加します。これにより、進行状況バーが表示されます。

    ```csharp
    public override void ProvideSearchSettings(IVsUIDataSource pSearchSettings)
    {
        Utilities.SetValue(pSearchSettings,
            SearchSettingsDataSource.SearchStartTypeProperty.Name,
             (uint)VSSEARCHSTARTTYPE.SST_INSTANT);
        Utilities.SetValue(pSearchSettings,
            SearchSettingsDataSource.SearchProgressTypeProperty.Name,
             (uint)VSSEARCHPROGRESSTYPE.SPT_DETERMINATE);
    }
    ```

     進行状況バーが表示されるようにするには、進行状況を報告する必要があります。 進行状況を報告するには、`TestSearchTask` クラスの `OnStartSearch` メソッドで次のコードをコメント解除します。

    ```csharp
    SearchCallback.ReportProgress(this, progress++, (uint)contentArr.GetLength(0));
    ```

4. 処理速度が低下して進行状況バーが表示されるようにするには、`TestSearchTask` クラスの `OnStartSearch` メソッドで次の行のコメントを解除します。

    ```csharp
    System.Threading.Thread.Sleep(100);
    ```

5. ソリューションをリビルドし、デバッグを開始して、新しい設定をテストします。

     検索を実行するたびに、進行状況バーが検索ウィンドウ ([検索] テキストボックスの下にある青い線) で表示されます。

## <a name="to-enable-users-to-refine-their-searches"></a>ユーザーが検索を絞り込むことができるようにするには
 **大文字と小文字の区別**や**単語単位の一致**などのオプションを使用して、ユーザーが検索を絞り込むことができるようにすることができます。 オプションは、チェックボックスとして表示されるブール値、またはボタンとして表示されるコマンドです。 このチュートリアルでは、ブール型のオプションを作成します。

1. *TestSearch.cs*ファイルで、次のコードを `TestSearch` クラスに追加します。 このコードは `SearchOptionsEnum` メソッドをオーバーライドします。これにより、検索の実装は、指定されたオプションがオンかオフかを検出できます。 @No__t_0 のコードは、case を <xref:Microsoft.VisualStudio.Shell.Interop.IVsEnumWindowSearchOptions> 列挙子に一致させるオプションを追加します。 Case を一致させるオプションは、`MatchCaseOption` プロパティとしても使用できます。

    ```csharp
    private IVsEnumWindowSearchOptions m_optionsEnum;
    public override IVsEnumWindowSearchOptions SearchOptionsEnum
    {
        get
        {
            if (m_optionsEnum == null)
            {
                List<IVsWindowSearchOption> list = new List<IVsWindowSearchOption>();

                list.Add(this.MatchCaseOption);

                m_optionsEnum = new WindowSearchOptionEnumerator(list) as IVsEnumWindowSearchOptions;
            }
            return m_optionsEnum;
        }
    }

    private WindowSearchBooleanOption m_matchCaseOption;
    public WindowSearchBooleanOption MatchCaseOption
    {
        get
        {
            if (m_matchCaseOption == null)
            {
                m_matchCaseOption = new WindowSearchBooleanOption("Match case", "Match case", false);
            }
            return m_matchCaseOption;
        }
    }
    ```

2. @No__t_0 クラスで、`OnStartSearch` メソッド内の次の行をコメント解除します。

    ```csharp
    matchCase = m_toolWindow.MatchCaseOption.Value;
    ```

3. オプションをテストします。

    1. プロジェクトをビルドし、デバッグを開始します。 実験用インスタンスが表示されます。

    2. ツールウィンドウで、テキストボックスの右側にある下向きの矢印をクリックします。

         [**大文字と小文字を区別**する] チェックボックスが表示されます。

    3. [**大文字と小文字を区別**する] チェックボックスをオンにし、いくつかの検索を実行します。

## <a name="to-add-a-search-filter"></a>検索フィルターを追加するには
 検索対象のセットをユーザーが絞り込むことができる検索フィルターを追加できます。 たとえば、ファイルエクスプローラーで、最近変更された日付とファイル名拡張子を使用してファイルをフィルター処理できます。 このチュートリアルでは、偶数行に対してのみフィルターを追加します。 ユーザーがそのフィルターを選択すると、検索ホストによって、検索クエリに指定した文字列が追加されます。 検索メソッド内でこれらの文字列を識別し、それに応じて検索ターゲットをフィルター処理できます。

1. *TestSearch.cs*ファイルで、次のコードを `TestSearch` クラスに追加します。 このコードでは、`SearchFiltersEnum` を実装しています。これによって、検索結果をフィルター処理して、偶数行だけが表示されるように指定する <xref:Microsoft.VisualStudio.PlatformUI.WindowSearchSimpleFilter> を追加します。

    ```csharp
    public override IVsEnumWindowSearchFilters SearchFiltersEnum
    {
        get
        {
            List<IVsWindowSearchFilter> list = new List<IVsWindowSearchFilter>();
            list.Add(new WindowSearchSimpleFilter("Search even lines only", "Search even lines only", "lines", "even"));
            return new WindowSearchFilterEnumerator(list) as IVsEnumWindowSearchFilters;
        }
    }

    ```

     検索コントロールに `Search even lines only` 検索フィルターが表示されるようになりました。 ユーザーがフィルターを選択すると、検索ボックスに文字列 `lines:"even"` が表示されます。 他の検索条件は、フィルターと同時に表示できます。 検索文字列は、フィルターの前、フィルターの後、またはその両方に表示される場合があります。

2. *TestSearch.cs*ファイルで、次のメソッドを `TestSearch` クラスの `TestSearchTask` クラスに追加します。 これらのメソッドは、次の手順で変更する `OnStartSearch` メソッドをサポートしています。

    ```csharp
    private string RemoveFromString(string origString, string stringToRemove)
    {
        int index = origString.IndexOf(stringToRemove);
        if (index == -1)
            return origString;
        else 
             return (origString.Substring(0, index) + origString.Substring(index + stringToRemove.Length)).Trim();
    }

    private string[] GetEvenItems(string[] contentArr)
    {
        int length = contentArr.Length / 2;
        string[] evenContentArr = new string[length];

        int indexB = 0;
        for (int index = 1; index < contentArr.Length; index += 2)
        {
            evenContentArr[indexB] = contentArr[index];
            indexB++;
        }

        return evenContentArr;
    }
    ```

3. @No__t_0 クラスで、次のコードを使用して `OnStartSearch` メソッドを更新します。 この変更により、フィルターをサポートするようにコードが更新されます。

    ```csharp
    protected override void OnStartSearch()
    {
        // Use the original content of the text box as the target of the search. 
        var separator = new string[] { Environment.NewLine };
        string[] contentArr = ((TestSearchControl)m_toolWindow.Content).SearchContent.Split(separator, StringSplitOptions.None);

        // Get the search option. 
        bool matchCase = false;
        matchCase = m_toolWindow.MatchCaseOption.Value;

        // Set variables that are used in the finally block.
        StringBuilder sb = new StringBuilder("");
        uint resultCount = 0;
        this.ErrorCode = VSConstants.S_OK;

        try
        {
            string searchString = this.SearchQuery.SearchString;

            // If the search string contains the filter string, filter the content array. 
            string filterString = "lines:\"even\"";

            if (this.SearchQuery.SearchString.Contains(filterString))
            {
                // Retain only the even items in the array.
                contentArr = GetEvenItems(contentArr);

                // Remove 'lines:"even"' from the search string.
                searchString = RemoveFromString(searchString, filterString);
            }

            // Determine the results. 
            uint progress = 0;
            foreach (string line in contentArr)
            {
                if (matchCase == true)
                {
                    if (line.Contains(searchString))
                    {
                        sb.AppendLine(line);
                        resultCount++;
                    }
                }
                else
                {
                    if (line.ToLower().Contains(searchString.ToLower()))
                    {
                        sb.AppendLine(line);
                        resultCount++;
                    }
                }

                SearchCallback.ReportProgress(this, progress++, (uint)contentArr.GetLength(0));

                // Uncomment the following line to demonstrate the progress bar. 
                // System.Threading.Thread.Sleep(100);
            }
        }
        catch (Exception e)
        {
            this.ErrorCode = VSConstants.E_FAIL;
        }
        finally
        {
            ThreadHelper.Generic.Invoke(() =>
            { ((TextBox)((TestSearchControl)m_toolWindow.Content).SearchResultsTextBox).Text = sb.ToString(); });

            this.SearchResults = resultCount;
        }

        // Call the implementation of this method in the base class. 
        // This sets the task status to complete and reports task completion. 
        base.OnStartSearch();
    }
    ```

4. コードをテストします。

5. プロジェクトをビルドし、デバッグを開始します。 Visual Studio の実験用インスタンスで、ツールウィンドウを開き、検索コントロールの下矢印をクリックします。

     **[大文字と小文字を区別]** する チェックボックスと **[偶数行のみ検索]** フィルターが表示されます。

6. フィルターを選択します。

     検索ボックスには、 **"偶数"** という行が含まれ、次の結果が表示されます。

     2つ良好

     4良好

     6\.

7. [検索] ボックスから `lines:"even"` を削除し、[**大文字と小文字を区別**する] チェックボックスをオンにして、検索ボックスに「`g`」と入力します。

     次の結果が表示されます。

     1つ進む

     2つ良好

     5\.

8. 検索ボックスの右側にある [X] を選択します。

     検索はクリアされ、元のコンテンツが表示されます。 ただし、[**大文字と小文字を区別**する] チェックボックスはオンのままです。
