---
title: CA2208:引数の例外を正しくインスタンス化します
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2208
- InstantiateArgumentExceptionsCorrectly
helpviewer_keywords:
- InstantiateArgumentExceptionsCorrectly
- CA2208
ms.assetid: e2a48939-d9fa-478c-b2f9-3bdbce07dff7
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 9f9425ab1ea9eadd3bd06d950118ce83ba5c35f9
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71231643"
---
# <a name="ca2208-instantiate-argument-exceptions-correctly"></a>CA2208:引数の例外を正しくインスタンス化します

|||
|-|-|
|TypeName|InstantiateArgumentExceptionsCorrectly|
|CheckId|CA2208|
|カテゴリ|Microsoft.Usage|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因

次のような状況が考えられます。

- 、、 <xref:System.ArgumentException>またはから派生した例外の種類の既定の (パラメーターなしの) コンストラクターが呼び出されました。

- 不適切な文字列引数が、、、またはから<xref:System.ArgumentException>派生した例外の種類のパラメーター化されたコンストラクターに渡されています。

## <a name="rule-description"></a>規則の説明

既定のコンストラクターを呼び出す代わりに、より意味のある例外メッセージを提供できるコンストラクターのオーバーロードのいずれかを呼び出します。 例外メッセージは、開発者を対象とし、エラー状態と、例外を修正または回避する方法を明確に説明する必要があります。

とその派生型の<xref:System.ArgumentException> 1 つの文字列コンストラクターおよび2つの文字列コンストラクターのシグネチャは、位置`message`と`paramName`パラメーターに関して一貫性がありません。 正しい文字列引数を使用して、これらのコンストラクターが呼び出されていることを確認します。 署名は次のとおりです。

- <xref:System.ArgumentException>(文字列`message`)
- <xref:System.ArgumentException>(string `message`, string `paramName`)
- <xref:System.ArgumentNullException>(文字列`paramName`)
- <xref:System.ArgumentNullException>(string `paramName`, string `message`)
- <xref:System.ArgumentOutOfRangeException>(文字列`paramName`)
- <xref:System.ArgumentOutOfRangeException>(string `paramName`, string `message`)
- <xref:System.DuplicateWaitObjectException>(文字列`parameterName`)
- <xref:System.DuplicateWaitObjectException>(string `parameterName`, string `message`)

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則違反を修正するには、メッセージ、パラメーター名、またはその両方を受け取るコンストラクターを呼び出し、呼び出されるの<xref:System.ArgumentException>型に対して引数が適切であることを確認します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

パラメーター化されたコンストラクターが正しい文字列引数で呼び出された場合にのみ、この規則からの警告を抑制しても安全です。

## <a name="example"></a>例

次のコードは、の<xref:System.ArgumentNullException>インスタンスを誤ってインスタンス化するコンストラクターを示しています。

[!code-cpp[FxCop.Usage.InstantiateArgumentExceptionsCorrectly#1](../code-quality/codesnippet/CPP/ca2208-instantiate-argument-exceptions-correctly_1.cpp)]
[!code-csharp[FxCop.Usage.InstantiateArgumentExceptionsCorrectly#1](../code-quality/codesnippet/CSharp/ca2208-instantiate-argument-exceptions-correctly_1.cs?range=3-6)]
[!code-vb[FxCop.Usage.InstantiateArgumentExceptionsCorrectly#1](../code-quality/codesnippet/VisualBasic/ca2208-instantiate-argument-exceptions-correctly_1.vb)]

次のコードでは、コンストラクターの引数を切り替えることによって、以前の違反を修正します。

[!code-cpp[FxCop.Usage.InstantiateArgumentExceptionsCorrectly#2](../code-quality/codesnippet/CPP/ca2208-instantiate-argument-exceptions-correctly_2.cpp)]
[!code-csharp[FxCop.Usage.InstantiateArgumentExceptionsCorrectly#2](../code-quality/codesnippet/CSharp/ca2208-instantiate-argument-exceptions-correctly_2.cs?range=3-6)]
[!code-vb[FxCop.Usage.InstantiateArgumentExceptionsCorrectly#2](../code-quality/codesnippet/VisualBasic/ca2208-instantiate-argument-exceptions-correctly_2.vb)]

## <a name="related-rules"></a>関連するルール

- [CA1507:文字列の代わりに文字列を使用する](ca1507.md)