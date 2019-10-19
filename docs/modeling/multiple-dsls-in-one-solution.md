---
title: 1 つのソリューション内の複数の DSL
ms.date: 11/04/2016
ms.topic: conceptual
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b5d21d3954a402e7ce8eb26c34d6a6a5c237309a
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72658347"
---
# <a name="multiple-dsls-in-one-solution"></a>1 つのソリューション内の複数の DSL

いくつかの DSL を単一ソリューションの一部としてパッケージ化し、同時にインストールすることができます。

複数の DSL を統合するためにいくつかの手法を使用できます。 詳細については、「 [Visual Studio Modelbus を使用](../modeling/integrating-models-by-using-visual-studio-modelbus.md)したモデルの統合」および「[方法: ドラッグアンドドロップハンドラーを追加する](../modeling/how-to-add-a-drag-and-drop-handler.md)」および「[コピー動作をカスタマイズ](../modeling/customizing-copy-behavior.md)する」を参照してください。

## <a name="build-more-than-one-dsl-in-the-same-solution"></a>同じソリューション内に複数の DSL を作成する

1. 新しい**VSIX プロジェクト**プロジェクトを作成します。

2. VSIX ソリューションディレクトリに2つ以上の DSL プロジェクトを作成します。

   - 各 DSL について、Visual Studio の新しいインスタンスを開きます。 新しい DSL を作成し、同じソリューション フォルダとして VSIX ソリューションを指定します。

   - 各 DSL は異なるファイル拡張子名を付けて作成します。

   - **Dsl**および**dslpackage**プロジェクトの名前を変更して、それらがすべて異なっているようにします。 たとえば、`Dsl1`、`DslPackage1`、`Dsl2`、`DslPackage2` のようになります。

   - **Source.extension.tt \* 各 Dslpackage**で、次の行を正しい Dsl プロジェクト名に更新します。

      `string dslProjectName = "Dsl2";`

   - VSIX ソリューションで、\* プロジェクトに Dsl * および DslPackage を追加します。 各ペアを独自のソリューション フォルダーに配置することを推奨します。

2. 以下のように DSL の VSIX マニフェストを結合します。

   1. _Yourvsixproject 配置_ **\source.extension.manifest**を開きます。

   2. DSL ごとに、 **[コンテンツの追加]** を選択し、次のように追加します。

       - プロジェクトを**MEF コンポーネント**として `Dsl*`

       - プロジェクトを**MEF コンポーネント**として `DslPackage*`

       - **VS パッケージ**としてのプロジェクトの `DslPackage*`

3. ソリューションをビルドします。

   この結果の VSIX では両方の DSL がインストールされます。 F5 キーを使用してテストするか、 _yourvsixproject 配置_ **\bin\debug \\ \* .vsix**に配置します。

## <a name="see-also"></a>関連項目

- [Visual Studio Modelbus によるモデルの統合](../modeling/integrating-models-by-using-visual-studio-modelbus.md)
- [方法: ドラッグ アンド ドロップ ハンドラーを追加する](../modeling/how-to-add-a-drag-and-drop-handler.md)
- [コピー動作のカスタマイズ](../modeling/customizing-copy-behavior.md)