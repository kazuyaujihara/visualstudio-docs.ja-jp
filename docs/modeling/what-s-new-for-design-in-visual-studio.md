---
title: Visual Studio 2017 での設計向けの新機能
titleSuffix: ''
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- what's new [Visual Studio], architecture and modeling
- architecture [Visual Studio], modeling
- modeling software [Visual Studio], What's New
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
monikerRange: vs-2017
ms.openlocfilehash: dc75c7414e0fff18f76d14f8f9a4e0779a9e7a2b
ms.sourcegitcommit: 6a19c5ece38a70731496a38f2ef20676ff18f8a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/09/2019
ms.locfileid: "65476534"
---
# <a name="whats-new-for-design-in-visual-studio-2017"></a>Visual Studio 2017 での設計向けの新機能

## <a name="live-dependency-validation"></a>ライブ依存関係の検証

不要な依存関係を削除するとは、技術的負債の管理の重要な部分です。 Visual Studio は、配置されている場所などの問題に関する正確な情報を含む、依存関係のライブの検証を提供します。 ライブ依存関係の検証のメリットをエラー一覧と、エディターの新機能です。

![アクションでのリアルタイム依存関係の検証](media/dep-validation-whatsnew-01.png)

オーサリング環境は、依存関係の検証のことを発見しやすく、身近に変更されました。 用語は、「レイヤー図」から「依存関係図」に変更されました。

**アーキテクチャ**メニューが直接依存関係図を作成するコマンドを含むようになりました。

![[アーキテクチャ] メニュー項目をライブ依存関係](media/dep-validation-whatsnew-02.png)

レイヤーのプロパティの名前と説明は、わかりやすいように変更されました。

![ライブ依存関係は、プロパティ名を更新します。](media/dep-validation-whatsnew-03.png)

すぐにときに表示するソリューションの現在のコード分析の結果で、変更の影響、ダイアグラムを保存します。 完了を待機する必要はありません、**依存関係の検証**コマンド。

詳細については、[このブログの投稿](https://devblogs.microsoft.com/devops/live-architecture-dependency-validation-in-visual-studio-15-preview-5/)を参照してください。

## <a name="uml-designers-have-been-removed"></a>UML デザイナー向けが削除されました

UML デザイナー向け Visual Studio から削除されました。

* UML 図が XML ファイルとして表示されるようになりました
* UML モデル エクスプ ローラーが存在しません
* モデリング プロジェクトの依存関係の検証の参照が使用されなく
* ソリューション エクスプ ローラーで、「レイヤー参照」ノードが表示されなくなります
* 依存関係 (レイヤー) ダイアグラムで「検証」ビルド アクションは使用されなく - ビルド タスクが削除されました
* バージョン間のラウンド トリップのプロジェクトの構造は保持されます。
* ことができますもを開く、作成、編集、および依存関係 (レイヤー) ダイアグラムを XML として保存
* 依存関係 (レイヤー) の図にリンクされている TFS の作業項目は、デザイン画面にアクセスできません。
* DSL またはレイヤーにから後方リンクはサポートされていません
* Modeling SDK での UML 拡張機能はサポートされなくなりました

.NET のアーキテクチャを視覚化するためのサポートとC++コードを利用[コード マップ](map-dependencies-across-your-solutions.md)します。

UML デザイナー向けの重要なユーザーの場合は、UML のニーズに代替のツールを決定するときに、Visual Studio 2015 またはそれ以前のバージョンを使用することもできます。

詳細については、[このブログの投稿](https://devblogs.microsoft.com/devops/uml-designers-have-been-removed-layer-designer-now-supports-live-architectural-analysis/)を参照してください。

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

## <a name="a-nameversionsupport-edition-support-for-architecture-and-modeling-tools"></a><a name="VersionSupport" />アーキテクチャ ツールとモデリング ツールのエディションのサポート

Visual Studio は、いくつかのエディションで使用できます。 すべては、アーキテクチャとモデリング ツールのサポートを提供します。 各ツールの利用可能情報を次の表に示します。

|**機能**|**Enterprise edition**|**Professional edition**|**Community エディション**|
|-|-|-|-|
|**コード マップ**|はい|のみコード マップの読み取りをサポートするには、フィルタ リングのコード マップ、新しいジェネリック ノードを追加して、選択範囲から新しいの有向グラフを作成します。|-|
|**依存関係図**|はい|のみ依存関係図の読み取りをサポートします。|のみ依存関係図の読み取りをサポートします。|
|**グラフの directed** (DGML ダイアグラム)|はい|はい|はい|
|**コード クローン**|はい|-|-|