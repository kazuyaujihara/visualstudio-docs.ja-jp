---
title: PROFILER_HEAP_OBJECT_OPTIONAL_INFO_TYPE 列挙型 |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: fcb55f5f-ce75-4d05-9ce9-ba28c622f97d
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0a56b05c572ec5d91914dd046bfdfa39224a07de
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62823609"
---
# <a name="profilerheapobjectoptionalinfotype-enumeration"></a>PROFILER_HEAP_OBJECT_OPTIONAL_INFO_TYPE 列挙型
別の種類のオプション情報を表します。 使用される[PROFILER_HEAP_OBJECT_OPTIONAL_INFO 構造体](../../winscript/reference/profiler-heap-object-optional-info-structure.md)します。  
  
## <a name="syntax"></a>構文  
  
```cpp
typedef [v1_enum] enum {    PROFILER_HEAP_OBJECT_OPTIONAL_INFO_PROTOTYPE                    = 0x00000001,    PROFILER_HEAP_OBJECT_OPTIONAL_INFO_FUNCTION_NAME                = 0x00000002,    PROFILER_HEAP_OBJECT_OPTIONAL_INFO_SCOPE_LIST                   = 0x00000003,    PROFILER_HEAP_OBJECT_OPTIONAL_INFO_INTERNAL_PROPERTY            = 0x00000004,    PROFILER_HEAP_OBJECT_OPTIONAL_INFO_NAME_PROPERTIES              = 0x00000005,    PROFILER_HEAP_OBJECT_OPTIONAL_INFO_INDEX_PROPERTIES             = 0x00000006,    PROFILER_HEAP_OBJECT_OPTIONAL_INFO_ELEMENT_ATTRIBUTES_SIZE      = 0x00000007,    PROFILER_HEAP_OBJECT_OPTIONAL_INFO_ELEMENT_TEXT_CHILDREN_SIZE   = 0x00000008,    PROFILER_HEAP_OBJECT_OPTIONAL_INFO_RELATIONSHIPS                = 0x00000009,    PROFILER_HEAP_OBJECT_OPTIONAL_INFO_WINRTEVENTS                  = 0x0000000A,    PROFILER_HEAP_OBJECT_OPTIONAL_INFO_MAX_VALUE                    = PROFILER_HEAP_OBJECT_OPTIONAL_INFO_WINRTEVENTS} PROFILER_HEAP_OBJECT_OPTIONAL_INFO_TYPE;  
```  
  
## <a name="members"></a>メンバー  
  
|メンバー|[値]|説明|  
|------------|-----------|-----------------|  
|PROFILER_HEAP_OBJECT_OPTIONAL_INFO_PROTOTYPE|0x00000001|ヒープ オブジェクトのプロトタイプについて説明します。|  
|PROFILER_HEAP_OBJECT_OPTIONAL_INFO_FUNCTION_NAME|0x00000002|ヒープ オブジェクトの関数名について説明します。|  
|PROFILER_HEAP_OBJECT_OPTIONAL_INFO_SCOPE_LIST|0x00000003|については、ヒープのオブジェクトの[PROFILER_HEAP_OBJECT_SCOPE_LIST 構造体](../../winscript/reference/profiler-heap-object-scope-list-structure.md)します。|  
|PROFILER_HEAP_OBJECT_OPTIONAL_INFO_INTERNAL_PROPERTY|0x00000004|ヒープ オブジェクトの内部プロパティに関する情報。|  
|PROFILER_HEAP_OBJECT_OPTIONAL_INFO_NAME_PROPERTIES|0x00000005|ヒープ オブジェクトの名前のプロパティに関する情報。|  
|PROFILER_HEAP_OBJECT_OPTIONAL_INFO_INDEX_PROPERTIES|0x00000006|ヒープ オブジェクトのインデックスのプロパティに関する情報。|  
|PROFILER_HEAP_OBJECT_OPTIONAL_INFO_ELEMENT_ATTRIBUTES_SIZE|0x00000007|DOM 要素に関連付けられている属性のサイズ。|  
|PROFILER_HEAP_OBJECT_OPTIONAL_INFO_ELEMENT_TEXT_CHILDREN_SIZE|0x00000008|DOM 要素に関連付けられている任意のテキストのサイズ。|  
|PROFILER_HEAP_OBJECT_OPTIONAL_INFO_RELATIONSHIPS|0x00000009|ヒープ オブジェクトの関係に関する情報。|  
|ROFILER_HEAP_OBJECT_OPTIONAL_INFO_WINRTEVENTS|0x0000000A|ヒープ オブジェクトの Windows ランタイム イベントに関する情報。|  
|PROFILER_HEAP_OBJECT_OPTIONAL_INFO_MAX_VALUE|PROFILER_HEAP_OBJECT_OPTIONAL_INFO_WINRTEVENTS|この列挙体の最大値。|