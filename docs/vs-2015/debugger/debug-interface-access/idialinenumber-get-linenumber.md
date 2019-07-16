---
title: Idialinenumber::get_linenumber |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaLineNumber::get_lineNumber method
ms.assetid: 2dff3fd9-097d-4645-bc1b-cb65ecbc42a6
caps.latest.revision: 11
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 0926c7805ac2deee5851627a764acfdea2f65cdb
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68152061"
---
# <a name="idialinenumbergetlinenumber"></a>IDiaLineNumber::get_lineNumber
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

ソース ファイル内の行番号を取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT get_lineNumber (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pRetVal`  
 [out]ソース ファイル内の行番号を返します。  
  
## <a name="return-value"></a>戻り値  
 正常に終了した場合は、`S_OK` を返します。 返します`S_FALSE`場合、このプロパティはサポートされていません。 それ以外の場合はエラー コードを返します。  
  
## <a name="example"></a>例  
  
```cpp#  
CComPtr< IDiaLineNumber> pLine;  
DWORD linenum;  
pLine->get_lineNumber( &linenum );  
```  
  
## <a name="see-also"></a>関連項目  
 [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)
