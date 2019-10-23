---
title: DBGPROP_INFO_FLAGS |Microsoft Docs
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
ms.openlocfilehash: 5b8131531292e0f88108942648073883050dd609
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72572583"
---
# <a name="dbgprop_info_flags"></a>DBGPROP_INFO_FLAGS
@No__t_0 フィールドを指定するために使用されます  
  
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
 @No__t_0 フィールドを初期化します。  
  
 DBGPROP_INFO_TYPE  
 @No__t_0 フィールドを初期化します。  
  
 DBGPROP_INFO_VALUE  
 @No__t_0 フィールドを初期化します。  
  
 DBGPROP_INFO_FULLNAME  
 @No__t_0 フィールドを初期化します。  
  
 DBGPROP_INFO_ATTRIBUTES  
 @No__t_0 フィールドを初期化します。  
  
 DBGPROP_INFO_DEBUGPROP  
 @No__t_1 インターフェイスを含む `pDebugProp` フィールドを初期化します。  
  
 DBGPROP_INFO_AUTOEXPAND  
 値フィールドに、この型のオブジェクトの自動展開値 (使用可能な場合) が含まれていることを指定します。  
  
## <a name="see-also"></a>関連項目  
 [DebugPropertyInfo 構造体](../../winscript/reference/debugpropertyinfo-structure.md)   
 [IDebugProperty インターフェイス](../../winscript/reference/idebugproperty-interface.md)