---
title: テキスト テンプレートのセキュリティ
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- text templates, security
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 66159516c6b1360203130dedb56c0e6c192a118a
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "60050012"
---
# <a name="security-of-text-templates"></a>テキスト テンプレートのセキュリティ
テキスト テンプレートには、次のセキュリティの懸念事項があります。

- テキスト テンプレートは、任意のコードが挿入される点で脆弱です。

- ホストがディレクティブ プロセッサの検索に使用するメカニズムが安全でない場合は、悪意のあるディレクティブ プロセッサを実行できます。

## <a name="arbitrary-code"></a>任意のコード
 テンプレートを記述するときは、 \<## > タグ内にコードを配置します。 これにより、任意のコードをテキスト テンプレート内から実行できます。

 信頼できるソースからテンプレートを取得していることを確認します。 信頼できる発行元から付属していないテンプレートを実行しないようにアプリケーションのエンドユーザーに警告していることを確認してください。

## <a name="malicious-directive-processor"></a>悪意のあるディレクティブ プロセッサ
 テキスト テンプレート エンジンは、出力ファイルへテンプレート テキストを変換するときに、変換ホストと 1 つまたは複数のディレクティブ プロセッサと対話します。 詳細については、[テキスト テンプレート変換プロセス](../modeling/the-text-template-transformation-process.md)を参照してください。

 ホストがディレクティブ プロセッサの検索に使用するメカニズムが安全でない場合は、悪意のあるディレクティブ プロセッサを実行するリスクがあります。 悪意のあるディレクティブ プロセッサは、テンプレートを実行するときに`FullTrust`モードで実行されるコードを提供する可能性があります。 カスタム テキスト テンプレート変換ホストを作成する場合は、ディレクティブ プロセッサを検索するエンジンのためにレジストリなど、セキュリティで保護されたメカニズムを使用しなければなりません。