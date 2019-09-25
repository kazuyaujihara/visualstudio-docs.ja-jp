---
title: '方法: ListObject 列をデータにマップする'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data [Office development in Visual Studio], mapping to ListObject column
- ListObject control, mapping data
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 6e0056687e8ca28af4dbc9032d7bbee0cf976378
ms.sourcegitcommit: e98db44f3a33529b0ba188d24390efd09e548191
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2019
ms.locfileid: "71253681"
---
# <a name="how-to-map-listobject-columns-to-data"></a>方法: ListObject 列をデータにマップする
  <xref:Microsoft.Office.Tools.Excel.ListObject> コントロールを <xref:System.Data.DataTable>にバインドするとき、リストの中のすべての列を表示しなくてもよい場合や、データにバインドされていない特定の列が含まれている場合があります。 <xref:Microsoft.Office.Tools.Excel.ListObject> メソッドを呼び出すと、 <xref:Microsoft.Office.Tools.Excel.ListObject.SetDataBinding%2A> に表示する列をマップできます。

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

 ![ビデオへのリンク](../vsto/media/playvideo.gif "ビデオへのリンク")関連のビデオデモについて[は、操作方法を参照してください。SharePoint リストに接続されている Excel でリストを作成しますか](http://go.microsoft.com/fwlink/?LinkID=130263)。

## <a name="map-columns"></a>マップ列

### <a name="to-map-a-data-table-to-columns-in-a-list"></a>データ テーブルをリスト内の列にマップするには

1. クラス レベルで <xref:System.Data.DataTable> を作成します。

     [!code-csharp[Trin_VstcoreHostControlsExcel#16](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet3.cs#16)]
     [!code-vb[Trin_VstcoreHostControlsExcel#16](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet3.vb#16)]

2. クラス (ドキュメントレベルのプロジェクトの`Startup`場合) または`ThisAddIn`クラス (VSTO アドインプロジェクトの場合) のイベントハンドラーにサンプルの列とデータを追加します。 `Sheet1`

     [!code-csharp[Trin_VstcoreHostControlsExcel#17](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet3.cs#17)]
     [!code-vb[Trin_VstcoreHostControlsExcel#17](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet3.vb#17)]

3. <xref:Microsoft.Office.Tools.Excel.ListObject.SetDataBinding%2A> メソッドを呼び出し、列名を表示順に渡します。 リストオブジェクトは新しく作成さ<xref:System.Data.DataTable>れたにバインドされますが、リストオブジェクト内の列の順序は、 <xref:System.Data.DataTable>に表示される順序とは異なります。

     [!code-csharp[Trin_VstcoreHostControlsExcel#18](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet3.cs#18)]
     [!code-vb[Trin_VstcoreHostControlsExcel#18](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet3.vb#18)]

## <a name="specify-unmapped-columns"></a>マップされていない列の指定
 列を <xref:System.Data.DataTable>にマップするときに空の文字列を渡して、特定の列をデータにバインドしないことも指定できます。 そのようにすると、データにバインドされない新しい列は <xref:Microsoft.Office.Tools.Excel.ListObject> コントロールに追加されます。

### <a name="to-specify-an-unmapped-column-when-mapping-listobject-columns"></a>ListObject 列をマップするときにマップしない列を指定するには

1. <xref:Microsoft.Office.Tools.Excel.ListObject.SetDataBinding%2A> メソッドを呼び出し、列名を表示順に渡します。 空の文字列を使用して、マップしない列を追加する位置を示します。この場合は、タイトル列と姓の列の間です。

     [!code-csharp[Trin_VstcoreHostControlsExcel#19](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet3.cs#19)]
     [!code-vb[Trin_VstcoreHostControlsExcel#19](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet3.vb#19)]

## <a name="compile-the-code"></a>コードのコンパイル
 このコード例では、このコードがあるワークシートに、 <xref:Microsoft.Office.Tools.Excel.ListObject> という名前の既存の `list1` があることを前提としています。

## <a name="see-also"></a>関連項目
- [実行時に VSTO アドインの Word 文書と Excel ブックを拡張する](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)
- [Office ドキュメントのコントロール](../vsto/controls-on-office-documents.md)
- [実行時に Office ドキュメントにコントロールを追加する](../vsto/adding-controls-to-office-documents-at-run-time.md)
- [方法: データを使用した ListObject コントロールの塗りつぶし](../vsto/how-to-fill-listobject-controls-with-data.md)
- [拡張オブジェクトを使用した Excel の自動化](../vsto/automating-excel-by-using-extended-objects.md)
- [ListObject コントロール](../vsto/listobject-control.md)
