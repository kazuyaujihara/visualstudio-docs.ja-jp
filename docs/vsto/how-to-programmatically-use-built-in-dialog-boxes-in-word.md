---
title: '方法: プログラムによって Word の組み込みダイアログ ボックスを使用して、'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Word [Office development in Visual Studio], dialog boxes
- dialog boxes, Word
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: f8037e4d91aa7706c7ffd7b9f32778dfeac79488
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56644940"
---
# <a name="how-to-programmatically-use-built-in-dialog-boxes-in-word"></a>方法: プログラムによって Word の組み込みダイアログ ボックスを使用して、
  Microsoft Office Word を使用する場合は、ユーザーの入力 ダイアログ ボックスを表示する必要がある生じるです。 公開されている Word では、組み込みダイアログ ボックスを使用する方法をする可能性がありますも作成できますが、独自、<xref:Microsoft.Office.Interop.Word.Dialogs>のコレクション、<xref:Microsoft.Office.Interop.Word.Application>オブジェクト。 これにより、200 以上の列挙体で表される組み込みダイアログ ボックスにアクセスすることができます。

 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]

## <a name="display-dialog-boxes"></a>ダイアログ ボックスを表示します。
 ダイアログ ボックスを表示するには、値のいずれかを使用、<xref:Microsoft.Office.Interop.Word.WdWordDialog>列挙体を作成する、<xref:Microsoft.Office.Interop.Word.Dialog>を表示する ダイアログ ボックスを表すオブジェクト。 次に呼び出す、<xref:Microsoft.Office.Interop.Word.Dialog.Show%2A>のメソッド、<xref:Microsoft.Office.Interop.Word.Dialog>オブジェクト。

 次のコード例は、表示する方法を示します、**ファイルを開く** ダイアログ ボックス。 この例を使用する実行から、`ThisDocument`または`ThisAddIn`プロジェクト内のクラス。

 [!code-vb[Trin_VstcoreWordAutomation#100](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#100)]
 [!code-csharp[Trin_VstcoreWordAutomation#100](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#100)]

### <a name="access-dialog-box-members-that-are-available-through-late-binding"></a>遅延バインディングで使用できるダイアログ ボックスのメンバーをへのアクセス
 いくつかのプロパティと Word のダイアログ ボックスのメソッドは、遅延バインディングを介してのみ使用可能なは。 Visual basic プロジェクト where **Option Strict**に、リフレクションを使用して、これらのメンバーにアクセスする必要があります。 詳細については、[Office ソリューションの遅延バインディング](../vsto/late-binding-in-office-solutions.md)を参照してください。

 次のコード例は、使用する方法を示します、**名前**のプロパティ、**ファイルを開く** ダイアログ ボックスで、Visual Basic プロジェクト where **Option Strict**オフまたは Visual C# では、プロジェクトの対象とする、[!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)]または[!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]します。 この例を使用する実行から、`ThisDocument`または`ThisAddIn`プロジェクト内のクラス。

 [!code-vb[Trin_VstcoreWordAutomation#122](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#122)]
 [!code-csharp[Trin_VstcoreWordAutomation#122](../vsto/codesnippet/CSharp/Trin_VstcoreWordAutomationCS/ThisDocument.cs#122)]

 次のコード例は、リフレクションを使用してアクセスする方法を示します、**名前**のプロパティ、**ファイルを開く** ダイアログ ボックスで、Visual Basic プロジェクト where **Option Strict**はします。 この例を使用する実行から、`ThisDocument`または`ThisAddIn`プロジェクト内のクラス。

 [!code-vb[Trin_VstcoreWordAutomation#102](../vsto/codesnippet/VisualBasic/Trin_VstcoreWordAutomationVB/ThisDocument.vb#102)]

## <a name="see-also"></a>関連項目
- [方法: プログラムによって Word のダイアログ ボックスを非表示モードでを使用して、](../vsto/how-to-programmatically-use-word-dialog-boxes-in-hidden-mode.md)
- [Word オブジェクト モデルの概要](../vsto/word-object-model-overview.md)
- [Office ソリューションの省略可能なパラメーター](../vsto/optional-parameters-in-office-solutions.md)
- [Option strict ステートメント](/dotnet/visual-basic/language-reference/statements/option-strict-statement)
- [リフレクション (C#)](/dotnet/csharp/programming-guide/concepts/reflection)
- [リフレクション (Visual Basic)](/dotnet/visual-basic/programming-guide/concepts/reflection)
