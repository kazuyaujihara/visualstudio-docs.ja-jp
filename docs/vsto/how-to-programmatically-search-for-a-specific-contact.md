---
title: '方法: プログラムによって特定の連絡先を検索します。'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- contacts [Office development in Visual Studio], searching
- searching contacts
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: feff583d28bf53f4bffc9b425d52902688b80a4b
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56607162"
---
# <a name="how-to-programmatically-search-for-a-specific-contact"></a>方法: プログラムによって特定の連絡先を検索します。
  この例では、Outlook の連絡先フォルダーから、姓と名前を指定して特定の連絡先を検索します。 この例では、 **John Evans** という名前の連絡先が連絡先フォルダーに存在することを前提にしています。

 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]

## <a name="example"></a>例
 [!code-csharp[Trin_Outlook_RL_SearchForContact#1](../vsto/codesnippet/CSharp/trin_outlook_rl_searchforcontact/thisaddin.cs#1)]
 [!code-vb[Trin_Outlook_RL_SearchForContact#1](../vsto/codesnippet/VisualBasic/trin_outlook_rl_searchforcontact/thisaddin.vb#1)]

## <a name="see-also"></a>関連項目
- [連絡先項目を操作します。](../vsto/working-with-contact-items.md)
- [VSTO アドインのプログラミングを始める](../vsto/getting-started-programming-vsto-add-ins.md)
