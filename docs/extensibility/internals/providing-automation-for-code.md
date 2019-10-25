---
title: コードの自動化の提供 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- CodeModel object
ms.assetid: 21cb3e63-f25c-404b-bc1d-a32ad0fdd4d5
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 874446aa6bf2e40a120aac49e7d91fd3d861d1d4
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72724960"
---
# <a name="providing-automation-for-code"></a>コードのオートメーションの提供
コードのオートメーションモデルを作成する必要はありません。 環境 SDK には、そのためのサンプルが用意されていません。 コードモデルの詳細については、<xref:EnvDTE.CodeModel> オブジェクトを参照してください。

 コードモデルを実装するには、内部データ構造によって決定されるインターフェイスを実装する必要があります。 オブジェクトは `IDispatch` クラスから派生する必要があります。

 拡張、<xref:EnvDTE.CodeModel> および <xref:EnvDTE.FileCodeModel> するオブジェクトは、<xref:EnvDTE.Project> オブジェクトから使用でき、次のようになります。

- <xref:EnvDTE.Project.CodeModel%2A>

- <xref:EnvDTE.ProjectItem.FileCodeModel%2A>

 @No__t_2 および <xref:EnvDTE.ProjectItem> オブジェクトから返すオブジェクトに、`CodeModel` または `FileCodeModel` インターフェイスだけを実装することを選択できます。 このインターフェイスには、プロジェクトシステムに適した機能をすべて提供します。

 標準 `CodeModel` および `FileCodeModel` インターフェイスからは使用できない機能 (メソッドやプロパティなど) を追加する場合は、標準から継承する独自のインターフェイスを作成します。 エンドユーザーが見つけられるように、プロジェクトシステムでドキュメント化してください。 標準のインターフェイスを返しますが、ユーザーは `QueryInterface` メソッドを呼び出すことも、存在することがわかっている場合はインターフェイスにキャストすることもできます。

## <a name="see-also"></a>関連項目
- [オートメーション モデルの概要](../../extensibility/internals/automation-model-overview.md)