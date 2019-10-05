---
title: CA1050:名前空間で型を宣言します
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1050
- DeclareTypesInNamespaces
helpviewer_keywords:
- DeclareTypesInNamespaces
- CA1050
ms.assetid: 1002748d-ac8d-404f-85dd-7a12d1ad3e05
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 8127c68cfe7eb541b8adea8affad99027e0c1fe7
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71235749"
---
# <a name="ca1050-declare-types-in-namespaces"></a>CA1050:名前空間で型を宣言します

|||
|-|-|
|TypeName|DeclareTypesInNamespaces|
|CheckId|CA1050|
|カテゴリ|Microsoft.Design|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
パブリック型またはプロテクト型が名前付き名前空間のスコープ外で定義されています。

## <a name="rule-description"></a>規則の説明
型は名前の競合を防ぐために名前空間で宣言され、オブジェクト階層内の関連する型を整理する手段として宣言されます。 名前付き名前空間の外部にある型は、コード内で参照できないグローバル名前空間にあります。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するには、名前空間に型を配置します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
この規則による警告を抑制する必要はありませんが、アセンブリが他のアセンブリと一緒に使用されない場合は、この操作を安全に行うことができます。

## <a name="example"></a>例
次の例では、名前空間の外部で型が正しく宣言されていないライブラリと、名前空間で宣言された同じ名前の型を持つライブラリを示します。

[!code-csharp[FxCop.Design.TypesLiveInNamespaces#1](../code-quality/codesnippet/CSharp/ca1050-declare-types-in-namespaces_1.cs)]
[!code-vb[FxCop.Design.TypesLiveInNamespaces#1](../code-quality/codesnippet/VisualBasic/ca1050-declare-types-in-namespaces_1.vb)]

## <a name="example"></a>例
次のアプリケーションは、以前に定義されたライブラリを使用します。 名前空間の外側で宣言された型は、名前空間で`Test`修飾されていない場合に作成されることに注意してください。 また、の`Test` `Goodspace`型にアクセスするには、名前空間の名前が必要です。

[!code-csharp[FxCop.Design.TestTypesLive#1](../code-quality/codesnippet/CSharp/ca1050-declare-types-in-namespaces_2.cs)]
[!code-vb[FxCop.Design.TestTypesLive#1](../code-quality/codesnippet/VisualBasic/ca1050-declare-types-in-namespaces_2.vb)]