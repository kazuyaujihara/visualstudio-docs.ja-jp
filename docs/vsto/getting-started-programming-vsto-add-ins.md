---
title: VSTO アドインのプログラミングの概要
ms.date: 02/02/2017
ms.topic: conceptual
f1_keywords:
- VST.ProjectItem.Outlook
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application-level add-ins [Office development in Visual Studio], getting started
- add-ins [Office development in Visual Studio], getting started
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 39cf3e8d59a2ced26f878da979fa87fc663b5bab
ms.sourcegitcommit: e98db44f3a33529b0ba188d24390efd09e548191
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2019
ms.locfileid: "71253590"
---
# <a name="get-started-programming-vsto-add-ins"></a>VSTO アドインのプログラミングの概要
  VSTO アドインを使用することにより、Microsoft Office アプリケーションを自動化し、アプリケーションの機能を拡張できるほか、アプリケーションのユーザー インターフェイス (UI) をカスタマイズすることもできます。 VSTO アドインと、Visual Studio を使用して作成できる他の種類の Office ソリューションとの比較の詳細については、「 [Office ソリューション開発の&#40;概要 VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md)」を参照してください。

 [!INCLUDE[appliesto_allapp](../vsto/includes/appliesto-allapp-md.md)]

## <a name="create-vsto-add-in-projects"></a>VSTO アドインプロジェクトの作成
 **[新しいプロジェクト]** ダイアログボックスの vsto アドインプロジェクトテンプレートのいずれかを使用して、vsto アドインプロジェクトを作成します。 これらのテンプレートには必要なアセンブリ参照とプロジェクト ファイルが含まれています。 Visual Studio には、Office のほとんどのアプリケーション用の VSTO アドイン プロジェクト テンプレートが用意されています。

 VSTO アドインプロジェクトを作成する方法の詳細については、「 [」を参照してください。Visual Studio で Office プロジェクトを作成する方法](../vsto/how-to-create-office-projects-in-visual-studio.md)」を参照してください。 プロジェクト テンプレートの詳細については、「[Office プロジェクト テンプレートの概要](../vsto/office-project-templates-overview.md)」を参照してください。

## <a name="develop-vsto-add-in-projects"></a>VSTO アドインプロジェクトの開発
 VSTO アドインプロジェクトを作成すると、Visual Studio によって、 *ThisAddIn* ( [!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)]) コードファイルまたは*ThisAddIn.cs* ( C#) コードファイルが自動的に作成されます。 このファイルには`ThisAddIn` 、VSTO アドインの基礎となるクラスが含まれています。 このクラスのメンバーを使用して、VSTO アドインが読み込まれたとき、またはアンロードされたときにコードを実行したり、ホスト アプリケーションのオブジェクト モデルにアクセスしたりすることができます。また、アプリケーションの機能を拡張することも可能です。 詳細については、「[プログラム VSTO アドイン](../vsto/programming-vsto-add-ins.md)」を参照してください。

## <a name="automate-applications-by-using-the-object-models"></a>オブジェクトモデルを使用してアプリケーションを自動化する
 Microsoft Office アプリケーションのオブジェクト モデルは、VSTO アドインでプログラミングに使用できる多くの型を公開します。 それらの型を使用してアプリケーションを自動化できます。 たとえば、Outlook でプログラムによって電子メールを作成および送信することもできれば、Word で文書を開き、コンテンツを追加することも可能です。 コードでホストアプリケーションのオブジェクトモデルにアクセスする方法の詳細については、「[プログラム VSTO アドイン](../vsto/programming-vsto-add-ins.md)」を参照してください。

 特定の Microsoft Office アプリケーションのオブジェクト モデルの詳細については、以下のトピックを参照してください。

- [Excel オブジェクトモデルの概要](../vsto/excel-object-model-overview.md)

- [Word オブジェクトモデルの概要](../vsto/word-object-model-overview.md)

- [Outlook オブジェクトモデルの概要](../vsto/outlook-object-model-overview.md)

- [InfoPath ソリューション](../vsto/infopath-solutions.md)

- [PowerPoint ソリューション](../vsto/powerpoint-solutions.md)

- [Project ソリューション](../vsto/project-solutions.md)

- [Visio オブジェクトモデルの概要](../vsto/visio-object-model-overview.md)

## <a name="customize-the-user-interface-of-applications"></a>アプリケーションのユーザーインターフェイスをカスタマイズする
 VSTO アドインを使用してホストアプリケーションの UI をカスタマイズするには、次のようないくつかの方法があります。

- Excel や Word の場合、ドキュメントにマネージド コントロールを追加できます。 詳細については、「 [VSTO アドインでの実行時の Word 文書と Excel ブックの拡張](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)」を参照してください。

- アプリケーションでサポートされている場合は、リボンをカスタマイズできます。 詳細については、「[リボンの概要](../vsto/ribbon-overview.md)」を参照してください。

- アプリケーションでサポートされている場合は、カスタム作業ウィンドウを作成できます。 詳細については、「[カスタム作業ウィンドウ](../vsto/custom-task-panes.md)」を参照してください。

- Outlook では、カスタム フォーム領域を作成できます。 詳細については、「 [Outlook フォーム領域の作成](../vsto/creating-outlook-form-regions.md)」を参照してください。

- すべての Microsoft Office アプリケーションで、VSTO アドインに Windows フォームを表示できます。

  Microsoft Office アプリケーションの UI をカスタマイズする方法の詳細については、「 [OFFICE ui のカスタマイズ](../vsto/office-ui-customization.md)」を参照してください。

## <a name="next-steps"></a>次の手順
 VSTO アドインの作成方法については、次のチュートリアルを参照してください。

- [チュートリアル: 初めての Excel 用 VSTO アドインを作成する](../vsto/walkthrough-creating-your-first-vsto-add-in-for-excel.md)

- [チュートリアル: Outlook 用の初めての VSTO アドインを作成する](../vsto/walkthrough-creating-your-first-vsto-add-in-for-outlook.md)

- [チュートリアル: 初めての PowerPoint 用 VSTO アドインを作成する](../vsto/walkthrough-creating-your-first-vsto-add-in-for-powerpoint.md)

- [チュートリアル: Project 用の最初の VSTO アドインを作成する](../vsto/walkthrough-creating-your-first-vsto-add-in-for-project.md)

- [チュートリアル: Word 用の最初の VSTO アドインを作成する](../vsto/walkthrough-creating-your-first-vsto-add-in-for-word.md)

  これらのチュートリアルでは、Visual Studio の Office 開発ツール、および VSTO アドインのプログラミング モデルを紹介します。

  Office プロジェクトの一般的なタスクについて説明するトピックの一覧については、「 [office プログラミングにおける一般的なタスク](../vsto/common-tasks-in-office-programming.md)」を参照してください。

## <a name="see-also"></a>関連項目
- [方法: Visual Studio での Office プロジェクトを作成する](../vsto/how-to-create-office-projects-in-visual-studio.md)
- [はじめに &#40;Visual Studio での Office 開発&#41;](../vsto/getting-started-office-development-in-visual-studio.md)
- [Office ソリューションにおけるコードの記述](../vsto/writing-code-in-office-solutions.md)
- [VSTO アドインのアーキテクチャ](../vsto/architecture-of-vsto-add-ins.md)
- [プログラム VSTO アドイン](../vsto/programming-vsto-add-ins.md)
