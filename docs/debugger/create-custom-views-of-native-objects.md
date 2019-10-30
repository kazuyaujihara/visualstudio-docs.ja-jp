---
title: C++ オブジェクトのカスタム ビューを作成する
description: Use the Natvis framework to customize the way that Visual Studio displays native types in the debugger
ms.date: 10/31/2018
ms.topic: conceptual
f1_keywords:
- natvis
dev_langs:
- C++
ms.assetid: 2d9a177a-e14b-404f-a6af-49498eff0bd7
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- cplusplus
ms.openlocfilehash: c38ff2fcc762ccc202e2a02ecd36e942db75ad3d
ms.sourcegitcommit: ab18c9d850192fc9ccec10961f1126e8b0cba8da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73061080"
---
# <a name="create-custom-views-of-c-objects-in-the-debugger-using-the-natvis-framework"></a>Create custom views of C++ objects in the debugger using the Natvis framework

The Visual Studio *Natvis* framework customizes the way native types appear in debugger variable windows, such as the **Locals** and **Watch** windows, and in **DataTips**. Natvis visualizations can help make the types you create more visible during debugging.

Natvis replaces the *autoexp.dat* file in earlier versions of Visual Studio with XML syntax, better diagnostics, versioning, and multiple file support.

## <a name="BKMK_Why_create_visualizations_"></a>Natvis visualizations

You use the Natvis framework to create visualization rules for the types you create, so that developers can see them more easily during debugging.

For example, the following illustration shows a variable of type [Windows::UI::Xaml::Controls::TextBox](/uwp/api/Windows.UI.Xaml.Controls.TextBox) in a debugger window without any custom visualizations applied.

![TextBox default visualization](../debugger/media/dbg_natvis_textbox_default.png "TextBox の既定の視覚表現")

強調表示された行には `Text` クラスの `TextBox` プロパティが示されています。 The complex class hierarchy makes it difficult to find this property. The debugger doesn't know how to interpret the custom string type, so you can't see the string held inside the textbox.

The same `TextBox` looks much simpler in the variable window when Natvis custom visualizer rules are applied. The important members of the class appear together, and the debugger shows the underlying string value of the custom string type.

![TextBox data using visualizer](../debugger/media/dbg_natvis_textbox_visualizer.png "ビジュアライザーを使用した TextBox データ")

## <a name="BKMK_Using_Natvis_files"></a>Use .natvis files in C++ projects

Natvis uses *.natvis* files to specify visualization rules. A *.natvis* file is an XML file with a *.natvis* extension. The Natvis schema is defined in *%VSINSTALLDIR%\Xml\Schemas\natvis.xsd*.

The basic structure of a *.natvis* file is one or more `Type` elements representing visualization entries. The fully qualified name of each `Type` element is specified in its `Name` attribute.

```xml
<?xml version="1.0" encoding="utf-8"?>
<AutoVisualizer xmlns="http://schemas.microsoft.com/vstudio/debugger/natvis/2010">
  <Type Name="MyNamespace::CFoo">
    .
    .
  </Type>

  <Type Name="...">
    .
    .
  </Type>
</AutoVisualizer>
```

Visual Studio provides some *.natvis* files in the *%VSINSTALLDIR%\Common7\Packages\Debugger\Visualizers* folder. These files have visualization rules for many common types, and can serve as examples for writing visualizations for new types.

### <a name="add-a-natvis-file-to-a-c-project"></a>Add a .natvis file to a C++ project

You can add a *.natvis* file to any C++ project.

**To add a new *.natvis* file:**

1. Select the C++ project node in **Solution Explorer**, and select **Project** > **Add new item**, or right-click the project and select **Add** > **New item**.

1. In the **Add New Item** dialog, select **Visual C++**  > **Utility** > **Debugger visualization file (.natvis)** .

1. Name the file, and select **Add**.

   The new file is added to **Solution Explorer**, and opens in the Visual Studio document pane.

The Visual Studio debugger loads *.natvis* files in C++ projects automatically, and by default, also includes them in the *.pdb* file when the project builds. If you debug the built app, the debugger loads the *.natvis* file from the *.pdb* file, even if you don't have the project open. If you don't want the *.natvis* file included in the *.pdb*, you can exclude it from the built *.pdb* file.

**To exclude a *.natvis* file from a *.pdb*:**

1. Select the *.natvis* file in **Solution Explorer**, and select the **Properties** icon, or right-click the file and select **Properties**.

1. Drop down the arrow next to **Excluded From Build** and select **Yes**, and then select **OK**.

>[!NOTE]
>For debugging executable projects, use the solution items to add any *.natvis* files that are not in the *.pdb*, since there is no C++ project available.

>[!NOTE]
>*.Pdb*から読み込まれた Natvis 規則は、 *.pdb*が参照するモジュールの型にのみ適用されます。 たとえば、Natvis `Test`という名前の型のエントリが*ある場合、このエントリは*、module1.vb の `Test` クラスにのみ適用さ*れます。* 別のモジュールも `Test` という名前のクラスを定義している場合 *、Natvis エントリは適用*されません。

### <a name="BKMK_natvis_location"></a>Natvis ファイルの場所

複数のプロジェクトに適用する場合は、 *natvis*ファイルをユーザーディレクトリまたはシステムディレクトリに追加できます。

*Natvis*ファイルは、次の順序で評価されます。

1. 読み込まれたプロジェクトに同じ名前のファイルが存在しない限り、デバッグ中の *.pdb*に埋め込まれている*natvis ファイル。*

