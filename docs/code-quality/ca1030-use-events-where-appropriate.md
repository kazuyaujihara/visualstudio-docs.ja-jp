---
title: CA1030:適切な場所にイベントを使用します
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- UseEventsWhereAppropriate
- CA1030
helpviewer_keywords:
- CA1030
- UseEventsWhereAppropriate
ms.assetid: ea051367-deeb-40f9-9b65-eb818f1e133a
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1054fa7b884c23edb76248cba17bab41cc64246f
ms.sourcegitcommit: f7c401a376ce410336846835332a693e6159c551
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57867433"
---
# <a name="ca1030-use-events-where-appropriate"></a>CA1030:適切な場所にイベントを使用します

|||
|-|-|
|TypeName|UseEventsWhereAppropriate|
|CheckId|CA1030|
|Category|Microsoft.Design|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因

メソッド名は、次のいずれかで始まります。

- アドオン
- RemoveOn
- 起動
- 発生させる

既定では、このルールだけを確認、外部から参照できるメソッドが、これは[構成可能な](#configurability)します。

## <a name="rule-description"></a>規則の説明

この規則では、通常はイベントに使用される名前を持つメソッドを検出します。 イベントがオブザーバーまたは公開/定期受信デザイン パターンに従ってください。1 つのオブジェクトの状態の変更は、その他のオブジェクトに伝達する必要があるときに使用されます。 明確に定義された状態の変更に応答するメソッドの呼び出しの場合、イベント ハンドラーで、メソッドを呼び出します。 メソッドを呼び出すオブジェクトは、メソッドを直接呼び出すのではなく、イベントを発生させる必要があります。

イベントの一般的な例は、ボタンのクリックしてなどのユーザー アクションを実行するコードのセグメントによって、ユーザー インターフェイス アプリケーションで表示されます。 .NET Framework のイベント モデルはユーザー インターフェイスに限定されません。必ず使用状態が 1 つまたは複数のオブジェクトに変更を伝達する必要があります。

## <a name="how-to-fix-violations"></a>違反の修正方法

オブジェクトの状態が変更されたときに、メソッドを呼び出すと、.NET のイベント モデルを使用してデザインを変更するかを検討してください。

## <a name="when-to-suppress-warnings"></a>警告を抑制します。

.NET のイベント モデルには、メソッドが機能しない場合は、このルールによる警告を抑制します。

## <a name="configurability"></a>構成機能

この規則からを実行している場合[FxCop アナライザー](install-fxcop-analyzers.md) (および静的コード分析ではなく)、のどの部分を構成することができます、コードベースでこのルールを実行する、アクセシビリティに基づきます。 など、非パブリック API サーフェイスに対してのみ、ルールを実行するかを指定するには、プロジェクト内の .editorconfig ファイルに次のキー/値ペアを追加します。

```
dotnet_code_quality.ca1030.api_surface = private, internal
```

このルールだけ、すべてのルール、またはすべてのルールは、このオプションは、このカテゴリ (デザイン) で構成できます。 詳細については、[構成 FxCop アナライザー](configure-fxcop-analyzers.md)を参照してください。