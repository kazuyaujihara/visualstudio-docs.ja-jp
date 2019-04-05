---
title: IDebugProgramNode2::GetEngineInfo |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugProgramNode2::GetEngineInfo
helpviewer_keywords:
- IDebugProgramNode2::GetEngineInfo
ms.assetid: 664e7fe5-9100-4b7d-9dc5-e5a4dd0d0451
caps.latest.revision: 14
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 1e3e24c2c326f7ebc7427da3804f17f1f75aeef4
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58975988"
---
# <a name="idebugprogramnode2getengineinfo"></a>IDebugProgramNode2::GetEngineInfo
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

プログラムを実行するデバッグ エンジン (DE) の識別子と名前を取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
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
  
#### <a name="parameters"></a>パラメーター  
 `pbstrEngine`  
 [out]プログラムを実行するデバイスの名前を返します (C++ に固有: これは、呼び出し元が、エンジンの名前に関心がないことを示す null ポインター)。  
  
 `pguidEngine`  
 [out]プログラムを実行する DE のグローバルに一意の識別子を返します (C++ に固有: これは、呼び出し元が、エンジンの GUID に興味がないことを示す null ポインター)。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。  
  
## <a name="see-also"></a>関連項目  
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)
