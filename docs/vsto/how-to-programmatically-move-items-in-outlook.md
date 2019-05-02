---
title: '方法: プログラムによって Outlook でアイテムを移動します。'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Outlook folders [Office development in Visual Studio], moving items
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 3dcbfbe7b6e6ac5bacb9e8e36e43d780d3051903
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62812565"
---
# <a name="how-to-programmatically-move-items-in-outlook"></a>方法: プログラムによって Outlook でアイテムを移動します。
  この例から未読の電子メール メッセージの移動、**受信トレイ**という名前のフォルダーに**テスト**します。 例では、のみ、単語が含まれているメッセージを移動**テスト**で、`Subject`フィールド。

 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]

## <a name="example"></a>例
 [!code-csharp[Trin_OL_MoveItems#1](../vsto/codesnippet/CSharp/Trin_OL_MoveItems/thisaddin.cs#1)]

## <a name="compile-the-code"></a>コードのコンパイル
 この例で必要な要素は次のとおりです。

- という名前の Outlook メール フォルダー**テスト**します。

- 電子メール メッセージが到着する単語**テスト**で、`Subject`フィールド。

## <a name="see-also"></a>関連項目
- [フォルダーを操作します。](../vsto/working-with-folders.md)
- [方法: 名前でフォルダーをプログラムで取得します。](../vsto/how-to-programmatically-retrieve-a-folder-by-name.md)
- [方法: プログラムによって特定のフォルダー内を検索します。](../vsto/how-to-programmatically-search-within-a-specific-folder.md)
- [方法: プログラムで電子メール メッセージを受信したときにアクションを実行します。](../vsto/how-to-programmatically-perform-actions-when-an-e-mail-message-is-received.md)
