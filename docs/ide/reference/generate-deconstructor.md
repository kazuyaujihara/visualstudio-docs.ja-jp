---
title: デコンストラクターのクイック アクションを生成する
ms.date: 02/19/2019
ms.topic: reference
author: kendrahavens
ms.author: kendrahavens
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: a609b16e0d1bc7e30dc26ef047228a6cacdb46b2
ms.sourcegitcommit: 11337745c1aaef450fd33e150664656d45fe5bc5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57324737"
---
# <a name="generate-a-deconstructor-in-visual-studio"></a>Visual Studio でデコンストラクターを生成する

このコード生成は以下に適用されます。

- C#

**概要:** 新しいデコンストラクターのメソッド スタブをすぐに生成できます。

**条件:** 型を自動的に正しく分解します。

**理由:** デコンストラクターの型を手動で指定できます。ただし、この機能では、正しい out パラメーターと共にスタブが生成されます。

## <a name="generate-deconstructor"></a>デコンストラクターの生成

1. out パラメーターを指定し、新しい型を宣言します。 この宣言により、宣言に一致するデコンストラクト インスタンスが見つからないとき、エラーが表示されます。

   ![デコンストラクター不足エラー](media/deconstruct.png)

2. 次に、以下のいずれかを実行します。

   - **キーボード**
      - 宣言にカーソルを置き、**Ctrl**+ **を押します。** **[クイック アクションとリファクタリング]** メニューをトリガーします。
   - **マウス**
      - 右クリックして **[クイック アクションとリファクタリング]** メニューを選択します。
      - テキスト カーソルが既に赤い波線の行にある場合は、左余白に表示されている ![ねじ回し](media/screwdriver.png) アイコンをクリックします。

      ![デコンストラクターのコード修正の生成](media/deconstruct-codefix.png)

3. **[Generate method 'MyInternalClass.Deconstruct']\(メソッド 'MyInternalClass.Deconstruct' の生成\)** を選択し、デコンストラクターを生成します。

   ![結果的に生成されるデコンストラクター コード](media/deconstruct-result.png)


## <a name="see-also"></a>関連項目

- [コード生成](../code-generation-in-visual-studio.md)
- [変更のプレビュー](../../ide/preview-changes.md)
- [.NET 開発者向けのヒント](../../ide/visual-studio-2017-for-dotnet-developers.md)