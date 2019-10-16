---
title: 'CA1031: 一般的な例外の種類はキャッチしません'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1031
- DoNotCatchGeneralExceptionTypes
helpviewer_keywords:
- CA1031
- DoNotCatchGeneralExceptionTypes
ms.assetid: cbc283ae-2a46-4ec0-940e-85aa189b118f
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: e157feb9b054cd6082f77c4f86277c35ddb02c34
ms.sourcegitcommit: 1507baf3a336bbb6511d4c3ce73653674831501b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72349131"
---
# <a name="ca1031-do-not-catch-general-exception-types"></a>CA1031: 一般的な例外の種類はキャッチしません

|||
|-|-|
|TypeName|DoNotCatchGeneralExceptionTypes|
|CheckId|CA1031|
|カテゴリ|Microsoft Design|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因
@No__t-0 や <xref:System.SystemException?displayProperty=fullName> などの一般的な例外が `catch` ステートメントでキャッチされるか、または `catch()` などの一般的な catch 句が使用されます。

## <a name="rule-description"></a>規則の説明
汎用的な例外はキャッチしないでください。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するには、より具体的な例外をキャッチするか、`catch` ブロックの最後のステートメントとして一般的な例外を再スローします。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
この規則による警告は抑制しないでください。 一般的な例外の種類をキャッチすると、ライブラリユーザーの実行時の問題が隠蔽されるため、デバッグが困難になる可能性があります。

> [!NOTE]
> .NET Framework 4 以降、共通言語ランタイム (CLR) は、オペレーティングシステムで発生した破損状態の例外、および @no__t 0 でのアクセス違反などのマネージコードによって処理されるようになりました。 .NET Framework 4 以降のバージョンでアプリケーションをコンパイルし、破損状態例外の処理を維持する場合は、破損状態例外を処理するメソッドに <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute> 属性を適用できます。

## <a name="example"></a>例
次の例は、この規則に違反する型と、`catch` ブロックを正しく実装する型を示しています。

[!code-cpp[FxCop.Design.ExceptionAndSystemException#1](../code-quality/codesnippet/CPP/ca1031-do-not-catch-general-exception-types_1.cpp)]
[!code-vb[FxCop.Design.ExceptionAndSystemException#1](../code-quality/codesnippet/VisualBasic/ca1031-do-not-catch-general-exception-types_1.vb)]
[!code-csharp[FxCop.Design.ExceptionAndSystemException#1](../code-quality/codesnippet/CSharp/ca1031-do-not-catch-general-exception-types_1.cs)]

## <a name="related-rules"></a>関連するルール
[CA2200: スタック詳細を保持するために再度スローします](../code-quality/ca2200.md)