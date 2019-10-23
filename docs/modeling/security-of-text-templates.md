---
title: テキスト テンプレートのセキュリティ
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- text templates, security
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: eab987d406d6a2c05c8350aaac9dd1ecfc13e4a8
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72660089"
---
# <a name="security-of-text-templates"></a>テキスト テンプレートのセキュリティ
テキストテンプレートには、次のようなセキュリティの問題があります。

- テキストテンプレートは、任意のコードの挿入に対して脆弱です。

- ディレクティブプロセッサを検索するためにホストが使用するメカニズムがセキュリティで保護されていない場合は、悪意のあるディレクティブプロセッサを実行できます。

## <a name="arbitrary-code"></a>任意のコード
 テンプレートを記述するときに、\< # # > タグ内に任意のコードを配置できます。 これにより、テキストテンプレート内から任意のコードを実行できます。

 信頼されたソースからテンプレートを取得していることを確認してください。 信頼できるソースからのものではないテンプレートを実行しないように、アプリケーションのエンドユーザーに警告してください。

## <a name="malicious-directive-processor"></a>悪意のあるディレクティブプロセッサ
 テキストテンプレートエンジンは、変換ホストと1つ以上のディレクティブプロセッサと対話し、テンプレートテキストを出力ファイルに変換します。 詳細については、「[テキストテンプレート変換プロセス](../modeling/the-text-template-transformation-process.md)」を参照してください。

 ディレクティブプロセッサを見つけるためにホストが使用するメカニズムが安全でない場合は、悪意のあるディレクティブプロセッサを実行するリスクがあります。 悪意のあるディレクティブプロセッサは、テンプレートの実行時に `FullTrust` モードで実行されるコードを提供できます。 カスタムテキストテンプレート変換ホストを作成する場合は、エンジンがディレクティブプロセッサを見つけるために、レジストリなどの安全な機構を使用する必要があります。