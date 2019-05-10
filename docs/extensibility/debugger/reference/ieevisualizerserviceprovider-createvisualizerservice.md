---
title: IEEVisualizerServiceProvider::CreateVisualizerService |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEEVisualizerServiceProvider::CreateVisualizerService
helpviewer_keywords:
- IEEVisualizerServiceProvider::CreateVisualizerService method
ms.assetid: f366f7c9-358d-46c8-993f-32ff86539833
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 0b45db093a451331de20b3f38bdf58f2669f0577
ms.sourcegitcommit: 6196d0b7fdcb08ba6d28a8151ad36b8d1139f2cc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65223670"
---
# <a name="ieevisualizerserviceprovidercreatevisualizerservice"></a>IEEVisualizerServiceProvider::CreateVisualizerService
このメソッドは、ビジュアライザー サービスを作成します。

## <a name="syntax"></a>構文

```cpp
HRESULT CreateVisualizerService(
   IDebugBinder*              binder,
   IDebugSymbolProvider*      pSymProv,
   IDebugAddress*             pAddress,
   IEEVisualizerDataProvider* dataProvider,
   IEEVisualizerService**     ppService
);
```

```csharp
int CreateVisualizerService(
   IDebugBinder binder,
   IDebugSymbolProvider      pSymProv,
   IDebugAddress             pAddress,
   IEEVisualizerDataProvider dataProvider,
   out IEEVisualizerService  ppService
);
```

## <a name="parameters"></a>パラメーター
 `binder`\

 [in][IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)オブジェクトに渡される[EvaluateSync](../../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md)します。

 `pSymProv`\

 [in][IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)オブジェクトに渡される`IDebugParsedExpression::EvaluateSync`します。

 `pAddress`\

 [in][IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)オブジェクトに渡される`IDebugParsedExression::EvaluateSync`します。

 `dataProvider`\

 [in]実装するオブジェクト、 [IEEVisualizerDataProvider](../../../extensibility/debugger/reference/ieevisualizerdataprovider.md) (式エバリュエーターで提供されている) インターフェイス。

 `ppService`\

 [out]作成したサービス。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="remarks"></a>Remarks
 `binder`、 `pSymProv`、および`pAddress`にパラメーターすべて渡された、`IDebugParsedExpression::EvaluateSync`メソッド。 `CreateVisualizerService` のみ呼び出される`IDebugParsedExpression::EvaluateSync`ビジュアライザーの型の式エバリュエーターのサポートの一部として。

## <a name="see-also"></a>関連項目
- [IEEVisualizerServiceProvider](../../../extensibility/debugger/reference/ieevisualizerserviceprovider.md)
- [EvaluateSync](../../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md)
- [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)
- [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)
- [IEEVisualizerDataProvider](../../../extensibility/debugger/reference/ieevisualizerdataprovider.md)