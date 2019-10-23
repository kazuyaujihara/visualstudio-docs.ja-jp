---
title: 開発時のシステムの検証
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- dependency diagrams
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 328b600a21adf274d1d016f595438eb5622ee853
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72663745"
---
# <a name="validate-your-system-during-development"></a>開発時のシステムの検証

Visual Studio を使用すると、ソフトウェアをユーザーの要件とシステムのアーキテクチャに準拠させることができます。

これらの各機能をサポートする Visual Studio のバージョンを確認するには、「 [Version support for architecture and modeling tools](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport)」を参照してください。

## <a name="key-tasks"></a>主なタスク

ソフトウェアを検証するには、次のタスクを使用します。

|**タスク**|**関連するトピック**|
|-|-|
|**ソフトウェアがユーザーの要件を満たしているか確認する**:<br /><br />要件とアーキテクチャモデルを使用すると、システムとそのコンポーネントのテストを整理するのに役立ちます。 こうすることで、ユーザーやその他の利害関係者にとって重要な要求をテストしやすくなり、要求が変更された場合にすばやくテストを更新することができます。|[モデルからテストを開発 -  には](../modeling/develop-tests-from-a-model.md)|
|**ソフトウェアが、意図されたシステム設計に合致した状態を保っているか確認する:**<br /><br />依存関係図は、アプリケーションのコンポーネント間の意図された依存関係を表します。 開発中に、コード内の実際の依存関係が、意図された設計に準拠しているか検証できます。|[コードから依存関係図を作成 -  に](../modeling/create-layer-diagrams-from-your-code.md)は<br />[依存関係図を使用してコードを検証 -  に](../modeling/validate-code-with-layer-diagrams.md)は|

## <a name="external-resources"></a>外部リソース

|**カテゴリ**|**Links**|
|-|-|
|**ビデオ**|![link ビデオ ](../data-tools/media/playvideo.gif) [Channel 9: Doug 7: Visual Studio 2010 を使用したコードの理解とシステムの設計](https://channel9.msdn.com/shows/VS2010Launch/Doug-Seven-Code-Understanding-and-Systems-Design-with-Visual-Studio-2010)<br /><br /> ![link ビデオ ](../data-tools/media/playvideo.gif) [Channel 9: アプリケーションの設計](https://channel9.msdn.com/blogs/clinted/uml-with-vs-2010-part-5-architecting-an-application))|
|**フォーラム**|- [Visual Studio の視覚化ツールとモデリング ツール](https://social.msdn.microsoft.com/Forums/en-US/home?forum=vsarch)<br />- [Visual Studio の機能拡張](https://social.msdn.microsoft.com/Forums/vstudio/home?forum=vsx)|

## <a name="see-also"></a>関連項目

- [ユーザー要件のモデリング](../modeling/model-user-requirements.md)
- [分析とモデルのアーキテクチャ](../modeling/analyze-and-model-your-architecture.md)

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]
