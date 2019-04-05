---
title: CA1725:パラメーター名は基本宣言と一致する必要があります |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- ParameterNamesShouldMatchBaseDeclaration
- CA1725
helpviewer_keywords:
- CA1725
- ParameterNamesShouldMatchBaseDeclaration
ms.assetid: 9b657ab0-fe81-4f4c-9481-ba746988c922
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: e97431b46640fb8241d6bde80d09d38084650be8
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58977223"
---
# <a name="ca1725-parameter-names-should-match-base-declaration"></a>CA1725:パラメーター名は基本宣言と同一でなければなりません
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|ParameterNamesShouldMatchBaseDeclaration|
|CheckId|CA1725|
|Category|Microsoft.Naming|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
 外部から参照できるメソッド オーバーライドでのパラメーターの名前は、メソッドの基本宣言またはメソッドのインターフェイス宣言のパラメーターの名前のパラメーターの名前と一致しません。

## <a name="rule-description"></a>規則の説明
 オーバーライド階層のパラメーターに対する一貫性のある名前付けによって、メソッド オーバーライドの有用性が高まります。 派生メソッドのパラメーター名が基本宣言のパラメーター名と異なる場合、メソッドが基本メソッドのオーバーライドであるか、またはメソッドの新しいオーバーライドであるかについて混乱が生じる可能性があります。

## <a name="how-to-fix-violations"></a>違反の修正方法
 このルールの違反を修正するには、基本宣言と一致するパラメーターの名前を変更します。 修正プログラムは、COM 参照可能なメソッドの互換性に影響する変更です。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 以前に出荷されたライブラリ内の COM 参照可能なメソッドを除き、この規則による警告を抑制しないでください。
