---
title: '方法: 現在の選択項目を表示および制限する'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language, accessing the current selection
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d8d10efbe87177f9caa6e3471e548569a59c3e47
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72667213"
---
# <a name="how-to-access-and-constrain-the-current-selection"></a>方法: 現在の選択項目を表示および制限する

ドメイン固有言語のコマンドまたはジェスチャハンドラーを記述する場合は、ユーザーが右クリックした要素を確認できます。 また、一部の図形またはフィールドが選択されないようにすることもできます。 たとえば、ユーザーがアイコンデコレータをクリックしたときに、そのアイコンが含まれている図形が選択されていることを示すことができます。 この方法で選択を制限すると、記述する必要があるハンドラーの数が減ります。 また、デコレータを避けなくても、図形内の任意の場所をクリックできるようになります。

## <a name="access-the-current-selection-from-a-command-handler"></a>コマンドハンドラーから現在の選択項目にアクセスする

ドメイン固有言語のコマンドセットクラスには、カスタムコマンドのコマンドハンドラーが含まれています。 ドメイン固有言語のコマンドセットクラスを派生させる <xref:Microsoft.VisualStudio.Modeling.Shell.CommandSet> クラスは、現在の選択項目にアクセスするためのいくつかのメンバーを提供します。

コマンドハンドラーでは、コマンドに応じて、モデルデザイナー、モデルエクスプローラー、またはアクティブウィンドウでの選択が必要になる場合があります。

### <a name="to-access-selection-information"></a>選択情報にアクセスするには

1. @No__t_0 クラスは、現在の選択にアクセスするために使用できる次のメンバーを定義します。

    |メンバー|説明|
    |-|-|
    |<xref:Microsoft.VisualStudio.Modeling.Shell.CommandSetLibrary.IsAnyDocumentSelectionCompartment%2A> メソッド|モデルデザイナーで選択されたいずれかの要素がコンパートメントシェイプの場合に `true` を返します。それ以外の場合は、`false` ます。|
    |<xref:Microsoft.VisualStudio.Modeling.Shell.CommandSetLibrary.IsDiagramSelected%2A> メソッド|モデルデザイナーでダイアグラムが選択されている場合は `true` を返します。それ以外の場合は、`false` ます。|
    |<xref:Microsoft.VisualStudio.Modeling.Shell.CommandSetLibrary.IsSingleDocumentSelection%2A> メソッド|モデルデザイナーで要素が1つだけ選択されている場合は `true` を返します。それ以外の場合は、`false` ます。|
    |<xref:Microsoft.VisualStudio.Modeling.Shell.CommandSetLibrary.IsSingleSelection%2A> メソッド|アクティブウィンドウで要素が1つだけ選択されている場合は `true` を返します。それ以外の場合は、`false` ます。|
    |<xref:Microsoft.VisualStudio.Modeling.Shell.CommandSetLibrary.CurrentDocumentSelection%2A> プロパティ|モデルデザイナーで選択されている要素の読み取り専用のコレクションを取得します。|
    |<xref:Microsoft.VisualStudio.Modeling.Shell.CommandSetLibrary.CurrentSelection%2A> プロパティ|アクティブウィンドウで選択されている要素の読み取り専用のコレクションを取得します。|
    |<xref:Microsoft.VisualStudio.Modeling.Shell.CommandSetLibrary.SingleDocumentSelection%2A> プロパティ|モデルデザイナーで選択のプライマリ要素を取得します。|
    |<xref:Microsoft.VisualStudio.Modeling.Shell.CommandSetLibrary.SingleSelection%2A> プロパティ|アクティブウィンドウ内の選択範囲のプライマリ要素を取得します。|

2. @No__t_1 クラスの <xref:Microsoft.VisualStudio.Modeling.Shell.CommandSet.CurrentDocView%2A> プロパティは、モデルデザイナーウィンドウを表す <xref:Microsoft.VisualStudio.Modeling.Shell.DiagramDocView> オブジェクトへのアクセスを提供し、モデルデザイナーで選択した要素に追加のアクセスを提供します。

