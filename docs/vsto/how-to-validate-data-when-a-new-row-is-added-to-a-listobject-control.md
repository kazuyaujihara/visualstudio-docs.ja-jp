---
title: '方法: ListObject コントロールに新しい行が追加されたときにデータを検証します。'
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
ms.openlocfilehash: d8aefab319b9b197b9b7df0e23fec71aa3cb64d1
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "60039312"
---
# <a name="how-to-validate-data-when-a-new-row-is-added-to-a-listobject-control"></a>方法: ListObject コントロールに新しい行が追加されたときにデータを検証します。
  ユーザーはデータにバインドされている <xref:Microsoft.Office.Tools.Excel.ListObject> コントロールに新しい行を追加できます。 変更をデータ ソースにコミットする前に、ユーザーのデータを検証できます。

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

## <a name="data-validation"></a>データの検証
 データにバインドされている <xref:Microsoft.Office.Tools.Excel.ListObject> に行が追加されるたびに、 <xref:Microsoft.Office.Tools.Excel.ListObject.BeforeAddDataBoundRow> イベントが発生します。 このイベントを処理することで、データの検証を実行できます。 たとえば、データ ソースに 18 歳と 65 の従業員のみを追加することができます、アプリケーションに必要な場合は、行を追加する前に入力された年齢がその範囲内にあることを確認します。

> [!NOTE]
>  常に、クライアントだけでなく、サーバー上のユーザー入力も確認する必要があります。 詳細については、次を参照してください。[クライアント アプリケーションをセキュリティで保護された](/dotnet/framework/data/adonet/secure-client-applications)します。

### <a name="to-validate-data-when-a-new-row-is-added-to-data-bound-listobject"></a>データ バインドされた ListObject に新規行が追加された場合にデータを検証するには

1. クラス レベルで ID および <xref:System.Data.DataTable> の変数を作成します。

     [!code-csharp[Trin_VstcoreHostControlsExcel#8](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#8)]
     [!code-vb[Trin_VstcoreHostControlsExcel#8](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet1.vb#8)]

2. 新規作成<xref:System.Data.DataTable>サンプルの列とデータを追加し、`Startup`のイベント ハンドラー、 `Sheet1` (ドキュメント レベルのプロジェクト) 内のクラスまたは`ThisAddIn`クラス (VSTO アドイン プロジェクトの場合)。

     [!code-csharp[Trin_VstcoreHostControlsExcel#9](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#9)]
     [!code-vb[Trin_VstcoreHostControlsExcel#9](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet1.vb#9)]

3. `list1_BeforeAddDataBoundRow` イベント ハンドラーに、入力された年齢が許容範囲内であるかどうかを確認するコードを追加します。

     [!code-csharp[Trin_VstcoreHostControlsExcel#10](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#10)]
     [!code-vb[Trin_VstcoreHostControlsExcel#10](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet1.vb#10)]

## <a name="compile-the-code"></a>コードのコンパイル
 このコード例では、このコードがあるワークシートに、 <xref:Microsoft.Office.Tools.Excel.ListObject> という名前の既存の `list1` があることを前提としています。

## <a name="see-also"></a>関連項目
- [Word 文書と Excel ブックを実行時に VSTO アドインで拡張します。](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)
- [Office ドキュメントのコントロール](../vsto/controls-on-office-documents.md)
- [実行時に Office ドキュメントにコントロールを追加します。](../vsto/adding-controls-to-office-documents-at-run-time.md)
- [ListObject コントロール](../vsto/listobject-control.md)
- [拡張オブジェクトを使用した Excel の自動化](../vsto/automating-excel-by-using-extended-objects.md)
- [方法: データに ListObject 列をマップします。](../vsto/how-to-map-listobject-columns-to-data.md)
