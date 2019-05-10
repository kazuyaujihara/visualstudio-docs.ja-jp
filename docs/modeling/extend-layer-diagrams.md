---
title: 依存関係図の拡張
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- dependency diagrams, creating extensions
- layer models
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9c164174b88ca9fdd815668084c1447e20de072c
ms.sourcegitcommit: 6a19c5ece38a70731496a38f2ef20676ff18f8a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/09/2019
ms.locfileid: "65476564"
---
# <a name="extend-dependency-diagrams"></a>依存関係図の拡張

作成し、依存関係図を更新し、Visual Studio での依存関係図と照らし合わせてプログラム コードの構造を検証するコードを記述することができます。 図のショートカット (コンテキスト) メニューに表示するコマンドを追加し、ドラッグ アンド ドロップ ジェスチャをカスタマイズし、テキスト テンプレートからレイヤー モデルにアクセスすることができます。 これらの拡張機能を VSIX (Visual Studio Integration Extension) にパッケージ化し、他の Visual Studio ユーザーに配布することができます。

## <a name="requirements"></a>必要条件

レイヤー拡張機能を開発するコンピューターに以下の項目がインストールされている必要があります。

- Visual Studio

- [Visual Studio SDK](../extensibility/visual-studio-sdk.md)

- Modeling SDK for Visual Studio

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

レイヤー拡張機能を実行するコンピューターにインストールされている Visual Studio の適切なエディションが必要です。 依存関係図をサポートする Visual Studio のエディションを確認するを参照してください。 [Edition のサポート アーキテクチャとモデリング ツール](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport)します。

## <a name="see-also"></a>関連項目

- [依存関係図:リファレンス](../modeling/layer-diagrams-reference.md)
- [依存関係図:ガイドライン](../modeling/layer-diagrams-guidelines.md)
- [コードからの依存関係図の作成](../modeling/create-layer-diagrams-from-your-code.md)
- [依存関係図を使用したコードの検証](../modeling/validate-code-with-layer-diagrams.md)
