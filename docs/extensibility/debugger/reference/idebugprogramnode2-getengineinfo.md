---
title: IDebugProgramNode2::GetEngineInfo |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProgramNode2::GetEngineInfo
helpviewer_keywords:
- IDebugProgramNode2::GetEngineInfo
ms.assetid: 664e7fe5-9100-4b7d-9dc5-e5a4dd0d0451
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: c31d3a858af2886a27a51e22e131cb89b2234d6e
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/09/2019
ms.locfileid: "65459075"
---
# <a name="idebugprogramnode2getengineinfo"></a>IDebugProgramNode2::GetEngineInfo
プログラムを実行するデバッグ エンジン (DE) の識別子と名前を取得します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetEngineInfo ( 
   BSTR* pbstrEngine,
   GUID* pguidEngine
);
```

```csharp
int GetEngineInfo(
   out string pbstrEngine,
   out Guid pguidEngine
);
```

## <a name="parameters"></a>パラメーター
 `pbstrEngine`\

 [out]プログラムを実行するデバイスの名前を返します (C++-特定します。 これは、呼び出し元が、エンジンの名前に関心がないことを示す null ポインター)。

 `pguidEngine`\

 [out]プログラムを実行する DE のグローバルに一意の識別子を返します (C++-特定します。 これは、呼び出し元が、エンジンの GUID に興味がないことを示す null ポインター)。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="see-also"></a>関連項目
- [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)