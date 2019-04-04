---
title: '方法: ワークシート内のデータベース レコードをスクロールします。'
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
ms.openlocfilehash: 7facc5a70b603b016bbafd207650caaef05027fa
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56600247"
---
# <a name="how-to-scroll-through-database-records-in-a-worksheet"></a>方法: ワークシート内のデータベース レコードをスクロールします。
  次の手順では、デザイナーを使用して、エンドユーザーがすべてのレコードをスクロールできるようにするコントロールでの Microsoft Office Excel ワークシートで、データベース テーブルから 1 つのフィールドを表示する方法を示します。

 ドキュメント レベルのプロジェクトでのみ、デザイナーを使用することができます。 ただし、コントロールを追加し、実行時にプログラムでデータにバインドすることができますも。 詳細については、「[チュートリアル:VSTO アドイン プロジェクトでの単純データ バインディング](../vsto/walkthrough-simple-data-binding-in-vsto-add-in-project.md)します。

 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]

## <a name="to-scroll-through-database-records-in-a-worksheet"></a>ワークシート内のデータベース レコードをスクロールするには

1.  Visual Studio で Excel のアプリケーション プロジェクトを開きます。

2.  開く、**データ ソース**ウィンドウと、データベースからデータ ソースを作成します。 詳細については、[新しい接続を追加](../data-tools/add-new-connections.md)を参照してください。

3.  を表示するデータを含むテーブルを展開し、特定の列を選択します。

4.  コントロールのリストを開く**NamedRange**します。

5.  ドラッグ、<xref:Microsoft.Office.Tools.Excel.NamedRange>コントロールをデータが表示されるセルにします。

6.  **Windows フォーム**のタブ、**ツールボックス**、追加、<xref:System.Windows.Forms.BindingNavigator>ワークシートに制御し、使用するコントロールを設定します。 詳細については、[BindingNavigator コントロールの概要&#40;Windows フォーム&#41;](/dotnet/framework/winforms/controls/bindingnavigator-control-overview-windows-forms)を参照してください。

## <a name="see-also"></a>関連項目
- [Office ソリューションでのコントロールにデータをバインドします。](../vsto/binding-data-to-controls-in-office-solutions.md)
