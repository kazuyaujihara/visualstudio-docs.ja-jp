---
title: IDebugPortRequest2::GetPortName |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugPortRequest2::GetPortName
helpviewer_keywords:
- IDebugPortRequest2::GetPortName
ms.assetid: 53e2a3a4-bb34-4a02-a983-6bd84ea70587
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: afed0bb700f41f7c39551f1a9bc7779f36b0ae57
ms.sourcegitcommit: c496a77add807ba4a29ee6a424b44a5de89025ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2019
ms.locfileid: "58963869"
---
# <a name="idebugportrequest2getportname"></a>IDebugPortRequest2::GetPortName
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

ポートの名前を取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT GetPortName(   
   BSTR* pbstrPortName  
);  
```  
  
```csharp  
int GetPortName(   
   out string pbstrPortName  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pbstrPortName`  
 [out]ポートの名前を返します。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。  
  
## <a name="remarks"></a>Remarks  
 [IDebugPortRequest2](../../../extensibility/debugger/reference/idebugportrequest2.md)が通常に渡されたインターフェイス デバッグ パッケージ (クライアント) からポートのサプライヤー (サーバー) の接続を取得するポート。 パッケージのデバッグとポートのサプライヤーの両方は、ポートに対して多数の選択肢に注意してください。 単純な文字列は、ポートを記述できる場合、`IDebugPortRequest2::GetPortName`メソッドには、接続を作成するのに十分な情報。 サーバーを使用して取得できるクライアントによって追加のインターフェイスを指定する場合は、`IDebugPortRequest2::QueryInterface`します。  
  
## <a name="see-also"></a>関連項目  
 [IDebugPortRequest2](../../../extensibility/debugger/reference/idebugportrequest2.md)
