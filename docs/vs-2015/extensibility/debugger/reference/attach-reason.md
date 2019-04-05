---
title: ATTACH_REASON |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- ATTACH_REASON
helpviewer_keywords:
- ATTACH_REASON enumeration
ms.assetid: 159fb70b-a344-4ba6-9115-b7eaa16e228f
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: c66894fe0515b28037bbb2a19715fa09cbf9fa62
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58977187"
---
# <a name="attachreason"></a>ATTACH_REASON
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

プログラム ノードにアタッチするデバッグ エンジン (DE) の理由を指定します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
enum enum_ATTACH_REASON {   
   ATTACH_REASON_LAUNCH = 0x0001,  
   ATTACH_REASON_USER   = 0x0002,  
   ATTACH_REASON_AUTO   = 0x0003  
};  
typedef DWORD ATTACH_REASON;  
```  
  
```csharp  
public enum enum_ATTACH_REASON {   
   ATTACH_REASON_LAUNCH = 0x0001,  
   ATTACH_REASON_USER   = 0x0002,  
   ATTACH_REASON_AUTO   = 0x0003  
};  
```  
  
## <a name="members"></a>メンバー  
 ATTACH_REASON_AUTO  
 プロセスがデバッグ モードでは現在ためにをアタッチします。  
  
 ATTACH_REASON_LAUNCH  
 プロセスが起動されているため、接続します。  
  
 ATTACH_REASON_USER  
 ユーザーの要求によりアタッチします。  
  
## <a name="remarks"></a>Remarks  
 これらの値がパラメーターとして使用される、[アタッチ](../../../extensibility/debugger/reference/idebugengine2-attach.md)と[アタッチ](../../../extensibility/debugger/reference/idebugprogramex2-attach.md)メソッド。  
  
## <a name="requirements"></a>必要条件  
 ヘッダー: msdbg.h  
  
 名前空間: Microsoft.VisualStudio.Debugger.Interop  
  
 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>関連項目  
 [列挙型](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [アタッチ](../../../extensibility/debugger/reference/idebugengine2-attach.md)   
 [添付](../../../extensibility/debugger/reference/idebugprogramex2-attach.md)
