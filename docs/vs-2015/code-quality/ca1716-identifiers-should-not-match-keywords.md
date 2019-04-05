---
title: CA1716:識別子はキーワードと |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- IdentifiersShouldNotMatchKeywords
- CA1716
helpviewer_keywords:
- IdentifiersShouldNotMatchKeywords
- CA1716
ms.assetid: 900cc8a1-1089-4069-a4ce-10b109ac4fab
caps.latest.revision: 23
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 35a97e62e17895cb700a1420c7851878f329112a
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58973510"
---
# <a name="ca1716-identifiers-should-not-match-keywords"></a>CA1716:識別子はキーワードと同一にすることはできません
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|IdentifiersShouldNotMatchKeywords|
|CheckId|CA1716|
|Category|Microsoft.Naming|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
 名前空間、型、または viritual またはインターフェイス メンバーの名前では、プログラミング言語で予約済みキーワードと一致します。

## <a name="rule-description"></a>規則の説明
 識別子の名前空間、型、および仮想インターフェイス メンバーを共通言語ランタイムを対象とする言語で定義されているキーワードと一致する必要があります。 によって使用される言語とキーワードの場合は、コンパイラのエラーやあいまいさづらくなる可能性、ライブラリを使用します。

 このルールは、次の言語のキーワードを確認します。

- Visual Basic

- C#

- C++/CLI

  大文字と小文字が使用される[!INCLUDE[vbprvb](../includes/vbprvb-md.md)]他の言語キーワード、および大文字小文字の比較を使用します。

## <a name="how-to-fix-violations"></a>違反の修正方法
 キーワードの一覧に表示されていない名前を選択します。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 このルールから警告を抑制するには、識別子は、API のユーザーを混同しないでことと、ライブラリが使用可能なすべての言語で使用できることと確信している場合、[!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]します。
