---
title: T4 CleanUpBehavior ディレクティブ
ms.date: 11/04/2016
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 27df15c0b935ff4bae497940c095dba1598bc4c1
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62964106"
---
# <a name="t4-cleanupbehavior-directive"></a>T4 CleanUpBehavior ディレクティブ

テキスト テンプレートを処理した後、appDomain を削除するには、次の行を含めます。

```
<#@ CleanupBehavior processor="T4VSHost" CleanupAfterProcessingtemplate="true" #>
```

テキスト テンプレートは、ホスト プロセスから分離した appDomain で処理されます。 ほとんどの場合、1 つのテキスト テンプレートが処理されると、次のテンプレートを処理するために appdomain が再度使用されます。 ただし、CleanupBehavior を指定した場合、appDomain は削除され、新しい appDomain で次のテンプレートが処理されます。

これによってテキスト処理は遅くなりますが、リソースが破棄されたことを確認するうえで役立ちます。

このディレクティブは、Visual Studio ホストでのみ動作します。