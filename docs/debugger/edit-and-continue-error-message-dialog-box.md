---
title: エディット コンティニュのエラー メッセージ ダイアログ ボックス |Microsoft Docs
ms.custom: ''
ms.date: 06/22/2018
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.ENC.SupportedButNotAvaiable
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5fd4fe31996a75c4b743f3dac12e7b945c912506
ms.sourcegitcommit: c5e72875206b8c5737c29d5b1ec7b86eec747303
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2018
ms.locfileid: "49382793"
---
# <a name="edit-and-continue-error-message"></a>エディット コンティニュのエラー メッセージ 

**エディット コンティニュ**エディット コンティニュをサポートするコード言語でのデバッグ中にエラー メッセージ ボックスが表示されますが、エディット コンティニュは行ったコード変更は使用できません。 エラー メッセージは、詳細な説明を提供します。 ダイアログ ボックスに応答すると、次のように選択します。 **OK**  ダイアログ ボックスを閉じ、編集操作をキャンセルします。  

このエラー メッセージの原因が考えられます。  

-   SQL Server のコードを編集しようとしています。
-   最適化されたコードを編集しようとしています。 リリース ビルドからデバッグ ビルドに切り替える必要があります。
-   実行されているときに、コードを編集しようとしての代わりに、デバッガーで一時停止中です。 お試しください[ブレークポイントを設定する](../debugger/using-breakpoints.md)、および一時停止中にコードを編集します。
-   アンマネージ デバッグのみが有効にすると、マネージ コードを編集しようとしています。 エディット コンティニュを使用しない[混合モード デバッグ](../debugger/how-to-debug-in-mixed-mode.md)します。
-   コード変更を行うと、プログラミング言語でのエディット コンティニュでできません。 詳細については、の記事をご覧ください[コードの変更がサポートされているC# ](supported-code-changes-csharp.md)、 [Visual Basic エディット コンティニュで編集をサポートされていない](unsupported-edits-in-visual-basic-edit-and-continue.md)、および[C++コードの変更がサポートされている](supported-code-changes-cpp.md).
-   デバッグを開始する代わりに、接続しているアプリでコードを編集しようとして、**デバッグ**メニュー。  
-   ワトソン博士のダンプ中にコードを編集しようとしています。デバッグ  
-   ハンドルされない例外が発生した後にコードを編集しようとして、オプション**ハンドルされない例外でコール スタックをアンワインド**が選択されていません。  
-   埋め込まれたランタイム アプリケーションのデバッグ中にコードを編集しようとしています。
-   64 ビット アプリのターゲットで 4.5.1 より前の .NET Framework のバージョンを使用してマネージ コードを編集しようとしています。 エディット コンティニュでを使用する .NET Framework 4.5.1 より前に、ターゲットを設定**x86**で、  **\<ProjectName >** > **プロパティ** > **コンパイル** タブで、**高度なコンパイラ**設定します。  
-   デバッグ中に変更されたが再読み込みされたアセンブリでコードを編集しようとしています。  
-   読み込まれていないアセンブリのコードを編集しようとしています。  
-   最新バージョンにビルド エラーがあるために、古いバージョンのアプリのデバッグを開始します。
  
詳細については次を参照してください:
- [C++ の編集と続行のブログを投稿します。](https://blogs.msdn.microsoft.com/vcblog/2016/07/01/c-edit-and-continue-in-visual-studio-2015-update-3/)  
- [サポートされるコードの変更 (C++)](../debugger/supported-code-changes-cpp.md)
- [エディット コンティニュ](../debugger/edit-and-continue.md)