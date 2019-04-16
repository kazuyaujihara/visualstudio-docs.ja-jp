---
title: Visual Studio 2019 の新機能
titleSuffix: ''
description: Visual Studio 2019 の新機能について説明します。
ms.date: 04/04/2019
helpviewer_keywords:
- Visual Studio, what's new
- what's new [Visual Studio]
ms.assetid: 00bec66b-bcee-46f5-91d9-f73a2b469744
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.prod: visual-studio-windows
ms.technology: vs-ide-general
ms.topic: conceptual
ms.workload:
- multiple
ms.openlocfilehash: 25a7f5f0e53518e9beb4b509ab27ae4de0f28fa7
ms.sourcegitcommit: b6177ce198c7c5a00030604c9d4faa735405d5df
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/04/2019
ms.locfileid: "59018156"
---
# <a name="whats-new-in-visual-studio-2019"></a>Visual Studio 2019 の新機能

**[16.0 リリース](/visualstudio/releases/2019/release-notes/)の更新**

>[!div class="button"]
>[Visual Studio 2019 のダウンロード](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019)

Visual Studio 2019 では、あらゆる開発者、アプリ、プラットフォームを対象とした最高クラスのツールとサービスを提供しています。 Visual Studio を初めて使用する方も、長年使用している方も、この新しいバージョンを気に入っていただけるでしょう。

新機能の大まかな要約を示します。

