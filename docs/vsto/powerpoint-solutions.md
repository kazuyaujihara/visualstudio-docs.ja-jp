---
title: PowerPoint ソリューション
ms.date: 08/14/2019
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office solutions [Office development in Visual Studio], PowerPoint
- templates [Office development in Visual Studio], PowerPoint
- solutions [Office development in Visual Studio], PowerPoint
- projects [Office development in Visual Studio], PowerPoint
- PowerPoint [Office development in Visual Studio]
- Office projects [Office development in Visual Studio], PowerPoint
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 70968682a8221b88859fd561c9f678aced2911b9
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2019
ms.locfileid: "69551471"
---
# <a name="powerpoint-solutions"></a>PowerPoint ソリューション
  Visual Studio には、Microsoft Office PowerPoint の VSTO アドインを作成するために使用できるプロジェクト テンプレートが用意されています。 VSTO アドインを使用すると、PowerPoint の自動化、PowerPoint 機能の拡張、PowerPoint ユーザー インターフェイス (UI) のカスタマイズが可能です。

 VSTO アドインの詳細については、「vsto アドインの[プログラミングの概要](../vsto/getting-started-programming-vsto-add-ins.md)」と「 [Vsto アドインのアーキテクチャ](../vsto/architecture-of-vsto-add-ins.md)」を参照してください。Microsoft Office を使用したプログラミングの初心者の場合は、「 [Visual Studio &#40;&#41;での Office 開発の概要](../vsto/getting-started-office-development-in-visual-studio.md)」を参照してください。

 [!INCLUDE[appliesto_pptallapp](../vsto/includes/appliesto-pptallapp-md.md)]

[!include[Add-ins note](includes/addinsnote.md)]

 ![ビデオへのリンク](../vsto/media/playvideo.gif "ビデオへのリンク")関連のビデオデモについて[は、操作方法を参照してください。Microsoft PowerPoint のアドインを作成しますか](http://go.microsoft.com/fwlink/?LinkId=132767)。

## <a name="automate-powerpoint-by-using-the-powerpoint-object-model"></a>PowerPoint オブジェクトモデルを使用して PowerPoint を自動化する
 PowerPoint オブジェクト モデルでは、PowerPoint の自動化に使用できる型が多数公開されています。 それらの型によって、次のような一般的なタスクを実行するコードを作成できます。

- プログラムによるプレゼンテーションの作成と書式指定

- プレゼンテーションへのスライドの追加または削除

- スライドへの図形の追加または変更

  VSTO アドインから PowerPoint オブジェクトモデルにアクセスするには、プロジェクトの`Application` `ThisAddIn`クラスのフィールドを使用します。 この`Application`フィールドは、PowerPoint の現在のインスタンスを表す[アプリケーション](/previous-versions/office/developer/office-2010/ff764034(v=office.14))オブジェクトを返します。 詳細については、「[プログラム VSTO アドイン](../vsto/programming-vsto-add-ins.md)」を参照してください。

  PowerPoint オブジェクト モデルを呼び出すときには、PowerPoint のプライマリ相互運用機能アセンブリに用意された型を使用します。 プライマリ相互運用機能アセンブリは、VSTO アドインのマネージド コードと PowerPoint の COM オブジェクト モデルとの仲介役を果たします。 PowerPoint プライマリ相互運用機能アセンブリのすべての型は、 [Microsoft の interop. powerpoint](/previous-versions/office/developer/office-2010/ff763170(v=office.14))名前空間で定義されています。 プライマリ相互運用機能アセンブリの詳細については、「 [ &#40;office&#41;ソリューション開発の概要 VSTO](../vsto/office-solutions-development-overview-vsto.md)と[office プライマリ相互運用機能アセンブリ](../vsto/office-primary-interop-assemblies.md)」を参照してください。

## <a name="WordOMDocumentation"></a>PowerPoint オブジェクトモデルのドキュメントを使用する
 PowerPoint オブジェクト モデルの詳細については、PowerPoint プライマリ相互運用機能アセンブリ (PIA) のリファレンスと、VBA オブジェクト モデルのリファレンスを参照してください。

### <a name="primary-interop-assembly-reference"></a>プライマリ相互運用機能アセンブリのリファレンス
 PowerPoint PIA のリファレンス ドキュメントは、PowerPoint のプライマリ相互運用機能アセンブリの型について説明しています。 このドキュメントは、次の場所から入手できます。[PowerPoint 2010 プライマリ相互運用機能アセンブリの参照](http://go.microsoft.com/fwlink/?LinkId=189588)。

 PIA のイベントの実装方法、PIA のクラスとインターフェイスの違いなど、PowerPoint PIA の設計に関する詳細情報を参照してください[Office プライマリ相互運用機能アセンブリのクラスおよびインターフェイスの概要](http://go.microsoft.com/fwlink/?LinkId=199885)。

### <a name="vba-object-model-reference"></a>VBA オブジェクトモデルのリファレンス
 VBA オブジェクト モデルのリファレンスでは、Visual Basic for Applications (VBA) コードに公開される PowerPoint オブジェクト モデルについて説明しています。 詳細については、「 [PowerPoint 2010 オブジェクトモデルのリファレンス](http://go.microsoft.com/fwlink/?LinkId=199770)」を参照してください。

 VBA オブジェクト モデルのリファレンス内のオブジェクトとメンバーはすべて、PowerPoint プライマリ相互運用機能アセンブリ (PIA) の型とメンバーに対応します。 たとえば、VBA オブジェクトモデルのリファレンス内の Presentation オブジェクトは、PowerPoint PIA の[プレゼンテーション](/previous-versions/office/developer/office-2010/ff761925(v=office.14))の種類に対応しています。 VBA オブジェクト モデルのリファレンスでは、ほとんどのプロパティ、メソッド、およびイベントのコード例を紹介しています。ただし、Visual Studio を使用して作成した PowerPoint VSTO アドイン プロジェクトでこのリファレンス内の VBA コードを使用するには、それらを Visual Basic または Visual C# に変換する必要があります。

## <a name="customize-the-user-interface-of-powerpoint"></a>PowerPoint のユーザーインターフェイスのカスタマイズ
 PowerPoint の UI を次のように変更できます。

|タスク|詳細情報|
|----------|--------------------------|
|カスタム作業ウィンドウを作成する。|[カスタム作業ウィンドウ](../vsto/custom-task-panes.md)|
|リボンにカスタム タブを追加する。|[リボンの概要](../vsto/ribbon-overview.md)|
|リボン上の組み込みタブにカスタム グループを追加する。|[方法: 組み込みタブをカスタマイズする](../vsto/how-to-customize-a-built-in-tab.md)|

 PowerPoint およびその他の Microsoft Office アプリケーションの UI をカスタマイズする方法の詳細については、「 [OFFICE ui のカスタマイズ](../vsto/office-ui-customization.md)」を参照してください。

## <a name="see-also"></a>関連項目
- [チュートリアル: 初めての PowerPoint 用 VSTO アドインを作成する](../vsto/walkthrough-creating-your-first-vsto-add-in-for-powerpoint.md)
- [VSTO アドインのプログラミングの概要](../vsto/getting-started-programming-vsto-add-ins.md)
- [Office ソリューションの開発&#40;の概要 VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md)
- [VSTO アドインのアーキテクチャ](../vsto/architecture-of-vsto-add-ins.md)
- [方法: Visual Studio での Office プロジェクトを作成する](../vsto/how-to-create-office-projects-in-visual-studio.md)
- [プログラム VSTO アドイン](../vsto/programming-vsto-add-ins.md)
- [Office ソリューションにおけるコードの記述](../vsto/writing-code-in-office-solutions.md)
- [Office プライマリ相互運用機能アセンブリ](../vsto/office-primary-interop-assemblies.md)
- [Office UI のカスタマイズ](../vsto/office-ui-customization.md)
- [Office 開発における PowerPoint 2010](http://go.microsoft.com/fwlink/?LinkId=199015)
