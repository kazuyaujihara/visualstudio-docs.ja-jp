---
title: '[全般] ([オプション] ダイアログ ボックス - [環境])'
ms.date: 03/28/2019
ms.topic: reference
f1_keywords:
- VS.Message.0x800a002e
- VS.ToolsOptionsPages.Environment.General
- VS.Environment.General
helpviewer_keywords:
- MRU lists
- windows, customizing
- MDI, environment options
- speed, environment animation
- File menu
- menus, customizing
- Windows menu customizing
- status bars, displaying
- IDE, startup options
- editors, autocompletion
- Options dialog box, General Environment
- General Environment Options dialog box
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4fdbd8c64514854aa77c358145badbf6583996f1
ms.sourcegitcommit: b14b7a938a2aba9fcce4d5e813aadf2040b0dcda
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2019
ms.locfileid: "58647272"
---
# <a name="options-dialog-box-environment--general"></a>[オプション] ダイアログ ボックス: [環境] \> [全般]

このページを使用して、統合開発環境 (IDE: Integrated Development Environment) のオプションのうち特に配色テーマ、ステータス バーの設定、およびファイル拡張子の関連付けを変更します。 **[オプション]** ダイアログ ボックスを表示するには、**[ツール]** メニューを開いて、**[オプション]** をクリックし、**[環境]** フォルダーを開き、**[全般]** ページをクリックします。 このページが一覧に表示されない場合は、**[オプション]** ダイアログ ボックスの **[すべての設定を表示]** チェック ボックスをオンにします。

## <a name="visual-experience"></a>視覚的効果

**配色テーマ**

IDE の配色テーマ (**[青]**、**[淡色]**、**[濃色]**、または **[青 (エクストラ コントラスト)]**) を選択します。

[Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=VisualStudioPlatformTeam.VisualStudio2017ColorThemeEditor) から **Visual Studio 配色テーマ エディター**をダウンロードしてインストールすることで、定義済みテーマを追加でインストールしたりカスタム テーマを作成したりすることもできます。 このツールをインストールすると、追加の配色テーマが **[配色テーマ]** ボックスの一覧に表示されます。

**タイトルの文字スタイルをメニュー バーに適用する**

メニューでは、タイトルの大文字と小文字のスタイルが既定で使用されます。 すべて大文字のスタイルを使用するには、このオプションをオフにします。

::: moniker range=">=vs-2019"

**ピクセルの密度が異なる画面のレンダリングを最適化する (再起動が必要)**

このオプションを使用して、モニターごとの 1インチあたりのドット数 (DPI) の認識 (または *PMA*) を有効または無効にします。 PMA を有効にすると、Visual Studio ユーザー インターフェイスは、表示倍率と DPI 構成に関係なく、すべてのモニターで鮮明に表示されます (複数のモニター間の表示も含まれます)。 PMA を有効にするには、Windows 10 April 2018 Update 以降および .NET Framework 4.8 以降が必要です  (これら 2 つの前提条件が満たされていない場合、このオプションは灰色表示されます)。

::: moniker-end

**クライアントのパフォーマンスに基づいて視覚的効果を自動的に調整する**

Visual Studio で視覚的効果を自動的に調整するか、ユーザーが明示的に調整するかを指定します。 この調整によって、色の表示がグラデーションからフラットに変わったり、メニューまたはポップアップ ウィンドウでのアニメーションの使用が制限されたりすることがあります。

**リッチ クライアント エクスペリエンスを有効にする**

グラデーションやアニメーションなど、Visual Studio の視覚的効果のすべてを有効にします。 リモート デスクトップ接続や古いグラフィックス アダプターを使用している場合は、これらの機能のパフォーマンスが低下する可能性があるため、このオプションをオフにします。 このオプションをオンにできるのは、**[クライアントのパフォーマンスに基づいて視覚的効果を自動的に調整する]** をオフにした場合だけです。

**可能ならハードウェアのグラフィックス アクセラレータを使用する**

可能な場合は、ソフトウェア アクセラレータではなく、ハードウェアのグラフィックス アクセラレータを使用します。

## <a name="other"></a>その他

**ウィンドウ メニューに表示する項目**

**[ウィンドウ]** メニューの [ウィンドウ] の一覧に表示されるウィンドウ数をカスタマイズします。 1 から 24 の範囲の数字を入力してください。 既定値は 10 です。

**項目を最近使用した一覧に表示**

**[ファイル]** メニューに表示される、最近使ったプロジェクトとファイルの数をカスタマイズします。 1 から 24 の範囲の数字を入力してください。 既定値は 10 です。 このオプションを使用すると、最近使用したプロジェクトやファイルを簡単に表示できます。

**ステータス バーの表示**

ステータス バーが表示されます。 ステータス バーは IDE ウィンドウの一番下にあり、処理中の操作の進行状況が表示されます。

**[閉じる] ボタンを、アクティブなツール ウィンドウに対してのみ実行する**

**[閉じる]** をクリックしたときに、ドッキング セット内のすべてのツール ウィンドウではなく、フォーカスのあるツール ウィンドウだけを閉じるように指定します。 既定では、このチェック ボックスはオンになっています。

**[自動的に隠す] ボタンを、アクティブなツール ウィンドウに対してのみ実行する**

**[自動的に隠す]** をクリックしたときに、ドッキング セット内のすべてのツール ウィンドウではなく、フォーカスのあるツール ウィンドウだけを自動的に非表示にするように指定します。 既定では、このチェック ボックスはオフになっています。

## <a name="see-also"></a>関連項目

- [[環境] ([オプション] ダイアログ ボックス)](../../ide/reference/environment-options-dialog-box.md)
- [ウィンドウ レイアウトをカスタマイズする](../../ide/customizing-window-layouts-in-visual-studio.md)