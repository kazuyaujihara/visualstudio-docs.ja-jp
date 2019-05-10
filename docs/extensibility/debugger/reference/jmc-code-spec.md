---
title: JMC_CODE_SPEC |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- JMC_CODE_SPEC
helpviewer_keywords:
- JMC_CODE_SPEC structure
ms.assetid: d89498f1-4234-46d9-b4e2-abbcbca5068a
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 4fe0a804922296e26846b9b477091883c742253e
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/09/2019
ms.locfileid: "65458098"
---
# <a name="jmccodespec"></a>JMC_CODE_SPEC
この構造体は、モジュールの JustMyCode 情報の設定に使用されます。

## <a name="syntax"></a>構文

```cpp
typedef struct _JMC_CODE_SPEC {
    BOOL fIsUserCode;
    BSTR bstrModuleName;
} JMC_CODE_SPEC;
```

```csharp
public struct JMC_CODE_SPEC {
    public int    fIsUserCode;
    public string bstrModuleName;
};
```

## <a name="members"></a>メンバー
`fIsUserCode`\
0 以外の値 (`TRUE`) モジュールは、ユーザー コードと見なす場合は、0 (`FALSE`) モジュールが外部コードとして扱うとデバッグする場合。

`bstrModuleName`\
対象のモジュールの名前。

## <a name="remarks"></a>Remarks
このような構造の一覧としてこの構造体が渡される、 [SetJustMyCodeState](../../../extensibility/debugger/reference/idebugengine3-setjustmycodestate.md)メソッド。

## <a name="requirements"></a>必要条件
ヘッダー: msdbg.h

名前空間: Microsoft.VisualStudio.Debugger.Interop

アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [構造体と共用体](../../../extensibility/debugger/reference/structures-and-unions.md)
- [SetJustMyCodeState](../../../extensibility/debugger/reference/idebugengine3-setjustmycodestate.md)
