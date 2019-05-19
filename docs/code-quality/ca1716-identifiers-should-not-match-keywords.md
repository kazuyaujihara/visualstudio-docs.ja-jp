---
title: CA1716:識別子はキーワードと同一にすることはできません
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- IdentifiersShouldNotMatchKeywords
- CA1716
helpviewer_keywords:
- IdentifiersShouldNotMatchKeywords
- CA1716
ms.assetid: 900cc8a1-1089-4069-a4ce-10b109ac4fab
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 47bbb39cadb6a092f71ebd7b3907f34fcc2782ce
ms.sourcegitcommit: 2ee11676af4f3fc5729934d52541e9871fb43ee9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "65842047"
---
# <a name="ca1716-identifiers-should-not-match-keywords"></a>CA1716:識別子はキーワードと同一にすることはできません

|||
|-|-|
|TypeName|IdentifiersShouldNotMatchKeywords|
|CheckId|CA1716|
|Category|Microsoft.Naming|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因

名前空間、型、または仮想またはインターフェイス メンバーのプログラミング言語で予約済みキーワードに一致します。

既定では、このルールのみが検索で外部から参照できる名前空間、型、およびメンバーが、これは[構成可能な](#configurability)します。

## <a name="rule-description"></a>規則の説明

識別子の名前空間、型、および仮想インターフェイス メンバーを共通言語ランタイムを対象とする言語で定義されているキーワードと一致する必要があります。 によって使用される言語とキーワードの場合は、コンパイラのエラーやあいまいさづらくなる可能性、ライブラリを使用します。

このルールは、次の言語のキーワードを確認します。

- Visual Basic
- C#
- C++/CLI

Visual Basic のキーワードの大文字と小文字が使用され、その他の言語に大文字小文字の比較が使用されます。

## <a name="how-to-fix-violations"></a>違反の修正方法

キーワードの一覧に表示されていない名前を選択します。

## <a name="when-to-suppress-warnings"></a>警告を抑制します。

識別子はありません、API のユーザーが混乱することと、ライブラリは .NET で使用可能なすべての言語で使用できることを確信している場合は、この規則による警告を抑制できます。

## <a name="configurability"></a>構成機能

この規則からを実行している場合[FxCop アナライザー](install-fxcop-analyzers.md) (および静的コード分析ではなく)、のどの部分を構成することができます、コードベースでこのルールを実行する、アクセシビリティに基づきます。 など、非パブリック API サーフェイスに対してのみ、ルールを実行するかを指定するには、プロジェクト内の .editorconfig ファイルに次のキー/値ペアを追加します。

```ini
dotnet_code_quality.ca1716.api_surface = private, internal
```

このルールだけ、すべてのルール、またはすべてのルールは、このオプションは、このカテゴリ (名前付け) で構成できます。 詳細については、次を参照してください。[構成 FxCop アナライザー](configure-fxcop-analyzers.md)します。