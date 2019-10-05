---
title: '方法: ListObject コントロールのサイズ変更'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- controls [Office development in Visual Studio], resizing
- ListObject control, resizing
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: d7dac99088dc57b538f7a26ffbd0bdc0e3e05b5a
ms.sourcegitcommit: e98db44f3a33529b0ba188d24390efd09e548191
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2019
ms.locfileid: "71252126"
---
# <a name="how-to-resize-listobject-controls"></a>方法: ListObject コントロールのサイズ変更
  <xref:Microsoft.Office.Tools.Excel.ListObject> コントロールのサイズは Microsoft Office Excel ブックにコントロールを追加するときに設定しますが、後でサイズを変更することもできます。 たとえば、2 列のリストを 3 列のリストに変更できます。

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

 ドキュメント レベルのプロジェクトでは、デザイン時または実行時に <xref:Microsoft.Office.Tools.Excel.ListObject> コントロールのサイズを変更できます。 VSTO アドインプロジェクト<xref:Microsoft.Office.Tools.Excel.ListObject>では、実行時にコントロールのサイズを変更できます。

 このトピックでは、次のタスクについて説明します。

- [デザイン時に ListObject コントロールのサイズを変更する](#designtime)

- [実行時にドキュメントレベルのプロジェクトの ListObject コントロールのサイズを変更する](#runtimedoclevel)

- [実行時に VSTO アドインプロジェクトの ListObject コントロールのサイズを変更する](#runtimeaddin)

  <xref:Microsoft.Office.Tools.Excel.ListObject>コントロールの詳細については、「 [ListObject コントロール](../vsto/listobject-control.md)」を参照してください。

  ![ビデオへのリンク](../vsto/media/playvideo.gif "ビデオへのリンク")関連のビデオデモについて[は、操作方法を参照してください。実行時にデータバインドリストオブジェクトに列を追加しますか?](http://go.microsoft.com/fwlink/?LinkID=130318).

## <a name="designtime"></a>デザイン時に ListObject コントロールのサイズを変更する
 リストのサイズを変更するには、サイズ変更ハンドルのいずれかをクリックしてドラッグでき、また **[リストのサイズ変更]** ダイアログ ボックスでそのサイズを再定義することもできます。

### <a name="to-resize-a-list-by-using-the-resize-list-dialog-box"></a>[リストのサイズ変更] ダイアログ ボックスを使用してリストのサイズを変更するには

1. <xref:Microsoft.Office.Tools.Excel.ListObject>テーブル内の任意の場所をクリックします。 リボンの [**テーブルツール** > の**デザイン**] タブが表示されます。

2. プロパティ セクションで、**テーブルのサイズ変更** をクリックします。

    ![VSTO_ResizeTable](../vsto/media/vsto-resizetable.png)

3. テーブルの新しいデータ範囲を選択します。

4. **[OK]** をクリックします。

## <a name="runtimedoclevel"></a>実行時にドキュメントレベルのプロジェクトの ListObject コントロールのサイズを変更する
 <xref:Microsoft.Office.Tools.Excel.ListObject> コントロールのサイズは、実行時に <xref:Microsoft.Office.Tools.Excel.ListObject.Resize%2A> メソッドを使用して変更できます。 このメソッドは、 <xref:Microsoft.Office.Tools.Excel.ListObject> コントロールをワークシート上の新しい位置に移動するためには使用できません。 ヘッダーは同じ行のままである必要があり、サイズを変更した <xref:Microsoft.Office.Tools.Excel.ListObject> コントロールは元のリスト オブジェクトに重なる必要があります。 サイズ変更した <xref:Microsoft.Office.Tools.Excel.ListObject> コントロールには、ヘッダー行および少なくとも 1 つのデータ行が含まれている必要があります。

### <a name="to-resize-a-list-object-programmatically"></a>リスト オブジェクトのサイズをプログラムで変更するには

1. <xref:Microsoft.Office.Tools.Excel.ListObject> に、セル **A1** から **B3** にまたがる `Sheet1`コントロールを作成します。

     [!code-csharp[Trin_VstcoreHostControlsExcel#6](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#6)]
     [!code-vb[Trin_VstcoreHostControlsExcel#6](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet1.vb#6)]

2. リストのサイズをセル **A1** から **C5**までに変更します。

     [!code-csharp[Trin_VstcoreHostControlsExcel#7](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#7)]
     [!code-vb[Trin_VstcoreHostControlsExcel#7](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet1.vb#7)]

## <a name="runtimeaddin"></a>実行時に VSTO アドインプロジェクトの ListObject のサイズを変更する
 実行時に、任意の開いているワークシート上の <xref:Microsoft.Office.Tools.Excel.ListObject> コントロールのサイズを変更できます。 VSTO アドインを使用してワークシート<xref:Microsoft.Office.Tools.Excel.ListObject>にコントロールを追加する方法の詳細については、 [「」を参照してください。ListObject コントロールをワークシート](../vsto/how-to-add-listobject-controls-to-worksheets.md)に追加します。

### <a name="to-resize-a-list-object-programmatically"></a>リスト オブジェクトのサイズをプログラムで変更するには

1. <xref:Microsoft.Office.Tools.Excel.ListObject> に、セル **A1** から **B3** にまたがる `Sheet1`コントロールを作成します。

     [!code-csharp[Trin_Excel_Dynamic_Controls#12](../vsto/codesnippet/CSharp/Trin_Excel_Dynamic_Controls/ThisAddIn.cs#12)]
     [!code-vb[Trin_Excel_Dynamic_Controls#12](../vsto/codesnippet/VisualBasic/Trin_Excel_Dynamic_Controls/ThisAddIn.vb#12)]

2. リストのサイズをセル **A1** から **C5**までに変更します。

     [!code-csharp[Trin_Excel_Dynamic_Controls#13](../vsto/codesnippet/CSharp/Trin_Excel_Dynamic_Controls/ThisAddIn.cs#13)]
     [!code-vb[Trin_Excel_Dynamic_Controls#13](../vsto/codesnippet/VisualBasic/Trin_Excel_Dynamic_Controls/ThisAddIn.vb#13)]

## <a name="see-also"></a>関連項目
- [実行時に VSTO アドインの Word 文書と Excel ブックを拡張する](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)
- [Office ドキュメントのコントロール](../vsto/controls-on-office-documents.md)
- [実行時に Office ドキュメントにコントロールを追加する](../vsto/adding-controls-to-office-documents-at-run-time.md)
- [ホスト項目とホストコントロールの概要](../vsto/host-items-and-host-controls-overview.md)
- [拡張オブジェクトを使用した Excel の自動化](../vsto/automating-excel-by-using-extended-objects.md)
- [ListObject コントロール](../vsto/listobject-control.md)
- [方法: ワークシートへの ListObject コントロールの追加](../vsto/how-to-add-listobject-controls-to-worksheets.md)
- [方法: ブックマークコントロールのサイズ変更](../vsto/how-to-resize-bookmark-controls.md)
- [方法: NamedRange コントロールのサイズ変更](../vsto/how-to-resize-namedrange-controls.md)
