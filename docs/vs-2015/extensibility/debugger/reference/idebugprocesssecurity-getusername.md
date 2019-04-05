---
title: IDebugProcessSecurity::GetUserName |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
helpviewer_keywords:
- IDebugProcessSecurity::GetUserName
ms.assetid: c73c60ac-da6e-45ae-8f04-95353a24ca3e
caps.latest.revision: 5
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 17a6ef52d7df1c60b0cb6581a7e15eeaf67e7875
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58977334"
---
# <a name="idebugprocesssecuritygetusername"></a>IDebugProcessSecurity::GetUserName
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

ポート サプライヤーからユーザー名を取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT GetUserName(  
    BSTR *pbstrUserName  
);  
```  
  
```csharp  
int GetUserName (  
    string pbstrUserName  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pbstrUserName`  
 [out]ユーザー名を表す文字列。  
  
## <a name="return-value"></a>戻り値  
 返します、メソッドが成功したかどうかは`S_OK`します。 それ以外の場合、エラー コードを返します。  
  
## <a name="remarks"></a>Remarks  
 `GetUserName` 表示されるユーザー名を返します、**ユーザー名**の列、**プロセスにアタッチ** ダイアログ ボックス。 表示する、**プロセスにアタッチ**ダイアログ ボックスで、をクリックして**プロセスにアタッチ**で、**ツール**でメニュー、[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]統合開発環境 (IDE)。  
  
## <a name="see-also"></a>関連項目  
 [IDebugProcessSecurity](../../../extensibility/debugger/reference/idebugprocesssecurity.md)
