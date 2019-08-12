---
title: CA1407:Com 参照可能な型で静的メンバーを使用しません
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1407
- AvoidStaticMembersInComVisibleTypes
helpviewer_keywords:
- CA1407
- AvoidStaticMembersInComVisibleTypes
ms.assetid: bebd0776-ad04-453c-bca8-8c124c2d7840
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 631be1a93318cd24af4251fefbc710294fa52bf7
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68922007"
---
# <a name="ca1407-avoid-static-members-in-com-visible-types"></a>CA1407:Com 参照可能な型で静的メンバーを使用しません

|||
|-|-|
|TypeName|AvoidStaticMembersInComVisibleTypes|
|CheckId|CA1407|
|Category|Microsoft. 相互運用性|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因
コンポーネントオブジェクトモデル (COM) に対して表示されるように明示的に`public``static`マークされている型には、メソッドが含まれています。

## <a name="rule-description"></a>規則の説明
COM はメソッドを`static`サポートしていません。

このルールは、プロパティとイベントのアクセサー、演算子のオーバーロードメソッド、または属性<xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute?displayProperty=fullName> <xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute?displayProperty=fullName>または属性のいずれかを使用してマークされたメソッドを無視します。

既定では、アセンブリ、パブリック型、パブリック型のパブリックインスタンスメンバー、およびパブリック値型のすべてのメンバーに対して、COM から参照できます。

このルールを実行するには、次の<xref:System.Runtime.InteropServices.ComVisibleAttribute>コードに示すよう`false`に、アセンブリレベル<xref:System.Runtime.InteropServices.ComVisibleAttribute>をに設定し`true`、クラスをに設定する必要があります。

```csharp
using System;
using System.Runtime.InteropServices;

[assembly: ComVisible(false)]
namespace Samples
{
    [ComVisible(true)]
    public class MyClass
    {
        public static void DoSomething()
        {
        }
    }
}
```

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するには、 `static`メソッドと同じ機能を提供するインスタンスメソッドを使用するようにデザインを変更します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
COM クライアントが`static`メソッドによって提供される機能へのアクセスを必要としない場合は、この規則による警告を抑制しても安全です。

## <a name="example-violation"></a>違反の例

### <a name="description"></a>説明
次の例は、 `static`この規則に違反するメソッドを示しています。

### <a name="code"></a>コード
[!code-csharp[FxCop.Interoperability.ComVisibleStaticMembersViolation#1](../code-quality/codesnippet/CSharp/ca1407-avoid-static-members-in-com-visible-types_1.cs)]

### <a name="comments"></a>コメント
この例では、 **FromPages**のメソッドを COM から呼び出すことはできません。

## <a name="example-fix"></a>修正の例

### <a name="description"></a>説明
前の例の違反を修正するには、メソッドをインスタンスメソッドに変更しますが、このインスタンスでは意味がありません。 より適切な解決策は、 `ComVisible(false)`メソッドを明示的に適用して、メソッドが COM から認識されないことを他の開発者に明確にすることです。

次の例は<xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute> 、メソッドに適用されます。

### <a name="code"></a>コード
[!code-csharp[FxCop.Interoperability.ComVisibleStaticMembersFixed#1](../code-quality/codesnippet/CSharp/ca1407-avoid-static-members-in-com-visible-types_2.cs)]

## <a name="related-rules"></a>関連するルール
[CA1017アセンブリを ComVisibleAttribute にマークします](../code-quality/ca1017-mark-assemblies-with-comvisibleattribute.md)

[CA1406Visual Basic 6 クライアントに対して Int64 引数を使用しない](../code-quality/ca1406-avoid-int64-arguments-for-visual-basic-6-clients.md)

[CA1413COM 参照可能な値型ではパブリックでないフィールドを避けてください](../code-quality/ca1413-avoid-non-public-fields-in-com-visible-value-types.md)

## <a name="see-also"></a>関連項目
[アンマネージ コードとの相互運用](/dotnet/framework/interop/index)