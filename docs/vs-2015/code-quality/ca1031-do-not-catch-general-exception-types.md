---
title: 'CA1031: 一般的な例外の種類をキャッチしない |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1031
- DoNotCatchGeneralExceptionTypes
helpviewer_keywords:
- CA1031
- DoNotCatchGeneralExceptionTypes
ms.assetid: cbc283ae-2a46-4ec0-940e-85aa189b118f
caps.latest.revision: 22
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 2696446ee2b257b78559909c0cba672cded39943
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72661894"
---
# <a name="ca1031-do-not-catch-general-exception-types"></a>CA1031: 一般的な例外の種類はキャッチしません
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|DoNotCatchGeneralExceptionTypes|
|CheckId|CA1031|
|カテゴリ|Microsoft Design|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因
 @No__t_0 や <xref:System.SystemException?displayProperty=fullName> などの一般的な例外は `catch` ステートメントでキャッチされます。また、`catch()` などの一般的な catch 句が使用されます。

## <a name="rule-description"></a>規則の説明
 汎用的な例外はキャッチしないでください。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則違反を修正するには、より具体的な例外をキャッチするか、`catch` ブロックの最後のステートメントとして一般的な例外を再スローします。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 この規則による警告は抑制しないでください。 一般的な例外の種類をキャッチすると、ライブラリユーザーの実行時の問題が隠蔽されるため、デバッグが困難になる可能性があります。

> [!NOTE]
> @No__t_0 以降、共通言語ランタイム (CLR) では、オペレーティングシステムで発生した破損状態の例外や、[!INCLUDE[TLA#tla_mswin](../includes/tlasharptla-mswin-md.md)] でのアクセス違反などのマネージコードがマネージコードによって処理されるようになりました。 @No__t_0 以降のバージョンでアプリケーションをコンパイルし、破損状態例外の処理を維持する場合は、破損状態例外を処理するメソッドに <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute> 属性を適用できます。

## <a name="example"></a>例
 次の例は、この規則に違反する型と、`catch` ブロックを正しく実装する型を示しています。

 [!code-cpp[FxCop.Design.ExceptionAndSystemException#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Design.ExceptionAndSystemException/cpp/FxCop.Design.ExceptionAndSystemException.cpp#1)]
 [!code-csharp[FxCop.Design.ExceptionAndSystemException#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.ExceptionAndSystemException/cs/FxCop.Design.ExceptionAndSystemException.cs#1)]
 [!code-vb[FxCop.Design.ExceptionAndSystemException#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.ExceptionAndSystemException/vb/FxCop.Design.ExceptionAndSystemException.vb#1)]

## <a name="related-rules"></a>関連規則
 [CA2200: スタック詳細を保持するために再度スローします](../code-quality/ca2200-rethrow-to-preserve-stack-details.md)
