---
title: '方法: トランザクションを使用してデータを保存する'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- saving data, using transactions
- System.Transactions namespace
- transactions, saving data
- data [Visual Studio], saving
ms.assetid: 8b835e8f-34a3-413d-9bb5-ebaeb87f1198
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: cfb03944743609d20d14f6104e5fadd529a5cfa6
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72641308"
---
# <a name="how-to-save-data-by-using-a-transaction"></a>方法: トランザクションを使用してデータを保存する

トランザクションにデータを保存するには、<xref:System.Transactions> 名前空間を使用します。 @No__t_0 オブジェクトを使用して、自動的に管理されるトランザクションに参加します。

プロジェクト*は、system.string アセンブリへ*の参照を使用して作成されるわけではないため、トランザクションを使用するプロジェクトへの参照を手動で追加する必要があります。

トランザクションを実装する最も簡単な方法は、`using` ステートメントで <xref:System.Transactions.TransactionScope> オブジェクトをインスタンス化することです。 (詳細については、「 [using ステートメント](/dotnet/visual-basic/language-reference/statements/using-statement)」および「 [using ステートメント](/dotnet/csharp/language-reference/keywords/using-statement)」を参照してください)。@No__t_2 ステートメント内で実行されるコードは、トランザクションに参加します。

トランザクションをコミットするには、using ブロックの最後のステートメントとして <xref:System.Transactions.TransactionScope.Complete%2A> メソッドを呼び出します。

トランザクションをロールバックするには、<xref:System.Transactions.TransactionScope.Complete%2A> メソッドを呼び出す前に例外をスローします。

## <a name="to-add-a-reference-to-the-systemtransactionsdll"></a>System.object への参照を追加するには

1. **[プロジェクト]** メニューの **[参照の追加]** をクリックします。

2. **[.Net]** タブ (SQL Server プロジェクトの **[SQL Server]** タブ) で [ **system.string] を選択し**、 **[OK]** を選択します。

     System.object への*参照がプロジェクト*に追加されます。

## <a name="to-save-data-in-a-transaction"></a>トランザクションにデータを保存するには

- トランザクションを含む using ステートメント内にデータを保存するコードを追加します。 次のコードは、using ステートメントで <xref:System.Transactions.TransactionScope> オブジェクトを作成およびインスタンス化する方法を示しています。

     [!code-vb[VbRaddataSaving#11](../data-tools/codesnippet/VisualBasic/save-data-by-using-a-transaction_1.vb)]
     [!code-csharp[VbRaddataSaving#11](../data-tools/codesnippet/CSharp/save-data-by-using-a-transaction_1.cs)]

## <a name="see-also"></a>関連項目

- [データをデータベースに保存する](../data-tools/save-data-back-to-the-database.md)
- [チュートリアル: トランザクションにデータを保存する](../data-tools/save-data-in-a-transaction.md)