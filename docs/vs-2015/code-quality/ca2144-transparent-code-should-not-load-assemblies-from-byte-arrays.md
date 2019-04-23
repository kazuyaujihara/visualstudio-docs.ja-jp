---
title: CA2144:透過的なコードは、バイト配列からアセンブリを読み込めません |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2144
ms.assetid: 777b1310-6e16-4413-b4ee-5f3136304f82
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: b54e74297ca44662f49b5842aae8e334a8f4045a
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "60095881"
---
# <a name="ca2144-transparent-code-should-not-load-assemblies-from-byte-arrays"></a>CA2144:透過的コードは、バイト配列からアセンブリを読み込んではならない
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|TransparentMethodsShouldNotLoadAssembliesFromByteArrays|
|CheckId|CA2144|
|カテゴリ|Microsoft.Security|
|互換性に影響する変更点|あり|

## <a name="cause"></a>原因
 透過的なメソッドは、次のメソッドのいずれかを使用してバイト配列からアセンブリを読み込みます。

- <xref:System.Reflection.Assembly.Load%2A>

- <xref:System.Reflection.Assembly.Load%2A>

- <xref:System.Reflection.Assembly.Load%2A>

## <a name="rule-description"></a>規則の説明
 透過的なコードはセキュリティ上重要な操作を実行できないため、透過的なコードのセキュリティ レビューは、クリティカル コードのセキュリティ レビューほど完全ではありません。 バイト配列から読み込まれるアセンブリは透過的なコード内で認識されない場合がありますが、監査を必要とする、クリティカルなコード、またはさらに重要であるセーフ クリティカルなコードがそのバイト配列に含まれる可能性があります。 そのため、透過的なコードはバイト配列からアセンブリを読み込んで必要があります。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則違反を修正するを使用してアセンブリを読み込んでいるメソッドをマーク、<xref:System.Security.SecurityCriticalAttribute>または<xref:System.Security.SecuritySafeCriticalAttribute>属性。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 この規則による警告は抑制しないでください。

## <a name="example"></a>例
 ルールは、透過的メソッドは、バイト配列からアセンブリを読み込んでいるために、次のコードに対して適用されます。

 [!code-csharp[FxCop.Security.CA2144.TransparentMethodsShouldNotLoadAssembliesFromByteArrays#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2144.transparentmethodsshouldnotloadassembliesfrombytearrays/cs/ca2144 - transparentmethodsshouldnotloadassembliesfrombytearrays.cs#1)]
