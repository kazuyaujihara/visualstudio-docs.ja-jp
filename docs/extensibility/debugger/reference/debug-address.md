---
title: DEBUG_ADDRESS |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- DEBUG_ADDRESS
helpviewer_keywords:
- DEBUG_ADDRESS structure
ms.assetid: 79f5e765-9aac-4b6e-82ef-bed88095e9ba
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 1d5851fd9fe7224d060b1454a7123b98f77216b4
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2018
ms.locfileid: "49813480"
---
# <a name="debugaddress"></a>DEBUG_ADDRESS
この構造体では、アドレスを表します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
typedef struct _tagDEBUG_ADDRESS {  
   ULONG32             ulAppDomainID;  
   GUID                guidModule;  
   _mdToken            tokClass;  
   DEBUG_ADDRESS_UNION addr;  
} DEBUG_ADDRESS;  
```  
  
```csharp  
public struct DEBUG_ADDRESS {  
   public uint                ulAppDomainID;  
   public Guid                guidModule;  
   public int                 tokClass;  
   public DEBUG_ADDRESS_UNION addr;  
}  
```  
  
## <a name="terms"></a>用語  
 ulAppDomainID  
 プロセス id です。  
  
 guidModule  
 このアドレスを含むモジュールの GUID です。  
  
 tokClass  
 クラスまたはこのアドレスの種類を識別するトークンです。  
  
> [!NOTE]
>  この値は、シンボル プロバイダーに固有で、クラス型の識別子として以外の一般的な意味を持たない。  
  
 Addr  
 A [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md)構造体は、個々 のアドレスの種類を記述する構造体の共用体が含まれています。 値`addr`します。`dwKind` [ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md)列挙体、共用体を解釈する方法について説明します。  
  
## <a name="remarks"></a>Remarks  
 この構造体に渡される、 [GetAddress](../../../extensibility/debugger/reference/idebugaddress-getaddress.md)情報を格納するメソッド。  
  
 **警告 [C++ のみ]**  
  
 場合`addr.dwKind`は`ADDRESS_KIND_METADATA_LOCAL`場合`addr.addr.addrLocal.pLocal`呼び出す必要がありますし、null 値でない`Release`トークンのポインターで。  
  
```  
if (addr.dwKind == ADDRESS_KIND_METADATA_LOCAL &&  addr.addr.addrLocal.pLocal != NULL)  
{  
    addr.addr.addrLocal.pLocal->Release();  
}  
```  
  
## <a name="requirements"></a>必要条件  
 ヘッダー: sh.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 アセンブリ: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>関連項目  
 [構造体と共用体](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [GetAddress](../../../extensibility/debugger/reference/idebugaddress-getaddress.md)   
 [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md)   
 [ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md)