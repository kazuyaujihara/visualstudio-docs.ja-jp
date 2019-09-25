---
title: '方法: プログラムによって非表示モードで Word のダイアログボックスを使用する'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- hidden dialog boxes
- Word [Office development in Visual Studio], dialog boxes
- dialog boxes, hidden mode in Word
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: e32c97069e3400b447f8756f9638c9d88d38d99a
ms.sourcegitcommit: e98db44f3a33529b0ba188d24390efd09e548191
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2019
ms.locfileid: "71255846"
---
# <a name="how-to-programmatically-use-word-dialog-boxes-in-hidden-mode"></a>方法: プログラムによって非表示モードで Word のダイアログボックスを使用する
  1つのメソッド呼び出しで複雑な操作を実行するには、Microsoft Office Word の組み込みダイアログボックスをユーザーに表示せずに呼び出します。 これを行うには、 <xref:Microsoft.Office.Interop.Word.Dialog.Execute%2A> <xref:Microsoft.Office.Interop.Word.Dialog.Display%2A>メソッドを呼び出さ<xref:Microsoft.Office.Interop.Word.Dialog>ずにオブジェクトのメソッドを使用します。

 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]

## <a name="examples"></a>使用例
 次のコード例では、 **[ページ設定]** ダイアログボックスを非表示モードで使用して、ユーザー入力なしで複数のページ設定プロパティを設定する方法を示します。 この例では<xref:Microsoft.Office.Interop.Word.Dialog> 、オブジェクトを使用して、カスタムページサイズを構成します。 ページ設定の特定の設定 (上余白、下余白など) は、 <xref:Microsoft.Office.Interop.Word.Dialog>オブジェクトの遅延バインディングプロパティとして使用できます。 これらのプロパティは、実行時に Word によって動的に作成されます。

 次の例は、Visual Basic プロジェクトでこのタスクを実行する方法を示します、 **Option Strict**オフ、および Visual C# プロジェクトを対象とするが、[!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)]します。 これらのプロジェクトでは、Visual Basic および Visual C# コンパイラで遅延バインディングの機能を使用できます。 この例を使用するに`ThisDocument`は、プロジェクトのクラスまたは`ThisAddIn`クラスから実行します。

 [!code-vb[Trin_VstcoreWordAutomation#123](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#123)]
 [!code-csharp[Trin_VstcoreWordAutomation#123](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#123)]

 次の例は、 **Option Strict**がオンになっている Visual Basic プロジェクトでこのタスクを実行する方法を示しています。 これらのプロジェクトでは、遅延バインディングプロパティにアクセスするためにリフレクションを使用する必要があります。 この例を使用するに`ThisDocument`は、プロジェクトのクラスまたは`ThisAddIn`クラスから実行します。

 [!code-vb[Trin_VstcoreWordAutomation#104](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#104)]

## <a name="see-also"></a>関連項目
- [方法: Word の組み込みダイアログボックスをプログラムで使用する](../vsto/how-to-programmatically-use-built-in-dialog-boxes-in-word.md)
- [Word オブジェクトモデルの概要](../vsto/word-object-model-overview.md)
- [Office ソリューションの遅延バインディング](../vsto/late-binding-in-office-solutions.md)
- [リフレクション (C#)](/dotnet/csharp/programming-guide/concepts/reflection)
- [リフレクション (Visual Basic)](/dotnet/visual-basic/programming-guide/concepts/reflection)
