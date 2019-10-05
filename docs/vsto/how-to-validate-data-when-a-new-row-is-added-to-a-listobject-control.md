---
title: ListObject コントロールに新しい行が追加されたときにデータを検証する
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- controls [Office development in Visual Studio], validating data
- ListObject control, new row
- ListObject control, validating data
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: f65bbc374c1d0ec2a940ff98fcc6f04e5391b2db
ms.sourcegitcommit: e98db44f3a33529b0ba188d24390efd09e548191
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2019
ms.locfileid: "71255676"
---
# <a name="how-to-validate-data-when-a-new-row-is-added-to-a-listobject-control"></a>方法: ListObject コントロールに新しい行が追加されたときにデータを検証する
  ユーザーはデータにバインドされている <xref:Microsoft.Office.Tools.Excel.ListObject> コントロールに新しい行を追加できます。 変更をデータ ソースにコミットする前に、ユーザーのデータを検証できます。

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

## <a name="data-validation"></a>データの検証
 データにバインドされている <xref:Microsoft.Office.Tools.Excel.ListObject> に行が追加されるたびに、 <xref:Microsoft.Office.Tools.Excel.ListObject.BeforeAddDataBoundRow> イベントが発生します。 このイベントを処理することで、データの検証を実行できます。 たとえば、アプリケーションで、18と65の間の従業員のみをデータソースに追加できるようにする必要がある場合は、行が追加される前に、入力された年齢がその範囲内であることを確認します。

> [!NOTE]
> 常に、クライアントだけでなく、サーバー上のユーザー入力も確認する必要があります。 詳細については、「[セキュリティで保護されたクライアントアプリケーション](/dotnet/framework/data/adonet/secure-client-applications)」を参照してください。

### <a name="to-validate-data-when-a-new-row-is-added-to-data-bound-listobject"></a>データ バインドされた ListObject に新規行が追加された場合にデータを検証するには

1. クラス レベルで ID および <xref:System.Data.DataTable> の変数を作成します。

     [!code-csharp[Trin_VstcoreHostControlsExcel#8](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#8)]
     [!code-vb[Trin_VstcoreHostControlsExcel#8](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet1.vb#8)]

2. 新しい<xref:System.Data.DataTable>を作成し、 `Sheet1`クラス (ドキュメントレベルのプロジェクト`Startup`の場合) または`ThisAddIn`クラス (VSTO アドインプロジェクトの場合) のイベントハンドラーにサンプルの列とデータを追加します。

     [!code-csharp[Trin_VstcoreHostControlsExcel#9](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#9)]
     [!code-vb[Trin_VstcoreHostControlsExcel#9](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet1.vb#9)]

3. `list1_BeforeAddDataBoundRow` イベント ハンドラーに、入力された年齢が許容範囲内であるかどうかを確認するコードを追加します。

     [!code-csharp[Trin_VstcoreHostControlsExcel#10](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#10)]
     [!code-vb[Trin_VstcoreHostControlsExcel#10](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet1.vb#10)]

## <a name="compile-the-code"></a>コードのコンパイル
 このコード例では、このコードがあるワークシートに、 <xref:Microsoft.Office.Tools.Excel.ListObject> という名前の既存の `list1` があることを前提としています。

## <a name="see-also"></a>関連項目
- [実行時に VSTO アドインの Word 文書と Excel ブックを拡張する](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)
- [Office ドキュメントのコントロール](../vsto/controls-on-office-documents.md)
- [実行時に Office ドキュメントにコントロールを追加する](../vsto/adding-controls-to-office-documents-at-run-time.md)
- [ListObject コントロール](../vsto/listobject-control.md)
- [拡張オブジェクトを使用した Excel の自動化](../vsto/automating-excel-by-using-extended-objects.md)
- [方法: ListObject 列をデータにマップする](../vsto/how-to-map-listobject-columns-to-data.md)
