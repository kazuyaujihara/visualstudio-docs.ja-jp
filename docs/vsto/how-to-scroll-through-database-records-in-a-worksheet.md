---
title: '方法: ワークシート内のデータベースレコードをスクロールする'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- databases [Office development in Visual Studio], scrolling records
- records [Office development in Visual Studio], scrolling
- data [Office development in Visual Studio], scrolling database records
- worksheets [Office development in Visual Studio], scrolling records
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: f0b3c6a8a9292ceda03c9d0020b78d9518ca49d9
ms.sourcegitcommit: e98db44f3a33529b0ba188d24390efd09e548191
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2019
ms.locfileid: "71252032"
---
# <a name="how-to-scroll-through-database-records-in-a-worksheet"></a>方法: ワークシート内のデータベースレコードをスクロールする
  次の手順では、デザイナーを使用して、Microsoft Office Excel ワークシートのデータベーステーブルから単一のフィールドを表示する方法を示します。このコントロールには、エンドユーザーがすべてのレコードをスクロールできるようにするコントロールがあります。

 デザイナーは、ドキュメントレベルのプロジェクトでのみ使用できます。 ただし、コントロールを追加し、実行時にプログラムによってデータにバインドすることもできます。 詳細については、「[チュートリアル:VSTO アドインプロジェクト](../vsto/walkthrough-simple-data-binding-in-vsto-add-in-project.md)での単純なデータバインディング。

 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]

## <a name="to-scroll-through-database-records-in-a-worksheet"></a>ワークシート内のデータベースレコードをスクロールするには

1. Visual Studio で Excel アプリケーションプロジェクトを開きます。

2. **[データソース]** ウィンドウを開き、データベースからデータソースを作成します。 詳細については、「[新しい接続の追加](../data-tools/add-new-connections.md)」を参照してください。

3. 表示するデータが含まれているテーブルを展開し、特定の列を選択します。

4. コントロールの一覧を開き、 **[NamedRange]** を選択します。

5. データを<xref:Microsoft.Office.Tools.Excel.NamedRange>表示するセルにコントロールをドラッグします。

6. **ツールボックス**の [ <xref:System.Windows.Forms.BindingNavigator> **Windows フォーム**] タブで、ワークシートにコントロールを追加し、使用するコントロールを設定します。 詳細については、「 [BindingNavigator &#40;コントロール&#41;の概要 Windows フォーム](/dotnet/framework/winforms/controls/bindingnavigator-control-overview-windows-forms)」を参照してください。

## <a name="see-also"></a>関連項目
- [Office ソリューションのコントロールにデータをバインドする](../vsto/binding-data-to-controls-in-office-solutions.md)
