---
title: SccAddFilesFromSCC 関数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- SccAddFilesFromSCC
helpviewer_keywords:
- SccAddFilesFromSCC function
ms.assetid: f21a3500-ade8-4dd8-8647-10e2179be9c1
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b827e1f7e26fb98e9d49de4e9fe2388e46ee07cb
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2018
ms.locfileid: "49831173"
---
# <a name="sccaddfilesfromscc-function"></a>SccAddFilesFromSCC 関数
この関数は、現在開いているプロジェクトをソース管理からファイルの一覧を追加します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
SCCRTN SccAddFilesFromSCC(  
   LPVOID  pContext,  
   HWND    hWnd,  
   LPSTR   lpUser,  
   LPSTR   lpAuxProjPath,  
   LONG    cFiles,  
   LPCSTR* lpFilePaths,  
   LPCSTR  lpDestination,  
   LPCSTR  lpComment,  
   LPBOOL  pbResults  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 pContext  
 [in]ソース管理プラグインのコンテキストのポインター。  
  
 hWnd  
 [in]ソース管理プラグインが提供される任意のダイアログ ボックスの親として使用できる IDE ウィンドウへのハンドル。  
  
 lpUser  
 [入力、出力] (最大 SCC_USER_SIZE、null 終端文字を含む) ユーザー名。  
  
 lpAuxProjPath  
 [入力、出力]プロジェクトを識別する、補助型の文字列 (最大`SCC_PRJPATH_`サイズは、null 終端文字を含めて)。  
  
 cFiles  
 [in]指定されたファイルの数`lpFilePaths`します。  
  
 lpFilePaths  
 [入力、出力]現在のプロジェクトに追加するファイル名の配列。  
  
 lpDestination  
 [in]ファイルが書き込まれる先のパス。  
  
 lpComment  
 [in]追加されるファイルのそれぞれに適用されるコメントです。  
  
 pbResults  
 [入力、出力]エラーまたは (0 以外の場合、または TRUE) に成功した場合に設定できるフラグの配列 (0 または FALSE) ファイルごとに (配列のサイズは以上である必要があります`cFiles`長い)。  
  
## <a name="return-value"></a>戻り値  
 この関数のソース管理プラグイン実装は、次の値のいずれかを返すが必要です。  
  
|[値]|説明|  
|-----------|-----------------|  
|SCC_E_PROJNOTOPEN|プロジェクトが開いていません。|  
|SCC_E_OPNOTPERFORMED|接続では、同じプロジェクトで指定したとおりにありません。 `lpAuxProjPath.`|  
|SCC_E_NOTAUTHORIZED|ユーザーは、データベースを更新する権限がありません。|  
|SCC_E_NONSPECIFICERROR|不明なエラー。|  
|SCC_I_RELOADFILE|ファイルまたはプロジェクトを再読み込みする必要があります。|  
  
## <a name="see-also"></a>関連項目  
 [ソース管理プラグイン API 関数](../extensibility/source-control-plug-in-api-functions.md)