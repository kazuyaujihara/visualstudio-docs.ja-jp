---
title: CA1725:パラメーター名は基本宣言と同一でなければなりません
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- ParameterNamesShouldMatchBaseDeclaration
- CA1725
helpviewer_keywords:
- CA1725
- ParameterNamesShouldMatchBaseDeclaration
ms.assetid: 9b657ab0-fe81-4f4c-9481-ba746988c922
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 457051fa9701aac81c92389d6d33e125f5064f1e
ms.sourcegitcommit: f7c401a376ce410336846835332a693e6159c551
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57873413"
---
# <a name="ca1725-parameter-names-should-match-base-declaration"></a>CA1725:パラメーター名は基本宣言と同一でなければなりません

|||
|-|-|
|TypeName|ParameterNamesShouldMatchBaseDeclaration|
|CheckId|CA1725|
|Category|Microsoft.Naming|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因

メソッドのオーバーライドでのパラメーターの名前は、基本メソッドの宣言のパラメーターの名前またはメソッドのインターフェイス宣言のパラメーターの名前と一致しません。

既定では、このルールだけを確認、外部から参照できるメソッドが、これは[構成可能な](#configurability)します。

## <a name="rule-description"></a>規則の説明

オーバーライド階層のパラメーターに対する一貫性のある名前付けによって、メソッド オーバーライドの有用性が高まります。 派生メソッドのパラメーター名が基本宣言のパラメーター名と異なる場合、メソッドが基本メソッドのオーバーライドであるか、またはメソッドの新しいオーバーライドであるかについて混乱が生じる可能性があります。

## <a name="how-to-fix-violations"></a>違反の修正方法

このルールの違反を修正するには、基本宣言と一致するパラメーターの名前を変更します。 修正プログラムは、COM 参照可能なメソッドの互換性に影響する変更です。

## <a name="when-to-suppress-warnings"></a>警告を抑制します。

以前に出荷されたライブラリ内の COM 参照可能なメソッドを除き、この規則による警告を抑制しないでください。

## <a name="configurability"></a>構成機能

この規則からを実行している場合[FxCop アナライザー](install-fxcop-analyzers.md) (および静的コード分析ではなく)、のどの部分を構成することができます、コードベースでこのルールを実行する、アクセシビリティに基づきます。 など、非パブリック API サーフェイスに対してのみ、ルールを実行するかを指定するには、プロジェクト内の .editorconfig ファイルに次のキー/値ペアを追加します。

```
dotnet_code_quality.ca1725.api_surface = private, internal
```

このルールだけ、すべてのルール、またはすべてのルールは、このオプションは、このカテゴリ (名前付け) で構成できます。 詳細については、[構成 FxCop アナライザー](configure-fxcop-analyzers.md)を参照してください。