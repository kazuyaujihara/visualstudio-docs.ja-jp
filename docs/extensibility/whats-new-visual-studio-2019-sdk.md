---
title: 新機能については、Visual Studio 2019 SDK |Microsoft Docs
ms.date: 03/29/2019
ms.topic: conceptual
ms.assetid: 4a07607b-0c87-4866-acd8-6d68358d6a47
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d4be152cfb39ddea9ddaeea56464a3447be4f2c6
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66320602"
---
# <a name="whats-new-in-the-visual-studio-2019-sdk"></a>Visual Studio 2019 SDK の新機能

Visual Studio SDK では、Visual Studio 2019 の次の新規および更新の機能があります。

## <a name="synchronously-autoloaded-extensions-warning"></a>同期的に自動的に読み込む拡張の警告

同期的に起動時に自動的に読み込むには、インストール済みの拡張機能のいずれかの場合、ユーザーは警告が表示されます。 表示される警告についての詳細については、[同期的に自動的に読み込む拡張](synchronously-autoloaded-extensions.md)します。

## <a name="single-unified-visual-studio-sdk"></a>Visual Studio SDK を 1 つに統合

1 つの NuGet パッケージを Visual Studio SDK のすべての資産を入手できるようになりました[Microsoft.VisualStudio.SDK](https://www.nuget.org/packages/microsoft.visualstudio.sdk)します。

## <a name="editor-registration-enhancements"></a>エディターの登録の機能強化

作成されてから、Visual Studio のカスタム エディター登録、エディターは、アフィニティは、特定の拡張子 (.xaml と .rc) を宣言できますまたは任意の拡張機能に適していますがサポートされて (. *)。 エディターの登録のサポートを広げる Visual Studio 2019 16.1 バージョン以降、います。

### <a name="filenames"></a>ファイル名

新しい適用することで、特定のファイル名をサポートしているエディターを登録できますに加え、または、特定のファイルの拡張機能のサポートを登録する代わりに、`ProvideEditorFilename`属性エディターのパッケージをします。

たとえば、すべての .json ファイルをサポートするエディターが適用されますこの`ProvideEditorExtension`属性をそのパッケージ。

```cs
[ProvideEditorExtension(typeof(MyEditor), ".json", MyEditor.Priority)]
```

16.1、以降 MyEditor には、いくつかのよく知られている .json ファイルのみサポートしている場合、代わりに適用できるこれら`ProvideEditorFilename`そのパッケージに属性します。

```cs
[ProvideEditorFilename(typeof(MyEditor), "particular.json", MyEditor.Priority)]
[ProvideEditorFilename(typeof(MyEditor), "special.json",    MyEditor.Priority)]
```

### <a name="uicontexts"></a>UIContexts

エディターでは、有効にする場合を表す 1 つまたは複数の UIContexts を登録できます。 UIContexts が 1 つまたは複数のインスタンスを適用することで登録されている`ProvideEditorUIContextAttribute`エディターを登録するパッケージにします。

場合は、エディターでは、登録済みの UIContexts があります。

- 特定の拡張子を持つファイルを開いたときに、少なくとも 1 つの登録済みの UIContexts の機能がアクティブで、エディターの検索で、エディターが含まれます。
- 登録済みの UIContexts のアクティブな場合、エディターは、エディターの検索には含まれません。

エディターでは、任意の UIContexts を登録しない場合は、その拡張子のエディターの検索に常に含まれます。

たとえば、ときに、エディターが使用可能なだけの場合、C#プロジェクトを開くと、適用することでこのアフィニティを宣言できますが、`ProvideEditorUIContext`属性。

```cs
[ProvideEditorUIContext(typeof(MyEditor), KnownUIContexts.CSharpProjectContext)]
```
