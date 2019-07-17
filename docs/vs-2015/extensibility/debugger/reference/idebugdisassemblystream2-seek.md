---
title: IDebugDisassemblyStream2::Seek |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugDisassemblyStream2::Seek
helpviewer_keywords:
- IDebugDisassemblyStream2::Seek
ms.assetid: afec3008-b1e0-4803-ad24-195dbfb6497e
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: d774cc0bf6bca1278423249960bbc5233aa6ad37
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68203014"
---
# <a name="idebugdisassemblystream2seek"></a>IDebugDisassemblyStream2::Seek
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

[逆アセンブル] ストリームの指定した位置の基準とした命令数が特定の読み取りポインターを移動します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT Seek(   
   SEEK_START          dwSeekStart,  
   IDebugCodeContext2* pCodeContext,  
   UINT64              uCodeLocationId,  
   INT64               iInstructions  
);  
```  
  
```csharp  
int Seek(   
   enum_SEEK_START    dwSeekStart,  
   IDebugCodeContext2 pCodeContext,  
   ulong              uCodeLocationId,  
   long               iInstructions  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `dwSeekStart`  
 [in]値、 [SEEK_START](../../../extensibility/debugger/reference/seek-start.md)シーク プロセスを開始する相対位置を指定する列挙体。  
  
 `pCodeContext`  
 [in][IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)シーク操作が関連してコードのコンテキストを表すオブジェクト。 場合にのみ、このパラメーターが使用される`dwSeekStart`  =  `SEEK_START_CODECONTEXT`。 そうしないと、このパラメーターは無視され、null 値を指定できます。  
  
 `uCodeLocationId`  
 [in]シーク操作が関連してコードの場所の識別子です。 このパラメーターを使用`dwSeekStart`  =  `SEEK_START_CODELOCID`。 そうしないと、このパラメーターは無視され、0 に設定することができます。 「解説」を参照してください、 [GetCodeLocationId](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodelocationid.md)メソッドについては、コードの場所の識別子。  
  
 `iInstructions`  
 [in]指定された位置を基準に移動する命令数`dwSeekStart`します。 この値は、後方に移動する負の値であることができます。  
  
## <a name="return-value"></a>戻り値  
 正常に終了した場合は、`S_OK` を返します。 返します`S_FALSE`シーク位置が使用可能な命令の一覧より後ろにあった場合。 それ以外の場合はエラー コードを返します。  
  
## <a name="remarks"></a>Remarks  
 リストの先頭の前に、シークであった場合は、読み取り位置が、一覧の最初の命令に設定されます。 参照してくださいがあった場合の位置に、リストの末尾の後に、読み取り位置が設定最後の命令の一覧で。  
  
## <a name="see-also"></a>関連項目  
 [IDebugDisassemblyStream2](../../../extensibility/debugger/reference/idebugdisassemblystream2.md)   
 [SEEK_START](../../../extensibility/debugger/reference/seek-start.md)   
 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)   
 [GetCodeLocationId](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodelocationid.md)
