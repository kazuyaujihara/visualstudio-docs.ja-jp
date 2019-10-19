---
title: IDebugPropertyEnumType_All Interface |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugPropertyEnumType_All
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDebugPropertyEnumType_All interface
ms.assetid: 4d0f4fd5-e5f7-47cb-b746-860d6363e2cd
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 737d1c5d4279a0a727f79326749dbf14a2fcd4c7
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72574313"
---
# <a name="idebugpropertyenumtype_all-interface"></a>IDebugPropertyEnumType_All インターフェイス
@No__t_0 インターフェイスは、適切な列挙子を要求しているときに、各 Iid がを `IDebugProperty::EnumMembers` にフィルターとして渡すことができるように定義されています。  
  
## <a name="syntax"></a>構文  
  
```cpp
IDebugPropertyEnumType_All : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド  
  
|メソッド|説明|  
|------------|-----------------|  
|[IDebugPropertyEnumType_All::GetName](../../winscript/reference/idebugpropertyenumtype-all-getname.md)|名前を説明するテキスト文字列を返します。|  
  
 次のインターフェイスは `IDebugPropertyEnumType_All` から継承し、追加のメソッドはありません。  
  
```cpp
IDebugPropertyEnumType_Arguments : IDebugPropertyEnumType_All   
IDebugPropertyEnumType_Locals : IDebugPropertyEnumType_All   
IDebugPropertyEnumType_LocalsPlusArgs : IDebugPropertyEnumType_All   
IDebugPropertyEnumType_Registers : IDebugPropertyEnumType_All  
```  
  
## <a name="see-also"></a>関連項目  
 [IDebugProperty::EnumMembers](../../winscript/reference/idebugproperty-enummembers.md)