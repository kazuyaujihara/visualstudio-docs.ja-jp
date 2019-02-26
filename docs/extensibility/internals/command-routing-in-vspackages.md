---
title: Vspackage でのルーティング コマンド |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- commands, routing
- command routing, Visual Studio SDK
ms.assetid: a9c7f9ae-3594-4557-a314-8cf76f5f8772
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 5749875a440a3122a06b81ae9d721e75ded6202c
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56641300"
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