---
title: CA1821:空のファイナライザーを削除します
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- RemoveEmptyFinalizers
- CA1821
helpviewer_keywords:
- CA1821
ms.assetid: 3f4855a0-e4a0-46e6-923c-4c3b7074048d
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9c8c4d4ca04c7a9a21cd1e80e4dc06e8d5a92c2f
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68921370"
---
# <a name="ca1821-remove-empty-finalizers"></a>CA1821:空のファイナライザーを削除します

|||
|-|-|
|TypeName|RemoveEmptyFinalizers|
|CheckId|CA1821|
|Category|Microsoft.Performance|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因
型は、空のファイナライザーを実装しているか、基本型のファイナライザーだけを呼び出すか、条件付きで出力されたメソッドのみを呼び出します。

## <a name="rule-description"></a>規則の説明
オブジェクトの有効期間の追跡に関連するパフォーマンス オーバーヘッドが増大するため、ファイナライザーは可能な限り使用しないでください。 ガベージコレクターは、オブジェクトを収集する前にファイナライザーを実行します。 これは、オブジェクトを収集するために2つのコレクションが必要であることを意味します。 空のファイナライザーでは、この追加のオーバーヘッドが発生することはありません。

## <a name="how-to-fix-violations"></a>違反の修正方法
空のファイナライザーを削除します。 デバッグにファイナライザーが必要な場合は、ファイナライザー全体をディレクティブ`#if DEBUG / #endif`で囲みます。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
この規則からのメッセージを抑制しないでください。 終了処理を抑制しないと、パフォーマンスが低下し、利点はありません。

## <a name="example"></a>例
次の例は、削除する必要がある空のファイナライザー、ディレクティブで`#if DEBUG / #endif`囲む必要があるファイナライザー、および`#if DEBUG / #endif`ディレクティブを正しく使用するファイナライザーを示しています。

[!code-csharp[FxCop.Performance.RemoveEmptyFinalizers#1](../code-quality/codesnippet/CSharp/ca1821-remove-empty-finalizers_1.cs)]