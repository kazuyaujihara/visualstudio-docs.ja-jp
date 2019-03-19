---
title: JS_PROPERTY_ATTRIBUTES 列挙型 |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- JS_PROPERTY_ATTRIBUTES
apilocation:
- jscript9diag.dll
ms.assetid: e83b9b6c-5b21-48d1-92b6-22bed926b18b
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 27aaadfd1d3ff38e9a0382ff1863b73d2bccc325
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58153488"
---
# <a name="jspropertyattributes-enumeration"></a>JS_PROPERTY_ATTRIBUTES 列挙型
プロパティの属性を指定します。  
  
## <a name="syntax"></a>構文  
  
```cpp
enum JS_PROPERTY_ATTRIBUTES{   JS_PROPERTY_ATTRIBUTE_NONE = 0,   JS_PROPERTY_HAS_CHILDREN = 0x1,   JS_PROPERTY_FAKE = 0x2,   JS_PROPERTY_METHOD = 0x4,   JS_PROPERTY_READONLY = 0x8,   JS_PROPERTY_NATIVE_WINRT_POINTER = 0x10} JS_PROPERTY_ATTRIBUTES;  
```  
  
## <a name="members"></a>メンバー  
  
|名前|説明|  
|----------|-----------------|  
|`JS_PROPERTY_ATTRIBUTE_NONE`|プロパティに属性がありません。|  
|`JS_PROPERTY_HAS_CHILDREN`|プロパティに子があります。|  
|`JS_PROPERTY_FAKE`|プロパティは、"[Methods]"などの偽のノードを表します。|  
|`JS_PROPERTY_METHOD`|プロパティはメソッドです。|  
|`JS_PROPERTY_READONLY`|プロパティは読み取り専用です。|  
|`JS_PROPERTY_NATIVE_WINRT_POINTER`|プロパティは、ネイティブ WinRT オブジェクトへのポインターです。|  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** jscript9diag.h です  
  
## <a name="see-also"></a>関連項目  
 [Windows スクリプト インターフェイスのリファレンス](../../winscript/reference/windows-script-interfaces-reference.md)