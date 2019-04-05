---
title: CA1061:基底クラスのメソッドを隠ぺいしない |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1061
- DoNotHideBaseClassMethods
helpviewer_keywords:
- DoNotHideBaseClassMethods
- CA1061
ms.assetid: 0bda9dc8-87b4-4038-ab9d-563298387466
caps.latest.revision: 11
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: e932b2c948493c4703e8edd5edb37818e80f0253
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58975834"
---
# <a name="ca1061-do-not-hide-base-class-methods"></a>CA1061:基底クラス メソッドを非表示にしません
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|DoNotHideBaseClassMethods|
|CheckId|CA1061|
|カテゴリ|Microsoft.Design|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
 派生型は、基本メソッドのいずれかと同じ数のパラメーターと同じ名前のメソッドを宣言します。1 つまたは複数のパラメーターはベース メソッドの対応するパラメーターの基本型です。残りのパラメーターは、基本メソッドの対応するパラメーターと同じ型であります。

## <a name="rule-description"></a>規則の説明
 派生メソッドのパラメーター シグネチャより弱い派生基底メソッドのパラメーター シグネチャ内の対応する型よりも型のみが異なる場合に、派生型で同じ名前のメソッドで基本データ型のメソッドは表示されません。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則の違反を修正するには、削除、メソッドの名前を変更またはメソッドは基本メソッドを隠ぺいしないように、パラメーターのシグネチャを変更します。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 この規則による警告は抑制しないでください。

## <a name="example"></a>例
 次の例では、規則に違反するメソッドを示します。

 [!code-csharp[FxCop.Design.HideBaseMethod#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.HideBaseMethod/cs/FxCop.Design.HideBaseMethod.cs#1)]
