---
title: ディレクトリの状態コードの列挙子 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- directory status code enumerator
- source control plug-ins, directory status enumeration
ms.assetid: 616026b5-f529-40ef-90c1-1836e116d797
caps.latest.revision: 14
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: e082a691a389d5cb9a8fa307a627b11911e0db78
ms.sourcegitcommit: c496a77add807ba4a29ee6a424b44a5de89025ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2019
ms.locfileid: "58978483"
---
# <a name="directory-status-code-enumerator"></a>ディレクトリの状態コードの列挙子
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

`SccDirStatus`列挙子には、ソース管理システムでディレクトリの状態を指定する名前付き定数の値が含まれています。 この列挙体を使って、 [SccDirQueryInfo](../extensibility/sccdirqueryinfo-function.md)します。 これは、ソース管理プラグイン API のバージョン 1.2 で導入されました。  
  
## <a name="syntax"></a>構文  
  
```  
enum SccDirStatus {  
   SCC_DIRSTATUS_INVALID       = -1L,  
   SCC_DIRSTATUS_NOTCONTROLLED = 0x0000L,  
   SCC_DIRSTATUS_CONTROLLED    = 0x0001L,  
   SCC_DIRSTATUS_EMPTYPROJ     = 0x0002L  
};  
```  
  
## <a name="members"></a>メンバー  
 SCC_DIRSTATUS_INVALID  
 状態を取得できませんでした。それに依存しないでください。  
  
 SCC_DIRSTATUS_NOTCONTROLLED  
 ディレクトリはソース管理下ではありません。  
  
 SCC_DIRSTATUS_CONTROLLED  
 ディレクトリは、ソース管理下にあること。  
  
 SCC_DIRSTATUS_EMPTYPROJ  
 このディレクトリに対応するプロジェクトが空です。  
  
## <a name="see-also"></a>関連項目  
 [ソース管理プラグイン](../extensibility/source-control-plug-ins.md)   
 [SccDirQueryInfo](../extensibility/sccdirqueryinfo-function.md)
