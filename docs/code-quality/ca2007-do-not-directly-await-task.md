---
title: CA2007:タスクを直接待機しないでください
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
ms.openlocfilehash: 0d3ab899ad660c637492a4c3d229779481184e95
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2019
ms.locfileid: "69547016"
---
# <a name="ca2007-do-not-directly-await-a-task"></a>CA2007:タスクを直接待機しないでください

|||
|-|-|
|TypeName|DoNotDirectlyAwaitATaskAnalyzer|
|CheckId|CA2007|
|Category|Microsoft.Reliability|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因

非同期メソッドは、を<xref:System.Threading.Tasks.Task>直接[待機](/dotnet/csharp/language-reference/keywords/await)します。

## <a name="rule-description"></a>規則の説明

非同期メソッドがを<xref:System.Threading.Tasks.Task>直接待機する場合、継続はタスクを作成したのと同じスレッドで発生します。 この動作は、パフォーマンスに関してはコストが高く、UI スレッドでデッドロックが発生する可能性があります。 を呼び出し<xref:System.Threading.Tasks.Task.ConfigureAwait(System.Boolean)?displayProperty=nameWithType>て、継続の意図を知らせることを検討してください。

この規則は[fxcop アナライザー](install-fxcop-analyzers.md)で導入されたもので、従来の FxCop 分析には存在しません。

## <a name="how-to-fix-violations"></a>違反の修正方法

違反を修正するに<xref:System.Threading.Tasks.Task.ConfigureAwait%2A>は、待機<xref:System.Threading.Tasks.Task>したでを呼び出します。 パラメーターには、 `true`また`false`はのいずれかを渡すことができます。 `continueOnCapturedContext`

- タスク`ConfigureAwait(true)`でを呼び出すと、明示的にを呼び<xref:System.Threading.Tasks.Task.ConfigureAwait%2A>出さない場合と同じ動作が行われます。 このメソッドを明示的に呼び出すことにより、元の同期コンテキストで継続を実行することをユーザーに知らせることができます。

- タスク`ConfigureAwait(false)`でを呼び出して、継続をスレッドプールにスケジュールします。これにより、UI スレッドでデッドロックが発生するのを回避できます。 を`false`渡すことは、アプリに依存しないライブラリに適したオプションです。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

コンシューマーがグラフィカルユーザーインターフェイス (GUI) アプリでないことがわかっている場合、またはコンシューマーがを<xref:System.Threading.SynchronizationContext>持っていない場合は、この警告を非表示にすることができます。

## <a name="example"></a>例

次のコードスニペットでは、警告が生成されます。

```csharp
public async Task Execute()
{
    Task task = null;
    await task;
}
```

違反を修正するには<xref:System.Threading.Tasks.Task.ConfigureAwait%2A> 、待機<xref:System.Threading.Tasks.Task>したでを呼び出します。

```csharp
public async Task Execute()
{
    Task task = null;
    await task.ConfigureAwait(false);
}
```

## <a name="configurability"></a>かつ

値を返さない非同期メソッドをこの規則から除外するかどうかを構成できます。 これらの種類のメソッドを除外するには、プロジェクトの editorconfig ファイルに次のキーと値のペアを追加します。

```ini
# Package version 2.9.0 and later
dotnet_code_quality.CA2007.exclude_async_void_methods = true

# Package version 2.6.3 and earlier
dotnet_code_quality.CA2007.skip_async_void_methods = true
```

また、この規則を適用する出力アセンブリの種類を構成することもできます。 たとえば、コンソールアプリケーションまたは動的にリンクされたライブラリ (つまり、UI アプリではない) を生成するコードにのみこの規則を適用するには、プロジェクトの editorconfig ファイルに次のキーと値のペアを追加します。

```ini
dotnet_code_quality.CA2007.output_kind = ConsoleApplication, DynamicallyLinkedLibrary
```

詳細については、「 [FxCop アナライザーの構成](configure-fxcop-analyzers.md)」を参照してください。

## <a name="see-also"></a>関連項目

- [ConfigureAwait を使用してタスクを待機する必要がありますか (false)?](https://github.com/Microsoft/vs-threading/blob/master/doc/cookbook_vs.md#should-i-await-a-task-with-configureawaitfalse)
- [Visual Studio で FxCop アナライザーをインストールする](install-fxcop-analyzers.md)