---
title: CA1303:ローカライズされるパラメーターとしてリテラルを渡さない
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- Do not pass literals as localized parameters
- DoNotPassLiteralsAsLocalizedParameters
- CA1303
helpviewer_keywords:
- DoNotPassLiteralsAsLocalizedParameters
- CA1303
ms.assetid: 904d284e-76d0-4b8f-a4df-0094de8d7aac
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 2700dc2ade7ba901f15f67045e3170e2bbb40ff8
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71235115"
---
# <a name="ca1303-do-not-pass-literals-as-localized-parameters"></a>CA1303:ローカライズされるパラメーターとしてリテラルを渡さない

|||
|-|-|
|TypeName|DoNotPassLiteralsAsLocalizedParameters|
|CheckId|CA1303|
|カテゴリ|Microsoft のグローバリゼーション|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因

メソッドは、.NET コンストラクターまたはメソッドにパラメーターとして文字列リテラルを渡し、その文字列はローカライズ可能である必要があります。

この警告は、リテラル文字列が値としてパラメーターまたはプロパティに渡され、次の1つ以上のケースが true の場合に発生します。

- パラメーター <xref:System.ComponentModel.LocalizableAttribute>またはプロパティの属性が true に設定されています。

- パラメーターまたはプロパティ名には、"Text"、"Message"、または "Caption" が含まれています。

- Console に渡される文字列パラメーターの名前です。 Write または Console. WriteLine メソッドは、"value" または "format" のいずれかです。

## <a name="rule-description"></a>規則の説明

ソースコードに埋め込まれている文字列リテラルをローカライズするのは困難です。

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則違反を修正するには、文字列リテラルを<xref:System.Resources.ResourceManager>クラスのインスタンスを通じて取得される文字列に置き換えます。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

コードライブラリがローカライズされない場合、またはコードライブラリを使用して、エンドユーザーまたは開発者に対して文字列が公開されていない場合は、この規則による警告を抑制することが安全です。

ユーザーは、パラメーターまたはプロパティの名前を変更するか、これらの項目を条件付きとしてマークすることによって、ローカライズされた文字列を渡さないメソッドに対するノイズを除去できます。

## <a name="example"></a>例

次の例は、2つの引数のいずれかが範囲外にある場合に例外をスローするメソッドを示しています。 最初の引数では、この規則に違反するリテラル文字列が例外コンストラクターに渡されます。 2番目の引数のコンストラクターには、から<xref:System.Resources.ResourceManager>取得した文字列が正しく渡されます。

[!code-cpp[FxCop.Globalization.DoNotPassLiterals#1](../code-quality/codesnippet/CPP/ca1303-do-not-pass-literals-as-localized-parameters_1.cpp)]
[!code-vb[FxCop.Globalization.DoNotPassLiterals#1](../code-quality/codesnippet/VisualBasic/ca1303-do-not-pass-literals-as-localized-parameters_1.vb)]
[!code-csharp[FxCop.Globalization.DoNotPassLiterals#1](../code-quality/codesnippet/CSharp/ca1303-do-not-pass-literals-as-localized-parameters_1.cs)]

## <a name="see-also"></a>関連項目

- [デスクトップアプリのリソース](/dotnet/framework/resources/index)