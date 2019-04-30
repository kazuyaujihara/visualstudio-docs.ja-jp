---
title: CA2103:命令型のセキュリティを確認します
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2103
- ReviewImperativeSecurity
helpviewer_keywords:
- CA2103
- ReviewImperativeSecurity
ms.assetid: d24fde71-bdf6-46c0-8965-9a73dc33c1aa
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2417266da44c4af38e37eb8e0f67ac13a5a7823e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62808241"
---
# <a name="ca2103-review-imperative-security"></a>CA2103:命令型のセキュリティを確認します

|||
|-|-|
|TypeName|ReviewImperativeSecurity|
|CheckId|CA2103|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
 メソッドが強制セキュリティを使用しています。また、そのメソッドで、確認要求がアクティブな場合に変更できるステータス情報または戻り値を使用して、アクセス許可を構築している可能性があります。

## <a name="rule-description"></a>規則の説明
 強制セキュリティでは、管理対象のオブジェクトを使用して、メタデータにアクセス許可とアクションを格納する属性を使用して、宣言型のセキュリティと比較して、コードの実行中に、アクセス許可とセキュリティ アクションを指定します。 強制セキュリティは、アクセス許可オブジェクトの状態を設定し、実行時までが使用できない情報を使用してセキュリティ アクションを選択することができますので、非常に柔軟性があります。 あるは、柔軟性は、アクションが有効になっている限り、アクセス許可の状態を判断するために使用のランタイム情報が変更されるリスクをものです。

 できる限り、宣言セキュリティを使用します。 宣言型の要求が簡単に理解できます。

## <a name="how-to-fix-violations"></a>違反の修正方法
 アクセス許可の状態は、アクセス許可が使用されている限り、変更できる情報を依存しないことを確認する命令型のセキュリティ確認要求を確認します。

## <a name="when-to-suppress-warnings"></a>警告を抑制します。
 アクセス許可は、データの変更に依存しない場合は、この規則による警告を抑制するのには安全です。 ただし、等価な宣言型に強制確認要求を変更することをお勧めします。

## <a name="see-also"></a>関連項目

- [安全なコーディングのガイドライン](/dotnet/standard/security/secure-coding-guidelines)
- [データとモデリング](/dotnet/framework/data/index)