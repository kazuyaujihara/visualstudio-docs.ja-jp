---
title: CA1707:識別子はアンダー スコアを含めることはできません |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- IdentifiersShouldNotContainUnderscores
- CA1707
helpviewer_keywords:
- CA1707
- IdentifiersShouldNotContainUnderscores
ms.assetid: 5fb539ef-c304-4323-90c0-b14386da9774
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 7973646aab545484287f5628eb0fa3cf3629db84
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/17/2019
ms.locfileid: "59651946"
---
# <a name="ca1707-identifiers-should-not-contain-underscores"></a>CA1707:識別子はアンダースコアを含むことはできません
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Visual Studio の最新ドキュメントについては、次を参照してください。 [ca 1707。識別子はアンダー スコアを含めることはできません](https://docs.microsoft.com/visualstudio/code-quality/ca1707-identifiers-should-not-contain-underscores)します。  
  
|||  
|-|-|  
|TypeName|IdentifiersShouldNotContainUnderscores|  
|CheckId|CA1707|  
|カテゴリ|Microsoft.Naming|  
|互換性に影響する変更点|重大なアセンブリで発生したときに<br /><br /> 非的な型パラメーターで発生したときに|  
  
## <a name="cause"></a>原因  
 識別子の名前にアンダー スコア (_) 文字が含まれています。  
  
## <a name="rule-description"></a>規則の説明  
 名前付け規則では、識別子名にアンダースコア (_) 文字を含めることができません。 このルールは、名前空間、型、メンバー、およびパラメーターを確認します。  
  
 名前付け規則では、共通言語ランタイムをターゲットとするライブラリの統一的な名前の付け方が規定されています。 これにより、新しいソフトウェア ライブラリを習得するまでの時間を短縮でき、マネージド コード開発の専門家によってライブラリが開発されたという信頼を顧客に与えることができます。  
  
## <a name="how-to-fix-violations"></a>違反の修正方法  
 名前からは、すべてのアンダー スコア文字を削除します。  
  
## <a name="when-to-suppress-warnings"></a>警告を抑制する状況  
 この規則による警告は抑制しないでください。  
  
## <a name="related-rules"></a>関連規則  
 [CA 1709:識別子では、大文字と小文字が正しく区別する必要があります。](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)  
  
 [CA1708:識別子は、ケース以外で相違させる必要があります。](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)
