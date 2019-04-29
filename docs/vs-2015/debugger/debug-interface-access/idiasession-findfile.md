---
title: Idiasession::findfile |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::findFile method
ms.assetid: a215dc21-b316-40d7-9923-55bfa014976b
caps.latest.revision: 12
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 1e791bc09ba3dd4f1811c650926eadb0f7f0462a
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62431642"
---
# <a name="idiasessionfindfile"></a>IDiaSession::findFile
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

コンパイル単位と名前のソース ファイルを取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp#  
HRESULT findFile (   
   IDiaSymbol*           pCompiland,  
   LPCOLESTR             name,  
   DWORD                 option,  
   IDiaEnumSourceFiles** ppResult  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pCompiland`  
 [in][IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)検索のコンテキストとして使用するコンパイル単位を表すオブジェクト。 このパラメーターに設定`NULL`すべてのコンパイル単位内でソース ファイルを検索します。  
  
 `name`  
 [in]取得するソース ファイルの名前を指定します。 このパラメーターに設定`NULL`のすべてのソース ファイルを取得します。  
  
 `option`  
 [in]名前の検索に適用される比較オプションを指定します。 値から、 [NameSearchOptions 列挙型](../../debugger/debug-interface-access/namesearchoptions.md)列挙体は、単独または組み合わせて使用できます。  
  
 `ppResult`  
 [out]返します、 [IDiaEnumSourceFiles](../../debugger/debug-interface-access/idiaenumsourcefiles.md)ソース ファイルの一覧を含むオブジェクトを取得します。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、返します`S_OK`、それ以外のエラー コードを返します。  
  
## <a name="example"></a>例  
  
```cpp#  
IDiaEnumSourceFiles* pEnum;  
pSession->findFile( NULL, L"sourcefile.cpp", nsFNameExt, &pEnum );  
```  
  
## <a name="see-also"></a>関連項目  
 [IDiaEnumSourceFiles](../../debugger/debug-interface-access/idiaenumsourcefiles.md)   
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [NameSearchOptions 列挙型](../../debugger/debug-interface-access/namesearchoptions.md)
