---
title: XSLT スタイル シートの編集
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 080bed0f-0ca9-4be7-aecd-6bdaebc04007
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: dab4013bf3921a2af4f69d464c10d1e70f9407b3
ms.sourcegitcommit: 3ca33862c1cfc3ccb83de3e95f1e69e860ab143a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57526205"
---
# <a name="edit-xslt-style-sheets"></a>XSLT スタイル シートの編集

XML エディターは、XSLT スタイル シートの編集にも使用できます。 IntelliSense、アウトライン、XML スニペットなどの、エディターが備える既定の機能を活用できます。 さらに、XSLT での開発を容易にする新機能もあります。

## <a name="xslt-features"></a>XSLT 機能

XSLT スタイル シートの操作時に固有な機能の説明を次の表に示します。

**構文の色分け表示**

XSLT キーワードなど`template`と`match`で指定された XSLT キーワードの色で表示されますが、**フォントおよび色**設定します。

**波線の下線**

XML エディターを使用して、インストールされている*置かれている xslt.xsd* XSLT スタイル シートを検証するファイル。 検証エラーは、青色の波下線で表示されます。 XML エディターでは、バック グラウンドとコンパイラのエラーや警告の適切な波下線が引かでスタイル シートもコンパイルします。

**スクリプト ブロックのサポート**

スクリプト ブロック内のコードは XSLT デバッガーによってサポートされているので、ブレークポイントを設定してスクリプト ブロックのコードをステップ実行することができます。

**XSLT 出力の表示**

XSL 変換を実行して、XML エディターからの出力を表示できます。 詳細については、「[方法 :XML エディターから XSLT 変換を実行](../xml-tools/how-to-execute-an-xslt-transformation-from-the-xml-editor.md)します。

**XSLT をデバッグします。**

XML エディターで XSLT ファイルから XSLT デバッガーを起動することができます。 このデバッガーは、XSLT ファイルでのブレークポイントの設定や、XSLT 実行状態の表示などをサポートしています。 XSLT 変数の上にカーソルを置くと、変数の値を示すツール ヒントが表示されます。 このデバッガーを使用すると、スタイル シートのデバッグや、他のアプリケーションから呼び出されたコンパイル済みの XSL 変換のデバッグが可能です。 詳細については、次を参照してください。 [XSLT のデバッグ](../xml-tools/debugging-xslt.md)します。

## <a name="see-also"></a>関連項目

- [XML エディター](../xml-tools/xml-editor.md)