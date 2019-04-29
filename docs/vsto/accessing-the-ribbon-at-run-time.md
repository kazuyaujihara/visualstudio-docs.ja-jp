---
title: 実行時にリボンへのアクセスします。
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Globals class, Ribbon
- Ribbon [Office development in Visual Studio], accessing
- RibbonManager class
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 6ddbb19c73660dcb77fc8166522946b0b3461e95
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63006763"
---
# <a name="access-the-ribbon-at-runtime"></a>実行時にリボンへのアクセスします。
  リボンを表示、非表示、変更するコードを作成し、ユーザーがカスタム作業ウィンドウ、アクション ウィンドウ、または Outlook フォーム領域のコントロールからそのコードを実行できるようにすることができます。

 リボンには、`Globals` クラスを使用してアクセスできます。 Outlook プロジェクトの場合は、特定の Outlook インスペクター ウィンドウまたは Outlook エクスプ ローラー ウィンドウに表示されるリボンにアクセスできます。

 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]

## <a name="access-the-ribbon-by-using-the-globals-class"></a>Globals クラスを使用して、リボンにアクセスします。
 `Globals` クラスを使用して、プロジェクトのどこからでもドキュメント レベルのプロジェクトまたは VSTO アドイン プロジェクトのリボンにアクセスできます。

 詳細については、`Globals`クラスを参照してください[Office プロジェクト内のオブジェクトへのアクセスをグローバル](../vsto/global-access-to-objects-in-office-projects.md)します。

 次の例では、`Globals` クラスを使用して `Ribbon1` という名前のカスタム リボンにアクセスし、リボンのコンボ ボックスに表示されるテキストを `Hello World` に設定します。

 [!code-vb[Trin_Outlook_FR_Access#4](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Access_O12/ThisAddIn.vb#4)]
 [!code-csharp[Trin_Outlook_FR_Access#4](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Access_O12/ThisAddIn.cs#4)]

## <a name="access-a-collection-of-ribbons-that-appear-in-a-specific-outlook-inspector-window"></a>特定の Outlook インスペクター ウィンドウに表示されるリボンのコレクションにアクセスします。
 Outlook で表示されるリボンのコレクションにアクセスすることができます*インスペクター*します。 インスペクターは、ユーザーが電子メール メッセージを作成するなど、特定のタスクを実行するときに、Outlook で開かれるウィンドウです。 インスペクター ウィンドウのリボンにアクセスするには、`Globals` クラスの `Ribbons` プロパティを呼び出し、インスペクターを表す <xref:Microsoft.Office.Interop.Outlook.Inspector> オブジェクトを渡します。

 次の例では、現在フォーカスがあるインスペクターのリボン コレクションを取得します。 この例では次に、`Ribbon1` という名前のリボンにアクセスして、リボンのコンボ ボックスに表示されるテキストを `Hello World` に設定します。

 [!code-vb[Trin_Outlook_FR_Access#5](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Access_O12/ThisAddIn.vb#5)]
 [!code-csharp[Trin_Outlook_FR_Access#5](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Access_O12/ThisAddIn.cs#5)]

## <a name="access-a-collection-of-ribbons-that-appear-for-a-specific-outlook-explorer"></a>特定の Outlook エクスプ ローラーに表示されるリボンのコレクションにアクセスします。
 Outlook で表示されるリボンのコレクションにアクセスすることができます*エクスプ ローラー*します。 エクスプ ローラーは、Outlook のインスタンスの主要なアプリケーション ユーザー インターフェイス (UI) です。 エクスプローラー ウィンドウのリボンにアクセスするには、`Globals` クラスの `Ribbons` プロパティを呼び出し、エクスプローラーを表す <xref:Microsoft.Office.Interop.Outlook.Explorer> オブジェクトを渡します。

 次の例では、現在フォーカスがあるエクスプローラーのリボン コレクションを取得します。 この例では次に、`Ribbon1` という名前のリボンにアクセスして、リボンのコンボ ボックスに表示されるテキストを `Hello World` に設定します。

 [!code-vb[Trin_Outlook_FR_Access#6](../vsto/codesnippet/VisualBasic/Trin_Outlook_FR_Access_O12/ThisAddIn.vb#6)]
 [!code-csharp[Trin_Outlook_FR_Access#6](../vsto/codesnippet/CSharp/Trin_Outlook_FR_Access_O12/ThisAddIn.cs#6)]

## <a name="see-also"></a>関連項目
- [リボンの概要](../vsto/ribbon-overview.md)
- [リボン デザイナー](../vsto/ribbon-designer.md)
- [Ribbon XML](../vsto/ribbon-xml.md)
- [リボン オブジェクト モデルの概要](../vsto/ribbon-object-model-overview.md)
- [チュートリアル: リボン デザイナーを使用してカスタム タブを作成します。](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)
- [チュートリアル: 実行時にリボン上のコントロールを更新します。](../vsto/walkthrough-updating-the-controls-on-a-ribbon-at-run-time.md)
- [Outlook のリボンをカスタマイズします。](../vsto/customizing-a-ribbon-for-outlook.md)
- [実行時にフォーム領域へのアクセスします。](../vsto/accessing-a-form-region-at-run-time.md)
