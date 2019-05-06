---
title: THREADPROPERTIES |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- THREADPROPERTIES
helpviewer_keywords:
- THREADPROPERTIES structure
ms.assetid: 7d397207-db03-4ec0-9f79-3794056ed89f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 55b3334c8bd28d3975f06aa39ca8c7fd719f1f9e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62913354"
---
# <a name="threadproperties"></a>THREADPROPERTIES
スレッドのプロパティについて説明します。

## <a name="syntax"></a>構文

```cpp
typedef struct _tagTHREADPROPERTIES { 
   THREADPROPERTY_FIELDS dwFields;
   DWORD                 dwThreadId;
   DWORD                 dwSuspendCount;
   DWORD                 dwThreadState;
   BSTR                  bstrPriority;
   BSTR                  bstrName;
   BSTR                  bstrLocation;
} THREADPROPERTIES;
```

```csharp
public struct THREADPROPERTIES { 
   public uint   dwFields;
   public uint   dwThreadId;
   public uint   dwSuspendCount;
   public uint   dwThreadState;
   public string bstrPriority;
   public string bstrName;
   public string bstrLocation;
};
```

## <a name="members"></a>メンバー
 フラグの組み合わせを dwFields A、 [THREADPROPERTY_FIELDS](../../../extensibility/debugger/reference/threadproperty-fields.md)有効ではこの構造体のフィールドを記述する列挙。

 dwThreadId スレッドの id。

 dwSuspendCount スレッドは中断回数です。

 dwThreadState A 値から、 [THREADSTATE](../../../extensibility/debugger/reference/threadstate.md)動作のスレッドの状態を示す列挙値。

 bstrPriority スレッドの優先順位を指定する文字列たとえば、"上記 Normal"、"Normal"または「時間は重要な」。

 bstName スレッド名。

 bstrLocation 通常実行が中断されているメソッドの名前として表現されるスレッドの場所 (通常は最上位のスタック フレーム)。

## <a name="remarks"></a>Remarks
 この構造体への呼び出しによって入力されます、 [GetThreadProperties](../../../extensibility/debugger/reference/idebugthread2-getthreadproperties.md)メソッド。 そのために返される情報は通常設定で使用、**スレッド**ウィンドウ。

## <a name="requirements"></a>必要条件
 ヘッダー: msdbg.h

 名前空間: Microsoft.VisualStudio.Debugger.Interop

 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [構造体と共用体](../../../extensibility/debugger/reference/structures-and-unions.md)
- [GetThreadProperties](../../../extensibility/debugger/reference/idebugthread2-getthreadproperties.md)
- [THREADPROPERTY_FIELDS](../../../extensibility/debugger/reference/threadproperty-fields.md)
- [THREADSTATE](../../../extensibility/debugger/reference/threadstate.md)