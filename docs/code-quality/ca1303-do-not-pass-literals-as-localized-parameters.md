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
ms.openlocfilehash: cc32db1aea9c5514a7548bc889b65463de3de3d5
ms.sourcegitcommit: 5483e399f14fb01f528b3b194474778fd6f59fa6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2019
ms.locfileid: "66714688"
---
# <a name="ca1303-do-not-pass-literals-as-localized-parameters"></a>CA1303:ローカライズされるパラメーターとしてリテラルを渡さない

|||
|-|-|
|TypeName|DoNotPassLiteralsAsLocalizedParameters|
|CheckId|CA1303|
|カテゴリ|Microsoft.Globalization|
|互換性に影響する変更点|中断なし|

## <a name="cause"></a>原因

メソッドを文字列リテラルをパラメーターとして渡し .NET コンス トラクターまたはメソッドにして、その文字列はローカライズ可能にする必要があります。

パラメーターまたはプロパティにリテラル文字列が値として渡され、1 つ以上の次の場合は true、この警告が発生します。

- <xref:System.ComponentModel.LocalizableAttribute>パラメーターまたはプロパティの属性が設定を true にします。

- パラメーターまたはプロパティ名には、"Text"、"Message"または「キャプション」が含まれています。

- Console.Write"または"Console.WriteLine メソッドに渡される文字列パラメーターの名前は、"value"または「形式」のいずれかです。

## <a name="rule-description"></a>規則の説明

ソース コードに埋め込まれている文字列リテラルは、ローカライズが困難です。

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則の違反を修正するには、インスタンスを通じて取得された文字列を文字列リテラルを置き換える、<xref:System.Resources.ResourceManager>クラス。

## <a name="when-to-suppress-warnings"></a>警告を抑制します。

コード ライブラリはローカライズされていない場合、または文字列が、エンドユーザーまたはコード ライブラリを使用して開発者に公開されない場合は、この規則による警告を抑制しても安全になります。

ユーザーは、渡すことはできませんローカライズされた文字列パラメーターまたはプロパティを名前変更、またはこれらのアイテムを条件付きとしてマークすることによってメソッドに対してノイズを回避できます。

## <a name="example"></a>例

次の例では、範囲外の 2 つの引数のいずれかのときに例外をスローするメソッドを示します。 最初の引数の例外のコンス トラクターに、この規則に違反するリテラル文字列が渡されます。 2 番目の引数のコンス トラクターが正しく渡されますを介して取得された文字列を<xref:System.Resources.ResourceManager>します。

[!code-cpp[FxCop.Globalization.DoNotPassLiterals#1](../code-quality/codesnippet/CPP/ca1303-do-not-pass-literals-as-localized-parameters_1.cpp)]
[!code-vb[FxCop.Globalization.DoNotPassLiterals#1](../code-quality/codesnippet/VisualBasic/ca1303-do-not-pass-literals-as-localized-parameters_1.vb)]
[!code-csharp[FxCop.Globalization.DoNotPassLiterals#1](../code-quality/codesnippet/CSharp/ca1303-do-not-pass-literals-as-localized-parameters_1.cs)]

## <a name="see-also"></a>関連項目

- [デスクトップ アプリでのリソース](/dotnet/framework/resources/index)