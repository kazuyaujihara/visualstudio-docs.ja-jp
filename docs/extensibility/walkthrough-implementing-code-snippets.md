---
title: 'チュートリアル: コードスニペットの実装 |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: adbc5382-d170-441c-9fd0-80faa1816478
author: madskristensen
ms.author: madsk
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- vssdk
ms.openlocfilehash: 84674a12165a3c5cd47c9004274669d377d330c5
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72632502"
---
# <a name="walkthrough-implement-code-snippets"></a>チュートリアル: コードスニペットの実装
コードスニペットを作成してエディター拡張機能に含めると、拡張機能のユーザーが独自のコードに追加できるようになります。

 コードスニペットは、ファイルに組み込むことができるコードまたはその他のテキストの断片です。 特定のプログラミング言語用に登録されているすべてのスニペットを表示するには、 **[ツール]** メニューの **[コードスニペットマネージャー]** をクリックします。 スニペットをファイルに挿入するには、スニペットを配置する場所を右クリックし、[スニペットの挿入] または [**ブロック**の挿入] をクリックして、目的のスニペットを見つけてダブルクリックします。 Tab キーまた**は Shift** +**tab**キー**を押して**スニペットの関連部分を変更し、enter キーまたは**Esc**キー**を押して**受け入れます。 詳細については、「[コードスニペット](../ide/code-snippets.md)」を参照してください。

 コードスニペットは、スニペット * ファイル名拡張子を持つ XML ファイルに含まれています。 スニペットには、スニペットが挿入された後に強調表示されるフィールドを含めることができます。これにより、ユーザーはそれらを見つけて変更できます。 スニペットファイルは、**コードスニペットマネージャー**に関する情報も提供します。これにより、スニペット名が正しいカテゴリに表示されます。 スニペットスキーマの詳細については、「[コードスニペットスキーマリファレンス](../ide/code-snippets-schema-reference.md)」を参照してください。

 このチュートリアルでは、次のタスクを実行する方法について説明します。

1. 特定の言語のコードスニペットを作成して登録します。

2. **[スニペットの挿入]** コマンドをショートカットメニューに追加します。

3. スニペット拡張を実装します。

   このチュートリアルは、 [「チュートリアル: Display ステートメントの入力候補](../extensibility/walkthrough-displaying-statement-completion.md)」に基づいています。

## <a name="prerequisites"></a>必要条件
 Visual Studio 2015 以降では、ダウンロードセンターから Visual Studio SDK をインストールしません。 これは、Visual Studio セットアップでオプション機能として含まれています。 VS SDK は、後でインストールすることもできます。 詳細については、「 [Visual STUDIO SDK のインストール](../extensibility/installing-the-visual-studio-sdk.md)」を参照してください。

## <a name="create-and-register-code-snippets"></a>コードスニペットの作成と登録
 通常、コードスニペットは、登録されている言語サービスに関連付けられています。 ただし、コードスニペットを登録するために <xref:Microsoft.VisualStudio.Package.LanguageService> を実装する必要はありません。 代わりに、スニペットインデックスファイルで GUID を指定し、プロジェクトに追加した <xref:Microsoft.VisualStudio.Shell.ProvideLanguageCodeExpansionAttribute> で同じ GUID を使用します。

 次の手順では、コードスニペットを作成し、特定の GUID に関連付ける方法を示します。

1. 次のディレクトリ構造を作成します。

    **%InstallDir%\TestSnippets\Snippets\1033 \\**

    ここで、 *% InstallDir%* は Visual Studio のインストールフォルダーです。 (通常、このパスはコードスニペットのインストールに使用されますが、任意のパスを指定できます)。

2. \ 1033 \ フォルダーで、 *.xml*ファイルを作成し、「 **testsnippets .xml**」という名前を指定します。 (通常、この名前はスニペットのインデックスファイルに使用されますが、 *.xml*ファイル名拡張子を持つ限り、任意の名前を指定できます)。次のテキストを追加し、プレースホルダー GUID を削除して、独自の GUID を追加します。

   ```xml
   <?xml version="1.0" encoding="utf-8" ?>
   <SnippetCollection>
       <Language Lang="TestSnippets" Guid="{00000000-0000-0000-0000-000000000000}">
           <SnippetDir>
               <OnOff>On</OnOff>
               <Installed>true</Installed>
               <Locale>1033</Locale>
               <DirPath>%InstallRoot%\TestSnippets\Snippets\%LCID%\</DirPath>
               <LocalizedName>Snippets</LocalizedName>
           </SnippetDir>
       </Language>
   </SnippetCollection>
   ```

