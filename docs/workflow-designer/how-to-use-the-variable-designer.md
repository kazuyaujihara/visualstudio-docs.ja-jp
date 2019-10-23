---
title: 'ワークフローデザイナー-方法: 変数デザイナーを使用する'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- System.Activities.Presentation.View.DesignTimeVariable.UI
ms.assetid: 0318dfb0-bf8f-4f92-9b86-ae4c1b2161ad
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 59a0da5ad0345ba0733f52d087b262bdc706cd21
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72650250"
---
# <a name="how-to-use-the-variable-designer"></a>変数デザイナーを使用する方法

変数デザイナーは、データ バインディングや条件ステートメントで使用する変数を作成するために使用します。 デザイナーにアクセスするには、デザインキャンバスの左下隅にある **[変数]** ボタンをクリックします。 デザイナーには、表形式で表示される変数の一覧が含まれており、**既定**の列を除き、各列ヘッダーで並べ替えることができます。 それぞれの変数には、名前、変数の型、スコープ、および既定値 (存在する場合) があります。 名前および既定値は編集可能なテキスト フィールドで、型およびスコープはドロップダウン リストです。 スコープは、変数デザイナーの呼び出し時に選択されたアクティビティです。 選択したスコープ内に変数を作成できない場合は、対応するスコープに変数を作成できる直近の先祖アクティビティが既定のスコープとなります。 詳細については、「[変数と引数 (.net)](/dotnet/framework/windows-workflow-foundation/variables-and-arguments)」を参照してください。

 いずれかの並べ替えコントロールをユーザーが明示的に使用するか、変数デザイナーを閉じてから開き直すか、または、別の変数を作成するまで、並べ替え順序は適用されません。

## <a name="to-create-a-new-variable"></a>新しい変数を作成するには

1. ワークフローまたはアクティビティソリューションを Visual Studio で開きます。

2. デザイン キャンバスで、ワークフローのアクティビティを選択します。

3. デザインキャンバスの左下隅にある **[変数]** ボタンをクリックして、変数デザイナーを開きます。 変数デザイナーが表示されます。

4. **[変数の作成]** という名前の空の行をクリックします。 次の既定値を使用して新しい変数を含む新しい行が追加されます **。ここで**、x は整数であり、x は、**一意の変数名を作成**するために自動的にインクリメントされる1の整数です。**スコープ**のを入力し、**シーケンス**を入力します。 **既定**では、値は追加されません。 これらの値は、ワークフローのデザイン プロセス中にいつでも変更できます。

    > [!NOTE]
    > 変数を削除するには、変数をクリックして選択し、 **del**キーを押します。

## <a name="see-also"></a>関連項目

- [ワークフロー デザイナーの使用](developing-applications-with-the-workflow-designer.md)
- [変数と引数](/dotnet/framework/windows-workflow-foundation/variables-and-arguments)
- [方法: 引数デザイナーを使用する](../workflow-designer/how-to-use-the-argument-designer.md)