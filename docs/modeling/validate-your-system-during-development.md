---
title: 開発時のシステムの検証
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- dependency diagrams
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9fb9810f1c212dfb881f5725676a79c6307b9cfa
ms.sourcegitcommit: 6a19c5ece38a70731496a38f2ef20676ff18f8a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/09/2019
ms.locfileid: "65476500"
---
# <a name="validate-your-system-during-development"></a>開発時のシステムの検証

Visual Studio は、ソフトウェアのユーザーの要件と、システムのアーキテクチャに一貫性を維持できます。

これらの各機能をサポートする Visual Studio のバージョンを確認するには、「 [Version support for architecture and modeling tools](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport)」を参照してください。

## <a name="key-tasks"></a>主なタスク

ソフトウェアを検証するのにには、次のタスクを使用します。

|**タスク**|**関連するトピック**|
|-|-|
|**ソフトウェアがユーザーの要件を満たしているか確認する**:<br /><br />システムとそのコンポーネントのテストを整理するために、要件モデルとアーキテクチャ モデルを使用します。 こうすることで、ユーザーやその他の利害関係者にとって重要な要求をテストしやすくなり、要求が変更された場合にすばやくテストを更新することができます。|- [モデルからテストを開発します。](../modeling/develop-tests-from-a-model.md)|
|**ソフトウェアが、意図されたシステム設計に合致した状態を保っているか確認する:**<br /><br />依存関係図には、アプリケーションのコンポーネント間で必要な依存関係について説明します。 開発中に、コード内の実際の依存関係が、意図された設計に準拠しているか検証できます。|- [コードから依存関係図を作成します。](../modeling/create-layer-diagrams-from-your-code.md)<br />- [依存関係図を使用したコードを検証します。](../modeling/validate-code-with-layer-diagrams.md)|

## <a name="external-resources"></a>外部リソース

|**カテゴリ**|**リンク**|
|-|-|
|**ビデオ**|![ビデオへのリンク](../data-tools/media/playvideo.gif) [Channel 9。Doug Seven:コードの理解と Visual Studio 2010 でのシステムの設計](https://channel9.msdn.com/shows/VS2010Launch/Doug-Seven-Code-Understanding-and-Systems-Design-with-Visual-Studio-2010)<br /><br /> ![ビデオへのリンク](../data-tools/media/playvideo.gif) [Channel 9。アプリケーションの設計](https://channel9.msdn.com/blogs/clinted/uml-with-vs-2010-part-5-architecting-an-application))|
|**フォーラム**|- [Visual Studio の視覚化ツールとモデリング ツール](https://social.msdn.microsoft.com/Forums/en-US/home?forum=vsarch)<br />- [Visual Studio 機能拡張](https://social.msdn.microsoft.com/Forums/vstudio/home?forum=vsx)|

## <a name="see-also"></a>関連項目

- [ユーザー要件のモデリング](../modeling/model-user-requirements.md)
- [分析し、モデルのアーキテクチャ](../modeling/analyze-and-model-your-architecture.md)

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]
