---
title: IntelliSense
description: Visual Studio for Mac で IntelliSense を使用することに関する情報
author: cobey
ms.author: cobey
ms.date: 08/16/2019
ms.openlocfilehash: 3e99c31b1ab4d12532d701e4626ac9c1aae7df56
ms.sourcegitcommit: 0bd63f3bc429ae059b9df6e45c6b8dcae6152940
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2019
ms.locfileid: "70026571"
---
# <a name="intellisense"></a>IntelliSense

IntelliSense には、コードの記述と編集を支援する機能がいくつかあります。 たとえば、IntelliSense エンジンでは、コード補完だけでなく、メンバー一覧、パラメーター ヒント、クイック ヒントも提供されます。

Visual Studio for Mac の場合、IntelliSense はコア エディター サービスから提供され、C#、XAML、F#、JavaScript など、さまざまな言語でサポートされています。 Visual Studio for Mac は高度な IntelliSense 機能も備えています。たとえば、プロジェクトにまだインポートされていないライブラリから入力候補を表示できます。

## <a name="code-completion"></a>コード補完

C# コード ファイルなど、サポートされているファイル内で入力しているとき、現在入力している文字列で有効な入力候補が入力候補一覧に表示され、入力を続けると更新されます。 さらに、テキストを削除すると、一覧が再び自動更新され、特定の文字列を補完する候補が増えます。 

入力候補ウィンドウには、入力候補を種類で絞り込むための機能もあります。 たとえば、クラスやデリゲートなどの型のみを表すように一覧のメンバーを制限できます。 このフィルタリング プロセスは、フィルタリングされる型を表す特定のアイコンをクリックするか、特定の型に対応しているキーボード ショートカットで有効にできます。 入力候補ウィンドウの下部には次のようなアイコンがあります。

| アイコン                         | name          | キーワード    | ホット キー |
| -----------------------------|---------------| -----------|--------|
| ![クラス アイコン](media/classes-icon.png)  | class         | `class`    |  ⌥C
| ![定数アイコン](media/constant-icon.png) | 定数      | `const`    |  ⌥O
| ![デリゲート アイコン](media/delegate-icon.png) | delegate      | `delegate` |  ⌥D
| ![列挙型アイコン](media/enums-icon.png)    | enum          | `enum`     |  ⌥E
| ![イベント アイコン](media/event-icon.png)    | event         |            |  ⌥V
| ![フィールド アイコン](media/fields-icon.png)   | フィールド         |            |  ⌥F
| ![インターフェイス アイコン](media/interface-icon.png)| interface     | `interface`|  ⌥I
| ![キーワード アイコン](media/keyword-icon.png)  | keyword       |            |  ⌥K
| ![メソッド アイコン](media/method-icon.png)   | メソッド        |            |  ⌥M
| ![名前空間アイコン](media/namespace-icon.png)| namespace     | `namespace`|  ⌥N
| ![プロパティ アイコン](media/props-icon.png)    | property      |            |  ⌥P
| ![スニペット アイコン](media/snippet-icon.png)  | snippet       | `class`    |  ⌥S
| ![構造体アイコン](media/struct-icon.png)   | 構造体     | `struct`   |  ⌥S

いずれかのアイコンをクリックするか、対応するホットキーを押すと、入力候補一覧はフィルター セットで定義されている型にのみ制限されます。  

![IntelliSense の型によるフィルター処理](media/intellisense-typefiltering.gif)

## <a name="show-import-items"></a>[Show Import Items]\(インポート項目を表示\)

既定では、IntelliSense の入力候補は、プロジェクトにインポートされているライブラリからのみ、入力候補を表示します。 たとえば、`using` 経由で `System.Collections.Generic` をインポートしていない場合、`List<>` の入力候補は表示されません。 インポートしていないライブラリから入力候補を表示するには、Visual Studio for Mac の基本設定内で **[Show Import Items]\(インポート項目を表示\)** を有効にする必要があります。 この設定は **[基本設定]、[テキスト エディター]、[IntelliSense]** の順に選択すると見つかります。

![IntelliSense の [Show Import Items]\(インポート項目を表示\)](media/intellisense-showimport.png)

**[Show Import Items]\(インポート項目を表示\)** を有効にすると、まだインポートしていない入力候補が入力候補一覧に含まれます。 宣言されていないライブラリに対応する項目を選択すると、そのライブラリの `using` ステートメントがコード ファイルのヘッダーに自動的に追加されます。 入力候補が属しているライブラリの名前も入力候補自体と共に一覧表示されます。

![[Show Import Items]\(インポート項目を表示\) の一覧](media/intellisense-importaction.png)

## <a name="parameter-window"></a>パラメーター ウィンドウ

IntelliSense のもう 1 つの機能は、適切なところでパラメーター リストを表示する機能です。 パラメーター リストからは、呼び出されるコードのメソッド シグネチャの詳細が提供されます。 シグネチャ内の上下矢印をクリックすることで、利用できるパラメーター シグネチャを順番に切り替え、ニーズに最も適したものを決定できます。 許可されるデータの型の詳細に加え、XML コメントにターゲット メソッドで定義されている説明が表示されることもあります。

![パラメーター リスト](media/intellisense-parameter.png)

パラメーターを入力すると、現在編集中のパラメーターが太字になります。一方、非アクティブなパラメーターには標準の太さになります。 


## <a name="triggering-completion-window-and-parameter-window"></a>入力候補ウィンドウとパラメーター ウィンドウのトリガー

入力候補ウィンドウは、ソース ファイル内で入力すると自動的にトリガーされます。 ただし、ショートカット `control-space` を使用して入力候補ウィンドウをトリガーすることもできます。 このショートカットを使用すると、入力候補一覧がキャレットの現在位置に表示されます。 

また、`control-shift-space` を入力することで、パラメーター ウィンドウの表示を手動でトリガーできます。 パラメーター リストにとって有効な位置にカレットがあるとき、パラメーター リストはキャレットの位置の近くに表示されます。

## <a name="see-also"></a>関連項目

- [クイック アクション (Windows 上の Visual Studio)](/visualstudio/ide/quick-actions)
- [コードのリファクタリング (Windows 上の Visual Studio)](/visualstudio/ide/refactoring-in-visual-studio)
