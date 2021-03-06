---
title: 'CA1061: 基本クラス メソッドを非表示にしません'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1061
- DoNotHideBaseClassMethods
helpviewer_keywords:
- DoNotHideBaseClassMethods
- CA1061
ms.assetid: 0bda9dc8-87b4-4038-ab9d-563298387466
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: da132ba941c448f6323199d8baca86841d192ecf
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2018
ms.locfileid: "49924123"
---
# <a name="ca1061-do-not-hide-base-class-methods"></a>CA1061: 基本クラス メソッドを非表示にしません

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

## <a name="when-to-suppress-warnings"></a>警告を抑制します。
 この規則による警告は抑制しないでください。

## <a name="example"></a>例
 次の例では、規則に違反するメソッドを示します。

 [!code-csharp[FxCop.Design.HideBaseMethod#1](../code-quality/codesnippet/CSharp/ca1061-do-not-hide-base-class-methods_1.cs)]