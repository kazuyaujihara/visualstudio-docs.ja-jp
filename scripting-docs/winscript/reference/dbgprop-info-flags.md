---
title: DBGPROP_INFO_FLAGS | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- DBGPROP_INFO_FLAGS
apilocation:
- scrobj.dll
f1_keywords:
- DBGPROP_INFO_FLAGS
helpviewer_keywords:
- DBGPROP_INFO_FLAGS
ms.assetid: e9450a21-a802-4c3e-8b3d-8e202f555de1
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c63cf941bca1965fc4a2e3997f0c0b50ebc44035
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62955303"
---
# <a name="dbgpropinfoflags"></a>DBGPROP_INFO_FLAGS
指定するために使用`DebugPropertyInfo`フィールド  
  
## <a name="syntax"></a>構文  
  
```cpp
enum {  
   DBGPROP_INFO_NAME  =0x001,  
   DBGPROP_INFO_TYPE  =0x002,  
   DBGPROP_INFO_VALUE  =0x004,  
   DBGPROP_INFO_FULLNAME  =0x020,  
   DBGPROP_INFO_ATTRIBUTES  =0x008,  
   DBGPROP_INFO_DEBUGPROP  =0x010,  
   DBGPROP_INFO_AUTOEXPAND  =0x8000000  
};  
```  
  
## <a name="members"></a>メンバー  
 DBGPROP_INFO_NAME  
 初期化します、`bstrName`フィールド。  
  
 DBGPROP_INFO_TYPE  
 初期化します、`bstrType`フィールド。  
  
 DBGPROP_INFO_VALUE  
 初期化します、`bstrValue`フィールド。  
  
 DBGPROP_INFO_FULLNAME  
 初期化します、`bstrFullName`フィールド。  
  
 DBGPROP_INFO_ATTRIBUTES  
 初期化します、`dwAttrib`フィールド。  
  
 DBGPROP_INFO_DEBUGPROP  
 初期化します、`pDebugProp`フィールドを含む、`IDebugProperty`インターフェイス。  
  
 DBGPROP_INFO_AUTOEXPAND  
 [値] フィールドは、この種類のオブジェクトの使用可能な場合は、自動拡張値を含める必要がありますを指定します。  
  
## <a name="see-also"></a>関連項目  
 [DebugPropertyInfo 構造体](../../winscript/reference/debugpropertyinfo-structure.md)   
 [IDebugProperty インターフェイス](../../winscript/reference/idebugproperty-interface.md)