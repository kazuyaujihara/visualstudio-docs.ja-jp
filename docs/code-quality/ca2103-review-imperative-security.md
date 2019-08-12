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
ms.openlocfilehash: 7acbb9d0127dd2ddb6668e72db8fa88124ec2b3c
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68921429"
---
# <a name="ca2103-review-imperative-security"></a>CA2103:命令型のセキュリティを確認します

|||
|-|-|
|TypeName|ReviewImperativeSecurity|
|CheckId|CA2103|
|Category|Microsoft.Security|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
メソッドが強制セキュリティを使用しています。また、そのメソッドで、確認要求がアクティブな場合に変更できるステータス情報または戻り値を使用して、アクセス許可を構築している可能性があります。

## <a name="rule-description"></a>規則の説明
命令型セキュリティは、属性を使用してメタデータにアクセス許可とアクションを格納する宣言セキュリティと比較して、マネージオブジェクトを使用して、コードの実行中にアクセス許可とセキュリティアクションを指定します。 強制セキュリティは、アクセス許可オブジェクトの状態を設定し、実行時まで使用できない情報を使用してセキュリティアクションを選択できるため、非常に柔軟性があります。 その柔軟性と共に、アクションが有効になっている限り、アクセス許可の状態を判断するために使用するランタイム情報が変更されていないというリスクが伴います。

できる限り、宣言セキュリティを使用します。 宣言型の要求は理解しやすくなります。

## <a name="how-to-fix-violations"></a>違反の修正方法
強制セキュリティ要求を確認して、アクセス許可の状態が、アクセス許可が使用されている限り変更できる情報に依存していないことを確認します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
権限がデータの変更に依存していない場合は、このルールからの警告を抑制しても安全です。 ただし、命令型の要求を、それと等価な宣言に変更することをお勧めします。

## <a name="see-also"></a>関連項目

- [安全なコーディングのガイドライン](/dotnet/standard/security/secure-coding-guidelines)
- [データとモデリング](/dotnet/framework/data/index)