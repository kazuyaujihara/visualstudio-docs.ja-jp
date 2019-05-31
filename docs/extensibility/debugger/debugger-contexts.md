---
title: デバッガー コンテキスト |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], contexts
ms.assetid: 79808036-b680-4e4c-9c61-4ed43aa11323
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 011999929fd4cb1508bf4958629e622684f35739
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66345989"
---
# <a name="debugger-contexts"></a>デバッガー コンテキスト
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]デバッグ、デバッグ エンジン (DE) の動作を同時にいくつかの異なるコンテキスト内で。

- コード コンテキスト、プログラムの実行のストリームの現在の場所について説明します。

- ドキュメントのコンテキストまたは位置で、ソース ドキュメント内の現在位置をについて説明します。

- 式の評価は行わコンテキストを記述する式の評価のコンテキスト。

## <a name="in-this-section"></a>このセクションの内容
 [コード コンテキスト](../../extensibility/debugger/code-context.md)場所コードは表現できない手順については、他の手段で、従来とは異なる言語ではなく現在の実行時のアーキテクチャでプログラムの命令ストリーム内のアドレスとして、コードのコンテキストについて説明します。

 [位置を文書化](../../extensibility/debugger/document-position.md)で IDE に既知のソース ファイル内の位置の抽象化を使用して Visual Studio のデバッグ ドキュメントの位置を定義します。

 [ドキュメント コンテキスト](../../extensibility/debugger/document-context.md)で Visual Studio のデバッグ ソース ファイルに関連ドキュメント コンテキストを表すについて説明します。 また、シンボル ハンドラーがドキュメントのコンテキストにコードのコンテキストをマップする方法について説明します。

 [式の評価コンテキスト](../../extensibility/debugger/expression-evaluation-context.md)Visual Studio で使用する式の評価コンテキストに情報を提供します。 たとえば、スタック フレームに関連付けられている式の評価のコンテキストでは、ローカル変数、メソッド パラメーター、およびクラス メンバーを評価するため、コンテキストを提供します。

## <a name="related-sections"></a>関連項目
 [概念をデバッグ](../../extensibility/debugger/debugger-concepts.md)デバッグ アーキテクチャの主要な概念について説明します。

 [コンポーネントのデバッグ](../../extensibility/debugger/debugger-components.md)Visual Studio のデバッグ エンジン (DE)、式エバリュエーター (EE) およびシンボル ハンドラー (SH) のコンポーネントのデバッグの概要を説明します。

 [タスクのデバッグ](../../extensibility/debugger/debugging-tasks.md)さまざまなプログラムの起動や式の評価などのタスクのデバッグへのリンクが含まれています。