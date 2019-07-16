---
title: IDebugExtendedField::GetExtendedKind |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
helpviewer_keywords:
- IDebugExtendedField::GetExtendedKind
- GetExtendedKind
ms.assetid: 20dc1c13-3cc0-4bb4-9c99-fa85587c86c3
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: fe3289652dd7880bd902f397e0c76584fdcda0ab
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68148959"
---
# <a name="idebugextendedfieldgetextendedkind"></a>IDebugExtendedField::GetExtendedKind
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

指定した拡張フィールドの種類を取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT GetExtendedKind(  
   FIELD_KIND_EX* pdwKind  
);  
```  
  
```csharp  
int GetExtendedKind(  
   ref enum_FIELD_KIND_EX pdwKind  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pdwKind`  
 [入力、出力]値を[FIELD_KIND_EX](../../../extensibility/debugger/reference/field-kind-ex.md)フィールドの種類を定義する列挙です。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。  
  
## <a name="see-also"></a>関連項目  
 [IDebugExtendedField](../../../extensibility/debugger/reference/idebugextendedfield.md)
