---
title: Vspackage でのルーティング コマンド |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- commands, routing
- command routing, Visual Studio SDK
ms.assetid: a9c7f9ae-3594-4557-a314-8cf76f5f8772
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a534a015f57a738ca65895002a6fec4454f0ae97
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66342226"
---
# <a name="command-routing-in-vspackages"></a>Vspackage のコマンド ルーティング
コマンドがルーティングされる[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]が実行されるコンテキストに基づきます。 外部から初期コンテキストからグローバル コンテキストにルーティングされます。

## <a name="in-this-section"></a>このセクションの内容
- [コマンド ルーティング アルゴリズム](../../extensibility/internals/command-routing-algorithm.md)

 コマンド ルーティングの解像度の順序について説明します。

- [利用可能なコマンド](../../extensibility/internals/command-availability.md)

 コマンド ルーティングについて説明します。

- [相互運用機能アセンブリを使用するコマンドとメニュー](../../extensibility/internals/commands-and-menus-that-use-interop-assemblies.md)

 ルーティング コマンドをマネージ コードと COM の間での考慮事項について説明します

## <a name="related-sections"></a>関連項目
- [コンテキスト オブジェクトの選択](../../extensibility/internals/selection-context-objects.md)

 ウィンドウで、ユーザーの選択コンテキストのフォーカスを特定する方法のモデルについて説明します。

- [コマンド、メニューのおよびツールバー](../../extensibility/internals/commands-menus-and-toolbars.md)

 メニュー、ツール バー、およびコマンド コンボ ボックスが含まれている UI を作成する方法について説明します。