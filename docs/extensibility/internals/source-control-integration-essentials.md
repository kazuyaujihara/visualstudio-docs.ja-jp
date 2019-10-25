---
title: ソース管理の統合の要点 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Source Control Integration, essentials
- Source Control Integration,overview
- essentials, Source Control Integration
ms.assetid: 442057cb-fd54-4283-96f8-2f6dc8bf2de7
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: fcce3d8fdcc1c99c9b91bfebec572033ff3beb1a
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72723476"
---
# <a name="source-control-integration-essentials"></a>ソース管理の統合の基本情報
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] は、基本的な機能を提供し、ソース管理プラグイン API (旧称: MSSCCI API) を使用して構築されたソース管理プラグインと VSPackage ベースのソース管理統合ソリューションの2種類のソース管理統合をサポートしています。これにより、より堅牢な機能が提供されます。

## <a name="source-control-plug-in"></a>ソース管理プラグイン
 ソース管理プラグインは、ソース管理プラグイン API を実装する DLL として記述されます。 登録とソース管理の統合機能は、API を通じて提供されます。 この方法は、ソース管理 VSPackage よりも実装が簡単であり、ほとんどのソース管理操作には [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ユーザーインターフェイス (UI) を使用します。

 ソース管理プラグイン API を使用してソース管理プラグインを実装するには、次の手順を実行します。

1. [ソース管理プラグイン](../../extensibility/source-control-plug-ins.md)に指定されている関数を実装する DLL を作成します。

2. 「[方法: ソース管理プラグインをインストール](../../extensibility/internals/how-to-install-a-source-control-plug-in.md)する」の説明に従って、適切なレジストリエントリを作成して、DLL を登録します。

3. ヘルパー UI を作成し、ソース管理アダプターパッケージ (ソース管理プラグインを通じてソース管理機能を処理する [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] コンポーネント) から要求されたときに表示されるようにします。

   詳細については、「[ソース管理プラグインの作成](../../extensibility/internals/creating-a-source-control-plug-in.md)」を参照してください。

## <a name="source-control-vspackage"></a>ソース管理 VSPackage
 ソース管理の VSPackage 実装を使用すると、[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ソース管理 UI のカスタマイズされた置換を開発できます。 この方法では、ソース管理の統合を完全に制御できますが、そのためには、UI 要素を提供し、それ以外の方法でプラグインの方法で提供されるソース管理インターフェイスを実装する必要があります。

 ソース管理 VSPackage を実装するには、次の操作を行う必要があります。

1. 「[登録と選択](../../extensibility/internals/registration-and-selection-source-control-vspackage.md)」で説明されているように、独自のソース管理 VSPackage を作成して登録します。

2. 既定のソース管理 UI をカスタム UI に置き換えます。 「[カスタムユーザーインターフェイス](../../extensibility/internals/custom-user-interface-source-control-vspackage.md)」を参照してください。

3. 使用するグリフを指定し、**ソリューションエクスプローラー**グリフイベントを処理します。 「[グリフコントロール](../../extensibility/internals/glyph-control-source-control-vspackage.md)」を参照してください。

4. クエリの編集およびクエリの保存イベントを処理します。クエリの [[保存の編集](../../extensibility/internals/query-edit-query-save-source-control-vspackage.md)] クエリに表示されます。

   詳細については、「[ソース管理の作成 VSPackage](../../extensibility/internals/creating-a-source-control-vspackage.md)」を参照してください。

## <a name="see-also"></a>関連項目
- [概要](../../extensibility/internals/source-control-integration-overview.md)
- [ソース管理プラグインの作成](../../extensibility/internals/creating-a-source-control-plug-in.md)
- [ソース管理 VSPackage の作成](../../extensibility/internals/creating-a-source-control-vspackage.md)