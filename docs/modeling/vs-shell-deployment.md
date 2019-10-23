---
title: VS Shell 配置
ms.date: 11/04/2016
ms.topic: conceptual
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0e010d2efd8174f2c61d7c97eb63d585f47812ff
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72663656"
---
# <a name="vs-shell-deployment"></a>VS Shell 配置

分離シェルを使用すると、ドメイン固有言語と対話するために必要な Visual Studio の機能と、そのソリューションをどのように表示するかを決定できます。 Visual Studio の分離シェルの詳細については、「[分離シェルのカスタマイズ](https://vspartner.com/pages/vsshells)」を参照してください。

Visual Studio シェルを配置ターゲットとして設定するには、次のようにします。

1. **Dslpackage**プロジェクトで、 **source.extension.tt**を開きます。

2. @No__t_0 挿入:

   ```xml
   <IsolatedShell Version="1.0">MyIsolatedShell</IsolatedShell>
   ```

   *MyIsolatedShell*を分離シェルパッケージの名前に置き換えます。