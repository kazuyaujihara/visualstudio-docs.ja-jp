---
author: dotpaul
ms.author: paulming
ms.date: 04/05/2019
ms.topic: include
ms.openlocfilehash: 43327901b2233b9b2818296f9269975d8524438b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62541567"
---
安全でないデシリアライザーは、信頼されていないデータを逆シリアル化時に脆弱です。 攻撃者は悪意のある副作用のある予期しない型を含めるためのシリアル化されたデータを変更できます。 安全ではないデシリアライザーに対する攻撃など、基になるオペレーティング システムに対してコマンドを実行、ネットワーク経由で通信したりできますファイルを削除します。