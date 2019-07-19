---
title: DA0011:CompareTo の負荷が高くなっています | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.performance.DA0011
- vs.performance.rules.DAExpensiveCompareTo
- vs.performance.11
- vs.performance.rules.DA0011
ms.assetid: 239a381d-0d97-4367-8668-746c93f5af2c
caps.latest.revision: 12
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 86d41a2717eb3ef7bd49f8d34b85198a55e5101c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68158649"
---
# <a name="da0011-expensive-compareto"></a>DA0011:CompareTo の負荷が高くなっています
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Visual Studio の最新ドキュメントについては、次を参照してください[DA0011:。CompareTo の負荷が](https://docs.microsoft.com/visualstudio/profiling/da0011-expensive-compareto)します。  
  
|||  
|-|-|  
|規則 ID|DA0011|  
|Category|.NET Framework の使用|  
|プロファイル方法|サンプリング<br /><br /> .NET メモリ|  
|Message|CompareTo 関数の負荷を抑える必要があります。メモリを割り当てることはできません。 可能な場合は、CompareTo 関数の複雑さを軽減してください。|  
|規則の種類|警告|  
  
## <a name="cause"></a>原因  
 型の CompareTo メソッドが高コストであるか、またはメモリを割り当てています。  
  
## <a name="rule-description"></a>規則の説明  
 CompareTo メソッドは効率的にする必要があります。メモリを割り当てることはできません。  
  
## <a name="how-to-fix-violations"></a>違反の修正方法  
 CompareTo メソッドの複雑さを軽減してください。
