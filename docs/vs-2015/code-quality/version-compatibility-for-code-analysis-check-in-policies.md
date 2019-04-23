---
title: コード分析チェックイン ポリシーのバージョンの互換性 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
helpviewer_keywords:
- version compatibility, code analysis check-in policy
- check-in policies, version compatibility for code analysis
ms.assetid: 1af376e3-3be7-4445-803b-76a858567a5b
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 0a63ead03baffaa0ce8047220ff1ce8a33c88be8
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "60082231"
---
# <a name="version-compatibility-for-code-analysis-check-in-policies"></a>コード分析を用いたチェックイン ポリシーに関するバージョンの互換性
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

評価およびコード分析チェックイン ポリシーの異なるバージョンを使用して作成する必要がある場合[!INCLUDE[esprtfc](../includes/esprtfc-md.md)]、方法の違いを理解する必要があります[!INCLUDE[vstsTfsOrcasLong](../includes/vststfsorcaslong-md.md)]と[!INCLUDE[vstsTfsRosarioShort](../includes/vststfsrosarioshort-md.md)]チェックイン ポリシーを評価します。  
  
## <a name="version-compatibility-for-evaluating-check-in-policies"></a>チェックイン ポリシーを評価するためのバージョンの互換性  
  
- コード分析チェックイン ポリシーが評価されるタイミング[!INCLUDE[vstsTfsOrcasShort](../includes/vststfsorcasshort-md.md)]、任意のルールに存在していた[!INCLUDE[vstsTfsRosarioShort](../includes/vststfsrosarioshort-md.md)]に存在しないが、[!INCLUDE[vstsTfsOrcasShort](../includes/vststfsorcasshort-md.md)]は無視されます。  
  
- コード分析チェックイン ポリシーが評価されるタイミング[!INCLUDE[vstsTfsRosarioShort](../includes/vststfsrosarioshort-md.md)]にのみ含まれているすべての新しいルール[!INCLUDE[vstsTfsOrcasShort](../includes/vststfsorcasshort-md.md)]は無視されます。  
  
- コード分析チェックイン ポリシー、規則アセンブリを指定する場合[!INCLUDE[vstsTfsOrcasShort](../includes/vststfsorcasshort-md.md)]では認識されないアセンブリで指定されているすべての規則は無視されます。  
  
- コード分析チェックイン ポリシーがルール アセンブリを指定するかどうかを[!INCLUDE[vstsTfsRosarioShort](../includes/vststfsrosarioshort-md.md)]認識しないメッセージが表示されます。  
  
## <a name="version-compatibility-for-authoring-check-in-policies"></a>チェックイン ポリシーを作成するためのバージョンの互換性  
  
- 使用して、コード分析チェックイン ポリシーを作成するかどうか、[!INCLUDE[vstsTfsOrcasShort](../includes/vststfsorcasshort-md.md)]バージョンの[!INCLUDE[esprtfc](../includes/esprtfc-md.md)]、使用することはできません、[!INCLUDE[vstsTfsRosarioShort](../includes/vststfsrosarioshort-md.md)]バージョンの[!INCLUDE[esprtfc](../includes/esprtfc-md.md)]を修正する方法。 また、[!INCLUDE[vstsTfsRosarioShort](../includes/vststfsrosarioshort-md.md)]ポリシーを評価することはできません。  
  
- 使用して、コード分析チェックイン ポリシーを作成するかどうかは[!INCLUDE[esprtfc](../includes/esprtfc-md.md)]で[!INCLUDE[vstsTfsRosarioShort](../includes/vststfsrosarioshort-md.md)]、使用することができます[!INCLUDE[esprtfc](../includes/esprtfc-md.md)]で[!INCLUDE[vstsTfsOrcasShort](../includes/vststfsorcasshort-md.md)]、およびポリシーを変更することができますもによって評価される[!INCLUDE[vstsTfsOrcasShort](../includes/vststfsorcasshort-md.md)]します。 使用して、ポリシーを変更した後[!INCLUDE[esprtfc](../includes/esprtfc-md.md)]で[!INCLUDE[vstsTfsOrcasShort](../includes/vststfsorcasshort-md.md)]を使用して、ポリシーを編集できなく[!INCLUDE[esprtfc](../includes/esprtfc-md.md)]で[!INCLUDE[vstsTfsRosarioShort](../includes/vststfsrosarioshort-md.md)]します。 [!INCLUDE[vstsTfsRosarioShort](../includes/vststfsrosarioshort-md.md)] 厳密な名前の不一致が問題なくポリシーを評価できます。  
  
- 両方に適用されるルールの設定でコード分析チェックイン ポリシーを作成する[!INCLUDE[vstsTfsRosarioShort](../includes/vststfsrosarioshort-md.md)]と[!INCLUDE[vstsTfsOrcasShort](../includes/vststfsorcasshort-md.md)]のポリシーを作成する必要があります[!INCLUDE[vstsTfsRosarioShort](../includes/vststfsrosarioshort-md.md)]、必要に応じて、すべての変更を行うし、ポリシーを保存します。 規則に対する変更にのみ存在する場合[!INCLUDE[vstsTfsOrcasShort](../includes/vststfsorcasshort-md.md)]、変更のポリシーを保存して[!INCLUDE[vstsTfsOrcasShort](../includes/vststfsorcasshort-md.md)]します。  
  
     後でポリシーを保存する[!INCLUDE[vstsTfsOrcasShort](../includes/vststfsorcasshort-md.md)]、内に存在する規則の設定を変更できなく[!INCLUDE[vstsTfsRosarioShort](../includes/vststfsrosarioshort-md.md)]のみです。
