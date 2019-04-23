---
title: Windows フォーム アプリケーションでルックアップ テーブルを作成する |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- lookup tables
- lookup tables, creating
ms.assetid: 0edd5385-c381-4b17-9096-74e2778db9d5
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 76c55d45e279a3fcf6579c77bf7d226c7baf13d2
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "60102979"
---
# <a name="create-lookup-tables-in-windows-forms-applications"></a>Windows フォーム アプリケーションでルックアップ テーブルを作成する
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

*ルックアップ テーブル*という用語は、関連する 2 つのデータ テーブルにバインドされているコントロールを表します。 この検索コントロールは、2 番目のテーブルで選択されている値に基づいて最初のテーブルからデータを表示します。  
  
 親テーブルの主ノードをドラッグして、ルックアップ テーブルを作成することができます (から、[データ ソース ウィンドウ](http://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992)) に関連する子テーブル内の列に既にバインドされているフォーム上のコントロール。  
  
 たとえば、販売データベースの `Orders` テーブルであれば、次のように使用されます。 `Orders` テーブルの各レコードには、注文した顧客を表す `CustomerID` が含まれます。 `CustomerID` は、`Customers` テーブルの顧客レコードを指す外部キーです。 このシナリオで展開する、`Orders`テーブルに、**データ ソース**ウィンドウに、メイン ノードを設定し、**詳細**します。 設定し、`CustomerID`列を使用して、 <xref:System.Windows.Forms.ComboBox> (または検索バインドをサポートするその他のコントロール) をドラッグし、`Orders`フォーム上にノード。 最後に、ドラッグ、 `Customers` 、関連する列にバインドされているコントロールの上に、この場合、<xref:System.Windows.Forms.ComboBox>にバインドされている、`CustomerID`列。  
  
## <a name="to-databind-a-lookup-control"></a>検索コントロールをデータバインドするには  
  
1. **[データ ソース]** ウィンドウを開く。  
  
    > [!NOTE]
    > 検索テーブルを作成するには、関連付けられた 2 つのテーブルまたはオブジェクトが **[データ ソース]** ウィンドウで使用可能になっている必要があります。
  
2. **[データ ソース]** ウィンドウで、親テーブルとそのすべての列および関連する子テーブルとそのすべて列が表示されるまでノードを展開します。  
  
    > [!NOTE]
    >  子テーブルのノードは、展開可能な子ノードとして親テーブルに表示されます。  
  
3. 子テーブルのノードのコントロール一覧の **[詳細]** を選択し、子テーブルのドロップ タイプを **[詳細]** に変更します。 詳細については、次を参照してください。[設定、データ ソース ウィンドウからドラッグするときに作成されるコントロール](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md)します。  
  
4. 2 つのテーブルの関連ノードを見つけます (、`CustomerID`前の例でのノード)。ドロップ型を変更、<xref:System.Windows.Forms.ComboBox>を選択して**ComboBox**コントロール リストから。  
  
5. メインの子テーブルのノードを **[データ ソース]** ウィンドウからフォームにドラッグします。  
  
     説明のラベルが付いたデータ バインド コントロールとツール ストリップ (<xref:System.Windows.Forms.BindingNavigator>) がフォームに表示されます。 A[データセット](../data-tools/dataset-tools-in-visual-studio.md)、TableAdapter、 <xref:System.Windows.Forms.BindingSource>、および<xref:System.Windows.Forms.BindingNavigator>コンポーネント トレイに表示されます。  
  
6. 今すぐからメインの親テーブル ノードをドラッグ、**データ ソース**ルックアップ コントロールに直接ウィンドウ (、 <xref:System.Windows.Forms.ComboBox>)。  
  
     これで検索バインドが確立されます。 コントロールに設定された個々のプロパティについては、次の表を参照してください。  
  
    |プロパティ|設定の説明|  
    |--------------|----------------------------|  
    |**DataSource**|Visual Studio は、このプロパティをコントロールにドラッグしたテーブルに対して作成された <xref:System.Windows.Forms.BindingSource> に設定します (コントロールの作成時に作成された <xref:System.Windows.Forms.BindingSource> とは異なります)。<br /><br /> 調整する必要がある場合は、これを表示する列を含むテーブルの <xref:System.Windows.Forms.BindingSource> に設定します。|  
    |**DisplayMember**|Visual Studio は、このプロパティをコントロールにドラッグするテーブルの主キーの後で、文字列データ型を含む最初の列に設定します。<br /><br /> 調整する必要がある場合は、これを表示する列の名前に設定します。|  
    |**ValueMember**|Visual Studio は、このプロパティを主キーに参加している最初の列、またはキーが定義されていない場合は、テーブルの最初の列に設定します。<br /><br /> 調整する必要がある場合は、これを表示する列を含むテーブルの主キーに設定します。|  
    |**SelectedValue**|Visual Studio は、このプロパティを **[データ ソース]** ウィンドウからドロップした元の列に設定します。<br /><br /> 調整する必要がある場合は、これを関連付けられたテーブルの外部キー列に設定します。|  
  
## <a name="see-also"></a>関連項目  
 [Visual Studio でのデータへの Windows フォーム コントロールのバインド](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)