2. 読み込ま C++れたプロジェクトまたはトップレベルソリューションにある natvis ファイル。 このグループには、 C++クラスライブラリを含む、読み込まれたすべてのプロジェクトが含まれますが、他の言語のプロジェクトは含まれません。

::: moniker range="vs-2017"

3. ユーザー固有の Natvis ディレクトリ (たとえば、 *%USERPROFILE%\Documents\Visual Studio 2017 \ ビジュアライザー*)。

::: moniker-end

::: moniker range=">= vs-2019"

3. ユーザー固有の Natvis ディレクトリ (たとえば、 *%USERPROFILE%\Documents\Visual Studio 2019 \ ビジュアライザー*)。

::: moniker-end

4. システム全体の Natvis ディレクトリ ( *%VSINSTALLDIR%\Common7\Packages\Debugger\Visualizers*)。 このディレクトリには、Visual Studio と共にインストールされる*natvis*ファイルがあります。 管理者のアクセス許可がある場合は、このディレクトリにファイルを追加できます。

## <a name="modify-natvis-files-while-debugging"></a>デバッグ中に natvis ファイルを変更する

IDE でプロジェクトのデバッグ中に*natvis*ファイルを変更できます。 デバッグしている Visual Studio の同じインスタンスでファイルを開き、変更して保存します。 ファイルが保存されるとすぐに、 **[ウォッチ]** ウィンドウと **[ローカル]** ウィンドウが更新され、変更が反映されます。

また、デバッグ中のソリューションで*natvis*ファイルを追加または削除したり、Visual Studio で関連する視覚エフェクトを追加または削除したりすることもできます。

デバッグ中に *.pdb*ファイルに埋め込まれている*natvis*ファイルを更新することはできません。

Visual Studio の外部で*natvis*ファイルを変更しても、変更は自動的には有効になりません。 デバッガーウィンドウを更新するには、 **[ウォッチ]** ウィンドウで .natvisreload コマンドを再評価します **。** その後、変更はデバッグセッションを再起動しなくても有効になります。

また、 **.natvisreload**コマンドを使用して、 *natvis*ファイルを新しいバージョンにアップグレードします。 たとえば、 *natvis*ファイルはソース管理にチェックインされ、他のユーザーが最近行った変更を取得することができます。

## <a name="BKMK_Expressions_and_formatting"></a> 式と書式
Natvis 視覚化では、C++ 式を使用して、表示するデータ項目を指定します。 「[コンテキスト演算子 (C++)](../debugger/context-operator-cpp.md)」で説明C++されている、デバッガーでの式の拡張と制限事項に加えて、次の点に注意してください。

- Natvis 式は、現在のスタック フレームではなく視覚化されるオブジェクトのコンテキストで評価されます。 たとえば、Natvis 式の `x` は、視覚化されるオブジェクト内の**x**という名前のフィールドを参照します。このフィールドは、現在の関数の**x**という名前のローカル変数ではありません。 Natvis 式でローカル変数にアクセスすることはできませんが、グローバル変数にはアクセスできます。

