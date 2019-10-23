---
title: コード分析を用いたチェックイン ポリシーに関するバージョンの互換性
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- version compatibility, code analysis check-in policy
- check-in policies, version compatibility for code analysis
ms.assetid: 1af376e3-3be7-4445-803b-76a858567a5b
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8385e2b36d09f029c4b8625e58cd99ecc06ea226
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72649023"
---
# <a name="version-compatibility-for-code-analysis-check-in-policies"></a>コード分析を用いたチェックイン ポリシーに関するバージョンの互換性

さまざまなバージョンの [!INCLUDE[esprtfc](../code-quality/includes/esprtfc_md.md)] を使用してコード分析チェックインポリシーを評価して作成する必要がある場合は、[!INCLUDE[vstsTfsOrcasLong](../code-quality/includes/vststfsorcaslong_md.md)] と [!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)] チェックインポリシーの評価方法の違いを把握しておく必要があります。

## <a name="version-compatibility-for-evaluating-check-in-policies"></a>チェックインポリシーを評価するためのバージョンの互換性

- コード分析のチェックインポリシーが [!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)] で評価される場合、[!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)] に存在していても [!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)] に存在しないすべての規則は無視されます。

- コード分析のチェックインポリシーが [!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)] で評価されると、[!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)] に限定されたすべての新しい規則は無視されます。

- コード分析のチェックインポリシーで規則アセンブリが指定されている場合、[!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)] は、認識されないアセンブリによって指定されたすべての規則を無視します。

- コード分析のチェックインポリシーで [!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)] が認識しない規則アセンブリが指定されている場合は、メッセージが表示されます。

## <a name="version-compatibility-for-authoring-check-in-policies"></a>チェックインポリシーを作成するためのバージョンの互換性

- @No__t_0 バージョンの [!INCLUDE[esprtfc](../code-quality/includes/esprtfc_md.md)] を使用してコード分析チェックインポリシーを作成した場合は、[!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)] バージョンの [!INCLUDE[esprtfc](../code-quality/includes/esprtfc_md.md)] を使用して変更することはできません。 また、[!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)] はポリシーを評価できません。

- @No__t_1 で [!INCLUDE[esprtfc](../code-quality/includes/esprtfc_md.md)] を使用してコード分析のチェックインポリシーを作成した場合は、[!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)] で [!INCLUDE[esprtfc](../code-quality/includes/esprtfc_md.md)] を使用して変更することができ、ポリシーは [!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)] で評価することもできます。 @No__t_1 で [!INCLUDE[esprtfc](../code-quality/includes/esprtfc_md.md)] を使用してポリシーを変更した後、[!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)] で [!INCLUDE[esprtfc](../code-quality/includes/esprtfc_md.md)] を使用してポリシーを編集することはできなくなりました。 [!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)] は、厳密な名前が一致しないと、ポリシーを評価できます。

- @No__t_0 と [!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)] の両方に適用されるルール設定を使用してコード分析のチェックインポリシーを作成するには [!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)] でポリシーを作成し、すべての変更を行い、ポリシーを保存する必要があります。 ルールに対する変更が [!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)] にのみ存在する場合は、[!INCLUDE[vstsTfsOrcasShort](../code-quality/includes/vststfsorcasshort_md.md)] でポリシーを変更して保存します。

   @No__t_0 にポリシーを保存すると、[!INCLUDE[vstsTfsRosarioShort](../code-quality/includes/vststfsrosarioshort_md.md)] にのみ存在する規則の設定を変更できなくなります。
