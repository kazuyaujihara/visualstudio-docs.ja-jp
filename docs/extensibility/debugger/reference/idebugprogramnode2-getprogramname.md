---
title: IDebugProgramNode2::GetProgramName |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugProgramNode2::GetProgramName
helpviewer_keywords:
- IDebugProgramNode2::GetProgramName
ms.assetid: 510c7f5d-48ff-4d9f-ad79-fbad9f15239d
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: ef32de11f1667e32684bf39e38f6b609fc67afa8
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62916836"
---
# <a name="idebugprogramnode2getprogramname"></a>IDebugProgramNode2::GetProgramName
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

プログラムの名前を取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT GetProgramName (   
   BSTR* pbstrProgramName  
);  
```  
  
```csharp  
int GetProgramName (   
   out string pbstrProgramName  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pbstrProgramName`  
 [out]プログラムの名前を返します。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。  
  
## <a name="remarks"></a>Remarks  
 このようなパスの部分もありますが、プログラムの名前、プログラムの名が、プログラムへのパスと同じものです。  
  
## <a name="example"></a>例  
 次の例は、単純なは、このメソッドを実装する方法を示しています。`CProgram`を実装するオブジェクト、 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)インターフェイス。 `MakeBstr`関数は、BSTR として指定した文字列のコピーを割り当てます。  
  
```cpp#  
HRESULT CProgram::GetProgramName(BSTR* pbstrProgramName) {    
   if (!pbstrProgramName)    
      return E_INVALIDARG;    
  
   // Assign the member program name to the passed program name.    
   *pbstrProgramName = MakeBstr(m_pszProgramName);    
   return NOERROR;    
}    
```  
  
## <a name="see-also"></a>関連項目  
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)
