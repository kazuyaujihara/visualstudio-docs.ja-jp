---
title: XmlMappedRange コントロール
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- XMLMappedRange control, data binding
- XMLMappedRange control
- XMLMappedRange control, events
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 01417d9c08491edc882f7f758bb36e6184500e52
ms.sourcegitcommit: dcbb876a5dd598f2538e62e1eabd4dc98595b53a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2019
ms.locfileid: "72985361"
---
# <a name="xmlmappedrange-control"></a>XmlMappedRange コントロール
  <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> コントロールは、非繰り返しスキーマ要素が Microsoft Office Excel のセルにマップされている場合にのみ作成される範囲です。 たとえば、スキーマ要素の `maxOccurs` 属性が1と等しい場合です。 XML にマップされた範囲が Visual Studio によって作成された後は、Excel オブジェクトモデルを走査する必要なく、直接プログラミングできます。 要素のマッピングが削除された場合、Excel 内の <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> コントロールのみを削除できます。

 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]

## <a name="bind-data-to-the-control"></a>コントロールにデータをバインドする
 <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> コントロールでは、単一のデータフィールド (単純データバインディング) へのバインドがサポートされています。 <xref:Microsoft.Office.Tools.Excel.ListObject> コントロールは、複合データバインディングをサポートでき、繰り返しスキーマ要素がセルにマップされるときに自動的に作成されます。 詳細については、「 [ListObject コントロール](../vsto/listobject-control.md)」を参照してください。

 <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> コントロールは、<xref:System.Windows.Forms.Control.DataBindings%2A> プロパティを使用してデータソースにバインドされます。 <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> がワークシートセルに追加されると、Visual Studio は、マップされたセル内のデータからデータセットを自動的に生成し、そのデータセットにコントロールをバインドします。 <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> の既定のデータバインディングプロパティは <xref:Microsoft.Office.Tools.Excel.XmlMappedRange.Value2%2A>です。

 バインドされたデータセット内のデータが任意のメカニズムによって更新されると、<xref:Microsoft.Office.Tools.Excel.XmlMappedRange> 制御によって変更が反映されます。

## <a name="formatting"></a>書式設定
 <xref:Microsoft.Office.Interop.Excel.Range>に適用できる <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> コントロールに同じ書式設定を適用できます。 これには、罫線、フォント、番号形式、スタイルが含まれます。

## <a name="events"></a>イベント
 <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> コントロールで使用できるイベントは次のとおりです。

- <xref:Microsoft.Office.Tools.Excel.XmlMappedRange.BeforeDoubleClick>

- <xref:Microsoft.Office.Tools.Excel.XmlMappedRange.BeforeRightClick>

- <xref:Microsoft.Office.Tools.Excel.XmlMappedRange.BindingContextChanged>

- <xref:Microsoft.Office.Tools.Excel.XmlMappedRange.Change>

- <xref:Microsoft.Office.Tools.Excel.XmlMappedRange.Selected>

- <xref:Microsoft.Office.Tools.Excel.XmlMappedRange.Deselected>

- <xref:System.ComponentModel.Component.Disposed>

- <xref:Microsoft.Office.Tools.Excel.XmlMappedRange.SelectionChange>

## <a name="see-also"></a>関連項目
- [拡張オブジェクトを使用して Excel を自動化する](../vsto/automating-excel-by-using-extended-objects.md)
- [方法: ワークシートに XMLMappedRange コントロールを追加する](../vsto/how-to-add-xmlmappedrange-controls-to-worksheets.md)
- [Office ソリューションのコントロールにデータをバインドする](../vsto/binding-data-to-controls-in-office-solutions.md)
- [方法: Visual Studio 内のワークシートにスキーマをマップする](../vsto/how-to-map-schemas-to-worksheets-inside-visual-studio.md)
- [ホスト項目とホストコントロールのプログラム上の制限事項](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)
