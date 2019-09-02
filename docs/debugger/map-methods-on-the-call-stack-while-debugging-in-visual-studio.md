---
title: 呼び出し履歴のビジュアルマップを作成する |Microsoft Docs
ms.date: 11/26/2018
ms.topic: conceptual
f1_keywords:
- vs.progression.debugwithcodemaps
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- call stacks, code maps
- Call Stack window, mapping calls
- debugging [Visual Studio], diagramming the call stack
- call stacks, mapping
- Call Stack window, visualizing
- debugging code visually
- debugging [Visual Studio], mapping the call stack
- call stacks, visualizing
- debugging, code maps
- Call Stack window, tracing calls visually
- Call Stack window, show on code map
- debugging [Visual Studio], tracing the call stack visually
- debugging [Visual Studio], visualizing the call stack
ms.assetid: d6a72e5e-f88d-46fc-94a3-1789d34805ef
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 62fb77590a20b0e31648cab10f310851fd65820e
ms.sourcegitcommit: 44e9b1d9230fcbbd081ee81be9d4be8a485d8502
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2019
ms.locfileid: "70179995"
---
# <a name="create-a-visual-map-of-the-call-stack-while-debugging-c-visual-basic-c-javascript"></a>デバッグ中に呼び出し履歴のビジュアルマップを作成するC#(、Visual Basic C++、、JavaScript)

デバッグ中に呼び出し履歴を視覚的にトレースするためのコード マップを作成します。 コメントをマップに追加することで、バグを見つけることに重点を置いてコードの動作を追跡できます。

