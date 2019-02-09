---
title: '方法: XSLT でブレークポイントを使用する'
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9676894b75696879b8c8193037822005658f5169
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2019
ms.locfileid: "55913942"
---
# <a name="how-to-use-breakpoints-with-xslt"></a>方法: XSLT でブレークポイントを使用します。

XSLT スタイル シート内または XML ソース ドキュメント内でブレークポイントを設定することができます。 タグにブレークポイントを設定した場合は、実行の開始時に、ソース行情報を含む次のステートメントにブレークポイントが移動します。

詳細については、次を参照してください。[デバッグの基礎。ブレークポイント](../debugger/using-breakpoints.md)します。

## <a name="set-a-breakpoint-in-a-style-sheet"></a>スタイル シートにブレークポイントを設定します。

XSLT スタイル シートでは、開始タグ、終了タグ、およびテキスト ノードにブレークポイントを設定できます。 スクリプト ブロック内のコードにブレークポイントを設定することもできます。

### <a name="to-set-a-breakpoint-in-a-style-sheet"></a>スタイル シート内にブレークポイントを設定するには

1.  XML エディターでスタイル シートを開きます。

2.  ブレークポイントの位置にカーソルを置き、右クリックし、 をポイント**ブレークポイント**、 をクリック**ブレークポイントの挿入**します。

3.  参照 ボタンをクリックします (**.**) で、**入力**ドキュメントのプロパティ ウィンドウのフィールド。

4.  XML ソース ドキュメントを見つけてクリックして**オープン**します。

     これで、XSLT 変換のために使用されるソース ドキュメント ファイルが設定されます。

5.  をクリックして、 **XSL のデバッグ**XML エディターのツールバーのボタンをクリックします。

## <a name="set-a-breakpoint-in-an-xml-source-document"></a>XML ソース ドキュメントにブレークポイントを設定します。

XML ソース ドキュメントでは、要素、属性、名前空間ノード、コメント、処理命令、およびテキスト ノードにブレークポイントを設定できます。 ドキュメント ノード、または、親要素から継承された名前空間ノードにブレークポイントを設定することはできません。

### <a name="to-set-a-breakpoint-in-an-xml-source-document"></a>XML ソース ドキュメント内にブレークポイントを設定するには

1.  XML エディターで XML ドキュメントを開きます。

2.  ブレークポイントの位置にカーソルを置き、右クリックし、 をポイント**ブレークポイント**、 をクリック**ブレークポイントの挿入**します。

3.  参照 ボタンをクリックします (**.**) で、 **Stylesheet**ドキュメントのプロパティ ウィンドウのフィールド。

4.  XML ソース ドキュメントを見つけてクリックして**オープン**します。

     これで、XSLT 変換のために使用されるソース ドキュメント ファイルが設定されます。

5.  をクリックして、 **XSL のデバッグ**XML エディターのツールバーのボタンをクリックします。

## <a name="see-also"></a>関連項目

- [チュートリアル: XSLT スタイル シートをデバッグします。](../xml-tools/walkthrough-debug-an-xslt-style-sheet.md)