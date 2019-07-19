---
title: MODULE_INFO_FLAGS |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- MODULE_INFO_FLAGS
helpviewer_keywords:
- MODULE_INFO_FLAGS enumeration
ms.assetid: e22d3723-b4d4-4524-8a2f-3adb55bbd273
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 14c9f36c82445f5279615591d38b110163a0829d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68181129"
---
# <a name="moduleinfoflags"></a>MODULE_INFO_FLAGS
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

モジュールのシンボルの状態を指定します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
enum enum_MODULE_INFO_FLAGS {  
   MIF_SYMBOLS_LOADED = 0x0001  
};  
typedef DWORD MODULE_INFO_FLAGS;  
```  
  
```csharp  
public enum enum_MODULE_INFO_FLAGS {  
   MIF_SYMBOLS_LOADED = 0x0001  
};  
```  
  
## <a name="members"></a>メンバー  
 MIF_SYMBOLS_LOADED  
 記号のセットを少なくとも 1 つは、モジュールによって読み込まれた (それ以外の場合シンボルが読み込まれていません)。  
  
## <a name="remarks"></a>Remarks  
 この値がによって返される、 [GetSymbolSearchInfo](../../../extensibility/debugger/reference/idebugsymbolsearchevent2-getsymbolsearchinfo.md)メソッド。  
  
## <a name="requirements"></a>必要条件  
 ヘッダー: msdbg.h  
  
 名前空間: Microsoft.VisualStudio.Debugger.Interop  
  
 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>関連項目  
 [列挙型](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetSymbolSearchInfo](../../../extensibility/debugger/reference/idebugsymbolsearchevent2-getsymbolsearchinfo.md)
