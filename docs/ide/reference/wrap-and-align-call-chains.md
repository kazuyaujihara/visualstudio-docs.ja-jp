---
title: 呼び出しチェーンのラップおよび配置
description: メソッド呼び出しのチェーンをラップし、配置する方法について説明します。
ms.date: 08/13/2019
ms.topic: reference
author: mikadumont
ms.author: midumont
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: 2a5b6bea4c915e029ca3ae448444decce0d7b041
ms.sourcegitcommit: b83fefa8177c5554cbe2c59c4d102cbc534f7cc6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69620014"
---
# <a name="wrap-and-align-call-chains"></a>呼び出しチェーンのラップおよび配置

このリファクタリングは以下に適用されます。

- C#

**概要:** メソッド呼び出しのチェーンをラップし、配置できます。

**条件:** 1 つのステートメントにある複数のメソッド呼び出しで構成される長いチェーンがあること。

**理由:** ユーザー設定に従ってラップまたはインデントされていると、長い一覧に目を通すときに便利です。

## <a name="how-to"></a>方法

1. 任意の呼び出しチェーンにカーソルを置きます。
2. 行の任意の場所で **Ctrl**+ **.** キーを押すと、 **[クイック アクションとリファクタリング]** メニューをトリガーします。
3. **[呼び出しチェーンのラップ]** または **[呼び出しチェーンのラップおよび配置]** を選択し、リファクタリングを受け入れます。

   ![呼び出しチェーンのラップおよび配置](media/wrap-call-chain.png)

## <a name="see-also"></a>関連項目

- [リファクタリング](../refactoring-in-visual-studio.md)
