---
title: DisplayKind |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
helpviewer_keywords:
- DisplayKind enumeration
ms.assetid: 940968c5-6065-4bda-8ee6-c31597db4d71
caps.latest.revision: 6
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 10bed6b3398b93b0776876491d812ec36c9e9e04
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58975264"
---
# <a name="displaykind"></a>DisplayKind
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

列挙から取得する情報の種類を表す有効な値、 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)オブジェクトし、ユーザーに表示します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
enum enum_DisplayKind  
{  
   DisplayKind_Value = 0x1,  
   DisplayKind_Name = 0x2,  
   DisplayKind_Type = 0x3,  
};  
typedef DWORD DisplayKind;  
```  
  
```csharp  
public enum enum_DisplayKind  
{  
   DisplayKind_Value = 0x1,  
   DisplayKind_Name = 0x2,  
   DisplayKind_Type = 0x3,  
};  
```  
  
#### <a name="parameters"></a>パラメーター  
 DisplayKind_Value  
 フィールドの値。  
  
 DisplayKind_Name  
 フィールドの名前。  
  
 DisplayKind_Type  
 フィールドの型。  
  
## <a name="requirements"></a>必要条件  
 ヘッダー:Ee.h  
  
 名前空間: Microsoft.VisualStudio.Debugger.Interop  
  
 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>関連項目  
 [列挙型](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetValueDisplayStringCount](../../../extensibility/debugger/reference/ieevisualizerservice-getvaluedisplaystringcount.md)
