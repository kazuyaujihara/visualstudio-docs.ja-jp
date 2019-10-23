---
title: '方法: ツールボックスにアクティビティを追加する (レガシ) |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
helpviewer_keywords:
- Toolbox, adding activities
- activities, adding to Toolbox
ms.assetid: b66ea29c-120b-40ba-8a61-c1c8240850fa
caps.latest.revision: 5
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: f3f982372f0189871c4f3d294c07a9e3cfc44391
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72656621"
---
# <a name="how-to-add-activities-to-the-toolbox-legacy"></a>方法: ツールボックスにアクティビティを追加する (レガシ)
@No__t_1 または [!INCLUDE[vstecwinfx](../includes/vstecwinfx-md.md)] を対象とする従来の [!INCLUDE[wfd1](../includes/wfd1-md.md)] を使用してワークフローソリューションを構築する場合、簡単にアクセスできるように、カスタムアクティビティを **[ツールボックス]** に配置したワークフロープロジェクトとそのデザイナーに追加できます。 ダイナミックリンクライブラリ (DLL) から、**ツールボックス**にアクティビティを直接追加することもできます。

### <a name="to-add-an-activity-to-the-toolbox-from-a-dll"></a>DLL からツールボックスにアクティビティを追加するには

1. **[Windows Workflow]** の下にある ツールボックス ウィンドウ画面を右クリックし、 **[アイテムの選択]** をクリックします。

2. **[ツールボックスアイテムの選択]** ダイアログボックスで、 **[システムコンポーネント]** タブをクリックし、ウィンドウの右下にある **[参照]** をクリックします。

3. **[ツールボックス]** に追加するカスタムアクティビティの実装が格納されているファイルディレクトリから DLL を選択し、 **[開く]** をクリックします。

4. **[OK]** をクリックして、ツールボックスへのアクティビティの追加を完了します。

## <a name="see-also"></a>参照
 [従来のアクティビティデザイナー](../workflow-designer/using-the-legacy-activity-designer.md) [レガシワークフローアクティビティ](../workflow-designer/legacy-workflow-activities.md)の使用