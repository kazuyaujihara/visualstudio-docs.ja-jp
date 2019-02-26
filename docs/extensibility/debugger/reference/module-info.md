---
title: MODULE_INFO |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- MODULE_INFO
helpviewer_keywords:
- MODULE_INFO structure
ms.assetid: f2e06180-1ab3-4eb5-a428-7994cceb61b6
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 0e3a11e368b6260d00f3f6ed0b19d94aa26bd31a
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56683611"
---
# <a name="moduleinfo"></a>MODULE_INFO
特定のモジュール (DLL、exe ファイルまたはアセンブリ) について説明します。

## <a name="syntax"></a>構文

```cpp
typedef struct tagMODULE_INFO { 
   MODULE_INFO_FIELDS dwValidFields;
   BSTR               m_bstrName;
   BSTR               m_bstrUrl;
   BSTR               m_bstrVersion;
   BSTR               m_bstrDebugMessage;
   UINT64             m_addrLoadAddress;
   UINT64             m_addrPreferredLoadAddress;
   DWORD              m_dwSize;
   DWORD              m_dwLoadOrder;
   FILETIME           m_TimeStamp;
   BSTR               m_bstrUrlSymbolLocation;
   MODULE_FLAGS       m_dwModuleFlags;
} MODULE_INFO;
```

```csharp
public struct MODULE_INFO { 
   public uint     dwValidFields;
   public string   m_bstrName;
   public string   m_bstrUrl;
   public string   m_bstrVersion;
   public string   m_bstrDebugMessage;
   public ulong    m_addrLoadAddress;
   public ulong    m_addrPreferredLoadAddress;
   public uint     m_dwSize;
   public uint     m_dwLoadOrder;
   public FILETIME m_TimeStamp;
   public string   m_bstrUrlSymbolLocation;
   public uint     m_dwModuleFlags;
};
```

## <a name="members"></a>メンバー
 フラグの組み合わせを dwValidFields A、 [MODULE_INFO_FIELDS](../../../extensibility/debugger/reference/module-info-fields.md)フィールドが記入を指定する列挙体。

 m_bstrName モジュール名。

 m_bstrUrl モジュールの URL。

 m_bstrVersion モジュールのバージョン。

 m_bstrDebugMessage、省略可能なメッセージが、モジュールに関するなど「シンボルを読み込めません」

 m_addrLoadAddress モジュールの読み込みアドレス。

 m_addrPreferredLoadAddress モジュールの標準読み込みアドレス。

 m_dwSize モジュールのサイズ。

 m_dwLoadOrder モジュールの読み込み順序。

 m_TimeStamp シンボル ファイルが最後に変更します。

 m_bstrUrlSymbolLocation シンボル ファイルの場所 (たとえば、".\\")、モジュールで指定します。 開始位置として、モジュールのシンボルを検索するために使用します。

 フラグの組み合わせを m_dwModuleFlags A、 [MODULE_FLAGS](../../../extensibility/debugger/reference/module-flags.md)モジュールを表す列挙体。

## <a name="remarks"></a>Remarks
 この構造体に渡される、 [GetInfo](../../../extensibility/debugger/reference/idebugmodule2-getinfo.md)メソッドでいっぱいになった場所。

 この構造で表示されている各モジュールに対応する、**モジュール**ウィンドウ。

## <a name="requirements"></a>必要条件
 ヘッダー: msdbg.h

 名前空間: Microsoft.VisualStudio.Debugger.Interop

 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [構造体と共用体](../../../extensibility/debugger/reference/structures-and-unions.md)
- [MODULE_INFO_FIELDS](../../../extensibility/debugger/reference/module-info-fields.md)
- [MODULE_FLAGS](../../../extensibility/debugger/reference/module-flags.md)
- [GetInfo](../../../extensibility/debugger/reference/idebugmodule2-getinfo.md)