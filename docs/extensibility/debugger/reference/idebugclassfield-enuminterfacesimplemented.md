---
title: IDebugClassField::EnumInterfacesImplemented |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugClassField::EnumInterfacesImplemented
helpviewer_keywords:
- IDebugClassField::EnumInterfacesImplemented method
ms.assetid: e5523e45-d350-491e-a92c-fe0ca97d2052
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: bffae40f1e5212132c89b6b71b7fc83cca6ebb42
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62877026"
---
# <a name="idebugclassfieldenuminterfacesimplemented"></a>IDebugClassField::EnumInterfacesImplemented
このクラスによって実装されるインターフェイスの列挙子を作成します。

## <a name="syntax"></a>構文

```cpp
HRESULT EnumInterfacesImplemented( 
   IEnumDebugFields** ppEnum
);
```

```csharp
int EnumInterfacesImplemented(
   out IEnumDebugFields ppEnum
);
```

#### <a name="parameters"></a>パラメーター
 `ppEnum`

 [out]返します、 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)実装されるインターフェイスのリストを表すオブジェクト。 インターフェイスがない場合は、null 値を返します。

## <a name="return-value"></a>戻り値
 成功した場合は S_OK を返します。 または、このクラスで実装されたインターフェイスがない場合は S_FALSE を返します。 それ以外の場合はエラー コードを返します。

## <a name="remarks"></a>Remarks
 列挙体の各要素は、 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)インターフェイスを記述するオブジェクト。 アンマネージ注[!INCLUDE[vcprvc](../../../code-quality/includes/vcprvc_md.md)]ため、このメソッドは、アンマネージ常に null 値を返します、コードが不連続エンティティとしてインターフェイスを使用しない[!INCLUDE[vcprvc](../../../code-quality/includes/vcprvc_md.md)]コード。

## <a name="see-also"></a>関連項目
- [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)
- [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)