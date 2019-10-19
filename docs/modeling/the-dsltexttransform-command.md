---
title: DslTextTransform コマンド
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language, commands
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a303fc3ddb880402e3f998b2360122f6f056b757
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72605939"
---
# <a name="the-dsltexttransform-command"></a>DslTextTransform コマンド
DslTextTransform は、TextTransform を呼び出すスクリプトであり、共通のオプションを使用して実行されます。 DslTextTransformation を使用すると、[!INCLUDE[dsl](../modeling/includes/dsl_md.md)] プロジェクトの夜間ビルドを自動化できます。 詳細については、「 [TextTransform ユーティリティを使用したファイルの生成](../modeling/generating-files-with-the-texttransform-utility.md)」を参照してください。

 DslTextTransform は、次のディレクトリにあります。

 **\<Visual Studio SDK インストールパス > \VisualStudioIntegration\Tools\Bin**

 DslTextTransform への入力として、次の引数を指定できます。

- ドメインモデルプロジェクトの出力ディレクトリ。

- デザイナー定義プロジェクトの出力ディレクトリ。

- テキストテンプレートファイルの場所。

  DslTextTransform は、既定のディレクティブプロセッサとアセンブリを使用して、指定されたテキストテンプレートファイルを処理します。 カスタムディレクティブプロセッサを作成する場合は、TextTransform を呼び出す独自のバッチファイルを作成できます。 このバッチファイルでは、アセンブリおよび関連付けられているカスタムディレクティブプロセッサを指定できます。