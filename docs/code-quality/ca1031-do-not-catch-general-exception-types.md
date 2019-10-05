---
title: CA1031:一般的な例外の種類はキャッチしません
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
ms.openlocfilehash: c1dc1e5ed18ddcd42d42c96f3f853808c58ade48
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71236065"
---
# <a name="ca1031-do-not-catch-general-exception-types"></a>CA1031:一般的な例外の種類はキャッチしません

|||
|-|-|
|TypeName|DoNotCatchGeneralExceptionTypes|
|CheckId|CA1031|
|カテゴリ|Microsoft.Design|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因
<xref:System.Exception?displayProperty=fullName>や`catch` `catch()`などの一般的な例外は、ステートメントでキャッチされます。または、のような一般的な catch 句が使用されます。 <xref:System.SystemException?displayProperty=fullName>

## <a name="rule-description"></a>規則の説明
汎用的な例外はキャッチしないでください。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するには、より具体的な例外をキャッチするか、 `catch`ブロック内の最後のステートメントとして一般的な例外を再スローします。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
この規則による警告は抑制しないでください。 一般的な例外の種類をキャッチすると、ライブラリユーザーの実行時の問題が隠蔽されるため、デバッグが困難になる可能性があります。

> [!NOTE]
> .NET Framework 4 以降、共通言語ランタイム (CLR) では、オペレーティングシステムで発生した破損状態の例外や、の[!INCLUDE[TLA#tla_mswin](../code-quality/includes/tlasharptla_mswin_md.md)]アクセス違反などのマネージコードがマネージコードによって処理されるようになりました。 .NET Framework 4 以降のバージョンでアプリケーションをコンパイルし、破損状態例外の処理を維持する場合は、破損状態例外を<xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>処理するメソッドに属性を適用できます。

## <a name="example"></a>例
次の例は、この規則に違反する型と、 `catch`ブロックを正しく実装する型を示しています。

[!code-cpp[FxCop.Design.ExceptionAndSystemException#1](../code-quality/codesnippet/CPP/ca1031-do-not-catch-general-exception-types_1.cpp)]
[!code-vb[FxCop.Design.ExceptionAndSystemException#1](../code-quality/codesnippet/VisualBasic/ca1031-do-not-catch-general-exception-types_1.vb)]
[!code-csharp[FxCop.Design.ExceptionAndSystemException#1](../code-quality/codesnippet/CSharp/ca1031-do-not-catch-general-exception-types_1.cs)]

## <a name="related-rules"></a>関連するルール
[CA2200スタックの詳細を保持するための再スロー](../code-quality/ca2200-rethrow-to-preserve-stack-details.md)