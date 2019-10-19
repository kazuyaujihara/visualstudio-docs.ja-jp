---
title: デバッガーでデータのカスタムビューを作成する |Microsoft Docs
ms.date: 01/09/2019
ms.topic: conceptual
f1_keywords:
- vs.debug
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- debugging [Visual Studio], inspecting programs
- debugger, viewing data
ms.assetid: 13e1105f-f987-402e-9108-ec6ac12be042
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 63dc11736e92013719fcda2bae0ba9599a8835aa
ms.sourcegitcommit: 184e2ff0ff514fb980724fa4b51e0cda753d4c6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72568993"
---
# <a name="create-custom-views-of-data-in-the-visual-studio-debugger-c-visual-basic-c"></a>Visual Studio デバッガーでのデータのカスタムビューの作成C#(、Visual Basic C++、)

@No__t_0 デバッガーには、プログラムの状態を調べたり変更したりするための多くのツールが用意されています。 ほとんどのツールは、中断モードだけで機能します。

## <a name="create-custom-views-of-data-in-variable-windows-and-datatips"></a>変数ウィンドウとデータヒントにデータのカスタムビューを作成する

 多くの[デバッガーウィンドウ](../debugger/debugger-windows.md)( **[自動]** 変数 ウィンドウや **[ウォッチ]** ウィンドウなど) を使用すると、変数を調べることができます。 デバッガー変数ウィンドウとC++ [DataTips](../debugger/view-data-values-in-data-tips-in-the-code-editor.md)で、型、マネージオブジェクト、および独自の型をどのように表示するかをカスタマイズできます。 詳細については、「[オブジェクトのC++カスタムビューを作成する](../debugger/create-custom-views-of-native-objects.md)」および「[管理オブジェクトのカスタムビューを作成](../debugger/create-custom-views-of-managed-objects.md)する」を参照してください。

## <a name="create-custom-visualizers"></a>カスタム ビジュアライザーを作成する

 ビジュアライザーを使用すると、オブジェクトまたは変数の内容を意味のある方法で表示できます。 Visual Studio デバッガーでは、ビジュアライザーは![、虫眼鏡アイコンアイコンを](../debugger/media/dbg-tips-visualizer-icon.png "ビジュアライザーアイコン")使用して開くことができるさまざまなウィンドウを参照します。 たとえば、html ビジュアライザーは、HTML 文字列がブラウザーでどのように解釈および表示されるかを示しています。 ビジュアライザーには、DataTips、 **[ウォッチ]** ウィンドウ、 **[自動変数]** ウィンドウ、および **[ローカル]** ウィンドウからアクセスできます。 **[クイックウォッチ]** ダイアログボックスには、ビジュアライザーも用意されています。 詳細については、「[Create Custom Visualizers](../debugger/create-custom-visualizers-of-data.md)」 (カスタム ビジュアライザーを作成する) を参照してください。

## <a name="see-also"></a>関連項目

- [デバッガーでのはじめに](../debugger/debugger-feature-tour.md)
- [コマンド ウィンドウ](../ide/reference/command-window.md)
- [デバッガーのセキュリティ](../debugger/debugger-security.md)
