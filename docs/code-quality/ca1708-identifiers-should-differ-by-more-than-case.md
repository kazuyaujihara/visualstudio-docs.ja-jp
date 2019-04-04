---
title: CA1708:識別子は、大文字と小文字の区別以外にも相違していなければなりません
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- IdentifiersShouldDifferByMoreThanCase
- CA1708
helpviewer_keywords:
- CA1708
- IdentifiersShouldDifferByMoreThanCase
ms.assetid: dac0f01d-dd21-484d-add1-c8cd2bf6969f
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 32ac2e430abdc068070457dcf362e39dcbc0b398
ms.sourcegitcommit: f7c401a376ce410336846835332a693e6159c551
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57867545"
---
# <a name="ca1708-identifiers-should-differ-by-more-than-case"></a>CA1708:識別子は、大文字と小文字の区別以外にも相違していなければなりません

|||
|-|-|
|TypeName|IdentifiersShouldDifferByMoreThanCase|
|CheckId|CA1708|
|Category|Microsoft.Naming|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因

これらは小文字に変換しているときに、2 つの型、メンバー、パラメーター、または完全修飾名前空間の名前は同じです。

既定では、このルールのみが検索で外部から参照可能な型、メンバー、および名前空間が、これは[構成可能な](#configurability)します。

## <a name="rule-description"></a>規則の説明

名前空間、型、メンバー、およびパラメーターの各識別子は、大文字/小文字以外のみでは区別できません。共通言語ランタイムを対象とする言語は、大文字と小文字を区別する必要はないためです。 たとえば、[!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]は広く使用されている大文字言語です。

この規則は、公開されているメンバーのみに適用されます。

## <a name="how-to-fix-violations"></a>違反の修正方法

大文字と小文字の他の識別子を比較した場合に一意の名前を選択します。

## <a name="when-to-suppress-warnings"></a>警告を抑制します。

この規則による警告は抑制しないでください。 ライブラリは、.NET Framework で使用可能なすべての言語で使用できるしない場合があります。

## <a name="configurability"></a>構成機能

この規則からを実行している場合[FxCop アナライザー](install-fxcop-analyzers.md) (および静的コード分析ではなく)、のどの部分を構成することができます、コードベースでこのルールを実行する、アクセシビリティに基づきます。 など、非パブリック API サーフェイスに対してのみ、ルールを実行するかを指定するには、プロジェクト内の .editorconfig ファイルに次のキー/値ペアを追加します。

```
dotnet_code_quality.ca1708.api_surface = private, internal
```

このルールだけ、すべてのルール、またはすべてのルールは、このオプションは、このカテゴリ (名前付け) で構成できます。 詳細については、[構成 FxCop アナライザー](configure-fxcop-analyzers.md)を参照してください。

## <a name="example-of-a-violation"></a>違反の例

次の例では、この規則違反を示します。

[!code-csharp[FxCop.Naming.IdentifiersShouldDifferByMoreThanCase#1](../code-quality/codesnippet/CSharp/ca1708-identifiers-should-differ-by-more-than-case_1.cs)]

## <a name="related-rules"></a>関連するルール

- [CA 1709:識別子では、大文字と小文字が正しく区別する必要があります。](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)