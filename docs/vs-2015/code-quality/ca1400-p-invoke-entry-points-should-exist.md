---
title: 'CA1400: P-Invoke エントリポイントが存在する必要があります |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1400
- PInvokeEntryPointsShouldExist
helpviewer_keywords:
- PInvokeEntryPointsShouldExist
- CA1400
ms.assetid: 1d64e470-7b2f-4cca-8fb0-ac92829e6332
caps.latest.revision: 21
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: d1083f7bbdf3b3af78b83aed293b31d898ae7522
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72661376"
---
# <a name="ca1400-pinvoke-entry-points-should-exist"></a>CA1400: P/Invoke エントリ ポイントは存在しなければなりません
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|PInvokeEntryPointsShouldExist|
|CheckId|CA1400|
|カテゴリ|Microsoft. 相互運用性|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因
 パブリックメソッドまたはプロテクトメソッドは、<xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName> でマークされます。 アンマネージ ライブラリの位置を特定できないか、メソッドがライブラリ内の関数と一致しません。 指定されたとおりに規則でメソッド名が見つからない場合は、メソッド名を ' A ' または ' W ' で suffixing ことで、メソッドの ANSI 文字バージョンまたはワイド文字バージョンを検索します。 一致するものが見つからない場合、ルールは __stdcall 名形式 (_MyMethod@12 を使用して関数を見つけようとします (12 は引数の長さを表します)。 一致する項目が見つからず、メソッド名が ' # ' で始まる場合、規則は、名前参照ではなく序数参照として関数を検索します。

## <a name="rule-description"></a>規則の説明
 @No__t_0 でマークされたメソッドが参照されているアンマネージ DLL に配置されていることを確認するためのコンパイル時チェックは使用できません。 指定された名前を持つ関数がライブラリ内にない場合、またはメソッドの引数が関数の引数と一致しない場合、共通言語ランタイムは例外をスローします。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則違反を修正するには、<xref:System.Runtime.InteropServices.DllImportAttribute> 属性を持つメソッドを修正します。 アンマネージライブラリが存在し、メソッドを含むアセンブリと同じディレクトリにあることを確認します。 ライブラリが存在し、正しく参照されている場合は、メソッド名、戻り値の型、および引数のシグネチャがライブラリ関数と一致していることを確認します。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 アンマネージライブラリがそれを参照するマネージアセンブリと同じディレクトリにある場合は、この規則からの警告を抑制しないでください。 アンマネージライブラリが見つからなかった場合は、このルールからの警告を抑制することが安全です。

## <a name="example"></a>例
 次の例は、規則に違反する型を示しています。 Kernel32.dll には `DoSomethingUnmanaged` という名前の関数がありません。

 [!code-csharp[FxCop.Interoperability.DLLExists#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Interoperability.DLLExists/cs/FxCop.Interoperability.DLLExists.cs#1)]

## <a name="see-also"></a>参照
 <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>
