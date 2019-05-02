---
title: UWP アプリの更新 |Microsoft Docs
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
ms.openlocfilehash: 0ee4c97c4ecbf665bbaef39b658a4b96715acb23
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63408644"
---
# <a name="refresh-a-uwp-app-in-visual-studio"></a>Visual Studio で UWP アプリを更新します。

 選択して、JavaScript を使用して UWP アプリを更新して、デバッグ中に、コードに変更を行うことができます、**更新の Windows アプリ**のボタンでは、**デバッグ**ツールバー。 このボタンを選択すると、デバッガーを停止したり再起動したりせずにアプリが再度読み込まれます。 更新機能によって、HTML、CSS、および JavaScript コードを変更し、その結果をすばやく確認できます。 この機能は UWP アプリをサポートします。

 更新では、アプリの状態は保持されません。また、アプリに対する次の変更は反映されません。

- パッケージ マニフェストに指定されたイメージの変更を含むパッケージ マニフェスト ファイルの変更。

- SDK 参照の追加や削除などの参照の変更、または Windows ランタイム コンポーネント (.winmd ファイル) の変更。

- .resjson ファイル内の文字列の変更などのリソースの変更。

- パス名の変更、新しいプロジェクト ファイル、または削除ファイルが発生するプロジェクト ファイルの変更。

- 選択したデバッグ デバイスの変更などのプロジェクトおよび項目プロパティの変更、またはファイルのパッケージ操作の変更 ([プロパティ] ウィンドウ内)。

> [!IMPORTANT]
> 参照やパッケージ マニフェストの変更など、上記の項目の変更を行った場合、HTML、CSS、および JavaScript のソース ファイルを更新するには、デバッガーを停止して再起動する必要があります。

### <a name="to-refresh-an-app"></a>アプリを更新するには

1. UWP プロジェクトを Visual Studio で開いて、次のように選択します。**ローカル マシン**デバッグ ターゲットとして。

     ![デバッグ ターゲット リスト](../debugger/media/js_select_target.png "JS_Select_Target")

3. F5 キーを押して、アプリをデバッグ モードで実行します。

4. Visual Studio に切り替えます 

5. UWP アプリのホーム ページで、HTML の一部を編集します。

7. をクリックして、**更新の Windows アプリ**のように、ボタン。![Windows アプリのボタンを更新](../debugger/media/js_refresh.png "JS_Refresh")します。 (または F4 キーを押します)。

8. アプリに切り替えます。 アプリが再度読み込まれ、更新された HTML は、アプリを表示するために使用します。

## <a name="see-also"></a>関連項目
- [クイック スタート:HTML および CSS のデバッグ](../debugger/quickstart-debug-html-and-css.md)