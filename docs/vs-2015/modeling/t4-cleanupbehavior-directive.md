---
title: T4 CleanUpBehavior ディレクティブ |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
ms.assetid: 9e5a211f-a3bf-4229-bff0-7d2e45b71c64
caps.latest.revision: 4
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: f964f37b347d588b1f7e590d918018c50e9f41c0
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68199832"
---
# <a name="t4-cleanupbehavior-directive"></a>T4 CleanUpBehavior ディレクティブ
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

テキスト テンプレートを処理した後、appDomain を削除するには、次の行を含めます。  
  
```  
<#@ CleanupBehavior processor="T4VSHost" CleanupAfterProcessingtemplate="true" #>  
```  
  
 テキスト テンプレートは、ホスト プロセスから分離した appDomain で処理されます。 ほとんどの場合、1 つのテキスト テンプレートが処理されると、次のテンプレートを処理するために appdomain が再度使用されます。 ただし、CleanupBehavior を指定した場合、appDomain は削除され、新しい appDomain で次のテンプレートが処理されます。  
  
 これによってテキスト処理は遅くなりますが、リソースが破棄されたことを確認するうえで役立ちます。  
  
 このディレクティブは、Visual Studio ホストでのみ動作します。
