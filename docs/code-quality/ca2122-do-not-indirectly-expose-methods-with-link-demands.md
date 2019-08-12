---
title: CA2122:リンク要求を含むメソッドを間接的に公開しません
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2122
- DoNotIndirectlyExposeMethodsWithLinkDemands
helpviewer_keywords:
- DoNotIndirectlyExposeMethodsWithLinkDemands
- CA2122
ms.assetid: 3eda58e7-c6ec-41c3-8112-ae0841109c6a
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 340d8f0a45506f15cdd9281f7ecda463583c3144
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68920824"
---
# <a name="ca2122-do-not-indirectly-expose-methods-with-link-demands"></a>CA2122:リンク要求を含むメソッドを間接的に公開しません

|||
|-|-|
|TypeName|DoNotIndirectlyExposeMethodsWithLinkDemands|
|CheckId|CA2122|
|Category|Microsoft.Security|
|互換性に影響する変更点|中断なし|

## <a name="cause"></a>原因
パブリックメンバーまたはプロテクトメンバーに[リンク確認要求](/dotnet/framework/misc/link-demands)があり、セキュリティチェックを実行しないメンバーによって呼び出されています。

## <a name="rule-description"></a>規則の説明
リンク確認要求では、直接の呼び出し元のアクセス許可しかチェックされません。 メンバー `X`が呼び出し元に対してセキュリティ要求を行わず、リンク確認要求によって保護されたコードを呼び出す場合`X` 、必要なアクセス許可を持たない呼び出し元は、を使用して保護されたメンバーにアクセスできます。

## <a name="how-to-fix-violations"></a>違反の修正方法
セキュリティ[データとモデリング](/dotnet/framework/data/index)またはリンク確認要求をメンバーに追加して、リンク確認要求で保護されたメンバーに安全にアクセスできないようにします。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
この規則からの警告を安全に抑制するには、破壊的な方法で使用できる操作またはリソースへの呼び出し元に対して、コードがアクセス権を付与しないようにする必要があります。

## <a name="example-1"></a>例 1
次の例は、規則に違反するライブラリと、ライブラリの弱点を示すアプリケーションを示しています。 サンプルライブラリには、規則に違反する2つのメソッドが用意されています。 メソッド`EnvironmentSetting`は、環境変数に無制限にアクセスするためのリンク確認要求によって保護されます。 メソッド`DomainInformation`は、を呼び出す`EnvironmentSetting`前に、その呼び出し元に対してセキュリティ要求を行いません。

[!code-csharp[FxCop.Security.UnsecuredDoNotCall#1](../code-quality/codesnippet/CSharp/ca2122-do-not-indirectly-expose-methods-with-link-demands_1.cs)]

## <a name="example-2"></a>例 2
次のアプリケーションは、セキュリティで保護されていないライブラリメンバーを呼び出します。

[!code-csharp[FxCop.Security.TestUnsecuredDoNot1#1](../code-quality/codesnippet/CSharp/ca2122-do-not-indirectly-expose-methods-with-link-demands_2.cs)]

この例を実行すると、次の出力が生成されます。

```txt
*Value from unsecured member: seattle.corp.contoso.com
```

## <a name="see-also"></a>関連項目

- [安全なコーディングのガイドライン](/dotnet/standard/security/secure-coding-guidelines)
- [リンク確認要求](/dotnet/framework/misc/link-demands)
- [データとモデリング](/dotnet/framework/data/index)