---
title: IDebugSettingsCallback2::EnumEEs |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugSettingsCallback2::EnumEEs
ms.assetid: 9f884c49-426f-461b-b547-9d909486e73f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 2cca998c4cdae8cc5e543a24a5cdfe18369e51b3
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68155212"
---
# <a name="idebugsettingscallback2enumees"></a>IDebugSettingsCallback2::EnumEEs
言語とベンダーの識別子を指定された使用可能な式エバリュエーターを列挙します。

## <a name="syntax"></a>構文

```cpp
HRESULT EnumEEs(
   DWORD  celtBuffer,
   GUID*  rgguidLang,
   GUID*  rgguidVendor,
   DWORD* pceltEEs
);
```

```csharp
public int EnumEEs(
   uint       celtBuffer,
   ref Guid   rgguidLang,
   ref Guid   rgguidVendor,
   ref uint[] pceltEEs
);
```

#### <a name="parameters"></a>パラメーター
 `celtBuffer`

 [in]要素の数、`pceltEEs`バッファー。

 `rgguidLang`

 [入力、出力]プログラミング言語の一意の識別子。

 `rgguidVendor`

 [入力、出力]仕入先の一意識別子。

 `pceltEEs`

 [入力、出力]式エバリュエーターの配列。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDebugSettingsCallback2](../../../extensibility/debugger/reference/idebugsettingscallback2.md)