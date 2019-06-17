---
title: m_children フィールド |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- m_children field, ContingentProperties class [.NET Framework debug engines]
ms.assetid: 0a3b5653-7bc0-4a7a-8963-9020bc52b9cb
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ab6446b18350fe1f11e0b164d9eb4bff39035ddb
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66330892"
---
# <a name="mchildren-field"></a>m_children フィールド
このタスクで登録されている子タスクの一覧。

 **名前空間:** <xref:System.Threading.Tasks?displayProperty=fullName>

 **アセンブリ:** mscorlib (で*mscorlib.dll*)

 .NET Framework からこの内部メンバーにアクセスできないため、次の構文には共通中間言語 (CIL) が提供されます。

## <a name="syntax"></a>構文

```csharp
.field public class System.Collections.Generic.List`1<class System.Threading.Tasks.Task> m_children
```

## <a name="remarks"></a>Remarks
 タスクの実行中にタスクを実行するスレッドのみがこの配列をアクセスする必要があります。

 タスクが完了した場合、他のスレッドには何も追加またはそこから何も削除されない限り、このフィールドにアクセスすることができます。

## <a name="see-also"></a>関連項目
- [ContingentProperties クラス](../../extensibility/debugger/contingentproperties-class-internal-members.md)