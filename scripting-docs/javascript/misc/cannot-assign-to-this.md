---
title: "'This' に割り当てることはできません |Microsoft Docs"
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT5000
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: ba2b0a2b-f0f8-4698-b335-a4ab6c166671
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4a4ba5d852a7d131a88930dd66931c026074549b
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "58149498"
---
# <a name="cannot-assign-to-this"></a>'this' に割り当てることはできません。
**this** に値を割り当てようとしました。 **this**は、[!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]キーワードのいずれかを参照します。

- 現在、メソッドを実行するオブジェクト

- 現在のメソッドはありません (または、メソッドが、他のオブジェクトに属していない) 場合は、グローバル オブジェクトです。

メソッドは、[!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]オブジェクトを介して呼び出される関数。 メソッド内で、**this**キーワードによって、メソッドが呼び出されたオブジェクトへの参照は、(クラスのコンス トラクターを呼び出すことによって作成されたオブジェクトである、**new**演算子)。

メソッド内では、**this** を使用して現在のオブジェクトを参照できますが、**this** に新しい値を割り当てることはできません。

## <a name="to-correct-this-error"></a>このエラーを解決するには

- **this**に割り当てないでください。 プロパティまたはオブジェクトのインスタンスのメソッドにアクセスするには、ドット演算子(例: **circle.radius**)を使用してます 。

  > [!NOTE]
  > ユーザーが作成した変数には**this**を指定することはできません。this; は、[!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]予約語。

## <a name="see-also"></a>関連項目

- [this ステートメント](../../javascript/reference/this-statement-javascript.md)
- [スクリプトのトラブルシューティング](../../javascript/advanced/troubleshooting-your-scripts-javascript.md)