---
title: IDebugProgramNode2::DetachDebugger_V7 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugProgramNode2::DetachDebugger
helpviewer_keywords:
- IDebugProgramNode2::DetachDebugger
- IDebugProgramNode2::DetachDebugger_V7
ms.assetid: d2d4b78e-a2dd-4217-97a6-ab648fd2ee2f
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: cbca803b7caaef3e5a5ae4cbc46fc8e850a1575b
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58973684"
---
# <a name="idebugprogramnode2detachdebuggerv7"></a>IDebugProgramNode2::DetachDebugger_V7
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

非推奨とされます。 使用しないでください。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT DetachDebugger_V7 (   
   void   
);  
```  
  
```csharp  
int DetachDebugger_V7 ();  
```  
  
## <a name="return-value"></a>戻り値  
 実装は常に返す必要があります`E_NOTIMPL`します。  
  
## <a name="remarks"></a>Remarks  
  
> [!WARNING]
>  [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)]、このメソッドは使用されなくと常に返す必要があります`E_NOTIMPL`します。  
  
 このメソッドは、デバッガーが突然終了するときに呼び出されます。 ユーザーがそこからデタッチされたものとしてこのメソッドが呼び出されるには、DE でプログラムが再開されます。 デバッグ イベントを送信する必要があります。 プログラムが、デバッガーの別のインスタンスからアタッチ可能な状態でなければなりません。  
  
## <a name="see-also"></a>関連項目  
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)
