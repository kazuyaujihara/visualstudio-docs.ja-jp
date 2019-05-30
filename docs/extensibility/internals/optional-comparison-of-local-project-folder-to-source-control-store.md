---
title: ソース管理ストアをプロジェクト フォルダーの比較 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- source control plug-ins, comparing versions
- source control plug-ins, local project folders
ms.assetid: 65217e8b-15a6-4446-92b0-4cff1c6220f5
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d675868e10a99a192681c52495ad3b37e384d390
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66350699"
---
# <a name="optional-comparison-of-local-project-folder-to-source-control-store"></a>ソース管理ストアとローカルのプロジェクト フォルダーとの比較 (オプション)
ソースの制御関数を使用して、ローカルのプロジェクト フォルダーとソース管理の間の比較が行われますプラグイン API 1.2 [SccDirQueryInfo](../../extensibility/sccdirqueryinfo-function.md)と[SccDirDiff](../../extensibility/sccdirdiff-function.md)します。

 内で**ソリューション エクスプ ローラー**、個々 のファイルではなく、フォルダーが選択されている場合、**バージョンを比較**ショートカット メニューを起動、新しい[SccDirQueryInfo](../../extensibility/sccdirqueryinfo-function.md)と[SccDirDiff](../../extensibility/sccdirdiff-function.md)ソース管理プラグインでします。

## <a name="new-capability-flags"></a>新しい機能フラグ
 `SCC_CAP_DIRECTORYDIFF`

 `SCC_CAP_DIRECTORYCHECKOUT`

## <a name="new-functions"></a>新しい関数
- [SccDirDiff](../../extensibility/sccdirdiff-function.md)

- [SccDirQueryInfo](../../extensibility/sccdirqueryinfo-function.md)

 `SccDirQueryInfo`関数は、前に呼び出されます`SccDirDiff`作業ディレクトリがソース管理の対象を判断します。 `SccDirDiff`関数は、現在のローカル ディレクトリと、対応するソース管理フォルダーの相違を表示します。 このコマンドは、ソース管理、ディレクトリに変更の一覧を表示するプラグインを確認します。 ソース管理プラグインは、相違点を表示する独自の UI を提供します。

> [!NOTE]
> この関数と同じコマンド フラグを使用して[SccDiff](../../extensibility/sccdiff-function.md)します。 ソース管理プラグイン プロバイダーとしては、ディレクトリの"クイック diff"操作をサポートすることができます。

## <a name="see-also"></a>関連項目
- [ソース管理プラグイン API バージョン 1.2 の新機能](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-2.md)