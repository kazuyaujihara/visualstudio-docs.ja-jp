---
title: パラメーターの順序変更C#リファクタリング () |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- vs.csharp.refactoring.reorder
dev_langs:
- CSharp
helpviewer_keywords:
- refactoring [C#], Reorder Parameters
- Reorder Parameters refactoring [C#]
ms.assetid: 4dabf21a-a9f0-41e9-b11b-55760cf2bd90
caps.latest.revision: 26
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: e39564fb108b63859620e2c4a650608cdf1e7e82
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72673140"
---
# <a name="reorder-parameters-refactoring-c"></a>パラメーター順序の再変更リファクタリング (C#)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

`Reorder Parameters` は、メソッドC# 、インデクサー、およびデリゲートのパラメーターの順序を簡単に変更できる視覚的なリファクタリング操作です。 `Reorder Parameters` は、宣言を変更し、メンバーが呼び出される任意の場所で、新しい順序を反映するようにパラメーターを再配置します。

 @No__t_0 操作を実行するには、メソッド、インデクサー、またはデリゲートの上または次にカーソルを置きます。 カーソルが位置にあるときに、キーボードショートカットを押すか、ショートカットメニューのコマンドをクリックして、`Reorder Parameters` 操作を呼び出します。

> [!NOTE]
> 拡張メソッドの最初のパラメーターの順序を変更することはできません。

### <a name="to-reorder-parameters"></a>パラメーターの順序を変更するには

1. @No__t_0 という名前のクラスライブラリを作成し、`Class1` を次のコード例に置き換えます。

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

3. **[リファクター]** メニューの **[パラメーターの並べ替え]** をクリックします。

     [**パラメーターの順序**の変更] ダイアログボックスが表示されます。

4. **[パラメーターの順序]** の変更 ダイアログボックスで、 **[パラメーター]** ボックスの一覧の `int i` を選択し、下矢印ボタンをクリックします。

     または、 **[パラメーター]** ボックスの `bool b` の後に `int i` ドラッグすることもできます。

5. [**パラメーターの順序**の変更] ダイアログボックスで、[ **OK]** をクリックします。

     **[パラメーターの並べ替え]** ダイアログボックスで 参照の **[変更のプレビュー]** オプションが選択されている場合は、 **[変更のプレビュー-パラメーターの並べ替え]** ダイアログボックスが表示されます。 シグネチャとメソッドの呼び出しの両方で `MethodB` のパラメーターリストの変更のプレビューを提供します。

    1. **[変更のプレビュー-パラメーターの並べ替え]** ダイアログボックスが表示されたら、 **[適用]** をクリックします。

         この例では、メソッドの宣言と `MethodB` のすべてのメソッド呼び出しサイトが更新されます。

## <a name="remarks"></a>Remarks
 パラメーターの順序を変更するには、メソッドの宣言またはメソッドの呼び出しを使用します。 メソッドまたはデリゲート宣言の上または上にカーソルを置き、本文には配置しません。

## <a name="see-also"></a>参照
 [リファクタリング (C#)](../csharp-ide/refactoring-csharp.md)