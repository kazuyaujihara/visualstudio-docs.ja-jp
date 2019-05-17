---
title: この関連メソッドは、次の既定の挿入、更新、または削除メソッドのバッキング メソッドです
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 62afa6da-97cf-48b9-8de3-33e4d72a0377
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: a5ae70462079589ba2b63ee50cf0b7a0570e056a
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/09/2019
ms.locfileid: "65457842"
---
# <a name="this-related-method-is-the-backing-method-for-the-following-default-insert-update-or-delete-methods"></a>この関連メソッドは、次の既定の挿入、更新、または削除メソッドのバッキング メソッドです

これは関連メソッドは次の既定のバッキング メソッド`Insert`、 `Update`、または`Delete`メソッド。 削除されると、これらのメソッドも削除されます。 続行しますか?

選択した`DataContext`メソッドは、現在の 1 つとして使用されて、 `Insert`、 `Update`、または`Delete`でエンティティ クラスのいずれかのメソッド、 **O/R デザイナー**します。 メソッドを選択した原因を削除、挿入を実行するための既定の実行時動作に戻すには、このメソッドを使用していたエンティティ クラスを更新、または更新中に削除します。

## <a name="selected-method-options"></a>選択したメソッドのオプション

- ランタイムの更新を使用するエンティティ クラスの原因と、選択したメソッドを削除して**はい**します。

   選択されたメソッドが削除され、このメソッドを使用して更新動作をオーバーライドしていたすべてのクラスは、既定の LINQ to SQL ランタイムの動作を使用するように戻されます。

- クリックして、選択したメソッドを変更せずに、メッセージ ボックスを閉じます**いいえ**します。

   メッセージ ボックスが閉じ、変更は行われません。

## <a name="see-also"></a>関連項目

- [Visual Studio の LINQ to SQL ツール](../data-tools/linq-to-sql-tools-in-visual-studio2.md)