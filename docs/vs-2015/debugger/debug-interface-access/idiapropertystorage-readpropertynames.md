---
title: IDiaPropertyStorage::ReadPropertyNames |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaPropertyStorage::ReadPropertyNames
ms.assetid: f8bcab77-afca-4a8f-8710-697842f8a518
caps.latest.revision: 13
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: f3f6d3ac520a396b5207767a3fec0913c801c287
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62537421"
---
# <a name="idiapropertystoragereadpropertynames"></a>IDiaPropertyStorage::ReadPropertyNames
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

対応する文字列名を取得では、プロパティの識別子を指定します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT ReadPropertyNames (  
   ULONG         cpropid,  
   PROPID const* rgpropid,  
   BSTR*         rglpwstrName  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `cpropid`  
 [in]プロパティ id の数`rgpropid`です。  
  
 `rgpropid`  
 [in]プロパティ id の名前を取得する対象の配列 (`PROPID`として WTypes.h で定義されている、 `ULONG`)。  
  
 `rglpwstrName`  
 [入力、出力]指定したプロパティ id のプロパティ名の配列。 配列のプロパティ名の要求の数を保持するために事前に割り当てる必要があり、以上を格納できる必要があります`cpropid``BSTR`文字列。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`。 それ以外の場合はエラー コードを返します。  
  
## <a name="remarks"></a>Remarks  
 返されるプロパティの名前を解放する必要があります (呼び出すことによって、`SysFreeString`関数) が必要な不要になった場合。  
  
## <a name="see-also"></a>関連項目  
 [IDiaPropertyStorage](../../debugger/debug-interface-access/idiapropertystorage.md)
