---
title: IDebugArrayObject2::GetBaseIndices |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
helpviewer_keywords:
- GetBaseIndices
- IDebugArrayObject2::GetBaseIndices
ms.assetid: 882951a2-3da0-49bf-8d1e-7daedd13ffe6
caps.latest.revision: 9
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 3c10fb65ec698bf9c5c9b7623b29e2f47851afe8
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58973748"
---
# <a name="idebugarrayobject2getbaseindices"></a>IDebugArrayObject2::GetBaseIndices
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

配列の次元数を指定されたインデックスごとに、基本のインデックス (下限) を取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT GetBaseIndices (  
   DWORD  dwRank,  
   DWORD* dwIndices  
);  
```  
  
```csharp  
int GetBaseIndices (  
   uint       dwRank,  
   out uint[] dwIndices  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `dwRank`  
 [in]配列の次元 (rank) の数。  
  
 `dwIndices`  
 [out]配列のベース インデックス (下限) です。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。  
  
## <a name="remarks"></a>Remarks  
 例として、この関数は、次の c# コードで作成された配列の「5」を返します。  
  
```  
int[] lengths = { 12 };  
int[] lowerbounds = { 5 };  
Array.CreateInstance(typeof(int), lengths, lowerbounds);  
```  
  
## <a name="see-also"></a>関連項目  
 [IDebugArrayObject2](../../../extensibility/debugger/reference/idebugarrayobject2.md)
