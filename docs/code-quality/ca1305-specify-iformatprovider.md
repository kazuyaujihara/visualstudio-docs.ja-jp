---
title: CA1305:IFormatProvider を指定します
ms.date: 06/30/2018
ms.topic: reference
f1_keywords:
- SpecifyIFormatProvider
- CA1305
helpviewer_keywords:
- CA1305
- SpecifyIFormatProvider
ms.assetid: fb34ed9a-4eab-47cc-8eef-3068a4a1397e
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- multiple
ms.openlocfilehash: a9f6c8fd44749de43d86bf8037df0130ad682321
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71235033"
---
# <a name="ca1305-specify-iformatprovider"></a>CA1305:IFormatProvider を指定します

|||
|-|-|
|TypeName|SpecifyIFormatProvider|
|CheckId|CA1305|
|カテゴリ|Microsoft のグローバリゼーション|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因

メソッドまたはコンストラクターが、 <xref:System.IFormatProvider?displayProperty=fullName>パラメーターを受け取るオーバーロードを持つ1つ以上のメンバーを呼び出します。このメソッドまたはコンストラクターは、 <xref:System.IFormatProvider>パラメーターを受け取るオーバーロードを呼び出しません。

このルールは、 <xref:System.IFormatProvider>パラメーターを無視するように記述されている .net メソッドの呼び出しを無視します。 ルールでは、次のメソッドも無視されます。

- <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType>
- <xref:System.Resources.ResourceManager.GetObject%2A?displayProperty=nameWithType>
- <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType>

## <a name="rule-description"></a>規則の説明

<xref:System.Globalization.CultureInfo?displayProperty=nameWithType>オブジェクトまた<xref:System.IFormatProvider>はオブジェクトが指定されていない場合、オーバーロードされたメンバーによって提供される既定値は、すべてのロケールで必要な結果を得られない可能性があります。 また、.NET メンバーは、コードに対して正しくない可能性がある仮定に基づいて、既定のカルチャと書式設定を選択します。 実際のシナリオに合わせてコードが期待どおりに動作することを確認するには、次のガイドラインに従って、カルチャ固有の情報を指定する必要があります。

- 値がユーザーに表示される場合は、現在のカルチャを使用します。 以下を参照してください。<xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType>

- 値がソフトウェアによって保存およびアクセスされる (ファイルまたはデータベースに保存される) 場合は、インバリアントカルチャを使用します。 以下を参照してください。<xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>

- 値の変換先がわからない場合は、データコンシューマーまたはプロバイダーによってカルチャが指定されていることを確認してください。

オーバーロードされたメンバーの既定の動作がニーズに適している場合でも、コードが自己文書化され、より簡単に管理できるように、カルチャ固有のオーバーロードを明示的に呼び出すことをお勧めします。

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則違反を修正するには、 <xref:System.IFormatProvider>引数を受け取るオーバーロードを使用します。 または、使用して、 [C# 文字列補間する](/dotnet/csharp/tutorials/string-interpolation)に渡すと、<xref:System.FormattableString.Invariant%2A?displayProperty=nameWithType>メソッド。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

既定の形式が正しい選択であることがわかっている場合や、コードの保守容易性が重要な開発の優先順位でない場合は、この規則による警告を抑制することが安全です。

## <a name="example"></a>例

次のコードでは、 `example1`文字列がルール CA1305 に違反しています。 文字列`example2`は、を<xref:System.IFormatProvider>実装するを<xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType>に<xref:System.String.Format(System.IFormatProvider,System.String,System.Object)?displayProperty=nameWithType>渡すことによって、ルール CA1305 を満たします。 文字列`example3`は、に<xref:System.FormattableString.Invariant%2A?displayProperty=fullName]>補間文字列を渡すことによって、ルール CA1305 を満たします。

```csharp
string name = "Georgette";

// Violates CA1305
string example1 = String.Format("Hello {0}", name);

// Satisfies CA1305
string example2 = String.Format(CultureInfo.CurrentCulture, "Hello {0}", name);

// Satisfies CA1305
string example3 = FormattableString.Invariant($"Hello {name}");
```

## <a name="related-rules"></a>関連するルール

- [CA1304CultureInfo を指定する](../code-quality/ca1304-specify-cultureinfo.md)

## <a name="see-also"></a>関連項目

- [CultureInfo クラスの使用](/dotnet/standard/globalization-localization/globalization#work-with-culture-specific-settings)