---
title: CA2239:オプションのフィールドに逆シリアル化メソッドを提供 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2239
- ProvideDeserializationMethodsForOptionalFields
helpviewer_keywords:
- ProvideDeserializationMethodsForOptionalFields
- CA2239
ms.assetid: 6480ff5e-0caa-4707-814e-2f927cdafef5
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 5bfb682e3b2220a6eb68e7f225e147b8106c3e7c
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58962520"
---
# <a name="ca2239-provide-deserialization-methods-for-optional-fields"></a>CA2239:省略可能なフィールドに、逆シリアル化メソッドを指定します
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|ProvideDeserializationMethodsForOptionalFields|
|CheckId|CA2239|
|カテゴリ|Microsoft.Usage|
|互換性に影響する変更点|中断なし|

## <a name="cause"></a>原因
 型がでマークされているフィールド、<xref:System.Runtime.Serialization.OptionalFieldAttribute?displayProperty=fullName>属性と型が逆シリアル化イベント処理メソッドを提供していません。

## <a name="rule-description"></a>規則の説明
 <xref:System.Runtime.Serialization.OptionalFieldAttribute>属性がシリアル化の影響を与えません。 属性でマークされたフィールドがシリアル化します。 ただし、フィールドは、逆シリアル化では無視され、その種類に関連付けられた既定値が保持されます。 逆シリアル化プロセス中にフィールドを設定するには、逆シリアル化イベント ハンドラーを宣言しなければなりません。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則違反を修正するには、型にメソッドを処理する逆シリアル化イベントを追加します。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 逆シリアル化プロセス中に、フィールドが無視される場合は、この規則による警告を抑制するのには安全です。

## <a name="example"></a>例
 省略可能なフィールドと逆シリアル化イベントを使用して型の処理メソッドを次の例に示します。

 [!code-csharp[FxCop.Usage.OptionalFields#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.OptionalFields/cs/FxCop.Usage.OptionalFields.cs#1)]
 [!code-vb[FxCop.Usage.OptionalFields#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.OptionalFields/vb/FxCop.Usage.OptionalFields.vb#1)]

## <a name="related-rules"></a>関連規則
 [CA2236:ISerializable 型の基本クラス メソッドを呼び出す](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md)

 [CA2240:ISerializable を正しく実装します。](../code-quality/ca2240-implement-iserializable-correctly.md)

 [CA2229: シリアル化コンストラクターを実装します](../code-quality/ca2229-implement-serialization-constructors.md)

 [CA2238:シリアル化メソッドを正しく実装します。](../code-quality/ca2238-implement-serialization-methods-correctly.md)

 [CA2235:すべてのシリアル化不可能なフィールドを設定します](../code-quality/ca2235-mark-all-non-serializable-fields.md)

 [CA2237:ISerializable 型を serializableattribute に設定します](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)

 [CA2120:セキュリティで保護されたシリアル化コンス トラクター](../code-quality/ca2120-secure-serialization-constructors.md)
