---
title: DOCCONTEXT_COMPARE |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- DOCCONTEXT_COMPARE
helpviewer_keywords:
- DOCCONTEXT_COMPARE enumeration
ms.assetid: ed947c34-b07e-4b69-8381-b6e7cb842862
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: f31b33eeb782e71a87103d26a3bb78175611644e
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66318141"
---
# <a name="doccontextcompare"></a>DOCCONTEXT_COMPARE
2 つのドキュメント コンテキストを比較するための条件を指定します。

## <a name="syntax"></a>構文

```cpp
enum enum_DOCCONTEXT_COMPARE {
    DOCCONTEXT_EQUAL         = 0x0001,
    DOCCONTEXT_LESS_THAN     = 0x0002,
    DOCCONTEXT_GREATER_THAN  = 0x0003,
    DOCCONTEXT_SAME_DOCUMENT = 0x0004
};
typedef DWORD DOCCONTEXT_COMPARE;
```

```csharp
enum enum_DOCCONTEXT_COMPARE {
    DOCCONTEXT_EQUAL         = 0x0001,
    DOCCONTEXT_LESS_THAN     = 0x0002,
    DOCCONTEXT_GREATER_THAN  = 0x0003,
    DOCCONTEXT_SAME_DOCUMENT = 0x0004
};
```

## <a name="fields"></a>フィールド
`DOCCONTEXT_EQUAL`\
ターゲット ドキュメントのコンテキストに相当するリスト内の最初のドキュメント コンテキストを検索します。

`DOCCONTEXT_LESS_THAN`\
ターゲット ドキュメントのコンテキストよりも小さいリスト内の最初のドキュメント コンテキストを検索します。

`DOCCONTEXT_GREATER_THAN`\
ターゲット ドキュメントのコンテキストよりも大きいリスト内の最初のドキュメント コンテキストを検索します。

`DOCCONTEXT_SAME_DOCUMENT`\
ターゲット ドキュメント コンテキストと同じドキュメント内にある一覧で最初のドキュメント コンテキストを検索します。

## <a name="remarks"></a>Remarks
引数として渡される、[比較](../../../extensibility/debugger/reference/idebugdocumentcontext2-compare.md)メソッド。

これらの値は、リストの最初のドキュメント コンテキストを検索するための比較条件の指定に使用されます。 ドキュメントのコンテキストがを介してに対して自身を比較するドキュメント コンテキストの一覧を指定された、`IDebugDocumentContext2::Compare`メソッド。 比較演算子の一覧で最初のドキュメント コンテキスト`true`が返されます。

## <a name="requirements"></a>必要条件
ヘッダー: msdbg.h

名前空間: Microsoft.VisualStudio.Debugger.Interop

アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [列挙型](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [Compare](../../../extensibility/debugger/reference/idebugdocumentcontext2-compare.md)
