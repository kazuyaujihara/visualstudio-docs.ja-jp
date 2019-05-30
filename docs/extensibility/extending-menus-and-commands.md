---
title: メニューとコマンドの拡張 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- menus, common tasks
- VSPackages, menu tasks
- .vsct files, common menu tasks
ms.assetid: 7b2be4b9-e3fe-4412-874f-ae72ebc84c4b
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d0810e1fde5b58416b94607dccf2004fe7edb67b
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66341148"
---
# <a name="extend-menus-and-commands"></a>メニューとコマンドを拡張します。
コマンドは、アクションとプロセスを Visual Studio に追加する方法です。 ほとんどの場合は、コマンドがメニューやツールバーに表示されます。 VSPackage プロジェクト テンプレートは、非常に基本的なコマンドを実装する方法を示します。 若干時間ですがまだ基本的な実装では、次を参照してください。[メニュー コマンドを使用して拡張機能を作成する](../extensibility/creating-an-extension-with-a-menu-command.md)します。

 Visual Studio コマンド、メニューおよびツールバーの詳細については、次を参照してください。[コマンド、メニュー、およびツールバー](../extensibility/internals/commands-menus-and-toolbars.md)します。

 コマンド、メニューのおよびツールバーがで定義されている、 *.vsct*されているファイルと VSPackage プロジェクトの一部です。 Visual Studio IDE についての情報を見つけることができます、 *.vsct*ファイル[Vspackage ではどのように追加のユーザー インターフェイス要素](../extensibility/internals/how-vspackages-add-user-interface-elements.md)します。

 次のトピックでは、さまざまな種類のコマンド、メニューのおよびツールバーを追加する方法について説明します。

## <a name="in-this-section"></a>このセクションの内容
- [Visual Studio のメニュー バーにメニューを追加](../extensibility/adding-a-menu-to-the-visual-studio-menu-bar.md)上の Visual Studio のメニュー バーにメニューを追加する方法について説明します。

- [キーボード ショートカットをメニュー項目にバインド](../extensibility/binding-keyboard-shortcuts-to-menu-items.md)メニュー項目を (CTRL + 3) などのキーボード ショートカットを追加する方法について説明します。

- [メニューにサブメニューを追加する](../extensibility/adding-a-submenu-to-a-menu.md)上部のメニューにサブメニューを追加する方法について説明します。

- [最近使用した一覧をサブメニューに追加](../extensibility/adding-a-most-recently-used-list-to-a-submenu.md)最近使用したリストに追加する方法について説明します。

- [ボタンの再利用可能なグループ作成](../extensibility/creating-reusable-groups-of-buttons.md)できるように、複数のメニューに含めることができます、コマンドの項目をグループ化する方法について説明します。

- [メニュー コマンドにアイコンを追加](../extensibility/adding-icons-to-menu-commands.md)ツールバーとメニューの両方でのコマンドにアイコンを追加する方法について説明します。

- [メニュー コマンドのテキストを変更する](../extensibility/changing-the-text-of-a-menu-command.md)の使用について説明します、`TextChanges`動的に変更するメニュー項目を有効にするフラグ。

- [コマンドの外観を変更](../extensibility/changing-the-appearance-of-a-command.md)を動的に有効または、コマンドを無効にする方法について説明します。

- [ユーザー インターフェイスを更新](../extensibility/updating-the-user-interface.md)を強制的に最新の変更を反映するように、ユーザー インターフェイスの更新方法について説明します。

- [メニュー コマンドのローカライズ](../extensibility/localizing-menu-commands.md) メニューのコマンドをローカライズする方法について説明します。