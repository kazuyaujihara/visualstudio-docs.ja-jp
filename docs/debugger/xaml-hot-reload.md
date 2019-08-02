---
title: XAML を使用した XAML の作成とデバッグホットリロード
description: XAML のホットリロード、または XAML のエディットコンティニュを使用すると、アプリの実行中に XAML コードを変更できます。
ms.custom: ''
ms.date: 02/28/2019
ms.topic: conceptual
helpviewer_keywords:
- xaml edit and continue
- xaml hot reload
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f1b2428024c30b8f96babf0cab6a56c60f52fa57
ms.sourcegitcommit: 3e74ec49a54e5c3da7631f4466128cdf4384af6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2019
ms.locfileid: "68711223"
---
# <a name="write-and-debug-running-xaml-code-with-xaml-hot-reload-in-visual-studio"></a>XAML を使用した実行中の XAML コードの作成とデバッグ Visual Studio でのホットリロード

Visual Studio XAML ホットリロードは、アプリの実行中に XAML コードを変更できるようにすることで、WPF または UWP アプリの UI を構築するのに役立ちます。 この機能を使用すると、実行中のアプリのデータコンテキスト、認証状態、およびデザイン時にシミュレートするのが困難なその他の実際の複雑さの恩恵を受けながら、XAML コードを段階的にビルドおよびテストできます。

XAML ホットリロードは、次のような場合に特に役立ちます。

* アプリがデバッグモードで起動された後に、XAML コードで見つかった UI の問題を修正します。

* アプリのランタイムコンテキストを活用しながら、開発中のアプリ用の新しい UI コンポーネントを構築します。

|サポートされているアプリケーションの種類|オペレーティング システムとツール|
|-|-|-|
|Windows Presentation Foundation (WPF) |.NET Framework 4.6+</br>Windows 7 以上 |
|ユニバーサル Windows アプリ (UWP)|Windows 10 以降、 [windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk) 14393 + |

> [!NOTE]
> 現在、visual Studio XAML ホットリロードは、デバッガーがアタッチされた状態で Visual Studio でアプリケーションを実行する場合にのみサポートされます (**F5 キー**または**デバッグを開始**します)。 *プロセスにアタッチ*することによって、このエクスペリエンスを有効にすることはできません。

## <a name="known-limitations"></a>既知の制限

XAML ホットリロードの既知の制限事項を次に示します。 に実行するすべての制限を回避するには、デバッガーを停止し、操作を完了します。

|制限|WPF|UWP|メモ|
|-|-|-|-|
|アプリの実行中にイベントをコントロールに接続する|サポート非対象|サポートなし|エラーを参照:*イベントが失敗したことを確認する*|
|リソースディクショナリ内のリソースオブジェクト (アプリのページ/ウィンドウや*app.xaml*など) の作成|サポート非対象|Supported|例: を```StaticResource```と```SolidColorBrush```して使用するために、をリソースディクショナリに追加します。</br>メモ:静的リソース、スタイルコンバーター、およびリソースディクショナリに記述されたその他の要素は、XAML ホットリロードの使用中に適用または使用できます。 リソースの作成のみがサポートされていません。</br> リソースディクショナリ```Source```のプロパティを変更しています。| 
|アプリの実行中に新しいコントロール、クラス、ウィンドウ、またはその他のファイルをプロジェクトに追加する|サポート非対象|サポート非対象|なし|
|NuGet パッケージの管理 (パッケージの追加/削除/更新)|サポート非対象|サポート非対象|なし|
|{X:Bind} markup extension を使用するデータバインディングの変更|N/A|Visual Studio 2019 以降のバージョンでサポートされています|Visual Studio 2017 またはそれ以前のバージョンではサポートされていません|

## <a name="error-messages"></a>エラー メッセージ

XAML ホットリロードの使用中に、次のエラーが発生する場合があります。

|エラー メッセージ|説明|
|-|-|-|
|イベントが失敗したことを確認する|[エラー] は、アプリケーションの実行中にサポートされていないコントロールの1つにイベントを送信しようとしていることを示します。|
|XAML のエディット コンティニュに更新する要素が見つかりませんでした。|アプリケーションでホットリロードを更新できない XAML を編集しているときに、エラーが発生します。</br> このエラーは、実行中のアプリを使用して、XAML が使用されているビューに移動することによって解決される場合があります。</br> このエラーは、デバッグセッションを再開するまで、特定の変更を適用できないことを意味します。 |
|この変更はデバッグ セッション中にはサポートされません。|エラーは、実行しようとしている変更が XAML ホットリロードでサポートされていないことを示します。 デバッグセッションを停止し、変更を加えてから、デバッグセッションを再開します。|
