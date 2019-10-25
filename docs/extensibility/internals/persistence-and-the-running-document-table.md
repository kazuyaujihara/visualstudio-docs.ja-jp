---
title: 永続化と実行中のドキュメントテーブル |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- persistence, managing
- IVsPersistHierarchyItem interface, implementing
- architecture, persistence
- running document table (RDT), architecture
ms.assetid: 27117eae-6c58-4189-a61a-1397a43b5ecf
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: f03836e1faaac03fbd89c0b93f37a698cbdcd56a
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72726083"
---
# <a name="persistence-and-the-running-document-table"></a>ドキュメント テーブルの保存と実行
@No__t_0 IDE では、プロジェクトは、プロジェクト項目の永続化を管理する役割を担っています。プロジェクト項目は、サービスを使用して実行される <xref:Microsoft.VisualStudio.Shell.Interop.SVsRunningDocumentTable> です。 ドキュメントは、Visual Studio 環境における永続化の基本単位です。 プロジェクトは、開いているすべてのドキュメントの状態を追跡するリソースである、実行中のドキュメントテーブル (RDT) を使用して、ドキュメントのオープン、保存、および名前変更を調整します。

## <a name="managing-persistence"></a>永続化の管理
 プロジェクトは、<xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem> インターフェイスを実装することによって、環境の永続性サービスを制御します。 環境はドキュメントを直接保存するように要求することはありませんが、所有するプロジェクト (または階層) にドキュメントを保存するように要求します。 これにより、プロジェクトは、プロジェクトアイテムデータをローカルファイル、リモートファイル、データベース、リポジトリ、またはその他のメディアに保存することができます。

 グローバル環境では、RDT が維持されます。 この環境では、RDT 内の開いているすべてのウィンドウとドキュメントのエントリを保持します。これにより、ソリューションが閉じられたときなど、特別な通知を受け取ることができます。 さらに、RDT を使用すると、環境が**ソリューションエクスプローラー**内の対応するノードを追跡できるようになります。 RDT は、プロジェクトファイルとプロジェクト項目ドキュメントの両方を含めて、開いている持続可能なオブジェクトごとに1つのレコードを保持します。

## <a name="see-also"></a>関連項目
- [ドキュメント テーブルの実行](../../extensibility/internals/running-document-table.md)
- [IDE での選択と通貨](../../extensibility/internals/selection-and-currency-in-the-ide.md)