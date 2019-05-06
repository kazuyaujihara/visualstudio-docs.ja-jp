---
title: VS Shell 配置
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 70f39dd23851a2ebc0a48afd05da54b0d8deb24a
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62934301"
---
# <a name="vs-shell-deployment"></a>VS Shell 配置

分離のシェルでは、Visual Studio を確認できます。 機能、ドメイン固有言語およびそのソリューションを表示する方法と対話する必要があります。 Visual Studio 分離シェルの詳細については、次を参照してください。[分離シェルのカスタマイズ](https://vspartner.com/pages/vsshells)します。

Visual Studio Shell は、デプロイ ターゲットとして設定します。

1. **DslPackage**プロジェクトを開き、 **source.extension.tt**します。

2. `<SupportedProducts>`を挿入します。

   ```xml
   <IsolatedShell Version="1.0">MyIsolatedShell</IsolatedShell>
   ```

   置換*MyIsolatedShell*分離シェルのパッケージの名前に置き換えます。