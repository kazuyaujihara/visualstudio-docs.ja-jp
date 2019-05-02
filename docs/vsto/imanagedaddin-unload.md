---
title: IManagedAddin::Unload
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Unload method
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 296502aa461688c34152d86ee21aab5f2c83ecb4
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62956745"
---
# <a name="imanagedaddinunload"></a>IManagedAddin::Unload
  管理対象の VSTO アドインがアンロードされる直前に呼び出されます。

## <a name="syntax"></a>構文

```csharp
HRESULT Unload();
```

## <a name="return-value"></a>戻り値
 メソッドが正常に完了したかどうかを示す HRESULT 値。

## <a name="remarks"></a>Remarks
 このメソッドは、Microsoft Office の現在のバージョンでは呼び出されません。 このメソッドは将来使用するために予約されています。

## <a name="see-also"></a>関連項目
- [IManagedAddin インターフェイス](../vsto/imanagedaddin-interface.md)
- [IManagedAddin::Load](../vsto/imanagedaddin-load.md)
