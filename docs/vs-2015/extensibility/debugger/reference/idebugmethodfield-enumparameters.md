---
title: IDebugMethodField::EnumParameters |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugMethodField::EnumParameters
helpviewer_keywords:
- IDebugMethodField::EnumParameters method
ms.assetid: d77b1197-deb6-4144-8d1b-8b09949ccfac
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 8ebdd604ba97fda8751cf037e7494b59e7bb77ff
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58977383"
---
# <a name="idebugmethodfieldenumparameters"></a>IDebugMethodField::EnumParameters
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

メソッドのパラメーターの列挙子を作成します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT EnumParameters(   
   IEnumDebugFields** ppParams  
);  
```  
  
```csharp  
int EnumParameters(  
   out IEnumDebugFields ppParams  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `ppParams`  
 [out]返します、 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)メソッドにパラメーターの一覧を表すオブジェクト。 それ以外の場合、パラメーターがない場合に null 値を返します。  
  
## <a name="return-value"></a>戻り値  
 成功した場合は S_OK を返します。 またはパラメーターがない場合は S_FALSE を返します。 それ以外の場合はエラー コードを返します。  
  
## <a name="remarks"></a>Remarks  
 各要素は、 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)さまざまな種類のパラメーターを表すオブジェクト。 呼び出す、 [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md)正確にパラメーターのオブジェクトが表す種類を決定するには、各オブジェクトのメソッド。  
  
 パラメーターには、その変数の名前とその型の両方が含まれています。 クラスのメソッドの最初のパラメーターは、通常"this"ポインターです。  
  
 パラメーターの型は、必要な場合のみを呼び出す、 [EnumArguments](../../../extensibility/debugger/reference/idebugmethodfield-enumarguments.md)メソッド。  
  
## <a name="see-also"></a>関連項目  
 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [EnumArguments](../../../extensibility/debugger/reference/idebugmethodfield-enumarguments.md)
