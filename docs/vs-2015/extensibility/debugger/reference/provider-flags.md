---
title: PROVIDER_FLAGS |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- PROVIDER_FLAGS
helpviewer_keywords:
- PROVIDER_FLAGS enumeration
ms.assetid: 8cbd2312-ed2f-4477-b192-c3f25c6098c3
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: c39aa316308f313bf23ef2c5680671585636f0a5
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58972767"
---
# <a name="providerflags"></a>PROVIDER_FLAGS
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

プログラムのプロバイダーから取得される必要なプロパティを指定します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
enum enum_PROVIDER_FLAGS {  
   PFLAG_NONE                    = 0x00,  
   PFLAG_REMOTE_PORT             = 0x01,  
   PFLAG_DEBUGGEE                = 0x02,  
   PFLAG_ATTACHED_TO_DEBUGGEE    = 0x04,  
   PFLAG_REASON_WATCH            = 0x08,  
   PFLAG_GET_PROGRAM_NODES       = 0x10,  
   PFLAG_GET_IS_DEBUGGER_PRESENT = 0x20  
};  
typedef DWORD PROVIDER_FLAGS;  
```  
  
```csharp  
public enum enum_PROVIDER_FLAGS {  
   PFLAG_NONE                    = 0x00,  
   PFLAG_REMOTE_PORT             = 0x01,  
   PFLAG_DEBUGGEE                = 0x02,  
   PFLAG_ATTACHED_TO_DEBUGGEE    = 0x04,  
   PFLAG_REASON_WATCH            = 0x08,  
   PFLAG_GET_PROGRAM_NODES       = 0x10,  
   PFLAG_GET_IS_DEBUGGER_PRESENT = 0x20  
};  
```  
  
## <a name="members"></a>メンバー  
 PFLAG_NONE  
 指定したフラグがありません。  
  
 PFLAG_REMOTE_PORT  
 呼び出し元が異なるコンピューター上のプログラムの一覧[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]します。  
  
 PFLAG_DEBUGGEE  
 プロセスのこのインスタンスによって現在デバッグ中[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]します。  
  
 PFLAG_ATTACH_TODEBUGGEE  
 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] デバッグ中のプログラムにアタッチされていますが、起動しませんでした。  
  
 PFLAG_REASON_WATCH  
 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] イベントを監視します。  
  
 PFLAG_GET_PROGRAM_NODES  
 呼び出し元が、`ProgramNodes`のフィールド、 [PROVIDER_PROCESS_DATA](../../../extensibility/debugger/reference/provider-process-data.md)構造体。  
  
 PFLAG_GET_IS_DEBUGGER_PRESENT  
 呼び出し元が、`fIsTheDebuggerPresent`のフィールド、`PROVIDER_PROCESS_DATA`構造体。  
  
## <a name="remarks"></a>Remarks  
 これらのフラグは、次のメソッドに渡されます。  
  
- [WatchForProviderEvents](../../../extensibility/debugger/reference/idebugprogramprovider2-watchforproviderevents.md)  
  
- [GetProviderProgramNode](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprogramnode.md)  
  
- [GetProviderProcessData](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprocessdata.md)  
  
  これらの値は、演算と組み合わせることができます`OR`します。  
  
## <a name="requirements"></a>必要条件  
 ヘッダー: msdbg.h  
  
 名前空間: Microsoft.VisualStudio.Debugger.Interop  
  
 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>関連項目  
 [列挙型](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [PROVIDER_PROCESS_DATA](../../../extensibility/debugger/reference/provider-process-data.md)   
 [WatchForProviderEvents](../../../extensibility/debugger/reference/idebugprogramprovider2-watchforproviderevents.md)   
 [GetProviderProgramNode](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprogramnode.md)   
 [GetProviderProcessData](../../../extensibility/debugger/reference/idebugprogramprovider2-getproviderprocessdata.md)
