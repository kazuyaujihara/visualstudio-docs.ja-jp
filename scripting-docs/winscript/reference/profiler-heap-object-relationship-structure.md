---
title: PROFILER_HEAP_OBJECT_RELATIONSHIP 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 3ab3d986-3314-4c7b-a1c8-18ed691a8b9c
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7a905a44f2ef686181c5a859699277d16f6cd374
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58153007"
---
# <a name="profilerheapobjectrelationship-structure"></a>PROFILER_HEAP_OBJECT_RELATIONSHIP 構造体
ヒープ オブジェクトのリレーションシップを表します。  
  
## <a name="syntax"></a>構文  
  
```cpp
typedef struct _PROFILER_HEAP_OBJECT_RELATIONSHIP{    PROFILER_HEAP_OBJECT_NAME_ID relationshipId;    PROFILER_RELATIONSHIP_INFO relationshipInfo;    [switch_type(PROFILER_RELATIONSHIP_INFO), switch_is(relationshipInfo)] union    {        [case(PROFILER_PROPERTY_TYPE_NUMBER)] double numberValue;        [case(PROFILER_PROPERTY_TYPE_STRING)] LPCWSTR stringValue;        [case(PROFILER_PROPERTY_TYPE_HEAP_OBJECT)] PROFILER_HEAP_OBJECT_ID objectId;        [case(PROFILER_PROPERTY_TYPE_EXTERNAL_OBJECT)] PROFILER_EXTERNAL_OBJECT_ADDRESS externalObjectAddress;    };} PROFILER_HEAP_OBJECT_RELATIONSHIP;  
```  
  
## <a name="members"></a>メンバー  
  
|メンバー|[値]|説明|  
|------------|-----------|-----------------|  
|relationshipId|[PROFILER_HEAP_OBJECT_NAME_ID 型](../../winscript/reference/profiler-heap-object-name-id-type.md)|リレーションシップの ID 名から、 [IActiveScriptProfilerHeapEnum::GetNameIdMap](../../winscript/reference/iactivescriptprofilerheapenum-getnameidmap.md)します。|  
|relationshipInfo|[PROFILER_RELATIONSHIP_INFO 列挙型](../../winscript/reference/profiler-relationship-info-enumeration.md)|リレーションシップについて説明します。|  
|numberValue|double|小数点の値です。 いずれかのみ`numberValue` / `stringValue` / `objectId` / `externalObjectAddress`に基づいて、設定は、`relationshipInfo`値。|  
|stringValue|LPCWSTR|文字列値。|  
|objectId|[PROFILER_HEAP_OBJECT_ID 型](../../winscript/reference/profiler-heap-object-id-type.md)|ヒープ オブジェクトの ID。|  
|externalObjectAddress|[PROFILER_EXTERNAL_OBJECT_ADDRESS 型](../../winscript/reference/profiler-external-object-address-type.md)|外部オブジェクトのアドレス。|  
|部分文字列|[PROFILER_PROPERTY_TYPE_SUBSTRING_INFO 構造体](../../winscript/reference/profiler-property-type-substring-info-structure.md)|部分文字列の種類に関する情報。|