3. さらに、生成されたコードでは、ドメイン固有言語用のコマンドセットクラスにエクスプローラーツールウィンドウプロパティとエクスプローラー選択プロパティが定義されています。

    - エクスプローラーのツールウィンドウプロパティは、ドメイン固有言語のエクスプローラーツールウィンドウクラスのインスタンスを返します。 エクスプローラーツールウィンドウクラスは <xref:Microsoft.VisualStudio.Modeling.Shell.ModelExplorerToolWindow> クラスから派生し、ドメイン固有言語のモデルエクスプローラーを表します。

    - @No__t_0 プロパティは、ドメイン固有言語の [モデルエクスプローラー] ウィンドウで選択されている要素を返します。

## <a name="determine-which-window-is-active"></a>アクティブなウィンドウを確認する

@No__t_0 インターフェイスには、シェルの現在の選択状態へのアクセスを提供するメンバーが含まれています。 @No__t_0 オブジェクトは、各の基本クラスで定義されている `MonitorSelection` プロパティを使用して、パッケージクラスまたはドメイン固有言語のコマンドセットクラスから取得できます。 パッケージクラスは <xref:Microsoft.VisualStudio.Modeling.Shell.ModelingPackage> クラスから派生し、コマンドセットクラスは <xref:Microsoft.VisualStudio.Modeling.Shell.CommandSet> クラスから派生します。

### <a name="to-determine-from-a-command-handler-what-type-of-window-is-active"></a>コマンドハンドラーから、どの種類のウィンドウがアクティブであるかを判断するには

1. @No__t_1 クラスの <xref:Microsoft.VisualStudio.Modeling.Shell.CommandSetLibrary.MonitorSelection%2A> プロパティは、シェルの現在の選択状態へのアクセスを提供する <xref:Microsoft.VisualStudio.Modeling.Shell.IMonitorSelectionService> オブジェクトを返します。

2. @No__t_1 インターフェイスの <xref:Microsoft.VisualStudio.Modeling.Shell.IMonitorSelectionService.CurrentSelectionContainer%2A> プロパティは、アクティブな選択コンテナーを取得します。アクティブなウィンドウとは異なる場合があります。

3. 次のプロパティをドメイン固有言語のコマンドセットクラスに追加して、アクティブなウィンドウの種類を判別します。

    ```csharp
    // using Microsoft.VisualStudio.Modeling.Shell;

    // Returns true if the model designer is the active selection container;
    // otherwise, false.
    protected bool IsDesignerActive
    {
        get
        {
            return (this.MonitorSelection.CurrentSelectionContainer
                is DiagramDocView);
        }
    }

    // Returns true if the model explorer is the active selection container;
    // otherwise, false.
    protected bool IsExplorerActive
    {
        get
        {
            return (this.MonitorSelection.CurrentSelectionContainer
                is ModelExplorerToolWindow);
        }
    }
    ```

## <a name="constrain-the-selection"></a>選択範囲を制限する

選択規則を追加することにより、ユーザーがモデル内の要素を選択したときにどの要素を選択するかを制御できます。 たとえば、ユーザーが複数の要素を1つの単位として扱うことができるようにするには、選択ルールを使用します。

### <a name="to-create-a-selection-rule"></a>選択ルールを作成するには

1. DSL プロジェクトでカスタムコードファイルを作成する

2. @No__t_0 クラスから派生した選択規則クラスを定義します。

3. 選択規則クラスの <xref:Microsoft.VisualStudio.Modeling.Diagrams.DiagramSelectionRules.GetCompliantSelection%2A> メソッドをオーバーライドして、選択条件を適用します。

4. ClassDiagram クラスの部分クラス定義をカスタムコードファイルに追加します。

     @No__t_0 クラスは <xref:Microsoft.VisualStudio.Modeling.Diagrams.Diagram> クラスから派生し、DSL プロジェクトの生成されたコードファイル Diagram.cs で定義されています。

