---
title: '方法: ソリューション内の複数のプロジェクトに対してマネージ コード規則セットの指定 |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.propertypages.solution
ms.assetid: 92dc3250-a010-4396-b515-f03a0b30cd2a
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 555f8cb0ace4386a3fba7730980295dc16e58b2a
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63426668"
---
# <a name="how-to-specify-managed-code-rule-sets-for-multiple-projects-in-a-solution"></a>方法: ソリューション内の複数のプロジェクトに対してマネージ コード規則セットを指定します。
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

既定で、Microsoft 最小推奨規則のコード分析がこのソリューションのすべてのマネージ プロジェクトに割り当てられている*ルール セット*します。 ソリューションのプロパティ ダイアログ ボックスで、ソリューションのプロジェクトに割り当てられる規則セットを変更できます。  
  
> [!NOTE]
> 既定では、プロジェクトのコード分析はビルド ステップとして実行されません。 ビルドのステップとして、コード分析を有効にするのを参照してください。[方法。マネージ コード プロジェクトのコード分析を構成する](../code-quality/how-to-configure-code-analysis-for-a-managed-code-project.md)します。  
  
### <a name="to-specify-a-rule-set-for-multiple-projects-in-a-managed-code--solution"></a>マネージド コード ソリューション内の複数のプロジェクトに対して規則セットを指定するには  
  
1. [!INCLUDE[vsPreLong](../includes/vsprelong-md.md)]、 [!INCLUDE[vsUltLong](../includes/vsultlong-md.md)]、または [!INCLUDE[vsPro](../includes/vspro-md.md)] で、ソリューションを開きます。  
  
2. **分析** メニューのをクリックして**ソリューションのコード分析を構成する**します。  
  
3. 必要に応じて、展開**共通プロパティ**、 をクリックし、**コード分析設定**します。  
  
4. 1 つ以上のプロジェクトに対して規則セットを指定できます。  
  
    - 個々のプロジェクトに対して規則セットを指定するには、プロジェクト名をクリックします。  
  
    - 複数のプロジェクトに対して規則セットを指定するには、Ctrl キーを押しながらプロジェクト名をクリックします。  
  
    - ソリューションに含まれるすべてのプロジェクトを指定するには、Shift キーを押しながらプロジェクトの一覧内をクリックします。  
  
5. をクリックして、**ルール セットの**フィールドのプロジェクトと、規則の名前の設定を適用する をクリックします。
