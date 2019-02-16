---
title: Excel 用ドキュメント レベル カスタマイズのプログラミングのスタート ガイド
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Excel solutions in Visual Studio
- Excel projects [Office development in Visual Studio], getting started
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 47762c781b24a31b90c75e5f8d9f0d00a6d3363d
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2019
ms.locfileid: "54870140"
---
# <a name="get-started-programming-document-level-customizations-for-excel"></a>Excel 用ドキュメント レベル カスタマイズのプログラミングのスタート ガイド
  Visual Studio を使用して Microsoft Office Excel のドキュメント レベルのカスタマイズを作成することを始めるには、次を知る必要があります。  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
## <a name="understand-how-document-level-customizations-for-excel-work"></a>Excel のドキュメント レベルのカスタマイズがどのように働くかの理解  
 Excel 用ドキュメント レベルのカスタマイズは、1 つのブックに基づいています。 カスタマイズの使用を開始するには、エンド ユーザーはブックを開くか、Excel テンプレートからブックを作成します。 たとえば、セルに入力する、ボタンおよびメニュー項目をクリックするといった、ブック内のイベントは、アセンブリ内のイベント処理メソッドを呼び出すことができます。 ブックが閉じられると、カスタマイズによって提供される機能は Excel では使用できず、それらが含まれているドキュメント内でのみ使用できます。  
  
 詳細については、次を参照してください。[のドキュメント レベル カスタマイズのアーキテクチャ](../vsto/architecture-of-document-level-customizations.md)します。  
  
## <a name="create-document-level-projects-for-excel"></a>Excel 用ドキュメント レベルのプロジェクトの作成  
 Excel 用ドキュメント レベルのカスタマイズを作成するで Excel ブックまたは Excel テンプレート プロジェクト テンプレートを使用して、**新しいプロジェクト** ダイアログ ボックス。 これらのテンプレートには必要なアセンブリ参照とプロジェクト ファイルが含まれています。  
  
 Excel 用ドキュメント レベルのプロジェクトを作成する方法の詳細については、次を参照してください。[方法。Visual Studio での Office プロジェクトの作成](../vsto/how-to-create-office-projects-in-visual-studio.md)です。 プロジェクト テンプレートの詳細については、次を参照してください。 [Office プロジェクト テンプレートの概要](../vsto/office-project-templates-overview.md)します。  
  
## <a name="program-excel-workbooks-by-using-host-items-and-host-controls"></a>ホスト項目とホスト コントロールを使用した Excel ブックのプログラミング  
 *ホスト項目*と*ホスト コントロール*は Visual Studio を使用して作成されたドキュメント レベル カスタマイズのプログラミング モデルを提供するクラスです。  
  
 ホスト項目は、コードのエントリ ポイントを提供し、ホスト コントロールや Windows フォーム コントロールのコンテナーとしても機能できます。 Excel 用ドキュメント レベルのプロジェクトにおいて、これらのホスト項目は、`ThisWorkbook`、`Sheet1`、`Sheet2`、および `Sheet3` クラスとして表されます。  
  
 ホスト コントロールは、リスト オブジェクトや範囲といったネイティブな Excel オブジェクトに基づいています。 ホスト コントロールは、ネイティブな Excel オブジェクトと同様の機能を提供し、新しいイベント、デザイナー サポート、およびデータ バインディング機能も備えています。 これにより、Excel オブジェクト モデルを操作することなくコード内で直接特定のオブジェクトを参照しやすく、プロジェクト コードおよび IntelliSense で最上位のオブジェクトとして表示されます。  
  
 詳細については、次のトピックを参照してください。  
  
-   [ドキュメント レベルのカスタマイズのプログラミング](../vsto/programming-document-level-customizations.md)  
  
-   [拡張オブジェクトを使用した Excel の自動化](../vsto/automating-excel-by-using-extended-objects.md)  
  
-   [ホスト項目とホスト コントロールの概要](../vsto/host-items-and-host-controls-overview.md)  
  
## <a name="customize-the-user-interface-of-excel"></a>Excel のユーザー インターフェイスのカスタマイズ  
 ほとんどの Microsoft Office ソリューションでは、ソリューションとの対話をユーザーに対していくつかの方法を提供する Office アプリケーションのユーザー インターフェイス (UI) を変更します。 ドキュメント レベルのカスタマイズを使用して Excel の UI を変更する方法はたくさんあります。 たとえば、コントロールを追加するには、リボンにまたは操作ウィンドウを表示することができます。 詳細については、次を参照してください。 [Office UI のカスタマイズ](../vsto/office-ui-customization.md)します。  
  
 Visual Studio で直接、プロジェクトに関連付けられているブックを開くこともできます。 ブック Visual Studio で開く場合に、Excel のユーザー インターフェイスを使用して、ブックを変更できます。 コントロールをワークシートにドラッグすることができます、デザイン サーフェイスとして、ブックを使用することもできます。 詳細については、次を参照してください。 [Visual Studio 環境における Office プロジェクト](../vsto/office-projects-in-the-visual-studio-environment.md)します。  
  
## <a name="use-data-binding"></a>データ バインディングの使用  
 ホスト コントロールはからドラッグできるコントロールのリストでも、**データソース**ウィンドウ。 このように自動的にホスト コントロールの追加 ウィンドウを使用し、設定したデータ ソースにバインドされます。 コードを記述せずには、データベース、web サービス、およびビジネス オブジェクトからデータを表示できます。 詳細については、次を参照してください。 [Office ソリューションでのコントロールにデータをバインド](../vsto/binding-data-to-controls-in-office-solutions.md)します。  
  
## <a name="next-steps"></a>次の手順  
 Excel 用ドキュメント レベルのカスタマイズを作成する方法についてを参照してください。[チュートリアル。最初の Excel 用ドキュメント レベルのカスタマイズを作成する](../vsto/walkthrough-creating-your-first-document-level-customization-for-excel.md)します。 このチュートリアルでは、Visual Studio と Excel のドキュメント レベルのカスタマイズのプログラミング モデルでの Office 開発ツールについて説明します。  
  
 Excel プロジェクトで、一般的なタスクを解説しているトピックの一覧は、次を参照してください。 [Office プログラミングで一般的なタスク](../vsto/common-tasks-in-office-programming.md)します。  
  
## <a name="see-also"></a>関連項目  
 [方法: Visual Studio での Office プロジェクトを作成します。](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [プログラムのドキュメント レベルのカスタマイズ](../vsto/programming-document-level-customizations.md)   
 [Excel ソリューション](../vsto/excel-solutions.md)   
 [チュートリアル: 最初の Excel 用ドキュメント レベルのカスタマイズを作成します。](../vsto/walkthrough-creating-your-first-document-level-customization-for-excel.md)   
 [Excel を使用したチュートリアル](../vsto/walkthroughs-using-excel.md)   
 [Excel オブジェクト モデルの概要](../vsto/excel-object-model-overview.md)   
 [Office ソリューションにおけるコードの記述](../vsto/writing-code-in-office-solutions.md)  
