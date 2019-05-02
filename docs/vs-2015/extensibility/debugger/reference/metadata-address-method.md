---
title: METADATA_ADDRESS_METHOD | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- METADATA_ADDRESS_METHOD
helpviewer_keywords:
- METADATA_ADDRESS_METHOD structure
ms.assetid: fc0e5370-1b4f-4867-837f-0d63c4b9dd09
caps.latest.revision: 7
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 08a70bc02268e5814982f76cd91dc5d2e2e1cac2
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62547092"
---
# <a name="metadataaddressmethod"></a>METADATA_ADDRESS_METHOD
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

この構造体は、クラスのメソッドのアドレスを表します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
typedef struct _tagMETADATA_ADDRESS_METHOD {  
   _mdToken tokMethod;  
   DWORD    dwOffset;  
   DWORD    dwVersion;  
} METADATA_ADDRESS_METHOD;  
```  
  
```csharp  
public struct METADATA_ADDRESS_METHOD {  
   public int  tokMethod;  
   public uint dwOffset;  
   public uint dwVersion;  
}  
```  
  
## <a name="terms"></a>用語  
 tokMethod  
 メソッドの ID。  
  
 [C++]`_mdToken`は、 `typedef` 32 ビット`int`します。  
  
 dwOffset  
 クラスからのオフセットは、このメソッドが (vtable へのオフセットを表すことができます) を開始します。  
  
 dwVersion  
 (この値は、シンボル プロバイダーに固有) メソッドのバージョン。  
  
## <a name="remarks"></a>Remarks  
 この構造体の共用体の一部は、 [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md)ときに構造体、`dwKind`のフィールド、`DEBUG_ADDRESS_UNION`構造に設定されている`ADDRESS_KIND_METHOD`(からの値、 [ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md)列挙型)。  
  
## <a name="requirements"></a>必要条件  
 ヘッダー: sh.h  
  
 名前空間: Microsoft.VisualStudio.Debugger.Interop  
  
 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>関連項目  
 [構造体と共用体](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md)   
 [ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md)
