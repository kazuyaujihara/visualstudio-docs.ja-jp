---
title: CA2007:タスクを直接待機しません
ms.date: 03/08/2019
ms.topic: reference
f1_keywords:
- CA2007
- DoNotDirectlyAwaitATaskAnalyzer
helpviewer_keywords:
- CA2007
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
ms.openlocfilehash: 8e94b67d1924e2144f658cd6bcd5989751efdb85
ms.sourcegitcommit: 1024f336dcd8e8a4c50b9a9ad8ec85b6e70073a8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57699681"
---
# <a name="ca2007-do-not-directly-await-a-task"></a>CA2007:タスクを直接待機しません

|||
|-|-|
|TypeName|DoNotDirectlyAwaitATaskAnalyzer|
|CheckId|CA2007|
|Category|Microsoft.Reliability|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因

非同期メソッド[待機](/dotnet/csharp/language-reference/keywords/await)、<xref:System.Threading.Tasks.Task>直接します。

## <a name="rule-description"></a>規則の説明

非同期のメソッドを待機すると、<xref:System.Threading.Tasks.Task>タスクを作成した同じスレッドで直接、継続が発生します。 この動作は、パフォーマンスの観点からコスト高にすることができます、UI スレッドでデッドロックが発生することができます。 呼び出し元を検討してください。 <xref:System.Threading.Tasks.Task.ConfigureAwait(System.Boolean)?displayProperty=nameWithType> 、意図したものの継続を通知します。

このルールで導入された[FxCop アナライザー](install-fxcop-analyzers.md) 「レガシー」(静的コード分析) が存在しない FxCop します。

## <a name="how-to-fix-violations"></a>違反の修正方法

違反を修正するのには、呼び出す<xref:System.Threading.Tasks.Task.ConfigureAwait%2A>、待機中に<xref:System.Threading.Tasks.Task>します。 いずれかを渡すことができます`true`または`false`の`continueOnCapturedContext`パラメーター。

- 呼び出す`ConfigureAwait(true)`タスクが明示的に呼び出すことと同じ動作<xref:System.Threading.Tasks.Task.ConfigureAwait%2A>します。 このメソッドを明示的に呼び出すには、意図的に、元の同期コンテキストで継続を実行する必要がある読者をれてしまいます。

- 呼び出す`ConfigureAwait(false)`、スレッド プールに継続をスケジュールするタスクの UI スレッドでデッドロックが発生を回避するためです。 渡す`false`アプリに依存しないライブラリに適したオプションです。

## <a name="when-to-suppress-warnings"></a>警告を抑制します。

この警告を抑制するには、コンシューマーは、グラフィカル ユーザー インターフェイス (GUI) アプリではないか、コンシューマーがないかどうかがわかっている場合、<xref:System.Threading.SynchronizationContext>します。

## <a name="example"></a>例

次のコード スニペットでは、警告が生成されます。

```csharp
public async Task Execute()
{
    Task task = null;
    await task;
}
```

違反を修正するには、呼び出す<xref:System.Threading.Tasks.Task.ConfigureAwait%2A>、待機中に<xref:System.Threading.Tasks.Task>:

```csharp
public async Task Execute()
{
    Task task = null;
    await task.ConfigureAwait(false);
}
```

## <a name="see-also"></a>関連項目

- [Configureawait (false) でのタスクを待機する必要がありますか。](https://github.com/Microsoft/vs-threading/blob/master/doc/cookbook_vs.md#should-i-await-a-task-with-configureawaitfalse)
- [FxCop アナライザーを Visual Studio をインストールします。](install-fxcop-analyzers.md)