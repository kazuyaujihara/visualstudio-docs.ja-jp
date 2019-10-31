---
title: 'チュートリアル: カスタムエディターへの機能の追加 |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], custom - add features
ms.assetid: bfe083b6-3e35-4b9c-ad4f-b30b9ff412a5
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: c5ea1c1bfa34399f4a2428aec2f51f97c9884216
ms.sourcegitcommit: 40bd5b27f247a07c2e2514acb293b23d6ce03c29
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2019
ms.locfileid: "73189064"
---
# <a name="walkthrough-add-features-to-a-custom-editor"></a>チュートリアル: カスタムエディターへの機能の追加
カスタムエディターを作成したら、それにさらに機能を追加できます。

## <a name="to-create-an-editor-for-a-vspackage"></a>VSPackage のエディターを作成するには

1. Visual Studio パッケージプロジェクトテンプレートを使用して、カスタムエディターを作成します。

     詳細については、「[チュートリアル: カスタムエディターを作成する](../extensibility/walkthrough-creating-a-custom-editor.md)」を参照してください。

2. エディターで1つのビューまたは複数のビューをサポートするかどうかを決定します。

     **[新しいウィンドウ]** コマンドをサポートするエディター、またはフォームビューとコードビューがあるエディターでは、個別のドキュメントデータオブジェクトとドキュメントビューオブジェクトが必要です。 1つのビューだけをサポートするエディターでは、ドキュメントデータオブジェクトとドキュメントビューオブジェクトを同じオブジェクトに実装できます。

     複数のビューの例については、「[複数のドキュメントビューのサポート](../extensibility/supporting-multiple-document-views.md)」を参照してください。

3. <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory> インターフェイスを設定して、エディターファクトリを実装します。

     詳細については、「[エディターファクトリ](../extensibility/editor-factories.md)」を参照してください。

4. エディターでドキュメントビューのオブジェクトウィンドウを管理するために、埋め込み先でのアクティブ化または簡略化された埋め込みを使用するかどうかを決定します。

     簡略化された埋め込みエディターウィンドウは標準のドキュメントビューをホストし、インプレースアクティベーションエディターウィンドウは ActiveX コントロールまたはその他のアクティブなオブジェクトをドキュメントビューとしてホストします。 詳細については、「簡略化された[埋め込み](../extensibility/simplified-embedding.md)と[インプレースアクティブ化](../extensibility/in-place-activation.md)」を参照してください。

5. コマンドを処理するための <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> インターフェイスを実装します。

6. ドキュメントの永続化と外部ファイルの変更への応答を提供します。

    1. ファイルを永続化するには、<xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2> を実装し、エディターのドキュメントデータオブジェクトに <xref:Microsoft.VisualStudio.Shell.Interop.IPersistFileFormat> します。

    2. 外部ファイルの変更に応答するには、<xref:Microsoft.VisualStudio.Shell.Interop.IVsFileChangeEx> を実装し、エディターのドキュメントデータオブジェクトに <xref:Microsoft.VisualStudio.Shell.Interop.IVsDocDataFileChangeControl> します。

        > [!NOTE]
        > `IVsFileChangeEx`へのポインターを取得するには、<xref:Microsoft.VisualStudio.Shell.Interop.SVsFileChangeEx> で `QueryService` を呼び出します。

7. ドキュメントの編集イベントをソースコード管理で調整します。 この場合は、以下の手順に従ってください。

    1. <xref:Microsoft.VisualStudio.Shell.Interop.SVsQueryEditQuerySave>で `QueryService` を呼び出すことによって `IVsQueryEditQuerySave2` へのポインターを取得します。

    2. 最初の編集イベントが発生したときに、<xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QueryEditFiles%2A> メソッドを呼び出します。

         このメソッドは、ファイルがまだチェックアウトされていない場合にチェックアウトするようにユーザーに求めます。"ファイルがチェックアウトされていません" 状態を処理して、エラーを回避してください。

    3. 同様に、ファイルを保存する前に、<xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2.QuerySaveFile%2A> メソッドを呼び出します。

         このメソッドは、ファイルが保存されていない場合、または最後の保存以降に変更された場合に、ファイルを保存するようにユーザーに要求します。

8. **[プロパティ]** ウィンドウを有効にすると、エディターで選択したテキストのプロパティを表示できます。 この場合は、以下の手順に従ってください。

    1. テキスト選択が変更されるたびに <xref:Microsoft.VisualStudio.Shell.Interop.ITrackSelection.OnSelectChange%2A> を呼び出し、<xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer>の実装に渡します。

    2. <xref:Microsoft.VisualStudio.Shell.Interop.ITrackSelection>へのポインターを取得するには、<xref:Microsoft.VisualStudio.Shell.Interop.STrackSelection> サービスで `QueryService` を呼び出します。

9. ユーザーがエディターと**ツールボックス**の間、または外部エディター (Microsoft Word など) と**ツールボックス**の間で項目をドラッグアンドドロップできるようにします。 この場合は、以下の手順に従ってください。

    1. エディターがドロップ先であることを IDE に警告するには、エディターに `IDropTarget` を実装します。

    2. エディターが**ツールボックス**内の項目を有効または無効にできるように、ビューに <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolboxUser> インターフェイスを実装します。

    3. <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.ResetDefaults%2A> を実装し、<xref:Microsoft.VisualStudio.Shell.Interop.SVsToolbox> サービスで `QueryService` を呼び出して、<xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox2> および <xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox3> インターフェイスへのポインターを取得します。

         これらの手順により、VSPackage で**ツールボックス**に新しい項目を追加できるようになります。

