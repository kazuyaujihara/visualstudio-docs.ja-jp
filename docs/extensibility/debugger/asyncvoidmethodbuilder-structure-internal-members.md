---
title: AsyncVoidMethodBuilder 構造体の内部メンバー |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debug engines, AsyncVoidMethodBuilder structure [.NET Framework]
- AsyncVoidMethodBuilder structure [.NET Framework debug engines]
ms.assetid: fe2970ab-d4c5-4355-a8e4-772ee0a57178
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 109f7d0491420ce4f3df2179dad15a582213d439
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66350940"
---
# <a name="asyncvoidmethodbuilder-structure---internal-members"></a>AsyncVoidMethodBuilder 構造体の内部メンバー
このトピックでの内部メンバーの説明、<xref:System.Runtime.CompilerServices.AsyncVoidMethodBuilder>クラス。 このクラスの詳細については、次を参照してください。、<xref:System.Runtime.CompilerServices.AsyncVoidMethodBuilder>リファレンス トピック。

 **名前空間:** <xref:System.Runtime.CompilerServices?displayProperty=fullName>

 **アセンブリ:** mscorlib (mscorlib.dll 内)

 .NET Framework からこれらの内部メンバーにアクセスできないため、次の構文には共通中間言語 (CIL) が提供されます。

## <a name="syntax"></a>構文

```csharp
.class public sequential ansi sealed beforefieldinit System.Runtime.CompilerServices.AsyncVoidMethodBuilder
       extends System.ValueType
       implements System.Runtime.CompilerServices.IAsyncMethodBuilder
```

## <a name="internal-members"></a>内部メンバー

|名前|説明|
|----------|-----------------|
|[ObjectIdForDebugger プロパティ](../../extensibility/debugger/asyncvoidmethodbuilder-objectidfordebugger-property.md)|デバッガーには、このビルダーを一意に識別するために使用するオブジェクトを取得します。|
|[m_objectIdForDebugger フィールド](../../extensibility/debugger/asyncvoidmethodbuilder-m-objectidfordebugger-field.md)|このビルダーを一意に識別するために、デバッガーによって使用される遅れて初期化されるオブジェクトを表します。|

## <a name="see-also"></a>関連項目
- <xref:System.Runtime.CompilerServices.AsyncVoidMethodBuilder>
- [.NET Framework の並列拡張機能の内部](../../extensibility/debugger/parallel-extension-internals-for-the-dotnet-framework.md)