チュートリアルについては、次のビデオをご覧ください。[ビデオ:コードマップデバッガーの統合を使用して視覚的にデバッグする (Channel 9)](http://go.microsoft.com/fwlink/?LinkId=293418)

コードマップで使用できるコマンドとアクションの詳細については、「[コードマップの参照および再配置](../modeling/browse-and-rearrange-code-maps.md)」を参照してください。

>[!IMPORTANT]
>コードマップは[Visual Studio Enterprise エディション](https://visualstudio.microsoft.com/downloads)でのみ作成できます。

コードマップを簡単に見てみましょう。

 ![コードマップでの呼び出し履歴を使用したデバッグ](../debugger/media/debuggermap_overview.png "DebuggerMap_Overview")

## <a name="MapStack"></a>呼び出し履歴でマップを作成する

1. Visual Studio Enterprise C# C++Visual Basic、、、または JavaScript プロジェクトで、[デバッグ] [ > **デバッグの開始**] の順に選択するか、 **F5**キーを押して、デバッグを開始します。

1. アプリが中断モードになった後、または関数にステップインする場合は、[**コードマップ**の**デバッグ** > ] を選択するか、 **ctrl**+**Shift**+ **`** キーを押します。

   現在の呼び出し履歴は新しいコード マップ上にオレンジ色で表示されます。

   ![コードマップの呼び出し履歴を表示]する(../debugger/media/debuggermap_seeundocallstack.png "DebuggerMap_SeeUndoCallStack")

デバッグを続行すると、コードマップが自動的に更新されます。 マップ項目またはレイアウトを変更しても、コードには影響しません。 マップでの名前変更、移動、削除は自由に行うことができます。

項目に関する詳細情報を取得するには、項目の上にマウスポインターを移動し、項目のツールヒントを確認します。 また、ツールバーの **[凡例]** を選択すると、各アイコンの意味を知ることができます。

![コードマップの凡例](../debugger/media/debuggermap_showlegend.png "コードマップの凡例")

>[!NOTE]
>コードマップの上部にある**古いバージョンのコードに基づい**ている可能性のあるメッセージは、マップを最後に更新した後にコードが変更された可能性があることを意味します。 たとえば、マップ上の呼び出しがコードに存在しなくなった可能性があります。 メッセージを閉じてから、マップを再び更新する前にソリューションをリビルドしてみます。

## <a name="map-external-code"></a>外部コードのマップ

既定では、ユーザー自身のコードだけがマップに表示されます。 マップ上の外部コードを表示するには、次のようにします。

- **[呼び出し履歴]** ウィンドウを右クリックし、 **[外部コードの表示]** を選択します。

  ![[呼び出し履歴] ウィンドウを使用して外部コードを表示する](../debugger/media/debuggermap_callstackmenu.png "DebuggerMap_CallStackMenu")
- または、[Visual Studio**ツール**で**マイコードのみを有効にする**] (または **[デバッグ]** ) >**オプション** > の **[デバッグ]** を選択解除します。

  [![オプション] ダイアログボックスを使用して外部コードを表示する](../debugger/media/debuggermap_debugoptions.png "DebuggerMap_DebugOptions")

## <a name="control-the-maps-layout"></a>マップのレイアウトを制御する

マップのレイアウトを変更しても、コードには影響しません。

マップのレイアウトを制御するには、マップのツールバーで **[レイアウト]** メニューを選択します。

**[レイアウト]** メニューでは、次のことができます。

- 既定のレイアウトを変更します。
- [**デバッグ時に自動的にレイアウト**を解除する] をオフにして、マップの並べ替えを自動的に停止します。
- **[インクリメンタルレイアウト]** をオフにして、項目を追加するときにできるだけ少ないマップを再配置します。

## <a name="MakeNotes"></a>コードに関するコメントを追加する

コメントを追加して、コード内で何が起こっているかを追跡できます。

コメントを追加するには、コードマップを右クリックし、[**新しいコメント**の**編集** > ] を選択して、コメントを入力します。

コメントに新しい行を追加するには、 **Shift**+キーを押しながら**enter**キーを押します。

 ![コードマップの呼び出し履歴にコメントを追加する](../debugger/media/debuggermap_addcomment.png "DebuggerMap_AddComment")

## <a name="UpdateMap"></a>次の呼び出し履歴でマップを更新する

アプリを次のブレークポイントに対して実行するか、関数にステップインすると、マップに新しい呼び出し履歴が自動的に追加されます。

![次の呼び出し履歴でコードマップを更新](../debugger/media/debuggermap_addclearcallstack.png "DebuggerMap_AddClearCallStack")

マップで新しい呼び出し履歴が自動的に追加されない![]ようにするには、[コードマップの呼び出し履歴を自動的に表示する] を選択します。コードマップのツールバーに自動的にコードマップの呼び出し履歴が(../debugger/media/debuggermap_automaticupdateicon.gif "表示")されます。 マップは、引き続き既存の呼び出し履歴を強調表示します。 マップを現在の呼び出し履歴を手動で追加するには、キーを押して**Ctrl**+**Shift**+ **`** します。

## <a name="AddRelatedCode"></a>関連するコードをマップに追加する

マップを作成したので、またC#は Visual Basic では、フィールド、プロパティ、その他のメソッドなどの項目を追加して、コード内で何が起こっているかを追跡できます。

コード内のメソッドの定義に進むには、マップ内のメソッドをダブルクリックするか、またはそのメソッドを選択して**F12**キーを押すか、右クリックして **[定義へのジャンプ]** を選択します。

![コードマップのメソッドのコード定義へのジャンプ](../debugger/media/debuggermap_gotocodedefinition.png "DebuggerMap_GoToCodeDefinition")

追跡する項目をマップに追加するには、メソッドを右クリックして、追跡する項目を選択します。追加された最新の項目は緑色で表示されます。

![呼び出し履歴コードマップのメソッドに関連するフィールド](../debugger/media/debuggermap_showedfields.png "DebuggerMap_ShowedFields")

>[!NOTE]
>既定では、マップに項目を追加すると、クラス、名前空間、アセンブリなどの親グループのノードも追加されます。 この機能をオンまたはオフにするには、コードマップツールバーの **[親を含める]** ボタンを選択するか、 **Ctrl**キーを押しながら項目を追加します。

![呼び出し履歴コードマップのメソッドにフィールドを表示する](../debugger/media/debuggermap_showfields.png "DebuggerMap_ShowFields")

コードのさらに多くの項目を表示するには、マップの作成を続けます。

 ![フィールドを使用するメソッドの参照: 呼び出し履歴コードマップ](../debugger/media/debuggermap_findallreferences.png "DebuggerMap_FindAllReferences")

 ![呼び出し履歴コードマップのフィールドを使用するメソッド](../debugger/media/debuggermap_foundallreferences.png "DebuggerMap_FoundAllReferences")

## <a name="FindBugs"></a>マップを使用してバグを見つける
 コードの視覚化はバグをよりすばやく見つけるために役立ちます。 たとえば、描画アプリのバグを調査しているとします。 直線を描画して元に戻そうとしても、別の直線を描画するまで何も起こりません。

 そのため、`clear`、`undo`、および `Repaint` メソッドにブレークポイントを設定し、デバッグを開始して、次のようなマップを作成します。

 ![別の呼び出し履歴をコードマップに追加する](../debugger/media/debuggermap_addpaintobjectcallstack.png "DebuggerMap_AddPaintObjectCallStack")

 マップ上のすべてのユーザー ジェスチャーが、`Repaint` を除いて、`undo` を呼び出していることがわかります。 これが原因で `undo` がすぐに動作しない可能性があります。

 バグを修正し、アプリの実行を続行すると、マップはから`undo`に`Repaint`新しい呼び出しを追加します。

 ![コードマップの呼び出し履歴に新しいメソッド呼び出しを追加し]ます(../debugger/media/debuggermap_addnewcallforrepaint.png "DebuggerMap_AddNewCallForRepaint")

## <a name="share-the-map-with-others"></a>他のユーザーとマップを共有する

マップをエクスポートし、Microsoft Outlook を使用して他のユーザーに送信し、ソリューションに保存して、バージョン管理にチェックインすることができます。

マップを共有または保存するには、コードマップツールバーの **[共有]** を使用します。

![呼び出し履歴コードマップを他のユーザーと共有]する(../debugger/media/debuggermap_sharewithothers.png "呼び出し履歴コードマップを他のユーザーと共有")する

## <a name="see-also"></a>関連項目
[ソリューション間の依存関係をマップする](../modeling/map-dependencies-across-your-solutions.md)

[コード マップを使用してアプリケーションをデバッグする](../modeling/use-code-maps-to-debug-your-applications.md)

[コード マップ アナライザーを使用して潜在的な問題を検索する](../modeling/find-potential-problems-using-code-map-analyzers.md)

[コード マップの参照および再配置](../modeling/browse-and-rearrange-code-maps.md)
