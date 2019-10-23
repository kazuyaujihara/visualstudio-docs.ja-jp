---
title: 名前の変更C#リファクタリング () |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- vs.csharp.refactoring.rename
dev_langs:
- CSharp
helpviewer_keywords:
- refactoring [C#], Rename
- Rename refactoring [C#]
ms.assetid: 268942fc-b142-4dfa-8d90-bedd548c2e4f
caps.latest.revision: 45
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 0db7696268e5e3d24d005fbf35a08b330f2dc849
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72667479"
---
# <a name="rename-refactoring-c"></a>名前の変更リファクタリング (C#)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

**名前の変更**は、Visual Studio 統合開発環境 (IDE: integrated development environment) のリファクタリング機能であり、フィールド、ローカル変数、メソッド、名前空間、プロパティ、型などのコードシンボルの識別子の名前を変更するための簡単な方法を提供します。 **名前**変更を使用すると、コメントや文字列内の名前を変更したり、識別子の宣言と呼び出しを変更したりできます。

> [!NOTE]
> Visual Studio のソース管理を使用する場合は、名前の変更のリファクタリングを実行する前に、ソースの最新バージョンを取得してください。

 名前の変更リファクタリングは、次の Visual Studio の機能から使用できます。

|特性|IDE でのリファクタリングの動作|
|-------------|----------------------------------------|
|コード エディター|コードエディターでは、特定の種類のコードシンボルにカーソルを置いたときに、名前の変更リファクタリングを使用できます。 カーソルがこの位置にある場合は、ショートカットキー (CTRL + R、CTRL + R) を入力するか、スマートタグ、ショートカットメニュー、または **[リファクター]** メニューから **[名前の変更]** コマンドを選択することによって、 **[名前の変更]** コマンドを呼び出すことができます。|
|クラス ビュー|クラスビューで識別子を選択すると、ショートカットメニューおよび **[リファクター]** メニューから [リファクタリングの名前変更] を使用できるようになります。|
|オブジェクト ブラウザー|オブジェクトブラウザーで識別子を選択した場合、リファクタリングは **[リファクター]** メニューからのみ使用できます。|
|Windows フォームデザイナーのプロパティグリッド|Windows フォームデザイナーの**プロパティグリッド**で、コントロールの名前を変更すると、そのコントロールの名前変更操作が開始されます。 **[名前の変更]** ダイアログボックスは表示されません。|
|ソリューション エクスプローラー|**ソリューションエクスプローラー**では、ショートカットメニューの **[名前の変更]** コマンドを使用できます。 選択したソースファイルに、クラス名がファイル名と同じクラスが含まれている場合は、このコマンドを使用して、ソースファイルの名前を同時に変更し、名前変更のリファクタリングを実行できます。<br /><br /> たとえば、既定の Windows ベースのアプリケーションを作成し、Form1.cs の名前を TestForm.cs に変更した場合、ソースファイル名 Form1.cs は TestForm.cs に変更され、そのクラスへのすべての参照は TestForm に名前が変更されます。 **注:** **元**に戻すコマンド (CTRL + Z) は、コード内のリファクタリングの名前変更のみを元に戻します。ファイル名は元の名前に変更されません。 <br /><br /> 選択したソースファイルに、ファイル名と同じ名前のクラスが含まれていない場合、**ソリューションエクスプローラー**の **[名前の変更]** コマンドではソースファイルの名前のみが変更され、名前変更のリファクタリングは実行されません。|

## <a name="rename-operations"></a>名前の変更操作
 **名前の変更**を実行すると、リファクタリングエンジンは、次の表に示すように、コードシンボルごとに固有の名前変更操作を実行します。

|コードシンボル|名前の変更操作|
|-----------------|----------------------|
|フィールド|フィールドの宣言と使用法を新しい名前に変更します。|
|ローカル変数|変数の宣言と使用法を新しい名前に変更します。|
|メソッド|メソッドの名前とそのメソッドへのすべての参照を新しい名前に変更します。 **注:** 拡張メソッドの名前を変更すると、名前の変更操作は、拡張メソッドが静的メソッドとインスタンスメソッドのどちらとして使用されているかに関係なく、スコープ内のメソッドのすべてのインスタンスに反映されます。 詳細については、「[拡張メソッド](https://msdn.microsoft.com/library/175ce3ff-9bbf-4e64-8421-faeb81a0bb51)」を参照してください。|
|Namespace|名前空間の名前を、宣言内の新しい名前、すべての `using` ステートメント、および完全修飾名に変更します。 **注:** 名前空間の名前を変更すると、[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]**プロジェクトデザイナー**の **[アプリケーション]** ページの "**既定の名前空間**" プロパティも更新されます。 このプロパティは、 **[編集]** メニューの **[元に戻す]** を選択してリセットすることはできません。 **既定の名前空間**プロパティの値をリセットするには、**プロジェクトデザイナー**でプロパティを変更する必要があります。 詳細については、「[アプリケーションページ](../ide/reference/application-page-project-designer-csharp.md)」を参照してください。|
|property|プロパティの宣言と使用法を新しい名前に変更します。|
|[種類]|コンストラクターとデストラクターを含む、すべての宣言および型のすべての使用法を新しい名前に変更します。 部分型の場合、名前の変更操作はすべての部分に反映されます。|

#### <a name="to-rename-an-identifier"></a>識別子の名前を変更するには

1. `RenameIdentifier` という名前のコンソール アプリケーションを作成し、`Program` を次のコード例で置き換えます。

    ```csharp
    class ProtoClassA
    {
        // Invoke on 'MethodB'.
        public void MethodB(int i, bool b) { }
    }

    class ProtoClassC
    {
        void D()
        {
            ProtoClassA MyClassA = new ProtoClassA();

            // Invoke on 'MethodB'.
            MyClassA.MethodB(0, false);
        }
    }
    ```

2. メソッド宣言またはメソッド呼び出しのいずれかで、`MethodB` にカーソルを置きます。

3. **[リファクター]** メニューの **[名前の変更]** をクリックします。 **[名前の変更]** ダイアログボックスが表示されます。

     また、カーソルを右クリックし、コンテキストメニューの **[リファクター]** をポイントし、 **[名前の変更]** をクリックして 名前の **[変更]** ダイアログボックスを表示することもできます。

4. **[新しい名前]** フィールドに、「`MethodC`」と入力します。

5. **[コメント内の検索]** チェックボックスをオンにします。

6. **[OK]** をクリックします。

7. **[変更のプレビュー]** ダイアログボックスで、 **[適用]** をクリックします。

#### <a name="to-rename-an-identifier-using-smart-tags"></a>スマートタグを使用して識別子の名前を変更するには

1. `RenameIdentifier` という名前のコンソール アプリケーションを作成し、`Program` を次のコード例で置き換えます。

    ```csharp
    class ProtoClassA
    {
        // Invoke on 'MethodB'.
        public void MethodB(int i, bool b) { }
    }

    class ProtoClassC
    {
        void D()
        {
            ProtoClassA MyClassA = new ProtoClassA();

            // Invoke on 'MethodB'.
            MyClassA.MethodB(0, false);
        }
    }
    ```

2. @No__t_0 の宣言で、メソッド識別子の上に「」または「backspace」と入力します。 スマートタグプロンプトがこの識別子の下に表示されます。

    > [!NOTE]
    > 識別子の宣言では、スマートタグを使用した名前変更のリファクタリングのみを呼び出すことができます。

3. キーボードショートカット SHIFT + ALT + F10 を入力し、下矢印を押してスマートタグメニューを表示します。

     -または-

     スマートタグを表示するには、スマートタグプロンプトの上にマウスポインターを移動します。 次に、スマートタグの上にマウスポインターを移動し、下矢印をクリックしてスマートタグメニューを表示します。

4. ' **@No__t_1identifer1 > ' を ' \<identifier2 > ' に**変更するメニュー項目を選択して、コードの変更をプレビューせずに、名前変更のリファクタリングを呼び出します。 **@No__t_1identifer1 >** へのすべての参照は、 **> \<identifier2**に自動的に更新されます。

     -または-

     [**プレビューによる名前**の変更] メニュー項目を選択して、コードへの変更のプレビューを使用して名前変更のリファクタリングを呼び出します。 **[変更のプレビュー]** ダイアログボックスが表示されます。

## <a name="remarks"></a>Remarks

## <a name="renaming-implemented-or-overridden-members"></a>実装またはオーバーライドされたメンバーの名前変更
 を実装/オーバーライドするか、他の型のメンバーによって実装またはオーバーライドされるメンバーの**名前を変更**すると、[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] によって、名前変更操作によって連鎖更新が発生するというダイアログボックスが表示されます。 **[続行]** をクリックすると、リファクタリングエンジンは、名前を変更されたメンバーと実装/オーバーライド関係がある基本型と派生型のすべてのメンバーを再帰的に検索し、名前を変更します。

 次のコード例には、実装/オーバーライドのリレーションシップを持つメンバーが含まれています。

 [!code-csharp[CsUsingCsIDERefactor#1](../snippets/csharp/VS_Snippets_VBCSharp/CsUsingCsIDERefactor/CS/Class1.cs#1)]

 前の例では、`C.Method()` が `Ibase.Method()` を実装するため、`C.Method()` の名前を変更しても `Ibase.Method()` の名前が変更されます。 次に、リファクターエンジンは、`Derived.Method()` によって実装された `Ibase.Method()` が `Derived.Method()` 名前を変更したことを再帰的に認識します。 リファクターエンジンでは、`Derived.Method()` が `Base.Method()` をオーバーライドしないため、`Base.Method()` の名前は変更されません。 **[名前]** の変更 ダイアログボックスで **[オーバーロードの名前の変更]** がオンになっていない場合、リファクタリングエンジンはここで停止します。

 **[オーバーロードの名前の変更]** チェックボックスをオンにすると、リファクタリングエンジンは、`Derived.Method()` をオーバーロードするので `Derived.Method(int i)` 名前 `Base.Method(int i)` を変更します。これは、`Derived.Method(int i)` によってオーバーライドされているために、`Base.Method()` のオーバーロードであるため `Base.Method(int i)` であるためです。

> [!NOTE]
> 参照アセンブリで定義されているメンバーの名前を変更すると、ダイアログボックスで、名前を変更するとビルドエラーが発生することが説明されます。

## <a name="renaming-properties-of-anonymous-types"></a>匿名型のプロパティの名前変更
 匿名型のプロパティの名前を変更すると、名前の変更操作は、同じプロパティを持つ他の匿名型のプロパティに反映されます。 次の例は、この動作を示しています。

```csharp
var a = new { ID = 1};
var b = new { ID = 2};
```

 前のコードでは、`ID` の名前を変更すると、基になる匿名型が同じであるため、両方のステートメントで `ID` が変更されます。

```csharp
var companyIDs =
    from c in companylist
    select new { ID = c.ID, Name = c.Name};

var orderIDs =
    from o in orderlist
    select new { ID = o.ID, Item = o.Name};
```

 前のコードでは、`ID` の名前を変更しても、`companyIDs` と `orderIDs` に同じプロパティがないため、`ID` のインスタンスは1つだけになります。

## <a name="see-also"></a>参照
 [リファクタリング (C#)](../csharp-ide/refactoring-csharp.md) [匿名型](https://msdn.microsoft.com/library/59c9d7a4-3b0e-475e-b620-0ab86c088e9b)