---
title: '方法: プログラムによって Visio 図面を閉じる'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], closing Visio documents
- Visio [Office development in Visual Studio], closing Visio documents
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 474efcb62cf7cadd9de82e41ff2ad36cebc046cb
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "60067656"
---
# <a name="how-to-programmatically-close-visio-documents"></a>方法: プログラムによって Visio 図面を閉じる
  `Microsoft.Office.Interop.Visio.Document.Close` メソッドを使用すると、アクティブな Microsoft Office Visio 図面を閉じることができます。

 このメソッドの詳細については、 [Microsoft.Office.Interop.Visio.Document.Close](/office/vba/api/Visio.Document.Close) メソッドの VBA リファレンス ドキュメントを参照してください。

## <a name="close-the-active-document"></a>アクティブなドキュメントを閉じる

### <a name="to-close-the-active-document"></a>作業中のドキュメントを閉じるには

- `Microsoft.Office.Interop.Visio.Document.Close` メソッドを呼び出して、作業中のドキュメントを閉じます。

     次のコード例を使用するで実行、 `ThisAddIn` Visio 用の VSTO アドイン プロジェクト内のクラス。

     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#7](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#7)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#7](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#7)]

## <a name="see-also"></a>関連項目
- [Visio ソリューション](../vsto/visio-solutions.md)
- [Visio オブジェクト モデルの概要](../vsto/visio-object-model-overview.md)
- [方法: プログラムによって新しい Visio 図面を作成します。](../vsto/how-to-programmatically-create-new-visio-documents.md)
- [方法: プログラムによって Visio 図面を開く](../vsto/how-to-programmatically-open-visio-documents.md)
- [方法: プログラムによって Visio 図面を保存します。](../vsto/how-to-programmatically-save-visio-documents.md)
- [方法: プログラムによって Visio 図面を印刷します。](../vsto/how-to-programmatically-print-visio-documents.md)
