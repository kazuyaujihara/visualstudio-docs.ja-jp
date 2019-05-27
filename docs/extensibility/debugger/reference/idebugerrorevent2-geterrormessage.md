---
title: IDebugErrorEvent2::GetErrorMessage |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugErrorEvent2::GetErrorMessage
helpviewer_keywords:
- IDebugErrorEvent2::GetErrorMessage
ms.assetid: 9e3b0d74-a2dd-4eaa-bd95-21b2f9c79409
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 55c36c6649b8ff2b1b0bebc57012970625a964b8
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2019
ms.locfileid: "66199940"
---
# <a name="idebugerrorevent2geterrormessage"></a>IDebugErrorEvent2::GetErrorMessage
人間が判読できるエラー メッセージの構築できるようにする情報を返します。

## <a name="syntax"></a>構文

```cpp
HRESULT GetErrorMessage(
   MESSAGETYPE* pMessageType,
   BSTR*        pbstrErrorFormat,
   HRESULT*     hrErrorReason,
   DWORD*       pdwType,
   BSTR*        pbstrHelpFileName,
   DWORD*       pdwHelpId
);
```

```csharp
int GetErrorMessage(
   out enum_MESSAGETYPE   pMessageType,
   out string             pbstrErrorFormat,
   out int                phrErrorReason,
   out uint               pdwType,
   out string             pbstrHelpFileName,
   out uint               pdwHelpId
);
```

## <a name="parameters"></a>パラメーター
`pMessageType`\
[out]値を返します、 [MESSAGETYPE](../../../extensibility/debugger/reference/messagetype.md)メッセージの型を記述する列挙。

`pbstrErrorFormat`\
[out]ユーザーには、最後のメッセージの形式 (詳細については、「解説」を参照してください)。

`hrErrorReason`\
[out]エラー コード、メッセージは、の詳細についてはします。

`pdwType`\
[out]エラーの重大度 (の MB_XXX 定数を使用して`MessageBox`。 たとえば、`MB_EXCLAMATION`または`MB_WARNING`)。

`pbstrHelpFileName`\
[out]ヘルプ ファイル (ヘルプ ファイルがない場合は、null 値に設定) へのパス。

`pdwHelpId`\
[out]表示するヘルプトピックのIDです（ヘルプトピックがない場合は0に設定されます）。

## <a name="return-value"></a>戻り値
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。

## <a name="remarks"></a>Remarks
 エラー メッセージの書式設定する必要があります`"What I was doing.  %1"`します。 `"%1"`エラー コードに由来のエラー メッセージで、呼び出し元によって置き換えられますし (で返される`hrErrorReason`)。 `pMessageType`パラメーターは、最後のエラー メッセージの表示方法を呼び出し元に通知します。

## <a name="see-also"></a>関連項目
- [IDebugErrorEvent2](../../../extensibility/debugger/reference/idebugerrorevent2.md)
- [MESSAGETYPE](../../../extensibility/debugger/reference/messagetype.md)