---
title: '方法: アドイン ユーザー インターフェイス エラーを表示します。'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- add-ins [Office development in Visual Studio], user interface errors
- errors [Office development in Visual Studio], user interface errors
- user interfaces [Office development in Visual Studio], errors
- application-level add-ins [Office development in Visual Studio], user interface errors
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 12fc82fd0c04e9f05ff55be24c3527ca95a357fb
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56596011"
---
# <a name="how-to-show-add-in-user-interface-errors"></a>方法: アドイン ユーザー インターフェイス エラーを表示します。
  既定では、VSTO アドインを Microsoft Office ユーザー インターフェイス (UI) と失敗した場合、操作をしようとするとエラー メッセージは表示されません。 しかし、UI に関連するエラー メッセージを表示するように Microsoft Office アプリケーションを構成できます。 これらのメッセージを使用すると、なぜカスタム リボンが表示されない、またはリボンが表示されますが、コントロールが表示されない理由を判断します。

 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]

## <a name="to-show-vsto-add-in-user-interface-errors"></a>VSTO アドインのユーザー インターフェイス エラーを表示するには

1.  アプリケーションを起動します。

2.  **[ファイル]** タブをクリックします。

3.  **[オプション]** をクリックします。

4.  [カテゴリ] ウィンドウで **[詳細]** をクリックします。

5.  詳細ウィンドウで、 **[VSTO アドイン ユーザー インターフェイスのエラーを表示する]** を選び、 **[OK]** をクリックします。

    > [!NOTE]
    >  Outlook の場合、詳細ウィンドウの **[開発]** セクションに **[VSTO アドイン ユーザー インターフェイスのエラーを表示する]** チェック ボックスがあります。 その他のアプリケーションの場合、このチェック ボックスは、詳細ウィンドウの **[全般]** セクションにあります。

## <a name="see-also"></a>関連項目
- [Office UI のカスタマイズ](../vsto/office-ui-customization.md)
- [Outlook フォーム領域の作成](../vsto/creating-outlook-form-regions.md)
- [リボンの概要](../vsto/ribbon-overview.md)
- [操作ウィンドウの概要](../vsto/actions-pane-overview.md)
