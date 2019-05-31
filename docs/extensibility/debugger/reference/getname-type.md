---
title: GETNAME_TYPE |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- GETNAME_TYPE
helpviewer_keywords:
- GETNAME_TYPE enumeration
ms.assetid: 2f9f1679-e9e8-4c9c-ac90-aa07bfe69914
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 1bdcbc4171c8a481ee0c45456ef5600f5150c6d0
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66317581"
---
# <a name="getnametype"></a>GETNAME_TYPE
取得するファイルの名前の種類を指定します。

## <a name="syntax"></a>構文

```cpp
enum enum_GETNAME_TYPE {
    GN_NAME         = 0,
    GN_FILENAME     = 1,
    GN_BASENAME     = 2,
    GN_MONIKERNAME  = 3,
    GN_URL          = 4,
    GN_TITLE        = 5,
    GN_STARTPAGEURL = 6
};
typedef DWORD GETNAME_TYPE;
```

```csharp
public enum enum_GETNAME_TYPE {
    GN_NAME         = 0,
    GN_FILENAME     = 1,
    GN_BASENAME     = 2,
    GN_MONIKERNAME  = 3,
    GN_URL          = 4,
    GN_TITLE        = 5,
    GN_STARTPAGEURL = 6
};
```

## <a name="fields"></a>フィールド
`GN_NAME`\
ドキュメントまたはコンテキストのフレンドリ名を指定します。

`GN_FILENAME`\
ドキュメントまたはコンテキストの完全なパスを指定します。

`GN_BASENAME`\
ドキュメントまたはコンテキストの完全なパスではなく基本ファイル名を指定します。

`GN_MONIKERNAME`\
モニカーの形式でドキュメントまたはコンテキストの一意の名前を指定します。

`GN_URL`\
ドキュメントまたはコンテキストの URL 名を指定します。

`GN_TITLE`\
存在する場合は、ドキュメントのタイトルを指定します。

`GN_STARTPAGEURL`\
プロセスの開始ページの URL を取得します。

## <a name="remarks"></a>Remarks
これらの値をパラメーターとして渡される、 [GetName](../../../extensibility/debugger/reference/idebugdocument2-getname.md)、 [GetName](../../../extensibility/debugger/reference/idebugdocumentcontext2-getname.md)、および[GetName](../../../extensibility/debugger/reference/idebugprocess2-getname.md)メソッド名を返しますの種類を指定します。

## <a name="requirements"></a>必要条件
ヘッダー: msdbg.h

名前空間: Microsoft.VisualStudio.Debugger.Interop

アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [列挙型](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
- [GetName](../../../extensibility/debugger/reference/idebugdocument2-getname.md)
- [GetName](../../../extensibility/debugger/reference/idebugdocumentcontext2-getname.md)
- [GetName](../../../extensibility/debugger/reference/idebugprocess2-getname.md)
