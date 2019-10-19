---
title: '方法: ドメイン固有言語の名前空間を変更する'
ms.date: 10/31/2018
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language, namespace
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b64a61c02f44db0ce70b758331d0d70f7bb8014d
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72653768"
---
# <a name="how-to-change-the-namespace-of-a-domain-specific-language"></a>方法: ドメイン固有言語の名前空間を変更する

ドメイン固有言語の名前空間を変更できます。 Dsl**エクスプローラー**、dsl パッケージプロジェクトのプロパティ、およびアセンブリ情報に変更を加えます。

## <a name="to-change-the-namespace-of-a-domain-specific-language"></a>ドメイン固有言語の名前空間を変更するには

1. **Dsl エクスプローラー**で**dsl**ノードを選択します。

2. **[プロパティ]** ウィンドウで、"**名前空間**" プロパティを変更します。

3. ソリューションを保存し、テンプレートを変換します。

4. **[プロジェクト]** メニューの **[Dsl プロパティ]** を選択します。

   プロジェクトのプロパティが表示されます。

5. **[アプリケーション]** タブを選択します。

6. "**既定の名前空間**" プロパティを新しい名前空間の名前に変更します。

7. アセンブリの名前も変更する場合は、[**アセンブリ名] プロパティ**を変更します。

8. アセンブリ名を変更した場合は、この行を開き、次の行を更新します。

   `string dslAssembly = "YourDSLassembly.Dsl.dll";`

9. カスタムコードを記述した場合は、コードファイル内の名前空間とクラス参照を必ず変更してください。

10. Visual Studio の実験的なインスタンスをリセットします。

    1. **\ Users \\** _{your name}_ **\AppData\Local\Microsoft\VisualStudio \\ \*Exp**を削除します。

    2. Windows の **スタート** メニューで、**すべてのプログラム**  > **Microsoft Visual Studio 2010 SDK**  > **ツール** の順に選択し、**実験的なインスタンスをリセット** >  ます。

11. **[ビルド]** メニューの **[ソリューションのリビルド]** をクリックします。

## <a name="see-also"></a>関連項目

[ドメイン固有言語ツールの用語集](https://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)