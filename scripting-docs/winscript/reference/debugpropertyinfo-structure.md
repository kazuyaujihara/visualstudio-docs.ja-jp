---
title: DebugPropertyInfo 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- DebugPropertyInfo
apilocation:
- scrobj.dll
helpviewer_keywords:
- DebugPropertyInfo structure
ms.assetid: 3246efbc-c212-4024-8f07-6414c2f85e75
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 99208626b41f2463178bccecf73c21a1d15fa765
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62955264"
---
# <a name="debugpropertyinfo-structure"></a>DebugPropertyInfo 構造体
オブジェクトの名前、型、および値を持つ階層的な性質について説明します。 ローカル変数、パラメーター、変数のウォッチ式、およびデバッグ プロパティを記述するために使用され、登録されます。  
  
## <a name="syntax"></a>構文  
  
```cpp
typedef struct DebugPropertyInfo{  
   DBGPROP_INFO_FLAGS  dwValidFields;  
   BSTR  bstrName;  
   BSTR  bstrType;  
   BSTR  bstrValue;  
   BSTR  bstrFullName;  
   DBGPROP_ATTRIB_FLAGS  dwAttrib;  
   IDebugProperty*  pDebugProp;  
};  
```  
  
## <a name="members"></a>メンバー  
 dwValidFields  
 列挙データ型フィールドが初期化されるかを指定するために使用します。  
  
 bstrName  
 コンテキスト内でプロパティ名。  
  
 bstrType  
 プロパティの型、書式設定された文字列。  
  
 bstrValue  
 プロパティの値を書式設定された文字列です。  
  
 bstrFullName  
 プロパティの完全名。  
  
 dwAttrib  
 デバッグ プロパティの属性のフラグを指定する列挙です。  
  
 pDebugProp  
 `IDebugProperty`この情報が記載されている`DebugPropertyInfo`構造体。  
  
## <a name="see-also"></a>関連項目  
 [IDebugProperty インターフェイス](../../winscript/reference/idebugproperty-interface.md)   
 [DBGPROP_ATTRIB_FLAGS](../../winscript/reference/dbgprop-attrib-flags.md)   
 [DBGPROP_INFO_FLAGS](../../winscript/reference/dbgprop-info-flags.md)