* **[開発](#develop)**:パフォーマンスの向上、迅速なコードのクリーンアップ、優れた検索結果による生産性向上に引き続き注力しています。
* **[共同作業](#collaborate)**:クラウド ファーストのワークフロー、リアルタイムでの編集とデバッグ、Visual Studio でのコード レビューによる自然な共同作業を体験してください。
* **[デバッグ](#debug)**:特定の値を強調表示してそこに移動したり、メモリの使用を最適化したり、アプリケーションの実行のスナップショットを自動的に取得したりできます。

このバージョンのすべての新機能の一覧は、[リリース ノート](/visualstudio/releases/2019/release-notes/)を参照してください。 

## <a name="develop"></a>開発

新機能で、時間を節約しましょう。
<br><br>
> [!VIDEO https://www.youtube.com/embed/n5sJ4EewKGk]

### <a name="improved-search"></a>検索機能の向上

新しい検索エクスペリエンス (以前のクイック起動) は、より高速でより効果的になりました。 入力すると、検索結果が動的に表示されるようになりました。 また、将来使用するためにコマンドをより簡単に記憶できるように、検索結果にコマンドのキーボード ショートカットが含まれるようになりました。

   ![Visual Studio 2019 の新しい検索エクスペリエンスのアニメーション](media/vs-2019/new-search-feature.gif)

新しいあいまい検索ロジックでは、入力ミスがあっても、目的の内容を検索できます。 新しい検索機能は、探しているものがコマンド、設定、ドキュメント、またはその他の便利な機能であるかに関わらず、検索対象を見つけやすくします。

### <a name="refactorings"></a>リファクタリング

新しい C# リファクタリングにより、コードの整理が簡単になります。 **Ctrl +.** を押し、 実行するアクションを選択するだけでリファクタリングを呼び出せます。 

   ![Visual Studio 2019 のリファクタリングのアニメーション](media/vs-2019/refactorings.gif)

メソッド パラメーターをラップできるものなど、新しいリファクタリングが多数追加されました。

### <a name="intellicode"></a>IntelliCode

[Visual Studio IntelliCode](/visualstudio/intellicode/) は、人工知能 (AI) を使用したソフトウェア開発作業を強化するための拡張機能です。 IntelliCode は GitHub 上の 2,000 のオープン ソース プロジェクト (それぞれに 100 個以上の星が付いています) 全体をトレーニングして、レコメンデーションを生成します。

 ![Visual Studio 2019 の IntelliCode のアニメーション](media/vs-2019/IntelliCode.gif)

Visual Studio IntelliCode が生産性の強化に役立つ方法を次にいくつか示します。

* 文脈に合わせてコードの入力候補を示す
* チームのパターンやスタイルに準拠するように開発者を導く
* 見つけにくいコード問題を見つける
* コード レビューの焦点を本当に重要な領域に向ける

Visual Studio 向けの IntelliCode を初めてプレビューしたときには、C# しかサポートしていませんでした。 今回、Visual Studio で C++ のサポートに加え、XAML のサポートも追加されました。

C# を使用している場合は、独自のコードでカスタム モデルをトレーニングする機能も追加されました。

IntelliCode の詳細については、ブログの投稿「[Code more, scroll less with Visual Studio IntelliCode](https://devblogs.microsoft.com/visualstudio/code-more-scroll-less-with-visual-studio-intellicode/)」(Visual Studio IntelliCode を使用して少ないスクロールで多くのコードを書く) を参照してください。 

### <a name="code-cleanup"></a>コードのクリーンアップ

新しいドキュメントの正常性インジケーターと組み合わされたのが、新しいコード クリーンアップ コマンドです。 この新しいコマンドを使用して、警告と提案を特定し、ボタンをクリックして両方を修正することができます。

クリーンアップにより、コードが書式設定され、[現在の設定](code-styles-and-quick-actions.md)、[.editorconfig files](create-portable-custom-editor-options.md)、または [Roslyn アナライザー](../code-quality/roslyn-analyzers-overview.md) のいずれかの提案に従って、任意のコード修正が適用されます。

   ![Visual Studio 2019 の新しいコード クリーンアップ コントロールのスクリーン ショット](media/vs-2019/code-cleanup-profile.png)

修正機能のコレクションをプロファイルとして保存することもできます。 たとえば、コードを書いている間に頻繁に適用する小規模なターゲット修正機能があり、コード レビューの前に適用する完全な修正機能のセットがそれ以外にある場合は、それらの異なるタスクに対処するためのプロファイルを構成することができます。

   ![Visual Studio 2019 の新しいコード クリーンアップ コントロールのスクリーン ショット](media/vs-2019/code-cleanup-profile-configure.png)

## <a name="collaborate"></a>共同作業

問題を解決するためにチームを作ります。
<br><br>
> [!VIDEO https://www.youtube.com/embed/dKLJsiK1QU8]

### <a name="cloud-first-workflow"></a>クラウド ファーストのワークフロー

Visual Studio 2019 を開いてまず気付くことは、新しいスタート ウィンドウです。

   ![Visual Studio 2019 の新しいスタート ウィンドウのスクリーンショット](media/vs-2019/start-window-dark.png)

スタート ウィンドウには、コードをすばやく書くためのいくつかのオプションが表示されています。 最初に、リポジトリからコードを複製したりチェックアウトしたりできるオプションを追加しました。  

   ![Visual Studio 2019 の 'Git ファースト' エクスペリエンスのアニメーション](media/vs-2019/git-first.gif)

スタート ウィンドウには、プロジェクトやソリューションを開いたり、ローカル フォルダーを開いたり、新しいプロジェクトを作成したりするオプションも含まれています。

詳しくは、「[Get to code:How we designed the new Visual Studio start window (コードを取得: 新しい Visual Studio 開始ウィンドウの設計方法)](https://devblogs.microsoft.com/visualstudio/get-to-code-how-we-designed-the-new-visual-studio-start-window/)」のブログ投稿をご覧ください。

### <a name="live-share"></a>Live Share

[Visual Studio Live Share](https://visualstudio.microsoft.com/services/live-share/) は開発者向けのサービスであり、これを使用することで、コードベースとそのコンテキストをチームメイトと共有し、Visual Studio 内から直接、双方向のインスタント コラボレーションを実現できます。 Live Share では自分が共有したプロジェクトをチームメイトがシームレスかつ安全に読み取り、移動、編集、デバッグすることができます。

また、Visual Studio 2019 では、このサービスは既定でインストールされます。

![Visual Studio 2019 の Live Share コラボレーション機能を示すアニメーション](media/vs-2019/live-share.gif)

詳しくは、「[Visual Studio Live Share for real-time code reviews and interactive education](https://devblogs.microsoft.com/visualstudio/visual-studio-live-share-for-real-time-code-reviews-and-interactive-education/)」(Visual Studio Live Share のリアルタイム コード レビューと対話型の教育) と「[Live Share now included with Visual Studio 2019](https://devblogs.microsoft.com/visualstudio/live-share-now-included-with-visual-studio-2019/)」(Visual Studio 2019 に Live Share を導入) のブログ投稿を参照してください。

### <a name="integrated-code-reviews"></a>統合されたコード レビュー

ダウンロードして Visual Studio 2019 で使用できる新しい拡張機能を導入しました。 この新しい拡張機能を使用すると、Visual Studio を離れることなく、チームからのプル要求を確認、実行、さらにはデバッグすることもできます。 GitHub と Azure DevOps の両方のリポジトリのコードをサポートしています。

   ![Visual Studio 2019 の新しいスタート ウィンドウのスクリーンショット](media/vs-2019/pr-experience.png)

今すぐ作業を開始するには、[Visual Studio 用のプル要求](https://aka.ms/pr4vs)拡張機能を Visual Studio Marketplace からダウンロードします。

## <a name="debug"></a>デバッグ

正確なターゲット設定に注力しています。
<br><br>
> [!VIDEO https://www.youtube.com/embed/hr72Fs8n_9c]

### <a name="performance-gains"></a>パフォーマンスの向上

1 回限り排他的な C++ データ ブレークポイントを .NET Core アプリケーション向けに採用しました。

   ![Visual Studio 2019 のデバッグ データ ブレークポイントを示すアニメーション](media/vs-2019/debug-data-breakpoints.gif)

コードを C++ と .NET Core のどちらで書いている場合でも、データ ブレークポイントは通常のブレークポイントを配置する適切な代替手段となります。 データ ブレークポイントは、グローバル オブジェクトがリストのどこで修正、追加、削除されているかを見つけるようなシナリオでも適しています。 

また、大規模なアプリケーションを開発している C++ の開発者の場合、Visual Studio 2019 ではシンボルをプロセス外にできるため、メモリ関連の問題が発生することなくアプリケーションをデバッグできます。

### <a name="search-while-debugging"></a>デバッグ時の検索

以前にも使ったことがあるかもしれませんが、値セットの中の文字列をウォッチ ウィンドウで調べます。 Visual Studio 2019 では、検索するオブジェクトと値を見つけやすくするため、ウォッチ、ローカル、自動変数のウィンドウに検索が追加されました。

   ![Visual Studio 2019 のデバッグ検索ウィンドウを示すアニメーション](media/vs-2019/debug-window-search.gif)

また、ウォッチ、ローカル、自動変数のウィンドウに表示される値を書式設定することもできます。  任意のウィンドウ内でいずれかの項目をダブルクリックしてコンマ (",") を追加し、使用可能な書式指定子のドロップダウン リストにアクセスします。各書式指定子には、意図した効果の説明が含まれています。

   ![Visual Studio 2019 の新しいウォッチ ウィンドウと値の書式設定機能](media/search-watch-window.png)

詳細については、「[Enhanced in Visual Studio 2019:Search for Objects and Properties in the Watch, Autos, and Locals Windows](https://devblogs.microsoft.com/visualstudio/enhanced-in-visual-studio-2019-search-for-objects-and-properties-in-the-watch-autos-and-locals-windows/)」(Visual Studio 2019 での機能拡張: [ウォッチ]、[自動変数]、[ローカル] ウィンドウでオブジェクトとプロパティを検索する) ブログ投稿をご覧ください。

### <a name="snapshot-debugger"></a>スナップショット デバッガー

何が起きているかを正確に把握するため、クラウド内でのアプリの実行のスナップショットを取得します。 (この機能は Visual Studio Enterprise でのみ使用できます。)

   ![Visual Studio 2019 Enterprise のスナップショット デバッガーを示すアニメーション](media/vs-2019/snapshot-debugger.gif)

Azure VM で実行される ASP.NET (Core およびデスクトップ) アプリケーションを対象とするサポートが追加されました。 また、Azure Kubernetes Service で実行されるアプリケーションのサポートが追加されました。 スナップショット デバッガーは、実稼働環境で発生する問題の解決にかかる時間を大幅に短縮するのに役立ちます。

詳細については、「[Debug live ASP.NET Azure apps using the Snapshot Debugger (スナップショット デバッガーを使用したライブ ASP.NET Azure アプリのデバッグ)](../debugger/debug-live-azure-applications.md)」ページと「[Introducing Time Travel Debugging for Visual Studio Enterprise 2019 (Visual Studio Enterprise 2019 のタイム トラベル デバッグの概要)](https://devblogs.microsoft.com/visualstudio/introducing-time-travel-debugging-for-visual-studio-enterprise-2019/)」ブログ投稿を参照してください。

## <a name="give-us-feedback"></a>フィードバックの送信

Visual Studio チームにフィードバックを送ることにどんな意味があるのでしょうか? お客様からのフィードバックは、すべて真剣に考慮することにしています。 フィードバックによって今後の動向が左右されることになります。

* Visual Studio を向上させることができるご提案がある場合は、[[提案の送信]](talk-to-us.md#i-want-to-make-a-suggestion-about-visual-studio-features) ツールを使用して、ご提案を送信してください。

* ハング、クラッシュ、またはその他のパフォーマンスの問題が発生した場合、[[問題の報告]](talk-to-us.md#i-want-to-report-a-problem-with-visual-studio) ツールを使用すると、再現コードやサポート ファイルを簡単に Microsoft と共有することができます。

## <a name="see-also"></a>関連項目

* [Visual Studio 2019 のお知らせ](https://devblogs.microsoft.com/visualstudio/visual-studio-2019-code-faster-work-smarter-create-the-future/)
* [Visual Studio 2019 リリース ノート](/visualstudio/releases/2019/release-notes/)
* [Visual Studio 2019 SDK の新機能](../extensibility/whats-new-visual-studio-2019-sdk.md)
* [Visual Studio 2019 for Mac が公開](https://devblogs.microsoft.com/visualstudio/visual-studio-2019-for-mac-is-now-available/)
* [Microsoft Connect(); 2018 カンファレンス](https://www.microsoft.com/connectevent)
