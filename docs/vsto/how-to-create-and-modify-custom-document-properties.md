---
title: '方法: 作成し、カスタム ドキュメント プロパティの変更'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- custom document properties
- documents [Office development in Visual Studio], properties
- document properties [Office development in Visual Studio]
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 7d6ef8332a5adc21e25f2a414c5b359e48cf1ba7
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62825792"
---
# <a name="how-to-create-and-modify-custom-document-properties"></a>方法: 作成し、カスタム ドキュメント プロパティの変更
  上記の Microsoft Office アプリケーションは、ドキュメントで保存される組み込みのプロパティを提供します。 さらに、ドキュメントで保存する追加情報がある場合は、カスタム ドキュメント プロパティを作成し、変更することができます。

 [!INCLUDE[appliesto_docprops](../vsto/includes/appliesto-docprops-md.md)]

 カスタム プロパティを操作するには、ドキュメントの CustomDocumentProperties プロパティを使用します。 たとえば、Microsoft Office Excel のドキュメント レベルのプロジェクトでは、 <xref:Microsoft.Office.Tools.Excel.Workbook.CustomDocumentProperties%2A> クラスの `ThisWorkbook` プロパティを使用します。 Excel の VSTO アドイン プロジェクトでは、 <xref:Microsoft.Office.Interop.Excel._Workbook.CustomDocumentProperties%2A> オブジェクトの <xref:Microsoft.Office.Interop.Excel.Workbook> プロパティを使用します。 これらのプロパティは、 <xref:Microsoft.Office.Core.DocumentProperties> オブジェクトのコレクションである <xref:Microsoft.Office.Core.DocumentProperty> オブジェクトを返します。 このコレクションの `Item` プロパティを使用すると、名前またはコレクション内のインデックスに基づいて特定のプロパティを取得できます。

 次の例は、Excel のドキュメント レベルのカスタマイズでカスタム プロパティを追加し、値を割り当てる方法を示します。

## <a name="example"></a>例
 [!code-vb[Trin_VstcoreProgramming#6](../vsto/codesnippet/VisualBasic/Trin_VstcoreProgrammingExcelVB/ThisWorkbook.vb#6)]
 [!code-csharp[Trin_VstcoreProgramming#6](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingExcelCS/ThisWorkbook.cs#6)]

## <a name="robust-programming"></a>信頼性の高いプログラミング
 未定義の `Value` プロパティにアクセスしようとすると、例外が発生します。

## <a name="see-also"></a>関連項目
- [VSTO アドインをプログラミングします。](../vsto/programming-vsto-add-ins.md)
- [ドキュメント レベルのカスタマイズのプログラミング](../vsto/programming-document-level-customizations.md)
- [方法: ドキュメント プロパティの読み書き](../vsto/how-to-read-from-and-write-to-document-properties.md)
