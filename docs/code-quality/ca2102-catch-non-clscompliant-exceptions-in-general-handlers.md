---
title: CA2102:汎用ハンドラーの CLSCompliant でない例外をキャッチします
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2102
- CatchNonClsCompliantExceptionsInGeneralHandlers
helpviewer_keywords:
- CA2102
ms.assetid: bf2df68f-d386-4379-ad9e-930a2c2e930d
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f62ad97bbb96f49a7263edd29f0f8a7c263bec4c
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71233012"
---
# <a name="ca2102-catch-non-clscompliant-exceptions-in-general-handlers"></a>CA2102:汎用ハンドラーの CLSCompliant でない例外をキャッチします

|||
|-|-|
|TypeName|CatchNonClsCompliantExceptionsInGeneralHandlers|
|CheckId|CA2102|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因

または<xref:System.Runtime.CompilerServices.RuntimeCompatibilityAttribute> <xref:System.Exception?displayProperty=fullName>でマークされていないアセンブリ内のメンバーには、を処理する catch ブロックが含まれており、その直後に次の一般的なcatchブロックが含まれていません。`RuntimeCompatibility(WrapNonExceptionThrows = false)` このルールは[!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 、アセンブリを無視します。

## <a name="rule-description"></a>規則の説明

共通言語仕様 (CLS <xref:System.Exception> ) に準拠しているすべての例外をキャッチする catch ブロック。 ただし、CLS に準拠していない例外はキャッチされません。 CLS 準拠でない例外は、ネイティブコードから、または Microsoft 中間言語 (MSIL) アセンブラによって生成されたマネージコードからスローされることがあります。 コンパイラC#と[!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]コンパイラでは、cls 準拠でない例外がスローされることは[!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]許可されておらず、cls に準拠していない例外はキャッチされないことに注意してください。 Catch ブロックの目的がすべての例外を処理する場合は、次の一般的な catch ブロック構文を使用します。

- C#: `catch {}`

- C++: `catch(...) {}`または`catch(Object^) {}`

以前に許可されていたアクセス許可が catch ブロックで削除されると、未処理の非 CLS 準拠の例外がセキュリティの問題になります。 CLS 準拠でない例外がキャッチされないため、CLS に準拠していない例外をスローする悪意のあるメソッドが、昇格されたアクセス許可で実行される可能性があります。

## <a name="how-to-fix-violations"></a>違反の修正方法

すべての例外をキャッチすることが目的である場合に、この規則違反を修正するには、汎用 catch ブロックを`RuntimeCompatibility(WrapNonExceptionThrows = true)`置き換えるか追加するか、またはアセンブリをマークします。 Catch ブロックで権限が削除された場合は、一般的な catch ブロックの機能を複製します。 すべての例外を処理することが意図されていない場合は、 <xref:System.Exception>が処理する catch ブロックを、特定の種類の例外を処理する catch ブロックで置き換えます。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

Try ブロックに CLS に準拠していない例外を生成する可能性のあるステートメントが含まれていない場合は、この規則からの警告を抑制することが安全です。 ネイティブコードまたはマネージコードでは、CLS に準拠していない例外がスローされる可能性があるため、try ブロック内のすべてのコードパスで実行できるすべてのコードの知識が必要です。 CLS 準拠でない例外は、共通言語ランタイムによってスローされないことに注意してください。

## <a name="example-1"></a>例 1

次の例は、CLS に準拠していない例外をスローする MSIL クラスを示しています。

```cpp
.assembly ThrowNonClsCompliantException {}
.class public auto ansi beforefieldinit ThrowsExceptions
{
   .method public hidebysig static void
         ThrowNonClsException() cil managed
   {
      .maxstack  1
      IL_0000:  newobj     instance void [mscorlib]System.Object::.ctor()
      IL_0005:  throw
   }
}
```

## <a name="example-2"></a>例 2

次の例は、規則を満たす一般的な catch ブロックを含むメソッドを示しています。

[!code-csharp[FxCop.Security.CatchNonClsCompliantException#1](../code-quality/codesnippet/CSharp/ca2102-catch-non-clscompliant-exceptions-in-general-handlers_1.cs)]

前の例を次のようにコンパイルします。

```cpp
ilasm /dll ThrowNonClsCompliantException.il
csc /r:ThrowNonClsCompliantException.dll CatchNonClsCompliantException.cs
```

## <a name="related-rules"></a>関連するルール

[CA1031一般的な例外の種類をキャッチしない](../code-quality/ca1031-do-not-catch-general-exception-types.md)

## <a name="see-also"></a>関連項目

- [例外と例外処理](/dotnet/csharp/programming-guide/exceptions/exceptions-and-exception-handling)
- [Ilasm.exe (IL アセンブラー)](/dotnet/framework/tools/ilasm-exe-il-assembler)
- [言語への非依存性、および言語非依存コンポーネント](/dotnet/standard/language-independence-and-language-independent-components)