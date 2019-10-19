---
title: 'CA2201: 予約された例外の種類 | を発生させません。Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- DoNotRaiseReservedExceptionTypes
- CA2201
helpviewer_keywords:
- CA2201
- DoNotRaiseReservedExceptionTypes
ms.assetid: dd14ef5c-80e6-41a5-834e-eba8e2eae75e
caps.latest.revision: 18
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: a550226a5ea1edb3b30e317be6b5682f4c204d52
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72667376"
---
# <a name="ca2201-do-not-raise-reserved-exception-types"></a>CA2201: 予約された例外の種類を発生させません
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|DoNotRaiseReservedExceptionTypes|
|CheckId|CA2201|
|カテゴリ|Microsoft. 使用方法|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
 メソッドによって、汎用的またはランタイムによって予約されている例外の種類が発生します。

## <a name="rule-description"></a>規則の説明
 次の例外の種類は、ユーザーに十分な情報を提供するには一般的ではありません。

- <xref:System.Exception?displayProperty=fullName>

- <xref:System.ApplicationException?displayProperty=fullName>

- <xref:System.SystemException?displayProperty=fullName>

  次の例外の種類は予約されており、共通言語ランタイムによってのみスローされる必要があります。

- <xref:System.ExecutionEngineException?displayProperty=fullName>

- <xref:System.IndexOutOfRangeException?displayProperty=fullName>

- <xref:System.NullReferenceException?displayProperty=fullName>

- <xref:System.OutOfMemoryException?displayProperty=fullName>

  **一般的な例外をスローしない**

  ライブラリまたはフレームワークで <xref:System.Exception> や <xref:System.SystemException> などの一般的な例外の種類をスローすると、コンシューマーは、処理方法がわからない不明な例外も含め、すべての例外をキャッチするように強制されます。

  代わりに、フレームワークに既に存在する派生型をスローするか、<xref:System.Exception> から派生する独自の型を作成します。

  **特定の例外をスローする**

  次の表に、パラメーターを検証したときにスローされる例外と、プロパティの set アクセサーの value パラメーターを示します。

|パラメーターの説明|例外|
|---------------------------|---------------|
|`null` リファレンス|<xref:System.ArgumentNullException?displayProperty=fullName>|
|許容範囲外の値 (コレクションまたはリストのインデックスなど)|<xref:System.ArgumentOutOfRangeException?displayProperty=fullName>|
|@No__t_0 値が無効です|<xref:System.ComponentModel.InvalidEnumArgumentException?displayProperty=fullName>|
|には、メソッドのパラメーター指定を満たさない形式 (`ToString(String)` の書式文字列など) が含まれています。|<xref:System.FormatException?displayProperty=fullName>|
|それ以外の場合は無効|<xref:System.ArgumentException?displayProperty=fullName>|

 操作がオブジェクトの現在の状態に対して無効である場合 <xref:System.InvalidOperationException?displayProperty=fullName>

 破棄されたオブジェクトに対して操作が実行されると <xref:System.ObjectDisposedException?displayProperty=fullName>

 操作がサポートされていない場合 (オーバーライドされたストリームのなど)、読み取り用に開かれたストリームに書き込むと、<xref:System.NotSupportedException?displayProperty=fullName> がスローされ**ます**

 変換によってオーバーフロー (明示的なキャスト演算子のオーバーロードなど) が発生すると、<xref:System.OverflowException?displayProperty=fullName> がスローされます。

 それ以外の場合は、<xref:System.Exception> から派生した独自の型を作成し、それをスローすることを検討してください。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則違反を修正するには、スローされた例外の型を、予約済みの型ではない特定の型に変更します。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 この規則による警告は抑制しないでください。

## <a name="related-rules"></a>関連規則
 [CA1031: 一般的な例外の種類はキャッチしません](../code-quality/ca1031-do-not-catch-general-exception-types.md)
