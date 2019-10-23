---
title: トランザクションを使用してデータを保存する |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- saving data, using transactions
- System.Transactions namespace
- transactions, saving data
- data [Visual Studio], saving
ms.assetid: 8b835e8f-34a3-413d-9bb5-ebaeb87f1198
caps.latest.revision: 16
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 85f3584073523e748168faf569aa918ba912fbf8
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72652833"
---
# <a name="save-data-by-using-a-transaction"></a>トランザクションを使用してデータを保存する
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

トランザクションにデータを保存するには、<xref:System.Transactions> 名前空間を使用します。 @No__t_0 オブジェクトを使用して、自動的に管理されるトランザクションに参加します。

 プロジェクトは、system.string アセンブリへの参照を使用して作成されるわけではないため、トランザクションを使用するプロジェクトへの参照を手動で追加する必要があります。

> [!NOTE]
> @No__t_0 名前空間は、Windows 2000 以降でサポートされています。

 トランザクションを実装する最も簡単な方法は、`using` ステートメントで <xref:System.Transactions.TransactionScope> オブジェクトをインスタンス化することです。 (詳細については、「 [Using ステートメント](https://msdn.microsoft.com/library/665d1580-dd54-4e96-a9a9-6be2a68948f1)」および「 [using ステートメント](https://msdn.microsoft.com/library/afc355e6-f0b9-4240-94dd-0d93f17d9fc3)」を参照してください)。@No__t_2 ステートメント内で実行されるコードは、トランザクションに参加します。

 トランザクションをコミットするには、using ブロックの最後のステートメントとして <xref:System.Transactions.TransactionScope.Complete%2A> メソッドを呼び出します。

 トランザクションをロールバックするには、<xref:System.Transactions.TransactionScope.Complete%2A> メソッドを呼び出す前に例外をスローします。

 詳細については、「[トランザクションにデータを保存する](../data-tools/save-data-in-a-transaction.md)」を参照してください。

### <a name="to-add-a-reference-to-the-systemtransactions-dll"></a>System.string dll への参照を追加するには

1. **[プロジェクト]** メニューの **[参照の追加]** をクリックします。

2. **[.Net]** タブ (SQL Server プロジェクトの **[SQL Server]** タブ) で [ **system.string] を選択し**、 **[OK]** を選択します。

     System.object への参照がプロジェクトに追加されます。

### <a name="to-save-data-in-a-transaction"></a>トランザクションにデータを保存するには

- トランザクションを含む using ステートメント内にデータを保存するコードを追加します。 次のコードは、using ステートメントで <xref:System.Transactions.TransactionScope> オブジェクトを作成およびインスタンス化する方法を示しています。

     [!code-csharp[VbRaddataSaving#11](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Form2.cs#11)]
     [!code-vb[VbRaddataSaving#11](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Form2.vb#11)]

## <a name="see-also"></a>参照
 [データをデータベースに保存する](../data-tools/save-data-back-to-the-database.md)
