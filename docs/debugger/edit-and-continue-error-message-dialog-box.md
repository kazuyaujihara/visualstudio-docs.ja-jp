---
title: '[エディットコンティニュエラーメッセージ] ダイアログボックス |Microsoft Docs'
ms.date: 10/15/2018
ms.topic: reference
f1_keywords:
- vs.debug.ENC.SupportedButNotAvailable
- vs.debug.ENC.CannotEditWhileException
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Edit and Continue Error Message dialog box
ms.assetid: f98c91c0-447a-4533-85b6-87170a0dc4c3
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7df95eae689f7c3abbb0d75a7557ce749bdceee5
ms.sourcegitcommit: 40bd5b27f247a07c2e2514acb293b23d6ce03c29
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2019
ms.locfileid: "73188224"
---
# <a name="edit-and-continue-error-message"></a>エディットコンティニュのエラーメッセージ

エディットコンティニュをサポートするコード言語でデバッグしているときにエディットコンティニュ**のエラーメッセージ**ボックスが表示されますが、エディットコンティニュはコードの変更に対しては使用できません。 エラーメッセージには、より詳細な説明が表示されます。 ダイアログに応答するには、 **[OK]** を選択してダイアログボックスを閉じ、編集を取り消します。

このエラーメッセージには次のような原因が考えられます。

- SQL Server コードを編集しようとしています。
- 最適化されたコードを編集しようとしています。 リリースビルドからデバッグビルドへの切り替えが必要になる場合があります。
- デバッガーで一時停止しているときではなく、実行中にコードを編集しようとしています。 [ブレークポイントを設定](../debugger/using-breakpoints.md)し、一時停止中にコードを編集してみてください。
- アンマネージデバッグのみが有効になっている場合に、マネージコードを編集しようとしています。 エディットコンティニュは[、混合モードのデバッグ](../debugger/how-to-debug-in-mixed-mode.md)では動作しません。
- エディットコンティニュでサポートされていないコード変更をプログラミング言語で作成します。 詳細については、「 [」のC#サポートされているコード変更](supported-code-changes-csharp.md)に関する記事、 [Visual Basic エディットコンティニュで](supported-code-changes-csharp.md)サポートされていない編集、[サポートされているC++コード変更](supported-code-changes-cpp.md)に関する記事を参照してください
- **デバッグメニューから**デバッグを開始するのではなく、アタッチされているアプリのコードを編集しようとしています。
- ワトソン博士ダンプのデバッグ中にコードを編集しようとしています。
- 未処理の例外が発生した後にコードを編集しようとしています。また、[ハンドルされない**例外で呼び出し履歴をアンワインド**する] オプションが選択されていませ
- 埋め込みランタイムアプリケーションのデバッグ中にコードを編集しようとしています。
- 64ビットのアプリターゲットで4.5.1 より前の .NET Framework バージョンを使用してマネージコードを編集しようとしています。 4\.5.1 より前の .NET Framework に対してエディットコンティニュを使用するには、 **\<ProjectName >**  > **プロパティ** >  **[コンパイル]** タブ、 **[詳細**設定] コンパイラ設定で、ターゲットを **[x86]** に設定します。
- デバッグ中に変更され、再読み込みされたアセンブリ内のコードを編集しようとしています。
- 読み込まれていないアセンブリ内のコードを編集しようとしています。
- 最新バージョンにビルドエラーがあるため、古いバージョンのアプリのデバッグを開始しています。

詳細については次を参照してください:
- [C++エディットコンティニュに関するブログ記事](https://devblogs.microsoft.com/cppblog/c-edit-and-continue-in-visual-studio-2015-update-3/)
- [サポートされているコード変更 (C++)](../debugger/supported-code-changes-cpp.md)
- [エディット コンティニュ](../debugger/edit-and-continue.md)