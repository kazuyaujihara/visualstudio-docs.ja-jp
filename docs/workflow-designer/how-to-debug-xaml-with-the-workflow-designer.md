---
title: ワークフローデザイナー:XAML のデバッグ
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: d9305dbc-af62-4bdd-b03f-c54e3fe9ecc7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- uwp
ms.openlocfilehash: af5b7585ed5c0f34eeb44edba8c60ba0d5e14559
ms.sourcegitcommit: e98db44f3a33529b0ba188d24390efd09e548191
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2019
ms.locfileid: "71254774"
---
# <a name="how-to-debug-xaml-with-the-workflow-designer"></a>方法: ワークフロー デザイナーを使用して XAML をデバッグする

ワークフローは XAML で定義されます。 ワークフローの UI 表現は、ワークフローを定義する XAML ツリーに基づいて構築されます。 デバッグエクスペリエンスは、ワークフローデザイナーでのワークフローのデバッグに似ています。 たとえば、XAML のデバッグ中に、[ローカル]、[ウォッチ]、および [スレッド] の各ウィンドウは、ワークフローデザイナーデバッグと同じように動作します。 また、XAML のデバッグ中に使用される呼び出し履歴ビューは、ワークフローの実行フローの行ベースの階層ビューです。

> [!NOTE]
> ワークフローの XAML がアクティビティと同じアセンブリ内にある場合、クラス名のアセンブリ部分は含まれません。 クラス (アクティビティ) 名のこの部分がないと、XAML を実行時に読み込むことができません。 メイン プロジェクトと同じ名前空間でアクティビティを定義することはお勧めしません。定義した場合は、XAML をデザイナーで編集した後に手動で編集する必要があります。

## <a name="to-debug-workflow-xaml"></a>ワークフローの XAML をデバッグするには

1. Visual Studio でワークフローまたはアクティビティプロジェクトを開きます。

2. デバッグ対象のアクティビティにブレークポイントを設定します。詳細につい[ては、「方法:ワークフロー](../workflow-designer/how-to-set-breakpoints-in-workflows.md)にブレークポイントを設定します。

3. ワークフロー定義が含まれている .xaml ファイルを右クリックし、 **[コードの表示]** を選択します。 デザイン ビューでブレークポイントを設定したアクティビティの XAML 要素宣言と同じ行に、ブレークポイントが表示されます。

4. 「[デバッグワークフロー](debugging-workflows-with-the-workflow-designer.md)」で説明されているように、デバッガーを起動します。

5. コードがいずれかのブレークポイントまで実行されると、そのブレークポイントに関連付けられている XAML 要素が強調表示されます。 次のブレークポイントに移動するには、 **F10**キーまたは**F11**キーを使用します。

## <a name="see-also"></a>関連項目

- [方法: ワークフロー内のブレークポイントを設定する](../workflow-designer/how-to-set-breakpoints-in-workflows.md)
- [ワークフローのデバッグ](debugging-workflows-with-the-workflow-designer.md)