- Natvis 式では、関数の評価や副作用は許可されません。 関数呼び出しと代入演算子は無視されます。 [デバッガーの組み込み関数](../debugger/expressions-in-the-debugger.md#BKMK_Using_debugger_intrinisic_functions_to_maintain_state) は、他の関数とは異なり副作用がないため、Natvis 式からは自由に呼び出すことができます。

- 式の表示方法を制御するには、「 [」のC++「書式指定子](format-specifiers-in-cpp.md#BKMK_Visual_Studio_2012_format_specifiers)」で説明されている書式指定子のいずれかを使用できます。 Natvis によって内部的に使用される場合 ( [Arrayitems の展開](../debugger/create-custom-views-of-native-objects.md#BKMK_ArrayItems_expansion)の `Size` 式など)、書式指定子は無視されます。

## <a name="natvis-views"></a>Natvis ビュー

異なる Natvis ビューを定義して、さまざまな方法で型を表示できます。 たとえば、`simple`という簡易ビューを定義する `std::vector` の視覚化を次に示します。 `DisplayString` と `ArrayItems` の要素は、既定のビューと `simple` ビューに表示されますが、`[size]` および `[capacity]` の項目は `simple` ビューに表示されません。

```xml
<Type Name="std::vector&lt;*&gt;">
    <DisplayString>{{ size={_Mylast - _Myfirst} }}</DisplayString>
    <Expand>
        <Item Name="[size]" ExcludeView="simple">_Mylast - _Myfirst</Item>
        <Item Name="[capacity]" ExcludeView="simple">_Myend - _Myfirst</Item>
        <ArrayItems>
            <Size>_Mylast - _Myfirst</Size>
            <ValuePointer>_Myfirst</ValuePointer>
        </ArrayItems>
    </Expand>
</Type>
```

**[ウォッチ]** ウィンドウで、ビュー書式指定子を使用して **、** 別のビューを指定します。 Simple ビューは、 **vec、view (simple)** として表示されます。

![簡易ビューでのウォッチウィンドウ](../debugger/media/watch-simpleview.png "単純なビューを備えた [ウォッチ] ウィンドウ")

## <a name="BKMK_Diagnosing_Natvis_errors"></a>Natvis エラー

デバッガーが視覚化エントリでエラーを検出すると、そのエラーは無視されます。 未加工の形式で型を表示するか、別の適切な視覚化を選択します。 Natvis 診断を使用して、デバッガーが視覚化エントリを無視した理由を理解し、基になる構文と解析エラーを確認することができます。

**Natvis 診断を有効にするには:**

- **ツール** > **オプション** (または**デバッグ** > **オプション**) で >**デバッグ** > **出力ウィンドウ**、**NatvisC++診断メッセージ (のみ)** を **エラー**、警告 に設定します。、または**Verbose**を選択し、 **OK**を選択します。

エラーは **[出力]** ウィンドウに表示されます。

## <a name="BKMK_Syntax_reference"></a> Natvis 構文のリファレンス

### <a name="BKMK_AutoVisualizer"></a> AutoVisualizer の要素
`AutoVisualizer` 要素は *.natvis* ファイルのルート ノードであり、名前空間 `xmlns:` 属性を含みます。

```xml
<?xml version="1.0" encoding="utf-8"?>
<AutoVisualizer xmlns="http://schemas.microsoft.com/vstudio/debugger/natvis/2010">
.
.
</AutoVisualizer>
```

`AutoVisualizer` 要素は、[型](#BKMK_Type)、 [HResult](#BKMK_HResult)、 [Uivisualizer](#BKMK_UIVisualizer)、および[customvisualizer](#BKMK_CustomVisualizer)の子を持つことができます。

### <a name="BKMK_Type"></a> Type 要素

基本 `Type` は次の例のようになります。

```xml
<Type Name="[fully qualified type name]">
  <DisplayString Condition="[Boolean expression]">[Display value]</DisplayString>
  <Expand>
    ...
  </Expand>
</Type>
```

 `Type` 要素は次を指定します。

1. 視覚エフェクトを使用する必要がある種類 (`Name` 属性)。

2. その型のオブジェクトの値がどのように表示されるか ( `DisplayString` 要素)。

3. ユーザーが変数ウィンドウ (`Expand` ノード) で型を展開したときに、型のメンバーがどのように表示されるかを指定します。

#### <a name="templated-classes"></a>テンプレートクラス
`Type` 要素の `Name` 属性は、アスタリスク `*` をワイルドカード文字として使用し、テンプレートクラス名に使用できます。

次の例では、オブジェクトが `CAtlArray<int>` であるか `CAtlArray<float>`であるかにかかわらず、同じ視覚化が使用されます。 `CAtlArray<float>`の特定の視覚化エントリがある場合は、それが汎用のものよりも優先されます。

```xml
<Type Name="ATL::CAtlArray&lt;*&gt;">
    <DisplayString>{{Count = {m_nSize}}}</DisplayString>
</Type>
```

マクロ $T 1、$T 2 などを使用して、視覚化エントリのテンプレートパラメーターを参照できます。 これらのマクロの例を見つけるには、Visual Studio に付属の *.natvis* ファイルをご覧ください。

#### <a name="BKMK_Visualizer_type_matching"></a> ビジュアライザーと型の対応付け
視覚化エントリの検証に失敗した場合は、次に利用可能な視覚エフェクトが使用されます。

#### <a name="inheritable-attribute"></a>継承可能な属性
省略可能な `Inheritable` 属性では、視覚化が基本データ型にのみ適用されるか、基本データ型とすべての派生型にのみ適用されるかを指定します。 `Inheritable` の既定値は `true`です。

次の例では、視覚化は `BaseClass` 型にのみ適用されます。

```xml
<Type Name="Namespace::BaseClass" Inheritable="false">
    <DisplayString>{{Count = {m_nSize}}}</DisplayString>
</Type>
```

#### <a name="priority-attribute"></a>Priority 属性

省略可能な `Priority` 属性は、定義の解析に失敗した場合に、代替定義を使用する順序を指定します。 `Priority` に指定できる値は、`Low`、`MediumLow`、`Medium`、`MediumHigh`、および `High`です。 既定値は `Medium`です。 `Priority` 属性は、同じ*natvis*ファイル内の優先度のみを区別します。

次の例では、最初に 2015 STL と一致するエントリを解析します。 解析に失敗した場合、2013バージョンの STL の代替エントリが使用されます。

```xml
<!-- VC 2013 -->
<Type Name="std::reference_wrapper&lt;*&gt;" Priority="MediumLow">
     <DisplayString>{_Callee}</DisplayString>
    <Expand>
        <ExpandedItem>_Callee</ExpandedItem>
    </Expand>
</Type>

<!-- VC 2015 -->
<Type Name="std::reference_wrapper&lt;*&gt;">
    <DisplayString>{*_Ptr}</DisplayString>
    <Expand>
        <Item Name="[ptr]">_Ptr</Item>
    </Expand>
</Type>
```

### <a name="optional-attribute"></a>Optional 属性
任意のノードに `Optional` 属性を配置できます。 省略可能なノード内の部分式が解析に失敗した場合、デバッガーはそのノードを無視しますが、残りの `Type` 規則を適用します。 次の型では、 `[State]` は省略不可能ですが、 `[Exception]` は省略可能です。  `MyNamespace::MyClass` に _`M_exceptionHolder`という名前のフィールドがある場合、[`[State]`] ノードと [`[Exception]`] ノードの両方が表示されますが、`_M_exceptionHolder` フィールドがない場合は、`[State]` ノードだけが表示されます。

```xml
<Type Name="MyNamespace::MyClass">
    <Expand>
      <Item Name="[State]">_M_State</Item>
      <Item Name="[Exception]" Optional="true">_M_exceptionHolder</Item>
    </Expand>
</Type>
```

### <a name="BKMK_Condition_attribute"></a> Condition 属性

オプションの `Condition` 属性は多くの視覚化要素で使用でき、視覚エフェクトルールを使用するタイミングを指定します。 If the expression inside the condition attribute resolves to `false`, the visualization rule doesn't apply. If it evaluates to `true`, or there is no `Condition` attribute, the visualization applies. You can use this attribute for if-else logic in the visualization entries.

For example, the following visualization has two `DisplayString` elements for a smart pointer type. When the `_Myptr` member is empty, the condition of the first `DisplayString` element resolves to `true`, so that form displays. When the `_Myptr` member is not empty, the condition evaluates to `false`, and the second `DisplayString` element displays.

```xml
<Type Name="std::auto_ptr&lt;*&gt;">
  <DisplayString Condition="_Myptr == 0">empty</DisplayString>
  <DisplayString>auto_ptr {*_Myptr}</DisplayString>
  <Expand>
    <ExpandedItem>_Myptr</ExpandedItem>
  </Expand>
</Type>
```

### <a name="includeview-and-excludeview-attributes"></a>IncludeView および ExcludeView 属性

The `IncludeView` and `ExcludeView` attributes specify elements to display or not display in specific views. For example, in the following Natvis specification of `std::vector`, the `simple` view doesn't display the `[size]` and `[capacity]` items.

```xml
<Type Name="std::vector&lt;*&gt;">
    <DisplayString>{{ size={_Mylast - _Myfirst} }}</DisplayString>
    <Expand>
        <Item Name="[size]" ExcludeView="simple">_Mylast - _Myfirst</Item>
        <Item Name="[capacity]" ExcludeView="simple">_Myend - _Myfirst</Item>
        <ArrayItems>
            <Size>_Mylast - _Myfirst</Size>
            <ValuePointer>_Myfirst</ValuePointer>
        </ArrayItems>
    </Expand>
</Type>
```

You can use the `IncludeView` and `ExcludeView` attributes on types and on individual members.

### <a name="BKMK_Versioning"></a> Version 要素
The `Version` element scopes a visualization entry to a specific module and version. The `Version` element helps avoid name collisions, reduces inadvertent mismatches, and allows different visualizations for different type versions.

If a common header file that is used by different modules defines a type, the versioned visualization appears only when the type is in the specified module version.

In the following example, the visualization is applicable only for the `DirectUI::Border` type found in the `Windows.UI.Xaml.dll` from version 1.0 to 1.5.

```xml
<Type Name="DirectUI::Border">
  <Version Name="Windows.UI.Xaml.dll" Min="1.0" Max="1.5"/>
  <DisplayString>{{Name = {*(m_pDO->m_pstrName)}}}</DisplayString>
  <Expand>
    <ExpandedItem>*(CBorder*)(m_pDO)</ExpandedItem>
  </Expand>
</Type>
```

You don't need both `Min` and `Max`. They are optional attributes. No wildcard characters are supported.

The `Name` attribute is in the format *filename.ext*, such as *hello.exe* or *some.dll*. No path names are allowed.

### <a name="BKMK_DisplayString"></a> DisplayString element
The `DisplayString` element specifies a string to show as the value of a variable. この要素には、任意の文字列を式と組み合わせて使用できます。 中かっこ内のすべてのものは式として解釈されます。 For instance, the following `DisplayString` entry:

```xml
<Type Name="CPoint">
  <DisplayString>{{x={x} y={y}}}</DisplayString>
</Type>
```

Means that variables of type `CPoint` display as in this illustration:

 ![Use a DisplayString element](../debugger/media/dbg_natvis_cpoint_displaystring.png "DisplayString 要素を使用する")

In the `DisplayString` expression, `x` and `y`, which are members of `CPoint`, are inside curly braces, so their values are evaluated. The example also shows how you can escape a curly brace by using double curly braces ( `{{` or `}}` ).

> [!NOTE]
> `DisplayString` 要素でのみ、任意の文字列と中かっこ構文を使用できます。 All other visualization elements accept only expressions that the debugger can evaluate.

### <a name="BKMK_StringView"></a> StringView element

The `StringView` element defines a value that the debugger can send to the built-in text visualizer. For example, given the following visualization for the `ATL::CStringT` type:

```xml
<Type Name="ATL::CStringT&lt;wchar_t,*&gt;">
  <DisplayString>{m_pszData,su}</DisplayString>
</Type>
```

The `CStringT` object displays in a variable window like this example:

![CStringT DisplayString element](../debugger/media/dbg_natvis_displaystring_cstringt.png "CStringT DisplayString 要素")

Adding a `StringView` element tells the debugger it can display the value as a text visualization.

```xml
<Type Name="ATL::CStringT&lt;wchar_t,*&gt;">
  <DisplayString>{m_pszData,su}</DisplayString>
  <StringView>m_pszData,su</StringView>
</Type>
```

During debugging, you can select the magnifying glass icon next to the variable, and then select **Text Visualizer** to display the string that **m_pszData** points to.

 ![StringView ビジュアライザーを使用した CStringT データ](../debugger/media/dbg_natvis_stringview_cstringt.png "StringView ビジュアライザーを含む CStringT データ")

式 `{m_pszData,su}` には、 C++値を Unicode 文字列として表示するための書式指定子**su**が含まれています。 詳細については、「 [」 C++の「書式指定子](../debugger/format-specifiers-in-cpp.md)」を参照してください。

### <a name="BKMK_Expand"></a>要素の展開

オプションの `Expand` ノードは、変数ウィンドウで型を展開するときに、視覚化された型の子をカスタマイズします。 `Expand` ノードは、子要素を定義する子ノードのリストを受け入れます。

- 視覚エフェクトエントリで `Expand` ノードが指定されていない場合、子は既定の展開規則を使用します。

- 子ノードが存在しない状態で `Expand` ノードが指定されている場合、その型はデバッガーウィンドウで展開できません。

#### <a name="BKMK_Item_expansion"></a> Item の展開

 `Item` 要素は、`Expand` ノードの最も基本的で一般的な要素です。 `Item` は 1 つの子要素を定義します。 たとえば、フィールド `top`、`left`、`right`、および `bottom` を持つ `CRect` クラスには、次の視覚化エントリがあります。

```xml
<Type Name="CRect">
  <DisplayString>{{top={top} bottom={bottom} left={left} right={right}}}</DisplayString>
  <Expand>
    <Item Name="Width">right - left</Item>
    <Item Name="Height">bottom - top</Item>
  </Expand>
</Type>
```

デバッガーウィンドウでは、`CRect` の型は次の例のようになります。

![項目要素の展開を含む CRect](../debugger/media/dbg_natvis_expand_item_crect1.png "Item 要素の展開を含む CRect")

デバッガーは、`Width` および `Height` 要素で指定された式を評価し、変数 ウィンドウの **値** 列に値を表示します。

デバッガーによって、カスタム展開のたびに **[Raw ビュー]** ノードが自動的に作成されます。 上のスクリーンショットでは、 **[Raw view]** ノードが展開され、オブジェクトの既定の未加工ビューがその Natvis の視覚化とどのように異なるかが示されています。 既定の展開では、基底クラスのサブツリーが作成され、基底クラスのすべてのデータメンバーが子として一覧表示されます。

> [!NOTE]
> Item 要素の式が複合型を指している場合は、**項目**ノード自体が展開可能です。

#### <a name="BKMK_ArrayItems_expansion"></a> Size
`ArrayItems` ノードを使用すると、Visual Studio デバッガーによって型が配列として解釈され、その個々の要素が表示されるようになります。 `std::vector` の視覚化は良い使用例です。

```xml
<Type Name="std::vector&lt;*&gt;">
  <DisplayString>{{size = {_Mylast - _Myfirst}}}</DisplayString>
  <Expand>
    <Item Name="[size]">_Mylast - _Myfirst</Item>
    <Item Name="[capacity]">(_Myend - _Myfirst)</Item>
    <ArrayItems>
      <Size>_Mylast - _Myfirst</Size>
      <ValuePointer>_Myfirst</ValuePointer>
    </ArrayItems>
  </Expand>
</Type>
```

`std::vector` は、変数ウィンドウで展開されると、その個々の要素が表示されます。

![ArrayItems の展開を使用する std:: vector](../debugger/media/dbg_natvis_expand_arrayitems_stdvector.png "ArrayItems の展開を使用した std::vector")

`ArrayItems` ノードには次のものが必要です。

- デバッガーが配列の長さを解釈するための `Size` 式 (整数に評価されることが必要)。
- 最初の要素を指す `ValuePointer` 式 (`void*` ではない要素型のポインターである必要があります)。

配列の既定の下限値は 0 です。 値をオーバーライドするには、`LowerBound` 要素を使用します。 Visual Studio に付属の*natvis*ファイルには例があります。

>[!NOTE]
>`[]` 演算子を使用することもできます。たとえば、`vector[i]`のように `ArrayItems`を使用する1次元配列の視覚エフェクトでは、型自体 (`CATLArray`など) ではこの演算子が許可されていません。

多次元配列を指定することもできます。 この場合、子要素を適切に表示するには、デバッガーに多少の情報が必要になります。

```xml
<Type Name="Concurrency::array&lt;*,*&gt;">
  <DisplayString>extent = {_M_extent}</DisplayString>
  <Expand>
    <Item Name="extent">_M_extent</Item>
    <ArrayItems Condition="_M_buffer_descriptor._M_data_ptr != 0">
      <Direction>Forward</Direction>
      <Rank>$T2</Rank>
      <Size>_M_extent._M_base[$i]</Size>
      <ValuePointer>($T1*) _M_buffer_descriptor._M_data_ptr</ValuePointer>
    </ArrayItems>
  </Expand>
</Type>
```

- `Direction` は、配列が行優先または列優先の順序であるかどうかを指定します。
- `Rank` は配列のランクを指定します。
- `Size` 要素は暗黙の `$i` パラメーターを受け取ります。このパラメーターは次元のインデックスに置き換えられて、その次元の配列の長さが特定されます。 前の例では、`_M_extent.M_base[0]` 式によって、0番目の次元の長さ、1番目の次元 `_M_extent._M_base[1]` などが指定されています。

次に、2次元の `Concurrency::array` オブジェクトがデバッガーウィンドウでどのように表示されるかを示します。

![ArrayItems の展開を含む2次元配列](../debugger/media/dbg_natvis_expand_arrayitems_2d.png "ArrayItems の展開を含む2次元配列")

#### <a name="BKMK_IndexListItems_expansion"></a> IndexListItems の展開

配列要素が連続してメモリ内に配置されている場合にのみ、`ArrayItems` 拡張を使用できます。 デバッガーは、ポインターをインクリメントするだけで次の要素を取得します。 値ノードのインデックスを操作する必要がある場合は、`IndexListItems` ノードを使用します。 `IndexListItems` ノードを含む視覚化を次に示します。

```xml
<Type Name="Concurrency::multi_link_registry&lt;*&gt;">
  <DisplayString>{{size = {_M_vector._M_index}}}</DisplayString>
  <Expand>
    <Item Name="[size]">_M_vector._M_index</Item>
    <IndexListItems>
      <Size>_M_vector._M_index</Size>
      <ValueNode>*(_M_vector._M_array[$i])</ValueNode>
    </IndexListItems>
  </Expand>
</Type>
```

`ArrayItems` と `IndexListItems` の唯一の違いは、暗黙的な `$i` パラメーターを使用して i<sup>番目</sup>の要素を完全に表現する必要がある `ValueNode`です。

>[!NOTE]
>`[]` 演算子を使用することもできます。たとえば、`vector[i]`のように `IndexListItems`を使用する1次元配列の視覚エフェクトでは、型自体 (`CATLArray`など) ではこの演算子が許可されていません。

#### <a name="BKMK_LinkedListItems_expansion"></a> LinkedListItems の展開

視覚化された型がリンク リストを表す場合、デバッガーは `LinkedListItems` ノードを使用してその子を表示できます。 次の `CAtlList` の種類の視覚化では `LinkedListItems`が使用されます。

```xml
<Type Name="ATL::CAtlList&lt;*,*&gt;">
  <DisplayString>{{Count = {m_nElements}}}</DisplayString>
  <Expand>
    <Item Name="Count">m_nElements</Item>
    <LinkedListItems>
      <Size>m_nElements</Size>
      <HeadPointer>m_pHead</HeadPointer>
      <NextPointer>m_pNext</NextPointer>
      <ValueNode>m_element</ValueNode>
    </LinkedListItems>
  </Expand>
</Type>
```

`Size` 要素はリストの長さを参照します。 `HeadPointer` は最初の要素を参照し、 `NextPointer` は次の要素を参照し、 `ValueNode` は項目の値を参照します。

デバッガーは、親リストの型ではなく、`LinkedListItems` node 要素のコンテキストで `NextPointer` および `ValueNode` 式を評価します。 前の例では、`CAtlList` には、リンクリストのノードである `CNode` クラス (`atlcoll.h`) があります。 `m_pNext` と `m_element` は、`CAtlList` クラスではなく `CNode` クラスのフィールドです。

`ValueNode` は空のままにするか、`this` を使用して `LinkedListItems` ノード自体を参照することができます。

#### <a name="customlistitems-expansion"></a>CustomListItems 展開
`CustomListItems` 展開を使用して、ハッシュ テーブルなどのデータ構造を走査する際にカスタム ロジックを記述することができます。 評価が必要なすべてのものに対して式C++を使用できるデータ構造を視覚化するには、`CustomListItems` を使用します。ただし、`ArrayItems`、`IndexListItems`、または `LinkedListItems` のモールドには適していません。

次の `CAtlMap` のビジュアライザーは、`CustomListItems` が適切な場合の優れた例です。

```xml
<Type Name="ATL::CAtlMap&lt;*,*,*,*&gt;">
    <AlternativeType Name="ATL::CMapToInterface&lt;*,*,*&gt;"/>
    <AlternativeType Name="ATL::CMapToAutoPtr&lt;*,*,*&gt;"/>
    <DisplayString>{{Count = {m_nElements}}}</DisplayString>
    <Expand>
      <CustomListItems MaxItemsPerView="5000" ExcludeView="Test">
        <Variable Name="iBucket" InitialValue="-1" />
        <Variable Name="pBucket" InitialValue="m_ppBins == nullptr ? nullptr : *m_ppBins" />
        <Variable Name="iBucketIncrement" InitialValue="-1" />

        <Size>m_nElements</Size>
        <Exec>pBucket = nullptr</Exec>
        <Loop>
          <If Condition="pBucket == nullptr">
            <Exec>iBucket++</Exec>
            <Exec>iBucketIncrement = __findnonnull(m_ppBins + iBucket, m_nBins - iBucket)</Exec>
            <Break Condition="iBucketIncrement == -1" />
            <Exec>iBucket += iBucketIncrement</Exec>
            <Exec>pBucket = m_ppBins[iBucket]</Exec>
          </If>
          <Item>pBucket,na</Item>
          <Exec>pBucket = pBucket->m_pNext</Exec>
        </Loop>
      </CustomListItems>
    </Expand>
</Type>
```

`Exec` を使用すると、展開で定義されている変数とオブジェクトを使用して、`CustomListItems` 拡張の内部でコードを実行できます。 論理演算子、算術演算子、代入演算子は `Exec` と共に使用できます。 `Exec` を使用して関数を評価することはできません。

`CustomListItems` は、次の組み込み関数をサポートしています。

- `strlen`、`wcslen`、`strnlen`、`wcsnlen`、`strcmp`、`wcscmp`、`_stricmp`、`_strcmpi`、`_wcsicmp`、`strncmp`、`wcsncmp`、`_strnicmp`、`_wcsnicmp`、`memcmp`、`memicmp`、`wmemcmp`、`strchr`、`wcschr`、`memchr`、`wmemchr`、`strstr`、`wcsstr`、`__log2`、`__findNonNull`
- `GetLastError`、`TlsGetValue`、`DecodeHString`、`WindowsGetStringLen`、`WindowsGetStringRawBuffer`、`WindowsCompareStringOrdinal`、`RoInspectCapturedStackBackTrace`、`CoDecodeProxy`、`GetEnvBlockLength`、`DecodeWinRTRestrictedException`、`DynamicMemberLookup`、`DecodePointer`、`DynamicCast`
- `ConcurrencyArray_OperatorBracket_idx // Concurrency::array<>::operator[index<>] and operator(index<>)`
- `ConcurrencyArray_OperatorBracket_int // Concurrency::array<>::operator(int, int, ...)`
- `ConcurrencyArray_OperatorBracket_tidx // Concurrency::array<>::operator[tiled_index<>] and operator(tiled_index<>)`
- `ConcurrencyArrayView_OperatorBracket_idx // Concurrency::array_view<>::operator[index<>] and operator(index<>)`
- `ConcurrencyArrayView_OperatorBracket_int // Concurrency::array_view<>::operator(int, int, ...)`
- `ConcurrencyArrayView_OperatorBracket_tidx // Concurrency::array_view<>::operator[tiled_index<>] and operator(tiled_index<>)`
- `Stdext_HashMap_Int_OperatorBracket_idx`
- `Std_UnorderedMap_Int_OperatorBracket_idx`
- `TreeTraverse_Init // Initializes a new tree traversal`
- `TreeTraverse_Next // Returns nodes in a tree`
- `TreeTraverse_Skip // Skips nodes in a pending tree traversal`

#### <a name="BKMK_TreeItems_expansion"></a> TreeItems の展開
 視覚化された型がツリーを表す場合、デバッガーはツリーをたどり、 `TreeItems` ノードを使用してその子を表示できます。 `TreeItems` ノードを使用した `std::map` 型の視覚化を次に示します。

```xml
<Type Name="std::map&lt;*&gt;">
  <DisplayString>{{size = {_Mysize}}}</DisplayString>
  <Expand>
    <Item Name="[size]">_Mysize</Item>
    <Item Name="[comp]">comp</Item>
    <TreeItems>
      <Size>_Mysize</Size>
      <HeadPointer>_Myhead->_Parent</HeadPointer>
      <LeftPointer>_Left</LeftPointer>
      <RightPointer>_Right</RightPointer>
      <ValueNode Condition="!((bool)_Isnil)">_Myval</ValueNode>
    </TreeItems>
  </Expand>
</Type>
```

構文は、`LinkedListItems` ノードに似ています。 `LeftPointer`、`RightPointer`、`ValueNode` は、ツリーノードクラスのコンテキストで評価されます。 `ValueNode` は空のままにするか、`this` を使用して `TreeItems` ノード自体を参照することができます。

#### <a name="BKMK_ExpandedItem_expansion"></a> ExpandedItem の展開
 `ExpandedItem` 要素は、視覚化された型の子であるかのように、基底クラスまたはデータメンバーのプロパティを表示することによって、集計された子ビューを生成します。 デバッガーは、指定された式を評価し、その結果の子ノードを視覚化された型の子リストに追加します。

たとえば、スマートポインターの種類 `auto_ptr<vector<int>>` は通常、次のように表示されます。

 ![自動&#95;ptr&#60;ベクター&#60;int&#62; &#62;の既定の展開](../debugger/media/dbg_natvis_expand_expandeditem_default.png "既定の展開")

 ベクターの値を表示するには、変数ウィンドウの2つのレベルをドリルダウンし、`_Myptr` メンバーを通過する必要があります。 `ExpandedItem` 要素を追加することで、階層から `_Myptr` 変数を排除し、vector の要素を直接表示できます。

```xml
<Type Name="std::auto_ptr&lt;*&gt;">
  <DisplayString>auto_ptr {*_Myptr}</DisplayString>
  <Expand>
    <ExpandedItem>_Myptr</ExpandedItem>
  </Expand>
</Type>
```

 ![自動&#95;ptr&#60;ベクター&#60;int&#62; &#62; ExpandedItem 拡張](../debugger/media/dbg_natvis_expand_expandeditem_visualized.png "ExpandedItem の展開")

派生クラスの基底クラスからプロパティを集計する方法を次の例に示します。 `CPanel` クラスが `CFrameworkElement`から派生しているとします。 基本 `CFrameworkElement` クラスのプロパティを繰り返す代わりに、`ExpandedItem` ノードの視覚化によって、これらのプロパティが `CPanel` クラスの子リストに追加されます。

```xml
<Type Name="CPanel">
  <DisplayString>{{Name = {*(m_pstrName)}}}</DisplayString>
  <Expand>
    <Item Name="IsItemsHost">(bool)m_bItemsHost</Item>
    <ExpandedItem>*(CFrameworkElement*)this,nd</ExpandedItem>
  </Expand>
</Type>
```

派生クラスの視覚化の対応付けを無効にする **nd** 書式指定子がここで必要になります。 それ以外の場合、式 `*(CFrameworkElement*)this` を指定すると、`CPanel` の視覚化が再度適用されます。これは、既定の視覚化の種類の照合ルールでは、最も適切なものと見なされるためです。 **Nd**書式指定子を使用して、基底クラスの視覚化を使用するようにデバッガーに指示します。基底クラスに視覚化がない場合は、既定の展開を使用します。

#### <a name="BKMK_Synthetic_Item_expansion"></a> Synthetic Item の展開
 `ExpandedItem` 要素は階層を排除することでデータ ビューを平坦化しますが、`Synthetic` ノードはその反対のことを行います。 これにより、式の結果ではない人工子要素を作成できます。 人工要素には、独自の子要素を含めることができます。 次の例では、 `Concurrency::array` 型の視覚化で `Synthetic` ノードを使用して、診断メッセージをユーザーに表示しています。

```xml
<Type Name="Concurrency::array&lt;*,*&gt;">
  <DisplayString>extent = {_M_extent}</DisplayString>
  <Expand>
    <Item Name="extent" Condition="_M_buffer_descriptor._M_data_ptr == 0">_M_extent</Item>
    <ArrayItems Condition="_M_buffer_descriptor._M_data_ptr != 0">
      <Rank>$T2</Rank>
      <Size>_M_extent._M_base[$i]</Size>
      <ValuePointer>($T1*) _M_buffer_descriptor._M_data_ptr</ValuePointer>
    </ArrayItems>
    <Synthetic Name="Array" Condition="_M_buffer_descriptor._M_data_ptr == 0">
      <DisplayString>Array members can be viewed only under the GPU debugger</DisplayString>
    </Synthetic>
  </Expand>
</Type>
```

 ![合成要素の展開を使用した Concurrency:: Array](../debugger/media/dbg_natvis_expand_synthetic.png "合成要素の展開を使用した Concurrency:: Array")

### <a name="BKMK_HResult"></a>HResult 要素
 `HResult` 要素を使用すると、デバッガーウィンドウで**HRESULT**に対して表示される情報をカスタマイズできます。 `HRValue` 要素には、カスタマイズする **HRESULT** の 32 ビット値を格納する必要があります。 `HRDescription` 要素には、デバッガーウィンドウに表示する情報が含まれています。

```xml

<HResult Name="MY_E_COLLECTION_NOELEMENTS">
  <HRValue>0xABC0123</HRValue>
  <HRDescription>No elements in the collection.</HRDescription>
</HResult>
```

### <a name="BKMK_UIVisualizer"></a>UIVisualizer 要素
`UIVisualizer` 要素は、グラフィカル ビジュアライザー プラグインをデバッガーに登録するために使用します。 グラフィカルビジュアライザーは、データ型と一貫性のある方法で変数またはオブジェクトを表示するダイアログボックスまたはその他のインターフェイスを作成します。 ビジュアライザープラグインは[VSPackage](../extensibility/internals/vspackages.md)として作成する必要があり、デバッガーが使用できるサービスを公開する必要があります。 *Natvis*ファイルには、プラグインの名前、公開されたサービスの GUID、視覚化できる型など、プラグインの登録情報が含まれています。

ここでは、UIVisualizer 要素の例を示しています。

```xml
<?xml version="1.0" encoding="utf-8"?>
<AutoVisualizer xmlns="http://schemas.microsoft.com/vstudio/debugger/natvis/2010">
    <UIVisualizer ServiceId="{5452AFEA-3DF6-46BB-9177-C0B08F318025}"
        Id="1" MenuName="Vector Visualizer"/>
    <UIVisualizer ServiceId="{5452AFEA-3DF6-46BB-9177-C0B08F318025}"
        Id="2" MenuName="List Visualizer"/>
.
.
</AutoVisualizer>
```

- 属性ペアの `ServiceId` - `Id` `UIVisualizer`を識別します。 `ServiceId` は、ビジュアライザーパッケージが公開するサービスの GUID です。 `Id` はビジュアライザーを区別する一意の識別子で、サービスが複数のサービスを提供している場合に使用します。 前の例では、同じビジュアライザーサービスに2つのビジュアライザーが用意されています。

- `MenuName` 属性は、デバッガーの虫眼鏡アイコンの横にあるドロップダウンリストに表示されるビジュアライザー名を定義します。 (例:

  ![UIVisualizer メニューのショートカットメニュー](../debugger/media/dbg_natvis_vectorvisualizer.png "UIVisualizer メニューのショートカット メニュー")

*Natvis*ファイルで定義されている各型は、表示可能な UI ビジュアライザーを明示的に一覧表示する必要があります。 デバッガーは、型エントリ内のビジュアライザー参照と、登録されているビジュアライザーを照合します。 たとえば、`std::vector` の次の型エントリは、前の例の `UIVisualizer` を参照します。

```xml
<Type Name="std::vector&lt;int,*&gt;">
  <UIVisualizer ServiceId="{5452AFEA-3DF6-46BB-9177-C0B08F318025}" Id="1" />
</Type>
```

 メモリ内のビットマップを表示するために使用する[イメージウォッチ](https://marketplace.visualstudio.com/items?itemName=VisualCPPTeam.ImageWatch2017)拡張機能の `UIVisualizer` の例を確認できます。

### <a name="BKMK_CustomVisualizer"></a>CustomVisualizer 要素
 `CustomVisualizer` は、Visual Studio code で視覚エフェクトを制御するために記述する VSIX 拡張機能を指定する機能拡張ポイントです。 VSIX 拡張機能の記述の詳細については、「 [Visual STUDIO SDK](../extensibility/visual-studio-sdk.md)」を参照してください。

XML Natvis 定義とは異なり、カスタムビジュアライザーを記述するには多くの作業が必要ですが、Natvis がサポートしている内容やサポートされていない機能についての制約があります。 カスタムビジュアライザーは、デバッガーの機能拡張 Api の完全なセットにアクセスできます。この Api は、デバッグ対象のプロセスに対してクエリや変更を行ったり、Visual Studio の他の部分と通信したりすることができます。

 `CustomVisualizer` 要素の `Condition`、`IncludeView`、および `ExcludeView` 属性を使用できます。