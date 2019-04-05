---
title: DslTextTransform コマンド
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language, commands
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 89d83da450014ebf29e2882438d27f9284c9bbbb
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2019
ms.locfileid: "55939035"
---
# <a name="the-dsltexttransform-command"></a>DslTextTransform コマンド
DslTextTransform.cmd、TextTransform.exe を呼び出すし、一般的なオプションを使用して実行するスクリプトです。 DslTextTransformation.cmd を使用して、夜間のビルドを自動化することができます、[!INCLUDE[dsl](../modeling/includes/dsl_md.md)]プロジェクト。 詳細については、[TextTransform ユーティリティを使ってファイルを生成する](../modeling/generating-files-with-the-texttransform-utility.md)を参照してください。

 DslTextTransform.cmd については、次のディレクトリにあります。

 **\<Visual Studio SDK Installation Path>\VisualStudioIntegration\Tools\Bin**

 DslTextTransform.cmd への入力として、次の引数を指定できます。

- ドメイン モデル プロジェクトの出力ディレクトリ。

- デザイナー定義プロジェクトの出力ディレクトリ。

- テキスト テンプレート ファイルの場所。

  DslTextTransform.cmd では、既定のディレクティブ プロセッサとアセンブリを使用して、指定したテキスト テンプレート ファイルを処理します。 カスタム ディレクティブ プロセッサを作成する場合は、独自 TextTransform.exe を呼び出すバッチ ファイルを作成できます。 このバッチ ファイルでは、アセンブリと関連付けられているカスタム ディレクティブ プロセッサを指定できます。