5. @No__t_1 クラスの <xref:Microsoft.VisualStudio.Modeling.Diagrams.Diagram.SelectionRules%2A> プロパティをオーバーライドして、カスタム選択規則を返します。

     @No__t_0 プロパティの既定の実装では、選択を変更しない選択ルールオブジェクトを取得します。

### <a name="example"></a>例

次のコードファイルは、選択範囲を拡張して、最初に選択された各ドメイン図形のすべてのインスタンスを含む選択規則を作成します。

```csharp
using System;
using System.Collections.Generic;
using Microsoft.VisualStudio.Modeling;
using Microsoft.VisualStudio.Modeling.Diagrams;

namespace CompanyName.ProductName.GroupingDsl
{
    public class CustomSelectionRules : DiagramSelectionRules
    {
        protected Diagram diagram;
        protected IElementDirectory elementDirectory;

        public CustomSelectionRules(Diagram diagram)
        {
            if (diagram == null) throw new ArgumentNullException();

            this.diagram = diagram;
            this.elementDirectory = diagram.Store.ElementDirectory;
        }

        /// <summary>Called by the design surface to allow selection filtering.
        /// </summary>
        /// <param name="currentSelection">[in] The current selection before any
        /// ShapeElements are added or removed.</param>
        /// <param name="proposedItemsToAdd">[in/out] The proposed DiagramItems to
        /// be added to the selection.</param>
        /// <param name="proposedItemsToRemove">[in/out] The proposed DiagramItems
        /// to be removed from the selection.</param>
        /// <param name="primaryItem">[in/out] The proposed DiagramItem to become
        /// the primary DiagramItem of the selection. A null value signifies that
        /// the last DiagramItem in the resultant selection should be assumed as
        /// the primary DiagramItem.</param>
        /// <returns>true if some or all of the selection was accepted; false if
        /// the entire selection proposal was rejected. If false, appropriate
        /// feedback will be given to the user to indicate that the selection was
        /// rejected.</returns>
        public override bool GetCompliantSelection(
            SelectedShapesCollection currentSelection,
            DiagramItemCollection proposedItemsToAdd,
            DiagramItemCollection proposedItemsToRemove,
            DiagramItem primaryItem)
        {
            if (currentSelection.Count == 0 && proposedItemsToAdd.Count == 0) return true;

            HashSet<DomainClassInfo> itemsToAdd = new HashSet<DomainClassInfo>();

            foreach (DiagramItem item in proposedItemsToAdd)
            {
                if (item.Shape != null)
                    itemsToAdd.Add(item.Shape.GetDomainClass());
            }
            proposedItemsToAdd.Clear();
            foreach (DomainClassInfo classInfo in itemsToAdd)
            {
                foreach (ModelElement element
                    in this.elementDirectory.FindElements(classInfo, false))
                {
                    if (element is ShapeElement)
                    {
                        proposedItemsToAdd.Add(
                            new DiagramItem((ShapeElement)element));
                    }
                }
            }

            return true;
        }
    }

    public partial class ClassDiagram
    {
        protected CustomSelectionRules customSelectionRules = null;

        protected bool multipleSelectionMode = true;

        public override DiagramSelectionRules SelectionRules
        {
            get
            {
                if (multipleSelectionMode)
                {
                    if (customSelectionRules == null)
                    {
                        customSelectionRules = new CustomSelectionRules(this);
                    }
                    return customSelectionRules;
                }
                else
                {
                    return base.SelectionRules;
                }
            }
        }
    }
}
```

## <a name="see-also"></a>関連項目

- <xref:Microsoft.VisualStudio.Modeling.Shell.CommandSet>
- <xref:Microsoft.VisualStudio.Modeling.Shell.ModelingPackage>
- <xref:Microsoft.VisualStudio.Modeling.Shell.DiagramDocView>
- <xref:Microsoft.VisualStudio.Modeling.Shell.ModelExplorerToolWindow>
- <xref:Microsoft.VisualStudio.Modeling.Shell.IMonitorSelectionService>
- <xref:Microsoft.VisualStudio.Modeling.Diagrams.DiagramSelectionRules>
- <xref:Microsoft.VisualStudio.Modeling.Diagrams.Diagram>