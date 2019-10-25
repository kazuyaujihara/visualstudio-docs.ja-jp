---
title: プロジェクトフォルダーをソース管理ストアに比較する |Microsoft Docs
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
ms.openlocfilehash: 45bd5b105a2fd24078bc85d8cf5b044351cd78be
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72726124"
---
# <a name="optional-comparison-of-local-project-folder-to-source-control-store"></a>ソース管理ストアとローカルのプロジェクト フォルダーとの比較 (オプション)
ソース管理プラグイン API 1.2 では、ローカルのプロジェクトフォルダーとソース管理を比較するには、関数[Sccdirqueryinfo](../../extensibility/sccdirqueryinfo-function.md)と[Sccdirdiff](../../extensibility/sccdirdiff-function.md)を使用します。

 **ソリューションエクスプローラー**内では、個々のファイルではなくフォルダーを選択すると、 **[バージョンの比較]** ショートカットメニューによって、ソース管理プラグインの新しい[sccdirqueryinfo](../../extensibility/sccdirqueryinfo-function.md)と[sccdirdiff](../../extensibility/sccdirdiff-function.md)が呼び出されます。

## <a name="new-capability-flags"></a>新しい機能フラグ
 `SCC_CAP_DIRECTORYDIFF`

 `SCC_CAP_DIRECTORYCHECKOUT`

## <a name="new-functions"></a>新しい関数
- [SccDirDiff](../../extensibility/sccdirdiff-function.md)

- [SccDirQueryInfo](../../extensibility/sccdirqueryinfo-function.md)

 @No__t_0 関数は、作業ディレクトリがソース管理されているかどうかを判断するために `SccDirDiff` する前に呼び出されます。 @No__t_0 関数は、現在のローカルディレクトリとそれに対応するソース管理フォルダーの相違点を表示します。 このコマンドは、ソース管理プラグインに対して、ディレクトリへの変更の一覧を表示するように要求します。 ソース管理プラグインには、違いを表示するための独自の UI が用意されています。

> [!NOTE]
> この関数は、 [Sccdiff](../../extensibility/sccdiff-function.md)と同じコマンドフラグを使用します。 ソース管理プラグインプロバイダーは、ディレクトリの "クイック diff" 操作をサポートしないことを選択できます。

## <a name="see-also"></a>関連項目
- [ソース管理プラグイン API バージョン 1.2 の新機能](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-2.md)