10. エディターに他のオプション機能を使用するかどうかを決定します。

    - エディターで検索と置換のコマンドをサポートするには、<xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget>を実装します。

    - エディターでドキュメントアウトラインツールウィンドウを使用する場合は、`IVsDocOutlineProvider`を実装します。

    - エディターでステータスバーを使用する場合は、<xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser> を実装し、<xref:Microsoft.VisualStudio.Shell.Interop.SVsStatusbar> の `QueryService` を呼び出して、`IVsStatusBar`へのポインターを取得します。

         たとえば、エディターでは、行または列の情報、選択モード (ストリーム/ボックス)、および挿入モード (insert/上書き) を表示できます。

    - エディターで `Undo` コマンドをサポートする場合は、OLE 元に戻すマネージャーモデルを使用することをお勧めします。 別の方法として、エディターで `Undo` コマンドを直接処理することもできます。

11. VSPackage の Guid、メニュー、エディター、およびその他の機能を含むレジストリ情報を作成します。

     次に、エディターを適切に登録する方法を示すために、 *.rgs*ファイルスクリプトに記述するコードの一般的な例を示します。

    ```csharp
    NoRemove Editors
    {
          ForceRemove {...guidEditor...} = s 'RTF Editor'
          {
             val Package = s '{...guidVsPackage...}'
             ForceRemove Extensions
             {
                val rtf = d 50
             }
          }
    }
    NoRemove Menus
    {
          val {...guidVsPackage...} = s ',203,11'
    }
    ```

12. 状況依存のヘルプサポートを実装します。

     この手順では、エディターの項目に対して F1 ヘルプとダイナミックヘルプウィンドウのサポートを提供できます。 詳細については、「[方法: エディターのコンテキストを指定する](/visualstudio/extensibility/how-to-provide-context-for-editors?view=vs-2015)」を参照してください。

13. `IDispatch` インターフェイスを実装することによって、エディターからオートメーションオブジェクトモデルを公開します。

     詳細については、「 [Contributing to the Automation Model](../extensibility/internals/contributing-to-the-automation-model.md)」を参照してください。

## <a name="robust-programming"></a>信頼性の高いプログラミング

- IDE が <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> メソッドを呼び出すと、エディターインスタンスが作成されます。 エディターが複数のビューをサポートしている場合、`CreateEditorInstance` はドキュメントデータとドキュメントビューオブジェクトの両方を作成します。 ドキュメントデータオブジェクトが既に開いている場合は、null 以外の `punkDocDataExisting` 値が `IVsEditorFactory::CreateEditorInstance`に渡されます。 エディターファクトリの実装では、既存のドキュメントデータオブジェクトに適切なインターフェイスを照会することによって互換性があるかどうかを判断する必要があります。 詳細については、「[複数のドキュメントビューのサポート](../extensibility/supporting-multiple-document-views.md)」を参照してください。

- 簡略化された埋め込み方法を使用する場合は、<xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane> インターフェイスを実装します。

- インプレースライセンス認証を使用する場合は、次のインターフェイスを実装します。

   <xref:Microsoft.VisualStudio.OLE.Interop.IOleObject>

   <xref:Microsoft.VisualStudio.OLE.Interop.IOleInPlaceActiveObject>

   <xref:Microsoft.VisualStudio.Shell.Interop.IOleInPlaceComponent>

  > [!NOTE]
  > `IOleInPlaceComponent` インターフェイスは、OLE 2 メニューのマージを避けるために使用されます。

   `IOleCommandTarget` の実装では、**切り取り**、**コピー**、**貼り付け**などのコマンドが処理されます。 `IOleCommandTarget`を実装する場合は、エディターが独自のコマンドメニュー構造を定義するために独自の*vsct*ファイルを必要とするか、[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]で定義された標準コマンドを実装できるかどうかを決定します。 通常、エディターでは、IDE のメニューを使用して拡張し、独自のツールバーを定義します。 ただし、IDE の標準コマンドセットを使用するだけでなく、エディターで独自の特定のコマンドを定義する必要がある場合もあります。 エディターは、使用する標準コマンドを宣言してから、新しいコマンド、コンテキストメニュー、トップレベルメニュー、ツールバーを*vsct*ファイルで定義する必要があります。 インプレースアクティブ化エディターを作成する場合は、<xref:Microsoft.VisualStudio.Shell.Interop.IOleInPlaceComponent> を実装し、OLE 2 メニューのマージを使用するのではなく、 *vsct*ファイルでエディターのメニューとツールバーを定義します。

- UI でメニューコマンド crowding を回避するには、新しいコマンドをにせよする前に、IDE の既存のコマンドを使用する必要があります。 共有コマンドは、 *Sharedcmddef. vsct*および*shellcmddef. vsct*で定義されています。 これらのファイルは、[!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] インストールの VisualStudioIntegration\Common\Inc サブディレクトリに既定でインストールされます。

- `ISelectionContainer` は、単一選択と複数選択の両方を表すことができます。 選択した各オブジェクトは、`IDispatch` オブジェクトとして実装されます。

- IDE では、<xref:Microsoft.VisualStudio.Shell.Interop.ILocalRegistry2.CreateInstance%2A> からアクセスできるサービスとして、または <xref:Microsoft.VisualStudio.Shell.Interop.ILocalRegistry2.CreateInstance%2A>を通じてインスタンス化できるオブジェクトとして `IOleUndoManager` が実装されています。 エディターは、`Undo` アクションごとに `IOleUndoUnit` インターフェイスを実装します。

- カスタムエディターは、次の2つの場所でオートメーションオブジェクトを公開できます。

  - `Document.Object`

  - `Window.Object`

## <a name="see-also"></a>関連項目

- [オートメーションモデルに貢献する](../extensibility/internals/contributing-to-the-automation-model.md)