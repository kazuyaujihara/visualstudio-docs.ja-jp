---
title: .Proj および .sln ファイルからソース管理の情報を削除します。
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- source control plug-ins, .sln and .proj files
ms.assetid: 7b06883f-35de-41e2-9a9e-d3edba236f17
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 081766a8169ccc54888a076012b8281c485a20e5
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66318820"
---
# <a name="removal-of-source-control-information-from-proj-and-sln-files"></a>.Proj および .Sln ファイルからのソース管理情報の削除
ソース管理プラグイン API、SCC のバージョン 1.2 では、情報は、MSSCCPRJ に格納されます。SCC ファイルです。 MSSCCPRJ 利点です。SCC ファイルでは、SCC 情報をしないソースして-.proj および .sln ファイルでは、制御します。

## <a name="version-12-changes"></a>バージョン 1.2 の変更
 ソース管理プラグインのソース管理プラグイン API バージョン 1.1 に基づく、ソース管理については、プロジェクト (.proj) とソリューション (.sln) ファイルに格納されます。 AuxPath でソース管理情報のデータベースの場所が指定され、ProjName で、データベース内の特定の場所を指定します。 ProjName は通常はできないため、有効なこれらの操作の後にこの動作分岐、フォーク、またはコピー操作の後に問題が発生できます。

 ソース管理プラグイン API バージョン 1.1 では、IDE の使用で ~ SAK ファイル、プラグインのサポート、MSSCCPRJ かどうかを検出します。ソース管理の情報を格納する SCC メソッド。 ソース管理プラグイン API バージョン 1.2 では、MSSCCPRJ のサポートを検出するための新しい機能を提供します。SCC ファイルを使用せず、~ SAK ファイル。 詳細については、次を参照してください。[の排除 ~ SAK ファイル](../../extensibility/internals/elimination-of-tilde-sak-files.md)します。

## <a name="see-also"></a>関連項目
- [ソース管理プラグイン API バージョン 1.2 の新機能](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-2.md)