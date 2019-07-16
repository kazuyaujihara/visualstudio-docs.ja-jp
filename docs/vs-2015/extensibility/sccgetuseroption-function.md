---
title: SccGetUserOption 関数 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- SccGetUserOption
helpviewer_keywords:
- SccGetUserOption function
ms.assetid: 17863747-1901-4c53-a2b3-ed996085e120
caps.latest.revision: 13
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: bd00a2b669b806b09a6ae221b2ba2e03f8d45ceb
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68200075"
---
# <a name="sccgetuseroption-function"></a>SccGetUserOption 関数
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

この関数は、さまざまなユーザー固有のオプションを取得します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
SCCRTN SccGetUserOption(  
   LPVOID pContext,  
   LONG nOption,  
   LPLONG lpVal  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 pContext  
 [in]ソース管理プラグインのコンテキストのポインター。  
  
 nOption  
 [in]検索するオプション（可能なオプションについては備考を参照）。  
  
 lpVal  
 [out]オプションに関連付けられている値。  
  
## <a name="return-value"></a>戻り値  
 この関数のソース管理プラグイン実装は、次の値のいずれかを返すが必要です。  
  
|[値]|説明|  
|-----------|-----------------|  
|SCC_OK|オプションが正常に取得されました。|  
|SCC_E_OPNOTSUPPORTED|オプションはサポートされていません。|  
|SCC_E_NONSPECIFICERROR|未指定のエラーが発生しました。|  
  
## <a name="remarks"></a>Remarks  
 このコマンドでは、次のオプションがサポートされています。  
  
|ユーザー オプション|説明|  
|-----------------|-----------------|  
|`SCC_USEROPT_CHECKOUT_LOCALVER`|ユーザーがファイルのローカル バージョンをチェック アウトするかどうかを判断します。 `lpVal` 割り当てられている`SCC_USEROPT_COLV_YES`(ユーザーがローカル ファイルをチェック アウトする) または`SCC_USEROPT_COLV_NO`します。|  
  
## <a name="see-also"></a>関連項目  
 [ソース管理プラグイン API 関数](../extensibility/source-control-plug-in-api-functions.md)   
 [エラー コード](../extensibility/error-codes.md)
