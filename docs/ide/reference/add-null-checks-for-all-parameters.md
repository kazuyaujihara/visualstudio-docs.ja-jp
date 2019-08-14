---
title: すべて (パラメーター) に対して null チェックを追加する
ms.date: 07/24/2019
ms.topic: reference
author: stcahlon
ms.author: t-shzach
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: da3a616844dbe914cfe796ec35d1501bf83dd1ef
ms.sourcegitcommit: 3e74ec49a54e5c3da7631f4466128cdf4384af6b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2019
ms.locfileid: "68712734"
---
# <a name="add-null-checks-for-all-parameters"></a>すべてのパラメーターに対して null チェックを追加する 

このリファクタリングは以下に適用されます。 

- C# 

**概要:** null 許容のチェックのないパラメーターがすべて無効であることを確認する `if` ステートメントを作成して追加します。 

**条件:** すべての適用可能なメソッド パラメーターに対して null チェックをすばやく追加する必要があります。

**理由:** 多くのパラメーターに対して null チェックを記述することは、時間がかかり、反復的になることがあります。 このリファクタリングを使用すると、簡単でプログラムがより堅牢になります。  

## <a name="how-to"></a>方法 

1. メソッド内の任意のパラメーターにカーソルを置きます。

2. 行の任意の場所で **Ctrl**+ **.** キーを押すと、 **[クイック アクションとリファクタリング]** メニューをトリガーします。

   ![クイック アクションとリファクタリング](media/add-null-checks-for-all-parameters.png)
   
3. **[Add null checks for all parameters]\(すべてのパラメーターに対して null チェックを追加する\)** オプションを選択します。

   ![すべてに対して null チェックを追加する](media/add-null-checks-for-all.png) 

## <a name="see-also"></a>関連項目 

- [リファクタリング](../refactoring-in-visual-studio.md) 
