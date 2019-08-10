---
title: CA2112:セキュリティで保護された型はフィールドを公開してはなりません
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2112
- SecuredTypesShouldNotExposeFields
helpviewer_keywords:
- SecuredTypesShouldNotExposeFields
- CA2112
ms.assetid: 9eb13a78-3487-49f2-81d1-3c3866db132f
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 43ef4165823f59045dda8c05b5679fdd3b795114
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68921089"
---
# <a name="ca2112-secured-types-should-not-expose-fields"></a>CA2112:セキュリティで保護された型はフィールドを公開してはなりません

|||
|-|-|
|TypeName|SecuredTypesShouldNotExposeFields|
|CheckId|CA2112|
|Category|Microsoft.Security|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
パブリックまたはプロテクト型にはパブリックフィールドが含まれ、[リンク確認要求](/dotnet/framework/misc/link-demands)によってセキュリティ保護されます。

## <a name="rule-description"></a>規則の説明
リンク確認要求で保護されている型のインスタンスに対するアクセス権がコードにある場合、その型のフィールドにアクセスするためにリンク確認要求に適合する必要はありません。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するには、フィールドを非パブリックにし、フィールドデータを返すパブリックプロパティまたはメソッドを追加します。 型の LinkDemand セキュリティチェックは、型のプロパティとメソッドへのアクセスを保護します。 ただし、コードアクセスセキュリティはフィールドには適用されません。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
セキュリティの問題と優れた設計の両方で、パブリックフィールドを非公開にすることで、違反を修正する必要があります。 セキュリティで保護されたままにする必要がある情報をフィールドに保持しておらず、フィールドの内容に依存していない場合は、この規則からの警告を抑制できます。

## <a name="example"></a>例
次の例は、セキュリティで保護され`SecuredTypeWithFields`ていないフィールドを持つライブラリ型`Distributor`()、ライブラリ型のインスタンスを作成できる型 ()、およびそれらを作成するためのアクセス許可を持たない型のインスタンスを作成するためのアプリケーションコードを構成します。では、型をセキュリティで保護するアクセス許可がない場合でも、インスタンスのフィールドを読み取ることができます。

次のライブラリコードは規則に違反しています。

[!code-csharp[FxCop.Security.LinkDemandOnField#1](../code-quality/codesnippet/CSharp/ca2112-secured-types-should-not-expose-fields_1.cs)]

## <a name="example-1"></a>例 1
アプリケーションでは、セキュリティで保護された型を保護するリンク確認要求のためにインスタンスを作成できません。 アプリケーションがセキュリティで保護された型のインスタンスを取得できるようにするクラスを次に示します。

[!code-csharp[FxCop.Security.LDOnFieldsDistributor#1](../code-quality/codesnippet/CSharp/ca2112-secured-types-should-not-expose-fields_2.cs)]

## <a name="example-2"></a>例 2
次のアプリケーションは、セキュリティで保護された型のメソッドにアクセスする権限を持たない場合に、コードからそのフィールドにアクセスできるようにする方法を示しています。

[!code-csharp[FxCop.Security.TestLinkDemandOnFields#1](../code-quality/codesnippet/CSharp/ca2112-secured-types-should-not-expose-fields_3.cs)]

この例を実行すると、次の出力が生成されます。

```txt
Creating an instance of SecuredTypeWithFields.
Secured type fields: 22, 33
Changing secured type's field...
Cached Object fields: 99, 33
```

## <a name="related-rules"></a>関連するルール

- [CA1051参照可能なインスタンスフィールドを宣言しない](../code-quality/ca1051-do-not-declare-visible-instance-fields.md)

## <a name="see-also"></a>関連項目

- [リンク確認要求](/dotnet/framework/misc/link-demands)
- [データとモデリング](/dotnet/framework/data/index)