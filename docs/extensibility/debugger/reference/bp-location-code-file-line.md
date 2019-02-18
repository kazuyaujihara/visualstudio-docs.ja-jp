---
title: BP_LOCATION_CODE_FILE_LINE |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- BP_LOCATION_CODE_FILE_LINE
helpviewer_keywords:
- BP_LOCATION_CODE_FILE_LINE structure
ms.assetid: 3ff32032-d412-44d3-91bf-870cc354a09e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 5ab7a0b226b7a8fac779e5c5109700a37e60d9d0
ms.sourcegitcommit: 752f03977f45169585e407ef719450dbe219b7fc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2019
ms.locfileid: "56315704"
---
# <a name="bplocationcodefileline"></a>BP_LOCATION_CODE_FILE_LINE
コードのソース ファイル内の特定の行のブレークポイントの場所のデータが含まれています。

## <a name="syntax"></a>構文

```cpp
typedef struct _BP_LOCATION_CODE_FILE_LINE {
    BSTR                     bstrContext;
    IDebugDocumentPosition2* pDocPos;
} BP_LOCATION_CODE_FILE_LINE;
```

## <a name="members"></a>メンバー
`bstrContext`  
ブレークポイントのコンテキスト、通常は呼び出し履歴で見られる同様のメソッドまたは関数の名前。

`pDocPos`  
[IDebugDocumentPosition2](../../../extensibility/debugger/reference/idebugdocumentposition2.md)ドキュメントのブレークポイントの位置を表すオブジェクト。

## <a name="remarks"></a>Remarks
この構造体のメンバーである、 [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md)構造体、共用体の一部として。

## <a name="requirements"></a>必要条件
ヘッダー: msdbg.h

名前空間: Microsoft.VisualStudio.Debugger.Interop

アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
[構造体と共用体](../../../extensibility/debugger/reference/structures-and-unions.md)  
[BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md)  
[IDebugDocumentPosition2](../../../extensibility/debugger/reference/idebugdocumentposition2.md)
