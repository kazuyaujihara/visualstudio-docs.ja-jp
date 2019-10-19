---
title: XSLT スタイル シートの編集
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 080bed0f-0ca9-4be7-aecd-6bdaebc04007
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7fc987f8362d5daf435b7e9de860cc13f16a1aaf
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72646058"
---
# <a name="edit-xslt-style-sheets"></a>XSLT スタイル シートの編集

XML エディターを使用して XSLT スタイルシートを編集することもできます。 IntelliSense、アウトライン、XML スニペットなどの、エディターが備える既定の機能を活用できます。 さらに、XSLT での開発を容易にする新機能もあります。

## <a name="xslt-features"></a>XSLT 機能

XSLT スタイル シートの操作時に固有な機能の説明を次の表に示します。

**構文の色分け**

@No__t_0 や `match` などの XSLT キーワードは、 **[フォントおよび色]** 設定で指定された xslt キーワードの色で表示されます。

**波下線**

XML エディターは、インストールされた*xslt .xsd*ファイルを使用して、xslt スタイルシートを検証します。 検証エラーは、青色の波下線で表示されます。 また、XML エディターでは、バックグラウンドでスタイルシートがコンパイルされ、コンパイラエラーまたは警告が適切な波下線付きで報告されます。

**スクリプトブロックのサポート**

スクリプト ブロック内のコードは XSLT デバッガーによってサポートされているので、ブレークポイントを設定してスクリプト ブロックのコードをステップ実行することができます。

**XSLT 出力の表示**

XSL 変換を実行し、XML エディターから出力を表示することができます。 詳細については、「[方法: XML エディターから XSLT 変換を実行](../xml-tools/how-to-execute-an-xslt-transformation-from-the-xml-editor.md)する」を参照してください。

**XSLT のデバッグ**

Xslt デバッガーは、XML エディターで XSLT ファイルから起動できます。 このデバッガーは、XSLT ファイルでのブレークポイントの設定や、XSLT 実行状態の表示などをサポートしています。 XSLT 変数の上にカーソルを置くと、変数の値を示すツール ヒントが表示されます。 このデバッガーを使用すると、スタイル シートのデバッグや、他のアプリケーションから呼び出されたコンパイル済みの XSL 変換のデバッグが可能です。 詳細については、「 [XSLT のデバッグ](../xml-tools/debugging-xslt.md)」を参照してください。

## <a name="see-also"></a>関連項目

- [XML エディター](../xml-tools/xml-editor.md)