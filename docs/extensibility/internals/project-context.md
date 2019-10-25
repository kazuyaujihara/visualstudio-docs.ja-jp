---
title: プロジェクトコンテキスト |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- projects [Visual Studio SDK], opening items
ms.assetid: d1803f4a-24eb-44b0-b5d2-cb40c15534be
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 8afa595a264f218fcc20f18de1c261a9ead6e030
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72725771"
---
# <a name="project-context"></a>プロジェクトのコンテキスト
ユーザーがプロジェクトおよびプロジェクト項目を追加または操作すると、IDE はプロジェクトコンテキストの概念を使用して、さまざまな操作を実行する方法を決定します。

 通常、ファイルは、ユーザーが **[新しいプロジェクト]** コマンドを選択して明示的に作成するか、 **[ファイル]** メニューの **[プロジェクトを開く]** コマンドを選択して使用できるようにすることで、ユーザーが明示的に作成する標準のプロジェクトオブジェクトです。 このような場合は、ファイルが作成され、プロジェクトのコンテキストで開かれます。また、プロジェクトの種類は、ドキュメントを編集するためのコンテキストを定義します。

 一部のプロジェクトは、非常に豊富なコンテキストを提供します。 たとえば、プロジェクトでは、プロジェクトスコープのプログラムによる名前空間またはデータバインディングのためのプロジェクトスコープデータベース接続を管理します。 ユーザーは、ソリューションエクスプローラーに表示されるプロジェクト項目などの特定のプロジェクトオブジェクトを使用して、ファイルまたはデータベース接続を直接開くことができます。

 それ以外の場合は、項目のプロジェクトコンテキストが明示的に指定されていません。 たとえば、ユーザーがファイルを開いたときに、 **[ファイル]** メニューの **[既存のファイルを開く]** コマンドを選択してファイルを開いたとき、またはユーザーがファイルで ファイル **[を検索]** コマンド**をクリックしたときに、項目のコンテキストは使用できません。[検索と置換**] ダイアログボックス。 このような状況に対処するために、IDE は <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument> を呼び出して、ドキュメントを開くための最適なプロジェクトを見つけるプロセスを管理します。

## <a name="see-also"></a>関連項目
- [プロジェクトの優先順位](../../extensibility/internals/project-priority.md)
- [プロジェクト テンプレートとプロジェクト項目テンプレートの追加](../../extensibility/internals/adding-project-and-project-item-templates.md)