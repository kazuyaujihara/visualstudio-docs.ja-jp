---
title: IDebugClassField::GetDefaultIndexer |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugClassField::GetDefaultIndexer
helpviewer_keywords:
- IDebugClassField::GetDefaultIndexer method
ms.assetid: 47ce4f45-3816-4b40-909c-5032d0692d75
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 6be0a1925a1e5d48941c1c0e13ac1b4789687229
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68191023"
---
# <a name="idebugclassfieldgetdefaultindexer"></a>IDebugClassField::GetDefaultIndexer
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

既定のインデクサーの名前を取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT GetDefaultIndexer(   
   BSTR* pbstrIndexer  
);  
```  
  
```csharp  
int GetDefaultIndexer(  
   out string pbstrIndexer  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pbstrIndexer`  
 [out]既定のインデクサーの名前を含む文字列を返します。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、S_OK を返します。 または、既定のインデクサーが存在しない場合は S_FALSE を返します。 それ以外の場合はエラー コードを返します。  
  
## <a name="remarks"></a>Remarks  
 クラスの既定のインデクサーはプロパティとしてマークされている、`Default`プロパティを配列にアクセスします。 これに固有[!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]します。 宣言されている既定のインデクサーの例を次に示します[!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]とその使用方法。  
  
```vb  
Imports System.Collections;  
  
Public Class Class1  
    Private myList as Hashtable  
  
    Default Public Property Item(ByVal Index As Integer) As Integer  
        Get  
            Return CType(List(Index), Integer)  
        End Get  
        Set(ByVal Value As Integer)  
            List(Index) = Value  
        End Set  
    End Property  
End Class  
  
Function GetItem(Index as Integer) as Integer  
    Dim classList as Class1 = new Class1  
    Dim value as Integer  
  
    ' Access array through default indexer  
    value = classList(2)  
  
    ' Access array through explicit property  
    value = classList.Item(2)  
  
    Return value  
End Function  
```  
  
## <a name="see-also"></a>関連項目  
 [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)
