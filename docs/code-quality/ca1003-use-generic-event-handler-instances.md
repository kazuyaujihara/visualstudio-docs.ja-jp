---
title: CA1003:汎用イベント ハンドラーのインスタンスを使用します
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- UseGenericEventHandlerInstances
- CA1003
helpviewer_keywords:
- CA1003
- UseGenericEventHandlerInstances
ms.assetid: 402101b6-555d-4cf7-b223-1d9fdfaaf1cd
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: f666dc71aaf9683d9a7c936cc4985e97146d9454
ms.sourcegitcommit: 2ee11676af4f3fc5729934d52541e9871fb43ee9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "65842525"
---
# <a name="ca1003-use-generic-event-handler-instances"></a>CA1003:汎用イベント ハンドラーのインスタンスを使用します

|||
|-|-|
|TypeName|UseGenericEventHandlerInstances|
|CheckId|CA1003|
|Category|Microsoft.Design|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因

型には、void を返すし、2 つのパラメーター (1 つはオブジェクトと、もう 1 つは EventArgs に割り当て可能な型は)、および含んでいるアセンブリのターゲットの .NET を含むシグネチャを持つデリゲートが含まれています。

既定では、このルールのみが検索に、外部から参照の種類が、これは[構成可能な](#configurability)します。

## <a name="rule-description"></a>規則の説明

.NET では、前に、イベント ハンドラーにカスタム情報を渡すために、新しいデリゲートする必要があるから派生したクラスが指定されている宣言、<xref:System.EventArgs?displayProperty=fullName>クラス。 これは、.NET ではなくなりました。 導入された .NET Framework、<xref:System.EventHandler%601?displayProperty=fullName>デリゲートから派生した任意のクラスを許可するジェネリック デリゲート<xref:System.EventArgs>イベント ハンドラーと共に使用します。

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則の違反を修正するには、デリゲートを削除しを使用してその使用を置き換える、<xref:System.EventHandler%601?displayProperty=fullName>を委任します。

デリゲートは、Visual Basic コンパイラでは、自動生成された場合に使用するイベントの宣言の構文を変更、<xref:System.EventHandler%601?displayProperty=fullName>を委任します。

## <a name="when-to-suppress-warnings"></a>警告を抑制します。

この規則による警告は抑制しないでください。

## <a name="configurability"></a>構成機能

この規則からを実行している場合[FxCop アナライザー](install-fxcop-analyzers.md) (および静的コード分析ではなく)、のどの部分を構成することができます、コードベースでこのルールを実行する、アクセシビリティに基づきます。 など、非パブリック API サーフェイスに対してのみ、ルールを実行するかを指定するには、プロジェクト内の .editorconfig ファイルに次のキー/値ペアを追加します。

```ini
dotnet_code_quality.ca1003.api_surface = private, internal
```

このルールだけ、すべてのルール、またはすべてのルールは、このオプションは、このカテゴリ (デザイン) で構成できます。 詳細については、次を参照してください。[構成 FxCop アナライザー](configure-fxcop-analyzers.md)します。

## <a name="example"></a>例

次の例では、規則に違反するデリゲートを示します。 Visual Basic の例では、コメントは、ルールを満たすために例を変更する方法を説明します。 例では、c# の例で、変更されたコードが表示されるに従います。

[!code-vb[FxCop.Design.CustomEventHandler#1](../code-quality/codesnippet/VisualBasic/ca1003-use-generic-event-handler-instances_1.vb)]
[!code-csharp[FxCop.Design.CustomEventHandler#1](../code-quality/codesnippet/CSharp/ca1003-use-generic-event-handler-instances_1.cs)]

次のコード スニペットでは、前の例は、規則を満たしてから、デリゲート宣言を削除します。 使用を置き換える、`ClassThatRaisesEvent`と`ClassThatHandlesEvent`メソッドを使用して、<xref:System.EventHandler%601?displayProperty=fullName>を委任します。

[!code-csharp[FxCop.Design.GenericEventHandler#1](../code-quality/codesnippet/CSharp/ca1003-use-generic-event-handler-instances_2.cs)]

## <a name="related-rules"></a>関連するルール

- [CA1005:ジェネリック型で過剰なパラメーターを回避します。](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)
- [CA 1010:コレクションは、ジェネリック インターフェイスを実装する必要があります。](../code-quality/ca1010-collections-should-implement-generic-interface.md)
- [CA 1000:ジェネリック型で静的メンバーを宣言しません](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)
- [CA 1002:ジェネリック リストを公開しません](../code-quality/ca1002-do-not-expose-generic-lists.md)
- [CA 1006:ジェネリック型メンバー シグネチャ内で入れ子にしません](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)
- [CA 1004:ジェネリック メソッドは、型パラメーターを指定する必要があります。](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)
- [CA 1007:適切な場所にジェネリックを使用します。](../code-quality/ca1007-use-generics-where-appropriate.md)

## <a name="see-also"></a>関連項目

- [ジェネリック](/dotnet/csharp/programming-guide/generics/index)