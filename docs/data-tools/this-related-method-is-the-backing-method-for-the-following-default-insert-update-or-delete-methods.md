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
ms.openlocfilehash: 11c5c7d3c8078aa420074e9e32bb132489b169c8
ms.sourcegitcommit: e98db44f3a33529b0ba188d24390efd09e548191
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2019
ms.locfileid: "71252942"
---
# <a name="this-related-method-is-the-backing-method-for-the-following-default-insert-update-or-delete-methods"></a>この関連メソッドは、次の既定の挿入、更新、または削除メソッドのバッキング メソッドです

この関連メソッドは、 `Insert` `Update`次の既定のメソッド、メソッド、また`Delete`はメソッドのバッキングメソッドです。 削除されると、これらのメソッドも削除されます。 続行しますか?

選択さ`DataContext`れたメソッドは`Insert`、現在、 **O/R デザイナー**のいずれかのエンティティクラスに対して、 `Update` `Delete` 、、のいずれかのメソッドとして使用されています。 選択したメソッドを削除すると、このメソッドを使用していたエンティティクラスは、更新時に挿入、更新、または削除を実行する既定の実行時の動作に戻ります。

## <a name="selected-method-options"></a>選択されたメソッドのオプション

- 選択したメソッドを削除して、エンティティクラスがランタイムの更新プログラムを使用するようにするには、 **[はい]** をクリックします。

   選択したメソッドが削除され、このメソッドを使用して更新動作をオーバーライドしたクラスは、既定の LINQ to SQL の実行時の動作を使用するように戻されます。

- 選択した方法を変更せずにメッセージボックスを閉じるには、 **[いいえ]** をクリックします。

   メッセージ ボックスが閉じ、変更は行われません。

## <a name="see-also"></a>関連項目

- [Visual Studio の LINQ to SQL ツール](../data-tools/linq-to-sql-tools-in-visual-studio2.md)