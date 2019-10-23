---
title: 'CA2102: 一般的なハンドラーでの CLSCompliant 以外の例外のキャッチ |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2102
- CatchNonClsCompliantExceptionsInGeneralHandlers
helpviewer_keywords:
- CA2102
ms.assetid: bf2df68f-d386-4379-ad9e-930a2c2e930d
caps.latest.revision: 21
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 051b59183a761477476269480ecdf83ccbf0cb37
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72652175"
---
# <a name="ca2102-catch-non-clscompliant-exceptions-in-general-handlers"></a>CA2102: 汎用ハンドラーの CLSCompliant でない例外をキャッチします
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|CatchNonClsCompliantExceptionsInGeneralHandlers|
|CheckId|CA2102|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因
 @No__t_0 でマークされていないアセンブリ内のメンバー、または `RuntimeCompatibility(WrapNonExceptionThrows = false)` としてマークされているメンバーが、<xref:System.Exception?displayProperty=fullName> を処理する catch ブロックを含んでおり、その直後に次の汎用 catch ブロックが含まれていません。 このルールは [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] アセンブリを無視します。

## <a name="rule-description"></a>規則の説明
 すべての共通言語仕様 (CLS) 準拠の例外をキャッチ <xref:System.Exception> を処理する catch ブロック。 ただし、CLS に準拠していない例外はキャッチされません。 CLS 準拠でない例外は、ネイティブコードから、または Microsoft 中間言語 (MSIL) アセンブラによって生成されたマネージコードからスローされることがあります。 C#および [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] コンパイラでは、cls 準拠でない例外がスローされることは許可されておらず、[!INCLUDE[vbprvb](../includes/vbprvb-md.md)] は cls に準拠していない例外をキャッチしないことに注意してください。 Catch ブロックの目的がすべての例外を処理する場合は、次の一般的な catch ブロック構文を使用します。

- C#: `catch {}`

- C++: `catch(...) {}` または `catch(Object^) {}`

  以前に許可されていたアクセス許可が catch ブロックで削除されると、未処理の非 CLS 準拠の例外がセキュリティの問題になります。 CLS 準拠でない例外がキャッチされないため、CLS に準拠していない例外をスローする悪意のあるメソッドが、昇格されたアクセス許可で実行される可能性があります。

## <a name="how-to-fix-violations"></a>違反の修正方法
 すべての例外をキャッチすることが目的である場合に、この規則違反を修正するには、汎用 catch ブロックを置き換えるか追加するか、アセンブリ `RuntimeCompatibility(WrapNonExceptionThrows = true)` をマークします。 Catch ブロックで権限が削除された場合は、一般的な catch ブロックの機能を複製します。 すべての例外を処理することを意図していない場合は、<xref:System.Exception> を処理する catch ブロックを、特定の種類の例外を処理する catch ブロックに置き換えます。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 Try ブロックに CLS に準拠していない例外を生成する可能性のあるステートメントが含まれていない場合は、この規則からの警告を抑制することが安全です。 ネイティブコードまたはマネージコードでは、CLS に準拠していない例外がスローされる可能性があるため、try ブロック内のすべてのコードパスで実行できるすべてのコードの知識が必要です。 CLS 準拠でない例外は、共通言語ランタイムによってスローされないことに注意してください。

## <a name="example"></a>例
 次の例は、CLS に準拠していない例外をスローする MSIL クラスを示しています。

```
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

## <a name="example"></a>例
 次の例は、規則を満たす一般的な catch ブロックを含むメソッドを示しています。

 [!code-csharp[FxCop.Security.CatchNonClsCompliantException#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Security.CatchNonClsCompliantException/cs/FxCop.Security.CatchNonClsCompliantException.cs#1)]

 前の例を次のようにコンパイルします。

```
ilasm /dll ThrowNonClsCompliantException.il
csc /r:ThrowNonClsCompliantException.dll CatchNonClsCompliantException.cs
```

## <a name="related-rules"></a>関連規則
 [CA1031: 一般的な例外の種類はキャッチしません](../code-quality/ca1031-do-not-catch-general-exception-types.md)

## <a name="see-also"></a>参照
 [例外と例外処理](https://msdn.microsoft.com/library/0001887f-4fa2-47e2-8034-2819477e2344) [Ilasm (IL アセンブラー)](https://msdn.microsoft.com/library/4ca3a4f0-4400-47ce-8936-8e219961c76f)による[セキュリティチェックのオーバーライド](https://msdn.microsoft.com/4acdeff5-fc05-41bf-8505-7387cdbfca28)[言語の非依存性と言語に依存しないコンポーネント](https://msdn.microsoft.com/library/4f0b77d0-4844-464f-af73-6e06bedeafc6)
