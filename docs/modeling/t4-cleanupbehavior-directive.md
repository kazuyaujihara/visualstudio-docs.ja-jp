---
title: T4 CleanUpBehavior ディレクティブ
ms.date: 11/04/2016
ms.topic: reference
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: da296be872daa89d2759566020452fab4951d3b8
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72606497"
---
# <a name="t4-cleanupbehavior-directive"></a>T4 CleanUpBehavior ディレクティブ

テキスト テンプレートを処理した後、appDomain を削除するには、次の行を含めます。

```
<#@ CleanupBehavior processor="T4VSHost" CleanupAfterProcessingtemplate="true" #>
```

テキスト テンプレートは、ホスト プロセスから分離した appDomain で処理されます。 ほとんどの場合、1 つのテキスト テンプレートが処理されると、次のテンプレートを処理するために appdomain が再度使用されます。 ただし、CleanupBehavior を指定した場合、appDomain は削除され、新しい appDomain で次のテンプレートが処理されます。

これによってテキスト処理は遅くなりますが、リソースが破棄されたことを確認するうえで役立ちます。

このディレクティブは、Visual Studio ホストでのみ動作します。