3. スニペットフォルダー内にファイルを作成し、 **test** `.snippet` という名前を指定して、次のテキストを追加します。

   ```xml
   <?xml version="1.0" encoding="utf-8" ?>
   <CodeSnippets  xmlns="http://schemas.microsoft.com/VisualStudio/2005/CodeSnippet">
       <CodeSnippet Format="1.0.0">
           <Header>
               <Title>Test replacement fields</Title>
               <Shortcut>test</Shortcut>
               <Description>Code snippet for testing replacement fields</Description>
               <Author>MSIT</Author>
               <SnippetTypes>
                   <SnippetType>Expansion</SnippetType>
               </SnippetTypes>
           </Header>
           <Snippet>
               <Declarations>
                   <Literal>
                     <ID>param1</ID>
                       <ToolTip>First field</ToolTip>
                       <Default>first</Default>
                   </Literal>
                   <Literal>
                       <ID>param2</ID>
                       <ToolTip>Second field</ToolTip>
                       <Default>second</Default>
                   </Literal>
               </Declarations>
               <References>
                  <Reference>
                      <Assembly>System.Windows.Forms.dll</Assembly>
                  </Reference>
               </References>
               <Code Language="TestSnippets">
                   <![CDATA[MessageBox.Show("$param1$");
        MessageBox.Show("$param2$");]]>
               </Code>
           </Snippet>
       </CodeSnippet>
   </CodeSnippets>
   ```

   次の手順は、コードスニペットを登録する方法を示しています。

### <a name="to-register-code-snippets-for-a-specific-guid"></a>特定の GUID のコードスニペットを登録するには

1. [確認]**テスト**プロジェクトを開きます。 このプロジェクトを作成する方法の詳細については、「[チュートリアル: 表示ステートメント入力候補](../extensibility/walkthrough-displaying-statement-completion.md)」を参照してください。

2. プロジェクトで、次のアセンブリへの参照を追加します。

    - VisualStudio。相互運用

    - VisualStudio (Microsoft. 相互運用性)

    - microsoft msxml

3. プロジェクトで、 **source.extension.vsixmanifest**ファイルを開きます。

4. **[アセット]** タブに**VsPackage**コンテンツタイプが含まれており、その**プロジェクト**がプロジェクトの名前に設定されていることを確認します。

5. 作成 テストプロジェクトを選択し、プロパティウィンドウ  **Pkgdef ファイルの生成** を **true** に設定します。 プロジェクトを保存します。

