---
title: このプロジェクトの作成に使用されるブックには、デザイナーで読み込めない ActiveX コントロールが含まれています
ms.date: 02/02/2017
ms.topic: conceptual
f1_keywords:
- VST.SelectDocWizard.ContainsActiveXControls
dev_langs:
- VB
- CSharp
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 27feb1c6a85740d8a9287ce3a2a47800595e178a
ms.sourcegitcommit: e98db44f3a33529b0ba188d24390efd09e548191
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2019
ms.locfileid: "71253785"
---
# <a name="the-workbook-used-to-create-this-project-contains-activex-controls-that-the-designer-cannot-load"></a>このプロジェクトの作成に使用されるブックには、デザイナーで読み込めない ActiveX コントロールが含まれています
  このエラーは、Word 文書または Excel ワークシートにプログラムでコントロールを追加し、その文書またはブックを保存して、保存した文書またはブックに基づいて新たなドキュメント レベルのソリューションを作成すると表示されます。

 コントロールのマネージド型を記述した情報は、文書またはブックと共に保存されません。 このような文書またはブックに基づいて新しいソリューションを作成すると、コントロールをホスト項目デザイナーに読み込むのに必要な情報が Visual Studio に提供されません。

## <a name="to-correct-this-error"></a>このエラーを解決するには

1. 文書またはブックを開きます。

2. 実行時に追加されたコントロールを削除します。 これを行うには、ドキュメントまたはブックでそれらを選択し、 **del**キーを押します。

3. 文書またはブックに基づいたドキュメント レベルのソリューションを作成します。

## <a name="see-also"></a>関連項目
- [方法: Visual Studio での Office プロジェクトを作成する](../vsto/how-to-create-office-projects-in-visual-studio.md)
- [実行時に Office ドキュメントにコントロールを追加する](../vsto/adding-controls-to-office-documents-at-run-time.md)
