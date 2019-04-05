---
title: '方法: XSLT でブレークポイントを使用する |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: bf7bbc2c-71dc-4cac-a6fc-add6b27d92ed
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 5590d9f33d2c34b7d3d86aaf00307419685ca8da
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58973997"
---
# <a name="how-to-use-breakpoints-with-xslt"></a>方法: XSLT でブレークポイントを使用する
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

XSLT スタイル シート内または XML ソース ドキュメント内でブレークポイントを設定することができます。 タグにブレークポイントを設定した場合は、実行の開始時に、ソース行情報を含む次のステートメントにブレークポイントが移動します。  
  
 詳細については、次を参照してください。[デバッグの基礎。ブレークポイント](http://msdn.microsoft.com/752a02c2-0ac7-4c8b-aa1b-4b2b3b21152e)します。  
  
## <a name="set-a-breakpoint-in-a-style-sheet"></a>スタイル シート内にブレークポイントを設定する  
 XSLT スタイル シートでは、開始タグ、終了タグ、およびテキスト ノードにブレークポイントを設定できます。 スクリプト ブロック内のコードにブレークポイントを設定することもできます。  
  
#### <a name="to-set-a-breakpoint-in-a-style-sheet"></a>スタイル シート内にブレークポイントを設定するには  
  
1.  XML エディターでスタイル シートを開きます。  
  
2.  ブレークポイントの位置にカーソルを置き、右クリックし、 をポイント**ブレークポイント**、 をクリック**ブレークポイントの挿入**します。  
  
3.  参照ボタンをクリックします (**.**) で、**入力**ドキュメントのプロパティ ウィンドウのフィールド。  
  
4.  XML ソース ドキュメントを見つけてクリックして**オープン**します。  
  
     これで、XSLT 変換のために使用されるソース ドキュメント ファイルが設定されます。  
  
5.  をクリックして、 **XSL のデバッグ**XML エディターのツールバーのボタンをクリックします。  
  
## <a name="set-a-breakpoint-in-an-xml-source-document"></a>XML ソース ドキュメント内にブレークポイントを設定する  
 XML ソース ドキュメントでは、要素、属性、名前空間ノード、コメント、処理命令、およびテキスト ノードにブレークポイントを設定できます。 ドキュメント ノード、または、親要素から継承された名前空間ノードにブレークポイントを設定することはできません。  
  
#### <a name="to-set-a-breakpoint-in-an-xml-source-document"></a>XML ソース ドキュメント内にブレークポイントを設定するには  
  
1.  XML エディターで XML ドキュメントを開きます。  
  
2.  ブレークポイントの位置にカーソルを置き、右クリックし、 をポイント**ブレークポイント**、 をクリック**ブレークポイントの挿入**します。  
  
3.  参照ボタンをクリックします (**.**) で、 **Stylesheet**ドキュメントのプロパティ ウィンドウのフィールド。  
  
4.  XML ソース ドキュメントを見つけてクリックして**オープン**します。  
  
     これで、XSLT 変換のために使用されるソース ドキュメント ファイルが設定されます。  
  
5.  をクリックして、 **XSL のデバッグ**XML エディターのツールバーのボタンをクリックします。  
  
## <a name="see-also"></a>関連項目  
 [チュートリアル: XSLT スタイル シートのデバッグ](../xml-tools/walkthrough-debug-an-xslt-style-sheet.md)