6. 静的 `SnippetUtilities` クラスをプロジェクトに追加します。

     [!code-csharp[VSSDKCompletionTest#22](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_1.cs)]
     [!code-vb[VSSDKCompletionTest#22](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_1.vb)]

7. SnippetUtilities クラスで、GUID を定義し、 *SnippetsIndex*ファイルで使用した値を指定します。

     [!code-csharp[VSSDKCompletionTest#23](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_2.cs)]
     [!code-vb[VSSDKCompletionTest#23](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_2.vb)]

8. @No__t_1 クラスに <xref:Microsoft.VisualStudio.Shell.ProvideLanguageCodeExpansionAttribute> を追加します。 この属性は、プロジェクト内の任意のパブリックまたは内部 (非静的) クラスに追加できます。 (場合によっては、VisualStudio 名前空間の `using` ディレクティブを追加する必要があります)。

     [!code-csharp[VSSDKCompletionTest#24](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_3.cs)]
     [!code-vb[VSSDKCompletionTest#24](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_3.vb)]

9. プロジェクトをビルドして実行します。 プロジェクトの実行時に起動される Visual Studio の実験用インスタンスでは、先ほど登録したスニペットが**testsnippets**言語の下にある**コードスニペットマネージャー**に表示されます。

## <a name="add-the-insert-snippet-command-to-the-shortcut-menu"></a>[スニペットの挿入] コマンドをショートカットメニューに追加する
 **[スニペットの挿入]** コマンドは、テキストファイルのショートカットメニューには含まれていません。 そのため、コマンドを有効にする必要があります。

#### <a name="to-add-the-insert-snippet-command-to-the-shortcut-menu"></a>[スニペットの挿入] コマンドをショートカットメニューに追加するには

1. @No__t_0 クラスファイルを開きます。

     このクラスは <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> を実装しているため、<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> メソッドで **[スニペットの挿入]** コマンドをアクティブにすることができます。 コマンドを有効にする前に、このメソッドがオートメーション関数の内部で呼び出されていないことを確認してください。これは、 **[スニペットの挿入]** コマンドをクリックすると、スニペットピッカーユーザーインターフェイス (UI) が表示されるためです。

     [!code-csharp[VSSDKCompletionTest#25](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_4.cs)]
     [!code-vb[VSSDKCompletionTest#25](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_4.vb)]

2. プロジェクトをビルドして実行します。 実験用インスタンスで、ファイル名拡張子が*zzz*のファイルを開き、その中の任意の場所を右クリックします。 ショートカットメニューに **[スニペットの挿入]** コマンドが表示されます。

## <a name="implement-snippet-expansion-in-the-snippet-picker-ui"></a>スニペットピッカー UI でのスニペット拡張の実装
 このセクションでは、ショートカットメニューの **[スニペットの挿入]** をクリックしたときにスニペットピッカー UI が表示されるように、コードスニペット拡張を実装する方法について説明します。 コードスニペットは、ユーザーがコードスニペットのショートカットを入力し、 **tab**キーを押したときにも展開されます。

 スニペットピッカー UI を表示し、ナビゲーションと挿入後のスニペットの受け入れを有効にするには、<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> メソッドを使用します。 挿入自体は、<xref:Microsoft.VisualStudio.TextManager.Interop.IVsExpansionClient.OnItemChosen%2A> メソッドによって処理されます。

 コードスニペット拡張の実装では、従来の <xref:Microsoft.VisualStudio.TextManager.Interop> インターフェイスが使用されます。 現在のエディタークラスからレガシコードに変換する場合は、従来のインターフェイスでは、行番号と列番号の組み合わせを使用してテキストバッファー内の場所を指定しますが、現在のクラスは1つのインデックスを使用することに注意してください。 したがって、バッファーには、それぞれが10文字 (1 文字としてカウントする改行) を持つ3つの行が含まれている場合、3行目の4番目の文字は現在の実装では27の位置にありますが、前の実装では行2の位置3にあります。

#### <a name="to-implement-snippet-expansion"></a>スニペット拡張を実装するには

1. @No__t_0 クラスを含むファイルに、次の `using` ディレクティブを追加します。

     [!code-csharp[VSSDKCompletionTest#26](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_5.cs)]
     [!code-vb[VSSDKCompletionTest#26](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_5.vb)]

2. @No__t_0 クラスが <xref:Microsoft.VisualStudio.TextManager.Interop.IVsExpansionClient> インターフェイスを実装するようにします。

     [!code-csharp[VSSDKCompletionTest#27](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_6.cs)]
     [!code-vb[VSSDKCompletionTest#27](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_6.vb)]

3. @No__t_0 クラスで、<xref:Microsoft.VisualStudio.Text.Operations.ITextStructureNavigatorSelectorService> をインポートします。

     [!code-csharp[VSSDKCompletionTest#28](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_7.cs)]
     [!code-vb[VSSDKCompletionTest#28](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_7.vb)]

4. コード拡張インターフェイスと <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> にプライベートフィールドを追加します。

     [!code-csharp[VSSDKCompletionTest#29](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_8.cs)]
     [!code-vb[VSSDKCompletionTest#29](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_8.vb)]

5. @No__t_0 クラスのコンストラクターで、次のフィールドを設定します。

     [!code-csharp[VSSDKCompletionTest#30](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_9.cs)]
     [!code-vb[VSSDKCompletionTest#30](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_9.vb)]

6. ユーザーが **[スニペットの挿入]** コマンドをクリックしたときにスニペットピッカーを表示するには、<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> メソッドに次のコードを追加します。 (この説明を読みやすくするために、ステートメント入力候補に使用される `Exec()`code は表示されません。代わりに、既存のメソッドにコードのブロックが追加されます)。文字をチェックするコードの後に、次のコードブロックを追加します。

     [!code-csharp[VSSDKCompletionTest#31](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_10.cs)]
     [!code-vb[VSSDKCompletionTest#31](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_10.vb)]

7. 移動できるフィールドがスニペットにある場合、拡張が明示的に許可されるまで拡張セッションは開いたままになります。スニペットにフィールドがない場合、セッションは閉じられ、<xref:Microsoft.VisualStudio.TextManager.Interop.IVsExpansionManager.InvokeInsertionUI%2A> メソッドによって `null` として返されます。 @No__t_0 メソッドで、前の手順で追加したスニペットピッカー UI コードの後に、スニペットナビゲーションを処理する次のコードを追加します (ユーザーがスニペットの挿入後に**Tab**キーまたは Shift +**tab** **キー**を押した場合)。

     [!code-csharp[VSSDKCompletionTest#32](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_11.cs)]
     [!code-vb[VSSDKCompletionTest#32](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_11.vb)]

8. ユーザーが対応するショートカットを入力して**tab**キーを押したときにコードスニペットを挿入するには、<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> メソッドにコードを追加します。 スニペットを挿入するプライベートメソッドが、後の手順で表示されます。 前の手順で追加したナビゲーションコードの後に、次のコードを追加します。

     [!code-csharp[VSSDKCompletionTest#33](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_12.cs)]
     [!code-vb[VSSDKCompletionTest#33](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_12.vb)]

9. @No__t_0 インターフェイスのメソッドを実装します。 この実装では、対象となるメソッドは <xref:Microsoft.VisualStudio.TextManager.Interop.IVsExpansionClient.EndExpansion%2A> と <xref:Microsoft.VisualStudio.TextManager.Interop.IVsExpansionClient.OnItemChosen%2A> だけです。 他のメソッドは <xref:Microsoft.VisualStudio.VSConstants.S_OK> を返すだけです。

     [!code-csharp[VSSDKCompletionTest#34](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_13.cs)]
     [!code-vb[VSSDKCompletionTest#34](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_13.vb)]

10. <xref:Microsoft.VisualStudio.TextManager.Interop.IVsExpansionClient.OnItemChosen%2A> メソッドを実装します。 展開を実際に挿入するヘルパーメソッドについては、後の手順で説明します。 @No__t_0 は、<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> から取得できる行と列の情報を提供します。

     [!code-csharp[VSSDKCompletionTest#35](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_14.cs)]
     [!code-vb[VSSDKCompletionTest#35](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_14.vb)]

11. 次のプライベートメソッドは、ショートカットまたはタイトルとパスに基づいて、コードスニペットを挿入します。 次に、スニペットを使用して <xref:Microsoft.VisualStudio.TextManager.Interop.IVsExpansion.InsertNamedExpansion%2A> メソッドを呼び出します。

     [!code-csharp[VSSDKCompletionTest#36](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_15.cs)]
     [!code-vb[VSSDKCompletionTest#36](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_15.vb)]

## <a name="build-and-test-code-snippet-expansion"></a>コードスニペットの展開のビルドとテスト
 プロジェクトでスニペットの展開が機能するかどうかをテストできます。

1. ソリューションをビルドします。 デバッガーでこのプロジェクトを実行すると、Visual Studio の2番目のインスタンスが開始されます。

2. テキストファイルを開き、テキストを入力します。

3. テキスト内の任意の場所を右クリックし、 **[スニペットの挿入]** をクリックします。

4. スニペットピッカー UI (**テスト置換フィールド**)」というポップアップが表示されます。 ポップアップをダブルクリックします。

     次のスニペットを挿入する必要があります。

    ```
    MessageBox.Show("first");
    MessageBox.Show("second");
    ```

     **Enter キーまた**は**Esc**キーは押さないでください。

5. Tab キーおよび**Shift** +**tab**キー**を押して**、"first" と "second" の間を切り替えます。

6. **Enter**キーまたは**Esc**キーを押して、挿入を受け入れます。

7. テキストの別の部分に「test」と入力し、 **tab**キーを押します。"Test" はコードスニペットのショートカットであるため、スニペットを再び挿入する必要があります。

## <a name="next-steps"></a>次のステップ
