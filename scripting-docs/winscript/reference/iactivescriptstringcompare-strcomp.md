---
title: 'IActiveScriptStringCompare:: StrComp |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptStringCompare.StrComp
apilocation:
- scrobj.dll
helpviewer_keywords:
- StrComp method, IActiveScriptStringCompare interface
ms.assetid: 124d1281-8037-4766-a2a1-61244ac1f114
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 233c427b634306527b0b0d496397e82f889560e2
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72577939"
---
# <a name="iactivescriptstringcomparestrcomp"></a>IActiveScriptStringCompare::StrComp
スクリプトエンジンの文字列比較メソッドを定義します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT StrComp(  
// The first string:  
    [in] BSTR bszStr1,    
// The second string:   
    [in] BSTR bszStr2,    
// The result of the comparison:  
    [out, retval] LONG* iRet   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `bszStr1`  
 第 1 文字列。  
  
 `bszStr2`  
 第 2 文字列。  
  
 `iRet`  
 比較の結果。 `bszStr1` と `bszStr2`are 同じ場合は0。`bszStr1`  <  `bszStr2`; の場合は-1。`bszStr1`  >  `bszStr2` の場合は1。  
  
## <a name="return-value"></a>戻り値  
 次のいずれかの値を返します。  
  
|戻り値|説明|  
|------------------|-------------|  
|`S_OK`|成功。|  
|`E_INVALIDARG`|引数が有効ではありません。|  
|`E_UNEXPECTED`|この呼び出しは想定されていませんでした (たとえば、スクリプトエンジンがまだ読み込まれていないか、初期化されていません)。|  
  
## <a name="remarks"></a>Remarks  
 このメソッドは、文字列比較が実行されるたびに呼び出されます。  
  
## <a name="example"></a>例  
 次の例は、文字列比較関数をオーバーロードする方法を示しています。 [IActiveScriptProperty:: SetProperty](../../winscript/reference/iactivescriptproperty-setproperty.md)を使用して SCRIPTPROP_STRINGCOMPAREINSTANCE を設定する場合は、オーバーロードを使用できます。  
  
```cpp#  
cpp_quote("// {58562769-ED52-42f7-8403-4963514E1F11}")  
cpp_quote("DEFINE_GUID(IID_IActiveScriptStringCompare, 0x58562769,   
    0xED52, 0x42f7, 0x84, 0x03, 0x49, 0x63, 0x51, 0x4E, 0x1F, 0x11);")  
cpp_quote("")  
  
cpp_quote("#define SCRIPTPROP_INTEGERMODE              0x00003000")  
cpp_quote("#define SCRIPTPROP_STRINGCOMPAREINSTANCE    0x00003001")  
cpp_quote("")  
interface IActiveScriptStringCompare;  
[  
         object,  
         uuid(58562769-ED52-42f7-8403-4963514E1F11),  
         pointer_default(unique)  
]  
interface IActiveScriptStringCompare : IUnknown  
{  
        // StrComp  
        //     bszStr1: first string  
        //     bszStr2: second string  
        //     iRet: 0 if identical, -1 if bszStr1 < bszStr2, 1 if   
        //         bszStr1 > bszStr2  
        //            
        //     Return values:  
        //         S_OK: Success  
        //         E_NOTIMPL: Not implemented  
        //  
        HRESULT StrComp(  
                [in] BSTR bszStr1,  
                [in] BSTR bszStr2,  
                [out, retval] LONG* iRet  
        );  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [IActiveScriptStringCompare インターフェイス](../../winscript/reference/iactivescriptstringcompare-interface.md)