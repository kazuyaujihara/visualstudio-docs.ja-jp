---
author: dotpaul
ms.author: paulming
ms.date: 04/05/2019
ms.topic: include
ms.openlocfilehash: 054198eff46c0983a5610b29dee5e29e5ac67a70
ms.sourcegitcommit: b468d71052a1b8a697f477ab23a3644de139f1e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2019
ms.locfileid: "67254186"
---
安全でないデシリアライザーは、信頼されていないデータを逆シリアル化時に脆弱です。 攻撃者は悪意のある副作用のあるオブジェクトを挿入する予期しない型を含めるためのシリアル化されたデータを変更できます。 安全ではないデシリアライザーに対する攻撃など、基になるオペレーティング システムに対してコマンドを実行、ネットワーク経由で通信したりできますファイルを削除します。