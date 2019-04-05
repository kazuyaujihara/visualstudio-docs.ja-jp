---
title: '[その他、XML、テキスト エディター オプション] ダイアログ ボックス |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: fd3fff31-cddc-422d-a2f0-a5a1ef492afd
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 0181609f083aada564edb585f64ccdaaf104ed15
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58963149"
---
# <a name="miscellaneous-xml-text-editor-options-dialog-box"></a>[その他] ([オプション] ダイアログ ボックス - [テキスト エディター] - [XML])
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
このダイアログ ボックスでは、XML エディターのオートコンプリートとスキーマの設定を変更することができます。 アクセスできる、**オプション** ダイアログ ボックスから、**ツール**メニュー。  
  
> [!NOTE]
>  選択すると、これらの設定は使用可能な**テキスト エディター**フォルダー、 **XML**フォルダーをクリックし、 **その他**オプションを**のオプション**  ダイアログ ボックス。  
  
## <a name="auto-insert"></a>自動挿入  
 **終了タグ**  
 オートコンプリートの設定をオンにした場合、エディターで、タグが既に閉じられていない場合、開始タグを閉じるに右の山かっこ (>) を入力すると、終了タグが自動的に追加されます。 これが既定の動作です。  
  
 空の要素の完了は、オートコンプリート設定に依存するわけではありません。 バックスラッシュ (/) を入力することで、いつでも空の要素をオートコンプリートできます。  
  
 **属性値の引用符**  
 XML 属性の作成時にエディターは `=" "` という文字を挿入し、二重引用符の内側にキャレット (^) を配置します。  
  
 既定でオンになっています。  
  
 **名前空間の宣言**  
 エディターは、必要に応じて名前空間の宣言を自動的に挿入します。  
  
 既定でオンになっています。  
  
 **その他のマークアップ (コメント、CDATA)**  
 コメント、CDATA、DOCTYPE、処理命令、およびその他のマークアップのオートコンプリートを有効にします。  
  
 既定でオンになっています。  
  
## <a name="network"></a>ネットワーク  
 **DTD とスキーマを自動的にダウンロードする**  
 HTTP の場所から、スキーマやドキュメント型定義 (DTD) を自動的にダウンロードします。 この機能は、プロキシ サーバーの自動検出を有効にした System.Net を使用します。  
  
 既定でオンになっています。  
  
## <a name="outlining"></a>アウトライン  
 **[ファイルが開かれたときにアウトライン モードを実行する]**  
 ファイルが開かれたときにアウトライン機能をオンにします。  
  
 既定でオンになっています。  
  
## <a name="caching"></a>キャッシュ  
 **スキーマ**  
 スキーマ キャッシュの場所を指定します。 参照ボタン (**.**) が表示されます、**ディレクトリ参照** ダイアログ ボックスで、現在のスキーマ キャッシュの場所。 別のディレクトリを選択またはダイアログ ボックスで、フォルダーを選択することができます、右クリックして選択**オープン**ディレクトリに参照してください。  
  
## <a name="see-also"></a>関連項目  
 [XML ドキュメントのプロパティと [プロパティ] ウィンドウ](../xml-tools/xml-document-properties-properties-window.md)   
 [XML エディターのコンポーネント](../xml-tools/xml-editor-components.md)
