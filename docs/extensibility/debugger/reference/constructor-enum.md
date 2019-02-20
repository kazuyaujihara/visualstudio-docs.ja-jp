---
title: CONSTRUCTOR_ENUM |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- CONSTRUCTOR_ENUM
helpviewer_keywords:
- CONSTRUCTOR_ENUM enumeration
ms.assetid: 6d335b2c-66bc-460c-a4a6-4f3f1b697c2c
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: bd5067591f4f296825db6362f4a7b91f1a7a37e8
ms.sourcegitcommit: 7153e2fc717d32e0e9c8a9b8c406dc4053c9fd53
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2019
ms.locfileid: "56412813"
---
# <a name="constructorenum"></a>CONSTRUCTOR_ENUM
さまざまな種類のコンス トラクターを選択します。

## <a name="syntax"></a>構文

```cpp
typedef enum ConstructorMatchOptions {
    crAll       = 0,
    crNonStatic = 1,
    crStatic    = 2
} CONSTRUCTOR_ENUM;
```

```csharp
public enum ConstructorMatchOptions {
    crAll       = 0,
    crNonStatic = 1,
    crStatic    = 2
};
```

## <a name="members"></a>メンバー
crAll  
すべてのコンス トラクターを選択します。

crNonStatic  
非静的コンス トラクターを選択します。

crStatic  
静的コンス トラクターを選択します。

## <a name="remarks"></a>Remarks
引数として渡される、 [EnumConstructors](../../../extensibility/debugger/reference/idebugclassfield-enumconstructors.md)メソッド。

## <a name="requirements"></a>必要条件
ヘッダー: sh.h

名前空間: Microsoft.VisualStudio.Debugger.Interop

アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
[列挙型](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)  
[GetReason](../../../extensibility/debugger/reference/idebugcanstopevent2-getreason.md)
