---
title: UWP アプリを更新する |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- JavaScript debugging, refreshing pages [UWP apps]
- debugging, refreshing pages [UWP apps]
- DOM Explorer, Refresh [UWP apps]
- Refresh [UWP apps]
ms.assetid: fd99ee60-fa94-46df-8b17-369f60bfd908
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- uwp
ms.openlocfilehash: 0b1d19c0b607d2c5a09fddc9d4550230e478d57a
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72730309"
---
# <a name="refresh-a-uwp-app-in-visual-studio"></a>Visual Studio での UWP アプリの更新

 デバッグ中にコードを変更した後、 **[デバッグ]** ツールバーの **[Windows アプリケーションの更新]** ボタンを選択することで、JavaScript を使用して UWP アプリを更新できます。 このボタンを選択すると、デバッガーを停止したり再起動したりせずにアプリが再度読み込まれます。 更新機能によって、HTML、CSS、および JavaScript コードを変更し、その結果をすばやく確認できます。 この機能は、UWP アプリでサポートされています。

 更新では、アプリの状態は保持されません。また、アプリに対する次の変更は反映されません。

- パッケージ マニフェストに指定されたイメージの変更を含むパッケージ マニフェスト ファイルの変更。

- SDK 参照の追加や削除などの参照の変更、または Windows ランタイム コンポーネント (.winmd ファイル) の変更。

- .resjson ファイル内の文字列の変更などのリソースの変更。

- パス名の変更、新しいプロジェクト ファイル、または削除ファイルが発生するプロジェクト ファイルの変更。

- 選択したデバッグ デバイスの変更などのプロジェクトおよび項目プロパティの変更、またはファイルのパッケージ操作の変更 ([プロパティ] ウィンドウ内)。

> [!IMPORTANT]
> 参照やパッケージ マニフェストの変更など、上記の項目の変更を行った場合、HTML、CSS、および JavaScript のソース ファイルを更新するには、デバッガーを停止して再起動する必要があります。

### <a name="to-refresh-an-app"></a>アプリを更新するには

1. Visual Studio で UWP プロジェクトを開いた状態で、デバッグターゲットとして **[ローカルコンピューター]** を選択します。

     ![デバッグターゲットリストの選択](../debugger/media/js_select_target.png "JS_Select_Target")

3. F5 キーを押して、アプリをデバッグ モードで実行します。

4. Visual Studio に切り替えます

5. UWP アプリのホームページで、一部の HTML を編集します。

7. **[Windows アプリケーションの更新]** ボタンをクリックします。次のように表示されます。 [ ![Windows アプリケーションの更新] ボタン](../debugger/media/js_refresh.png "JS_Refresh")。 (または F4 キーを押します)。

8. アプリに切り替えます。 アプリが再読み込みされ、更新された HTML がアプリのレンダリングに使用されます。

## <a name="see-also"></a>関連項目
- [クイック スタート: HTML および CSS のデバッグ](../debugger/quickstart-debug-html-and-css.md)