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
ms.openlocfilehash: 25c60bc42895a0527f1638dada5a28a1631314e0
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63417879"
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
> [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)]、このメソッドは使用されなくと常に返す必要があります`E_NOTIMPL`します。  
  
 このメソッドは、デバッガーが突然終了するときに呼び出されます。 ユーザーがそこからデタッチされたものとしてこのメソッドが呼び出されるには、DE でプログラムが再開されます。 デバッグ イベントを送信する必要があります。 プログラムが、デバッガーの別のインスタンスからアタッチ可能な状態でなければなりません。  
  
## <a name="see-also"></a>関連項目  
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)
