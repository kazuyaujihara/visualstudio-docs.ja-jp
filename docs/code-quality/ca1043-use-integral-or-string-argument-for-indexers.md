---
title: CA1043:インデクサーには整数または文字列引数を使用します
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- CA1043
- UseIntegralOrStringArgumentForIndexers
helpviewer_keywords:
- CA1043
- UseIntegralOrStringArgumentForIndexers
ms.assetid: d7f14b9e-2220-4f80-b6b8-48c655a05701
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: ca381d88524535ad042b5bd3efda25f8cc350fa4
ms.sourcegitcommit: 2ee11676af4f3fc5729934d52541e9871fb43ee9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "65842121"
---
# <a name="ca1043-use-integral-or-string-argument-for-indexers"></a>CA1043:インデクサーには整数または文字列引数を使用します

|||
|-|-|
|TypeName|UseIntegralOrStringArgumentForIndexers|
|CheckId|CA1043|
|Category|Microsoft.Design|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因

型には、他にもインデックスの型を使用するインデクサーが含まれています。 <xref:System.Int32?displayProperty=fullName>、 <xref:System.Int64?displayProperty=fullName>、 <xref:System.Object?displayProperty=fullName>、または<xref:System.String?displayProperty=fullName>します。

既定では、このルールのみが検索に、パブリックおよびプロテクトの種類が、これは[構成可能な](#configurability)します。

## <a name="rule-description"></a>規則の説明

インデクサー、つまり、インデックス付きプロパティは、インデックスの整数または文字列型を使用する必要があります。 これらの型は、通常データ構造のインデックス作成に使用され、ライブラリのユーザビリティを向上させます。 使用、<xref:System.Object>型がデザイン時に特定の整数または文字列型を指定できない場合に限定する必要があります。 設計では、インデックスの他の種類が必要とする場合は、型は、論理データ ストアを表すかどうかを再確認します。 論理データ ストアを表さない場合は、メソッドを使用します。

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則違反を修正するには、整数または文字列型にインデックスを変更またはインデクサーではなく、メソッドを使用します。

## <a name="when-to-suppress-warnings"></a>警告を抑制します。

非標準のインデクサーの必要性を慎重に検討した後にのみこの規則による警告を抑制します。

## <a name="configurability"></a>構成機能

この規則からを実行している場合[FxCop アナライザー](install-fxcop-analyzers.md) (および静的コード分析ではなく)、のどの部分を構成することができます、コードベースでこのルールを実行する、アクセシビリティに基づきます。 など、非パブリック API サーフェイスに対してのみ、ルールを実行するかを指定するには、プロジェクト内の .editorconfig ファイルに次のキー/値ペアを追加します。

```ini
dotnet_code_quality.ca1043.api_surface = private, internal
```

このルールだけ、すべてのルール、またはすべてのルールは、このオプションは、このカテゴリ (デザイン) で構成できます。 詳細については、次を参照してください。[構成 FxCop アナライザー](configure-fxcop-analyzers.md)します。

## <a name="example"></a>例

次の例では、インデクサーを使用する、<xref:System.Int32>インデックス。

[!code-csharp[FxCop.Design.IntegralOrStringIndexers#1](../code-quality/codesnippet/CSharp/ca1043-use-integral-or-string-argument-for-indexers_1.cs)]
[!code-cpp[FxCop.Design.IntegralOrStringIndexers#1](../code-quality/codesnippet/CPP/ca1043-use-integral-or-string-argument-for-indexers_1.cpp)]
[!code-vb[FxCop.Design.IntegralOrStringIndexers#1](../code-quality/codesnippet/VisualBasic/ca1043-use-integral-or-string-argument-for-indexers_1.vb)]

## <a name="related-rules"></a>関連するルール

- [CA 1023:インデクサーを多次元することはできません。](../code-quality/ca1023-indexers-should-not-be-multidimensional.md)
- [CA 1024:適切な場所のプロパティを使用します。](../code-quality/ca1024-use-properties-where-appropriate.md)