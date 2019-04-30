---
title: データ連結 ActiveX コントロールのデバッグ |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- data-bound controls, ActiveX
- ActiveX controls, debugging
- controls [Visual Studio], ActiveX
ms.assetid: 9f6e1f00-e25b-48a9-8484-7e67a1232461
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2b5b3d5a58c87988c950328a8b0136986b3a149f
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62852416"
---
# <a name="debugging-a-data-bound-activex-control"></a>データ連結 ActiveX コントロールのデバッグ
データ ソース コントロールに連結する ActiveX コントロールを開発している場合、独自のコンテナー アプリケーションを作成し、そのコンテナーを使用して ActiveX コントロールをデバッグできます。

 たとえば、ダイアログ ベースの MFC アプリケーションを作成して、ダイアログ ボックスにデータ連結コントロールとデータ ソース コントロールを配置します。 この MFC アプリケーションは、データ連結 ActiveX コントロールをデバッグするためのコンテナー実行可能ファイルとして、ランタイム テストに使用できます。

## <a name="using-the-test-container"></a>テスト コンテナーの使用
 簡単に変更できるコンテナーでコントロールまたはコンテナーのさまざまなインターフェイスをサポートする場合は、デバッグ セッションの実行可能ファイルとして ActiveX テスト コンテナーを使用します。 ActiveX テスト コンテナーで、**[コンテナー]** メニューの **[オプション]** をクリックしてさまざまなインターフェイスを有効にします。 詳細については、次を参照してください。[テスト プロパティとテスト コンテナーでイベント](/cpp/mfc/testing-properties-and-events-with-test-container)します。

 デバッグ中にコンテナーのコードにステップ インする必要がある場合は、デバッグ バージョンのコンテナーを使用するか、デバッグ バージョンの ActiveX テスト コンテナーを使用します。 詳細については、次を参照してください。 [TSTCON サンプル。ActiveX コントロール テスト コンテナー](https://msdn.microsoft.com/library/72fa40ef-27d3-400c-813f-10b03236e600)します。

## <a name="see-also"></a>関連項目
- [COM および ActiveX のデバッグ](../debugger/com-and-activex-debugging.md)
- [ActiveX コントロール](/cpp/mfc/activex-controls)