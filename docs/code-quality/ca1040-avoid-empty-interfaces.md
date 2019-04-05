---
title: CA1040:空のインターフェイスは使用しません
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- CA1040
- AvoidEmptyInterfaces
helpviewer_keywords:
- AvoidEmptyInterfaces
- CA1040
ms.assetid: 120a741b-5fd1-4836-8453-7857e0cd0380
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 726953de0a92c0237ecaf7b724d9586a5d0f4c16
ms.sourcegitcommit: f7c401a376ce410336846835332a693e6159c551
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57868731"
---
# <a name="ca1040-avoid-empty-interfaces"></a>CA1040:空のインターフェイスは使用しません

|||
|-|-|
|TypeName|AvoidEmptyInterfaces|
|CheckId|CA1040|
|Category|Microsoft.Design|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因

インターフェイスのメンバーの宣言または他の 2 つ以上のインターフェイスの実装はできません。

既定では、このルールだけを確認、外部から参照できるインターフェイスが、これは[構成可能な](#configurability)します。

## <a name="rule-description"></a>規則の説明

インターフェイスには、動作や使用のコントラクトを実現するメンバーが定義されます。 インターフェイスで示される機能は、継承の階層構造内に型が存在するかどうかにかかわらず、どの型からも適用できます。 型ではインターフェイスのメンバーに実装することで、インターフェイスが実装されます。 空のインターフェイスでは、すべてのメンバーは定義しません。 そのため、実装できるコントラクトは定義しません。

空のデザインが含まれている場合、型インターフェイスの実装が期待される、マーカーまたは型のグループを識別する方法として、インターフェイスを使用している可能性があります。 この id は実行時に発生した場合、これを実現する正しい方法は、カスタム属性を使用します。 対象の種類を識別するために存在するか、属性がない場合や、属性のプロパティを使用します。 Id は、空のインターフェイスを使用することができますし、コンパイル時に行う必要があります。 場合、

## <a name="how-to-fix-violations"></a>違反の修正方法

インターフェイスを削除するか、メンバーを追加します。 空のインターフェイスは、型のセットのラベル付けに使用されているが場合、は、カスタム属性を持つインターフェイスを置き換えます。

## <a name="when-to-suppress-warnings"></a>警告を抑制します。

コンパイル時に一連の型を識別するために、インターフェイスを使用する場合、この規則による警告を抑制するのには安全です。

## <a name="configurability"></a>構成機能

この規則からを実行している場合[FxCop アナライザー](install-fxcop-analyzers.md) (および静的コード分析ではなく)、のどの部分を構成することができます、コードベースでこのルールを実行する、アクセシビリティに基づきます。 など、非パブリック API サーフェイスに対してのみ、ルールを実行するかを指定するには、プロジェクト内の .editorconfig ファイルに次のキー/値ペアを追加します。

```
dotnet_code_quality.ca1040.api_surface = private, internal
```

このルールだけ、すべてのルール、またはすべてのルールは、このオプションは、このカテゴリ (デザイン) で構成できます。 詳細については、[構成 FxCop アナライザー](configure-fxcop-analyzers.md)を参照してください。

## <a name="example"></a>例

次の例では、空のインターフェイスを示します。

[!code-csharp[FxCop.Design.InterfacesNotEmpty#1](../code-quality/codesnippet/CSharp/ca1040-avoid-empty-interfaces_1.cs)]
[!code-cpp[FxCop.Design.InterfacesNotEmpty#1](../code-quality/codesnippet/CPP/ca1040-avoid-empty-interfaces_1.cpp)]
[!code-vb[FxCop.Design.InterfacesNotEmpty#1](../code-quality/codesnippet/VisualBasic/ca1040-avoid-empty-interfaces_1.vb)]