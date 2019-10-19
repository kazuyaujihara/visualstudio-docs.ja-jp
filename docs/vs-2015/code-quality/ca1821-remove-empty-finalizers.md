---
title: 'CA1821: 空のファイナライザーを削除します |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- RemoveEmptyFinalizers
- CA1821
helpviewer_keywords:
- CA1821
ms.assetid: 3f4855a0-e4a0-46e6-923c-4c3b7074048d
caps.latest.revision: 15
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 3d340d69ee32de20142abf740f7fedc871c9733a
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72657471"
---
# <a name="ca1821-remove-empty-finalizers"></a>CA1821: 空のファイナライザーを削除します
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|RemoveEmptyFinalizers|
|CheckId|CA1821|
|カテゴリ|Microsoft. パフォーマンス|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因
 型は、空のファイナライザーを実装しているか、基本型のファイナライザーだけを呼び出すか、条件付きで出力されたメソッドのみを呼び出します。

## <a name="rule-description"></a>規則の説明
 オブジェクトの有効期間の追跡に関連するパフォーマンス オーバーヘッドが増大するため、ファイナライザーは可能な限り使用しないでください。 ガベージコレクターは、オブジェクトを収集する前にファイナライザーを実行します。 これは、オブジェクトを収集するために2つのコレクションが必要であることを意味します。 空のファイナライザーでは、この追加のオーバーヘッドが発生することはありません。

## <a name="how-to-fix-violations"></a>違反の修正方法
 空のファイナライザーを削除します。 デバッグにファイナライザーが必要な場合は `#if DEBUG / #endif` ディレクティブでファイナライザー全体を囲みます。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 この規則からのメッセージを抑制しないでください。 終了処理を抑制しないと、パフォーマンスが低下し、利点はありません。

## <a name="example"></a>例
 次の例は、削除する必要がある空のファイナライザー、`#if DEBUG / #endif` ディレクティブで囲む必要があるファイナライザー、および `#if DEBUG / #endif` ディレクティブを正しく使用するファイナライザーを示しています。

 [!code-csharp[FxCop.Performance.RemoveEmptyFinalizers#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Performance.RemoveEmptyFinalizers/cs/FxCop.Performance.RemoveEmptyFinalizers.cs#1)]
