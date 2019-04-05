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
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2019
ms.locfileid: "55955675"
---
# <a name="vs-shell-deployment"></a>VS Shell 配置

分離のシェルでは、Visual Studio を確認できます。 機能、ドメイン固有言語およびそのソリューションを表示する方法と対話する必要があります。 Visual Studio 分離シェルの詳細については、[分離シェルのカスタマイズ](https://vspartner.com/pages/vsshells)を参照してください。

Visual Studio Shell は、デプロイ ターゲットとして設定します。

1. **DslPackage**プロジェクトを開き、 **source.extension.tt**します。

2. `<SupportedProducts>`を挿入します。

   ```xml
   <IsolatedShell Version="1.0">MyIsolatedShell</IsolatedShell>
   ```

   置換*MyIsolatedShell*分離シェルのパッケージの名前に置き換えます。