---
title: CA1720:識別子には型名を含めないでください
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- CA1720
- IdentifiersShouldNotContainTypeNames
helpviewer_keywords:
- IdentifiersShouldNotContainTypeNames
- CA1720
ms.assetid: c95ee48f-f23a-45f0-ac9e-a3c1ecfabdea
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d0eb7cfeb2271b7ed01f59d4892987fb2ef72808
ms.sourcegitcommit: f7c401a376ce410336846835332a693e6159c551
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57867720"
---
# <a name="ca1720-identifiers-should-not-contain-type-names"></a>CA1720:識別子には型名を含めないでください

|||
|-|-|
|TypeName|IdentifiersShouldNotContainTypeNames|
|CheckId|CA1720|
|Category|Microsoft.Naming|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因

メンバーのパラメーターの名前には、データ型の名前が含まれています。

- または -

メンバーの名前には、言語固有のデータ型の名前が含まれています。

既定では、このルールだけを確認、外部から参照できるメンバーが、これは[構成可能な](#configurability)します。

## <a name="rule-description"></a>規則の説明

パラメーターおよびメンバーの名前は、その意味は、開発ツールが提供する予定されている、型を説明するよりもを通信に使用される向上します。 データ型の名前を使用する場合は、メンバーの名前は、言語固有ではなく、言語に依存しない名前を使用します。 例については、代わりに、C#型名`int`、使用言語に依存しないデータ型の名前、`Int32`します。

各トークンのパラメーターまたはメンバーの名前は、大文字と小文字で、次の言語に固有のデータ型名に対してチェックされます。

- Bool
- WChar
- Int8
- UInt8
- Short
- UShort
- Int
- UInt
- 整数型
- UInteger
- Long
- ULong
- 符号なし
- 符号付き
- Float
- float32
- float64

さらに、パラメーターの名前もチェックされます、次の言語に依存しないデータ型名に対して大文字と小文字。

- Object
- obj
- ブール型
- Char
- String
- SByte
- Byte
- UByte
- Int16
- UInt16
- Int32
- UInt32
- Int64
- UInt64
- IntPtr
- ptr
- ポインター
- UInptr
- UPtr
- UPointer
- Single
- 倍精度浮動小数点型
- Decimal (10 進数型)
- GUID

## <a name="how-to-fix-violations"></a>違反の修正方法

**場合は、パラメーターに対して起動します。**

パラメーターの名前のデータ型識別子をその意味をより詳しく説明している用語をまたは 'value' などの汎用的な用語のいずれかに置き換えます。

**メンバーに対して起動: 場合**

その意味、言語に依存しないに相当する、または 'value' などの汎用的な用語をより詳しく説明している用語を言語に固有のデータ型識別子、メンバーの名前に置き換えます。

## <a name="when-to-suppress-warnings"></a>警告を抑制します。

型に基づくパラメーターおよびメンバーの名前は、適切な可能性があります。 ただし、新規の開発、されていないシナリオが発生する、この規則による警告を抑制する必要があります。 以前に出荷されたライブラリでは、この規則による警告を抑制する必要があります。

## <a name="configurability"></a>構成機能

この規則からを実行している場合[FxCop アナライザー](install-fxcop-analyzers.md) (および静的コード分析ではなく)、のどの部分を構成することができます、コードベースでこのルールを実行する、アクセシビリティに基づきます。 など、非パブリック API サーフェイスに対してのみ、ルールを実行するかを指定するには、プロジェクト内の .editorconfig ファイルに次のキー/値ペアを追加します。

```
dotnet_code_quality.ca1720.api_surface = private, internal
```

このルールだけ、すべてのルール、またはすべてのルールは、このオプションは、このカテゴリ (名前付け) で構成できます。 詳細については、次を参照してください。[構成 FxCop アナライザー](configure-fxcop-analyzers.md)します。

## <a name="related-rules"></a>関連するルール

- [CA 1709:識別子では、大文字と小文字が正しく区別する必要があります。](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)
- [CA1708:識別子は、ケース以外で相違させる必要があります。](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)
- [CA 1707:識別子はアンダー スコアを含めることはできません。](../code-quality/ca1707-identifiers-should-not-contain-underscores.md)
- [CA1719:パラメーター名は、メンバー名と一致する必要があります。](../code-quality/ca1719-parameter-names-should-not-match-member-names.md)