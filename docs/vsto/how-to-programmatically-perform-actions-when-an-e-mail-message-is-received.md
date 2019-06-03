---
title: プログラムで電子メール メッセージを受信した場合のアクションを実行します。
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Outlook [Office development in Visual Studio], actions when e-mail is received
- NewMail event
- mail items [Office development in Visual Studio], custom actions
- e-mail [Office development in Visual Studio], custom actions
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: a0787db2f7055bc65871227b9fcf8cbbb60ec1d8
ms.sourcegitcommit: 25570fb5fb197318a96d45160eaf7def60d49b2b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/30/2019
ms.locfileid: "66402198"
---
# <a name="how-to-programmatically-perform-actions-when-an-email-message-is-received"></a>方法: プログラムで電子メール メッセージを受信したときにアクションを実行します。
  この例では、ユーザーが電子メール メッセージを受信すると、カスタム アクションが実行します。

 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]

## <a name="example"></a>例
 [!code-vb[Trin_Outlook_RL_PerformActions#1](../vsto/codesnippet/VisualBasic/Trin_Outlook_RL_PerformActions/thisaddin.vb#1)]
 [!code-csharp[Trin_Outlook_RL_PerformActions#1](../vsto/codesnippet/CSharp/Trin_Outlook_RL_PerformActions/thisaddin.cs#1)]

## <a name="see-also"></a>関連項目
- [方法: Office プロジェクトでのイベント ハンドラーを作成します。](../vsto/how-to-create-event-handlers-in-office-projects.md)
- [メールの項目を操作します。](../vsto/working-with-mail-items.md)
- [VSTO アドインのプログラミングを始める](../vsto/getting-started-programming-vsto-add-ins.md)
