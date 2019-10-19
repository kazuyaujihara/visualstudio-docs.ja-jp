---
title: 'ワークフローデザイナー-方法: 引数デザイナーを使用する'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- System.Activities.Presentation.View.ArgumentDesigner.UI
- System.Activities.Presentation.View.DesignTimeArgument.UI
ms.assetid: 64813fd5-1ea1-499a-98b4-ab2a44b7ee5e
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9c3f8216bb0dfe3813e4852151c351b865128d0c
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72650284"
---
# <a name="how-to-use-the-argument-designer"></a>引数デザイナーを使用する方法

引数デザイナーを使用すると、アクティビティとの間でデータの送受信を簡単に行うことができます。 デザイナーにアクセスするには、デザインキャンバスの左下隅にある **[引数]** ボタンをクリックします。 デザイナーには、表形式で表示される引数の一覧が含まれており、**既定値**の列を除き、各列ヘッダーで並べ替えることができます。 各引数には、名前、方向 (入力、出力、入力/出力、またはプロパティ)、型、および既定の式の値 (存在する場合) が含まれます。 名前および既定の式の値は編集可能なテキスト フィールドで、型および方向はドロップダウンです。 詳細については、「[変数と引数 (.net)](/dotnet/framework/windows-workflow-foundation/variables-and-arguments)」を参照してください。

## <a name="to-create-a-new-argument"></a>新しい引数を作成するには

1. ワークフローまたはアクティビティソリューションを Visual Studio で開きます。

2. デザインキャンバスの左下隅にある **[引数]** ボタンをクリックして、引数デザイナーを開きます。 引数デザイナーが表示されます。

3. **[引数の作成]** というラベルの付いた空の行をクリックします。 これにより、新しい引数を含む新しい行が追加されます。**名前**には argumentx を使用します。ここ**で** **、x**は、一意の引数名を作成するために自動的にインクリメントされる初期値1を持つ整数です。**引数の型**に**文字列**を指定します。 **既定値**の値は追加されません。 これらの値は、ワークフローのデザイン プロセス中にいつでも変更できます。

    > [!NOTE]
    > 引数を削除するには、引数をクリックして選択し、 **del**キーを押します。

## <a name="see-also"></a>関連項目

- [ワークフロー デザイナーの使用](developing-applications-with-the-workflow-designer.md)
- [変数と引数](/dotnet/framework/windows-workflow-foundation/variables-and-arguments)