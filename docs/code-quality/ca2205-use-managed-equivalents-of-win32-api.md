---
title: CA2205:Win32 API に相当するマネージド API を使用します
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- UseManagedEquivalentsOfWin32Api
- CA2205
helpviewer_keywords:
- UseManagedEquivalentsOfWin32Api
- CA2205
ms.assetid: 1c65ab59-3e50-4488-a727-3969c7f6cbe4
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: ad26dcbbbef5a34796ca0aa134653c3c9df5d763
ms.sourcegitcommit: e98db44f3a33529b0ba188d24390efd09e548191
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2019
ms.locfileid: "71253258"
---
# <a name="ca2205-use-managed-equivalents-of-win32-api"></a>CA2205:Win32 API に相当するマネージド API を使用します

|||
|-|-|
|TypeName|UseManagedEquivalentsOfWin32Api|
|CheckId|CA2205|
|カテゴリ|Microsoft.Usage|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因

プラットフォーム呼び出しメソッドが定義されており、同等の機能を持つメソッドが .NET に存在します。

## <a name="rule-description"></a>規則の説明

Platform invoke メソッドは、アンマネージ DLL 関数を呼び出すために使用され<xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName> 、属性`Declare`または Visual Basic 内のキーワードを使用して定義されます。 プラットフォーム呼び出しメソッドが正しく定義されていないと、misnamed 関数、パラメーターと戻り値のデータ型のマッピングが正しくない、または呼び出し規約や文字などの不適切なフィールドの指定などの問題が原因で、実行時例外が発生する可能性があります。一連. 使用可能な場合は、アンマネージメソッドを直接定義して呼び出すよりも、より簡単でエラーが発生しやすくなります。 プラットフォーム呼び出しメソッドを呼び出すと、対処する必要がある追加のセキュリティ問題が発生する可能性もあります。

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則違反を修正するには、アンマネージ関数の呼び出しを、それと等価なマネージ関数の呼び出しに置き換えます。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

推奨される置換方法によって必要な機能が提供されない場合は、この規則による警告を非表示にします。

## <a name="example"></a>例

次の例は、規則に違反するプラットフォーム呼び出しメソッドの定義を示しています。 さらに、プラットフォーム呼び出しメソッドと同等のマネージメソッドの呼び出しが表示されます。

[!code-csharp[FxCop.Usage.ManagedEquivalents#1](../code-quality/codesnippet/CSharp/ca2205-use-managed-equivalents-of-win32-api_1.cs)]
[!code-vb[FxCop.Usage.ManagedEquivalents#1](../code-quality/codesnippet/VisualBasic/ca2205-use-managed-equivalents-of-win32-api_1.vb)]

## <a name="related-rules"></a>関連するルール

- [CA1404P/Invoke の直後に GetLastError を呼び出します](../code-quality/ca1404-call-getlasterror-immediately-after-p-invoke.md)
- [CA1060P/Invoke を NativeMethods クラスに移動する](../code-quality/ca1060-move-p-invokes-to-nativemethods-class.md)
- [CA1400P/Invoke エントリポイントが存在する必要があります](../code-quality/ca1400-p-invoke-entry-points-should-exist.md)
- [CA1401P/Invoke は表示されません](../code-quality/ca1401-p-invokes-should-not-be-visible.md)
- [CA2101P/Invoke 文字列引数のマーシャリングを指定します](../code-quality/ca2101-specify-marshaling-for-p-invoke-string-arguments.md)