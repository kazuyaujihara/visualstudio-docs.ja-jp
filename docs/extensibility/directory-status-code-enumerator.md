---
title: ディレクトリの状態コードの列挙子 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- directory status code enumerator
- source control plug-ins, directory status enumeration
ms.assetid: 616026b5-f529-40ef-90c1-1836e116d797
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 7b6e113949c9e87605895bbb43aa1ae4b4df0496
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66348036"
---
# <a name="directory-status-code-enumerator"></a>ディレクトリの状態コードの列挙子
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
 SCC_DIRSTATUS_INVALID 状態を取得できませんでした。それに依存しないでください。

 SCC_DIRSTATUS_NOTCONTROLLED ディレクトリはソース管理下ではありません。

 SCC_DIRSTATUS_CONTROLLED ディレクトリは、ソース管理下にあること。

 このディレクトリに対応する SCC_DIRSTATUS_EMPTYPROJ プロジェクトが空です。

## <a name="see-also"></a>関連項目
- [ソース管理プラグイン](../extensibility/source-control-plug-ins.md)
- [SccDirQueryInfo](../extensibility/sccdirqueryinfo-function.md)