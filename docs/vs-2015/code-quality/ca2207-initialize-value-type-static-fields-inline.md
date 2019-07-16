---
title: CA2207:値型の静的フィールドのインラインを初期化します |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- InitializeValueTypeStaticFieldsInline
- CA2207
helpviewer_keywords:
- CA2207
- InitializeValueTypeStaticFieldsInline
ms.assetid: d1ea9d8b-ecc2-46ca-86e2-c41dd0e76658
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 4f8bc843dc20df03ddf38a7506342addb6477297
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68142523"
---
# <a name="ca2207-initialize-value-type-static-fields-inline"></a>CA2207:値型のスタティック フィールドのインラインを初期化します
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|InitializeValueTypeStaticFieldsInline|
|CheckId|CA2207|
|カテゴリ|Microsoft.Usage|
|互換性に影響する変更点|中断なし|

## <a name="cause"></a>原因
 値型では、明示的な静的コンス トラクターを宣言します。

## <a name="rule-description"></a>規則の説明
 値型が宣言されている場合、すべての値型フィールドが 0 に設定され、すべての参照型フィールドに設定は、既定の初期化が行われる`null`(`Nothing` Visual Basic で)。 明示的な静的コンス トラクターを実行して、インスタンス コンス トラクターにのみ保証されます。 または、型の静的メンバーが呼び出されます。 そのため、インスタンス コンス トラクターを呼び出さずに、型が作成される場合、静的コンス トラクターを実行する保証されません。

 C# および Visual Basic のコンパイラが追加するかどうかは、すべての静的データが初期化されたインラインと明示的な静的コンス トラクターが宣言されていない、 `beforefieldinit` MSIL クラスの定義にフラグ。 コンパイラでは、静的な初期化コードを含むプライベート静的コンス トラクターも追加します。 このプライベート静的コンス トラクター、型の静的フィールドにアクセスする前に実行することが保証されます。

## <a name="how-to-fix-violations"></a>違反の修正方法
 解決するには、は、この規則違反は、宣言されていて、静的コンス トラクターを削除するときに、すべての静的データを初期化します。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 この規則による警告は抑制しないでください。

## <a name="related-rules"></a>関連規則
 [CA 1810:参照型の静的フィールドのインラインを初期化します](../code-quality/ca1810-initialize-reference-type-static-fields-inline.md)
