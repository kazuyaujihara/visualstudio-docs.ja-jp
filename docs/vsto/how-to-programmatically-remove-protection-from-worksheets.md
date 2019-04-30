---
title: '方法: プログラムによってワークシートの保護を解除します。'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- worksheets, unprotecting
- documents [Office development in Visual Studio], document protection
- document protection, removing from worksheets
- Unprotect method
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: ccf7de70c3ef741119ec22f8fa9bc76868a47030
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62955956"
---
# <a name="how-to-programmatically-remove-protection-from-worksheets"></a>方法: プログラムによってワークシートの保護を解除します。
  プログラムを使用して、Microsoft Office Excel ワークシートから保護を削除できます。

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

 次の例では、変数 `getPasswordFromUser`を使用して、ユーザーから取得したパスワードを格納します。

## <a name="to-unprotect-a-worksheet-in-a-document-level-customization"></a>ドキュメント レベルのカスタマイズでワークシートの保護を解除するには

1. 呼び出す、<xref:Microsoft.Office.Tools.Excel.Worksheet.Unprotect%2A>メソッドのワークシートと必要な場合、そのパスワードを渡します。 この例では、 `Sheet1`という名前のワークシートを操作していると仮定します。

     [!code-csharp[Trin_VstcoreExcelAutomation#28](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#28)]
     [!code-vb[Trin_VstcoreExcelAutomation#28](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#28)]

## <a name="to-unprotect-a-worksheet-in-a-vsto-add-in"></a>VSTO アドインでワークシートの保護を解除するには

1. 呼び出す、<xref:Microsoft.Office.Interop.Excel._Worksheet.Unprotect%2A>メソッドのアクティブなワークシートと必要な場合、そのパスワードを渡します。

     [!code-csharp[Trin_VstcoreExcelAutomationAddIn#18](../vsto/codesnippet/CSharp/trin_vstcoreexcelautomationaddin/ThisAddIn.cs#18)]
     [!code-vb[Trin_VstcoreExcelAutomationAddIn#18](../vsto/codesnippet/VisualBasic/trin_vstcoreexcelautomationaddin/ThisAddIn.vb#18)]

## <a name="see-also"></a>関連項目
- [ワークシートを操作します。](../vsto/working-with-worksheets.md)
- [方法: プログラムによってワークシートを保護します。](../vsto/how-to-programmatically-protect-worksheets.md)
- [方法: プログラムによってブックを保護します。](../vsto/how-to-programmatically-protect-workbooks.md)
- [方法: プログラムによってワークシートを非表示します。](../vsto/how-to-programmatically-hide-worksheets.md)
- [Office プロジェクト内のオブジェクトへのグローバル アクセス](../vsto/global-access-to-objects-in-office-projects.md)
