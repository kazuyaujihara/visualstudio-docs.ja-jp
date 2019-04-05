---
title: '方法: Backstage ビューにコントロールを追加します。 '
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- customizing the Ribbon, menus
- controls, Ribbon
- menus, customizing
- Microsoft Office Button
- custom Ribbon, menus
- Ribbon, customizing
- Office button
- Ribbon, menus
- Microsoft Office Menu
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: bb038fdebdfefeb5f401860c17b5567028c3bb77
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56621345"
---
# <a name="how-to-add-controls-to-the-backstage-view"></a>方法: Backstage ビューにコントロールを追加します。
  リボン デザイナーを使用して、クリックすると表示されるメニューにコントロールを追加、**ファイル**タブ。コントロールに追加する、アプリケーションを実行すると、**ファイル**タブ表示という名前のグループ**アドイン**します。

 Visual Studio でリボン デザイナーを使用して、組み込みのコントロールの前後にコントロールを配置できません。 ビルトイン コントロールは、Backstage ビューで既に表示されているコントロールです。 組み込みのコントロールの前後にコントロールを配置する場合は、リボン XML を使用する必要があります。 詳細については**リボン (XML)** を参照してください[リボン XML](../vsto/ribbon-xml.md)します。 Backstage ビューをカスタマイズする方法の詳細については、[開発者向け Office 2010 の Backstage ビュー](http://go.microsoft.com/fwlink/?LinkId=182189)と[開発者向け Office 2010 の Backstage ビューをカスタマイズ](http://go.microsoft.com/fwlink/?LinkId=182188)を参照してください。

 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]

### <a name="to-add-controls-to-backstage-view"></a>Backstage ビューにコントロールを追加するには

1.  デザイン ビューで、リボン項目を開きます。

     追加する方法については、**リボン (ビジュアル デザイナー)** をプロジェクトに項目を参照してください[方法。リボンのカスタマイズの概要](../vsto/how-to-get-started-customizing-the-ribbon.md)します。

2.  リボン デザイナーで、クリックして、**ファイル**タブ。

     メニュー デザイナーが表示されます。 このデザイン サーフェイスにコントロールが含まれていません。

3.  **Office リボン コントロール**のタブ、**ツールボックス**、次のコントロールのいずれかをメニュー デザイナーにドラッグします。

    -   ボタン

    -   CheckBox

    -   Gallery

    -   メニュー

    -   区切り記号

    -   SplitButton

    -   ToggleButton

4.  メニューの新しい位置に移動するコントロールをドラッグします。

## <a name="see-also"></a>関連項目
- [リボンの概要](../vsto/ribbon-overview.md)
- [リボン デザイナー](../vsto/ribbon-designer.md)
- [Ribbon XML](../vsto/ribbon-xml.md)
- [方法: 開始するリボンをカスタマイズします。](../vsto/how-to-get-started-customizing-the-ribbon.md)
- [チュートリアル: リボン デザイナーを使用してカスタム タブを作成します。](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)
