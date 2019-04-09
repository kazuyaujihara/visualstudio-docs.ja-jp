---
title: IDebugMessageEvent2::GetMessage |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugMessageEvent2::GetMessage
helpviewer_keywords:
- GetMessage method
- IDebugMessageEvent2::GetMessage method
ms.assetid: 9fca7285-f7f1-422d-8565-92bf0e0db60a
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: e571a7ba2116c093f8d4e4afd78fffc5014ae906
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58963356"
---
# <a name="idebugmessageevent2getmessage"></a>IDebugMessageEvent2::GetMessage
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

表示するメッセージを取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT GetMessage(   
   MESSAGETYPE* pMessageType,  
   BSTR*        pbstrMessage,  
   DWORD*       pdwType,  
   BSTR*        pbstrHelpFileName,  
   DWORD*       pdwHelpId  
);  
```  
  
```csharp  
int GetMessage(   
   out enum_MESSAGETYPE pMessageType,  
   out string           pbstrMessage,  
   out uint             pdwType,  
   out string           pbstrHelpFileName,  
   out uint             dwHelpId  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pMessageType`  
 [out]値を返します、 [MESSAGETYPE](../../../extensibility/debugger/reference/messagetype.md)メッセージの種類を表す列挙体。  
  
 `pbstrMessage`  
 [out]メッセージを返します。  
  
 `pdwType`  
 [out]Win32 の規則を使用して、メッセージの種類を返します`MessageBox`関数。 参照してください、 [AfxMessageBox](http://msdn.microsoft.com/library/d66d0328-cdcc-48f6-96a4-badf089099c8)詳細については、関数。  
  
 `pbstrHelpFileName`  
 [入力、出力]ヘルプ ファイルの名前を返します。 ヘルプ ファイルが存在しない場合、null (C++) または (C#) 値が空にすることがあります。  
  
 `pdwHelpId`  
 [入力、出力]ヘルプ識別子を返します。 ヘルプがない場合は 0 を関連付けられるこのメッセージ。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。  
  
## <a name="see-also"></a>関連項目  
 [IDebugMessageEvent2](../../../extensibility/debugger/reference/idebugmessageevent2.md)   
 [メッセージの種類](../../../extensibility/debugger/reference/messagetype.md)   
 [AfxMessageBox](http://msdn.microsoft.com/library/d66d0328-cdcc-48f6-96a4-badf089099c8)
