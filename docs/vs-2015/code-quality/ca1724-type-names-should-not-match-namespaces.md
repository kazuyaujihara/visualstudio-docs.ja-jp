---
title: 'CA1724: 型名を名前空間と一致させることはできません |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- TypeNamesShouldNotMatchNamespaces
- CA1724
helpviewer_keywords:
- TypeNamesShouldNotMatchNamespaces
- CA1724
ms.assetid: 329af3b5-5600-4101-831d-531ab3eb7060
caps.latest.revision: 19
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 53c99e34bf253b0962d054685ce637c3849a2857
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72671596"
---
# <a name="ca1724-type-names-should-not-match-namespaces"></a>CA1724: 型名は名前空間と同一にすることはできません
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|TypeNamesShouldNotMatchNamespaces|
|CheckId|CA1724|
|カテゴリ|Microsoft.Naming|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
 大文字と小文字を区別しない比較では、型名が [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] 名前空間名と一致します。

## <a name="rule-description"></a>規則の説明
 型の名前は、[!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] クラス ライブラリで定義されている名前空間の名前と一致しないようにする必要があります。 この規則に違反すると、ライブラリが使いづらくなります。

## <a name="how-to-fix-violations"></a>違反の修正方法
 @No__t_0 クラスライブラリの名前空間の名前と一致しない型名を選択してください。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 新しい開発では、このルールの警告を抑制する必要がある既知のシナリオはありません。 警告を抑制する前に、ライブラリのユーザーと一致する名前が混同されているかどうかを慎重に検討してください。 配布ライブラリの場合、このルールからの警告を抑制することが必要になる場合があります。
