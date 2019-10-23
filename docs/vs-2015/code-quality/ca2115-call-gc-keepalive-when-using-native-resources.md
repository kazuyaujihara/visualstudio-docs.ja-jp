---
title: 'CA2115: GC を呼び出します。ネイティブリソースを使用する場合の KeepAlive |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CallGCKeepAliveWhenUsingNativeResources
- CA2115
helpviewer_keywords:
- CA2115
- CallGCKeepAliveWhenUsingNativeResources
ms.assetid: f00a59a7-2c6a-4bbe-a1b3-7bf77d366f34
caps.latest.revision: 20
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: e0aa10cc453919a2a79ee6d3d46db95c19d8756e
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72658693"
---
# <a name="ca2115-call-gckeepalive-when-using-native-resources"></a>CA2115: ネイティブ リソースを使用しているときには GC.KeepAlive を呼び出します
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|CallGCKeepAliveWhenUsingNativeResources|
|CheckId|CA2115|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|中断なし|

## <a name="cause"></a>原因
 ファイナライザーを持つ型で宣言されたメソッドが、<xref:System.IntPtr?displayProperty=fullName> または <xref:System.UIntPtr?displayProperty=fullName> フィールドを参照していますが、<xref:System.GC.KeepAlive%2A?displayProperty=fullName> を呼び出していません。

## <a name="rule-description"></a>規則の説明
 ガベージコレクションは、マネージコードにそれ以上の参照がない場合に、オブジェクトを終了します。 オブジェクトへのアンマネージ参照によって、ガベージコレクションが妨げられることはありません。 この規則では、アンマネージ コードでまだ使用されているのに、アンマネージ リソースが終了されたときに発生する可能性のあるエラーを検出します。

 このルールは、<xref:System.IntPtr> および <xref:System.UIntPtr> フィールドにアンマネージリソースへのポインターが格納されていることを前提としています。 ファイナライザーの目的はアンマネージリソースを解放することであるため、この規則では、ポインターフィールドが指すアンマネージリソースがファイナライザーによって解放されることを前提としています。 また、アンマネージリソースをアンマネージコードに渡すために、メソッドがポインターフィールドを参照していることも前提としています。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則違反を修正するには、メソッドに <xref:System.GC.KeepAlive%2A> への呼び出しを追加し、現在のインスタンス (およびC# C++の `this`) を引数として渡します。 オブジェクトをガベージコレクションから保護する必要があるコードの最後の行の後に、呼び出しを配置します。 @No__t_0 の呼び出しの直後に、オブジェクトは、マネージ参照がないと仮定して、ガベージコレクションの準備が整っていると見なされます。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 この規則は、偽陽性の原因となる可能性のあるいくつかの仮定を行います。 次の場合に、この規則による警告を抑制することができます。

- ファイナライザーでは、メソッドによって参照される <xref:System.IntPtr> または <xref:System.UIntPtr> フィールドの内容が解放されることはありません。

- メソッドは、<xref:System.IntPtr> または <xref:System.UIntPtr> フィールドをアンマネージコードに渡しません。

  除外する前に、他のメッセージを慎重に確認してください。 このルールは、再現およびデバッグが困難なエラーを検出します。

## <a name="example"></a>例
 次の例では、`BadMethod` に `GC.KeepAlive` の呼び出しが含まれていないため、規則に違反します。 修正されたコードが `GoodMethod` に含まれています。

> [!NOTE]
> この例は擬似コードですが、コードをコンパイルして実行しますが、アンマネージリソースが作成または解放されないため、警告は発生しません。

 [!code-csharp[FxCop.Security.IntptrAndFinalize#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Security.IntptrAndFinalize/cs/FxCop.Security.IntptrAndFinalize.cs#1)]

## <a name="see-also"></a>参照
 <xref:System.GC.KeepAlive%2A?displayProperty=fullName> <xref:System.IntPtr?displayProperty=fullName>
 <xref:System.Object.Finalize%2A?displayProperty=fullName>
 <xref:System.UIntPtr?displayProperty=fullName>
 [Dispose パターン](https://msdn.microsoft.com/library/31a6c13b-d6a2-492b-9a9f-e5238c983bcb)
