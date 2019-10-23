---
title: 'CA1804: 使用されていないローカル | を削除します。Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1804
- RemoveUnusedLocals
helpviewer_keywords:
- RemoveUnusedLocals
- CA1804
ms.assetid: cc332e67-6543-4813-bd8a-6f6fc75bf22a
caps.latest.revision: 20
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 824a65e765f21748b97292beea64ea6c9bd64a1b
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72671562"
---
# <a name="ca1804-remove-unused-locals"></a>CA1804: 使用されていないローカルを削除します
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|RemoveUnusedLocals|
|CheckId|CA1804|
|カテゴリ|Microsoft. パフォーマンス|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因
 メソッドはローカル変数を宣言しますが、代入ステートメントの受信者としての場合を除き、変数は使用しません。 この規則による分析のために、テストされたアセンブリはデバッグ情報を使用してビルドする必要があり、関連付けられているプログラムデータベース (.pdb) ファイルが使用可能である必要があります。

## <a name="rule-description"></a>規則の説明
 使用されていないローカル変数や不要な引数があると、アセンブリのサイズが大きくなり、パフォーマンスが低下します。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則違反を修正するには、ローカル変数を削除するか、使用します。 @No__t_2 オプションがC#有効になっている場合、[!INCLUDE[dnprdnlong](../includes/dnprdnlong-md.md)] に含まれるコンパイラは、使用されていないローカル変数を削除することに注意してください。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 変数がコンパイラによって生成された場合、このルールからの警告を非表示にします。 また、パフォーマンスとコードの保守が主要な問題でない場合は、このルールからの警告を抑制するか、ルールを無効にすることも安全です。

## <a name="example"></a>例
 次の例では、使用されていないローカル変数をいくつか示します。

 [!code-csharp[FxCop.Performance.UnusedLocals#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Performance.UnusedLocals/cs/FxCop.Performance.UnusedLocals.cs#1)]
 [!code-vb[FxCop.Performance.UnusedLocals#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Performance.UnusedLocals/vb/FxCop.Performance.UnusedLocals.vb#1)]

## <a name="related-rules"></a>関連規則
 [CA1809: ローカルを使用しすぎないでください](../code-quality/ca1809-avoid-excessive-locals.md)

 [CA1811: 呼び出されていないプライベート コードを使用しません](../code-quality/ca1811-avoid-uncalled-private-code.md)

 [CA1812: インスタンス化されていない内部クラスを使用しないでください](../code-quality/ca1812-avoid-uninstantiated-internal-classes.md)

 [CA1801: 使用されていないパラメーターをレビューします](../code-quality/ca1801-review-unused-parameters.md)
