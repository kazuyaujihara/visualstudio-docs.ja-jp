---
title: Live Unit Testing の概要
description: Live Unit Testing の利点と、Live Unit Testing を使用してプロジェクトを単体テストする方法について説明します。
ms.date: 09/11/2017
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio ALM
- Live Unit Testing
author: rpetrusha
ms.author: ronpet
ms.workload:
- dotnet
ms.openlocfilehash: a5acf1857309236727cd0bab4d9d981d814292b9
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62786082"
---
# <a name="live-unit-testing-introduction"></a>Live Unit Testing の統合

Live Unit Testing は、Visual Studio 2017 で導入されたテクノロジです。 コードの変更を行いながらリアルタイムで単体テストを自動的に実行することができます。

ライブ単体テスト

- 安心してコードのリファクタリングと変更を行うことができます。 Live Unit Testing を使用すると、コードの編集時に、関係するすべてのテストが自動的に実行され、加えた変更によってコードの破損が起きないことを確認することができます。

- 単体テストが適切にコードをカバーしているかどうかが示され、単体テストでカバーされていないコードも表示されます。 Live Unit Testing は、リアルタイムでコード カバレッジをグラフィカルに表示します。これにより、各コード行をカバーしているテストの数、および任意の単体テストでカバーされていない行をひとめで把握することができます。

1 つ以上の単体テスト プロジェクトを含むソリューションがある場合、Live Unit Testing を有効にするには、Visual Studio の最上位メニューから、**[テスト]** > **[Live Unit Testing]** > **[開始]** の順に選択します。

> [!NOTE]
> Live Unit Testing は、Visual Studio Enterprise エディションでのみ使用できます。

Live Unit Testing について詳細を学習するには:

- [Live Unit Testing の使用の開始](live-unit-testing-start.md)に関する入門チュートリアルを試してみてください。

- 詳細については、[Visual Studio Enterprise Edition での Live Unit Testing の使用](live-unit-testing.md)に関するページを参照してください。

- 「[Live Unit Testing に関する FAQ](live-unit-testing-faq.md)」を参照してください。Live Unit Testing の新しい機能に加えて、ヒントとテクニックが説明されています。

- Live Unit Testing の概要とその機能については、Channel 9 のビデオをご覧ください。 </p>

   > [!VIDEO https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T105/player]

## <a name="related-resources"></a>関連資料

- [コード テスト ツール](https://visualstudio.microsoft.com/vs/testing-tools/)
- [コードの単体テスト](unit-test-your-code.md)
