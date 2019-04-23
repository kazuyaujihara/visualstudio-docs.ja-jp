---
title: CA1726:用語を使用します |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- UsePreferredTerms
- CA1726
helpviewer_keywords:
- UsePreferredTerms
ms.assetid: 642b2acd-3a33-4d1f-b0a7-67073ae73be2
caps.latest.revision: 24
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 67dab4c732faa04af44800f740d78c4ce4f9dc80
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/17/2019
ms.locfileid: "59664113"
---
# <a name="ca1726-use-preferred-terms"></a>CA1726:適切な用語を使用します
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Visual Studio の最新ドキュメントについては、次を参照してください。 [ca 1726 適切な。適切な用語を使用して、](https://docs.microsoft.com/visualstudio/code-quality/ca1726-use-preferred-terms)します。  
  
|||  
|-|-|  
|TypeName|UsePreferredTerms|  
|CheckId|CA1726|  
|カテゴリ|Microsoft.Naming|  
|互換性に影響する変更点|– アセンブリで発生した場合<br /><br /> 非的な型パラメーターで発生した場合|  
  
## <a name="cause"></a>原因  
 外部から参照可能な識別子の名前に含まれている用語に対応する、別の推奨される用語があります。 または、名前には、フラグまたはフラグの用語が含まれています。  
  
## <a name="rule-description"></a>規則の説明  
 このルールは、識別子をトークンに解析します。 各 1 つのトークンと連続する 2 つのトークンの組み合わせとカスタム ディクショナリの非推奨のセクションのルールに組み込まれている用語が比較されます。 次の表では、ルールとその推奨される代替手段に組み込まれている条件を示します。  
  
|廃止された用語|推奨用語|  
|-------------------|--------------------|  
|`Arent`|`AreNot`|
|`Cancelled`|`Canceled`|
|`Cant`|`Cannot`|
|`ComPlus`|`EnterpriseServices`|
|`Couldnt`|`CouldNot`|
|`Didnt`|`DidNot`|
|`Doesnt`|`DoesNot`|
|`Dont`|`DoNot`|
|`Flag` または `Flags`|置換用語はありません。 使用しないでください。|
|`Hadnt`|`HadNot`|
|`Hasnt`|`HasNot`|
|`Havent`|`HaveNot`|
|`Indices`|`Indexes`|
|`Isnt`|`IsNot`|
|`LogIn`|`LogOn`|
|`LogOut`|`LogOff`|
|`Shouldnt`|`ShouldNot`|
|`SignOn`|`SignIn`|
|`SignOff`|`SignOut`|
|`Wasnt`|`WasNot`|
|`Werent`|`WereNot`|
|`Wont`|`WillNot`|
|`Wouldnt`|`WouldNot`|
|`Writeable`|`Writable`|
  
## <a name="how-to-fix-violations"></a>違反の修正方法  
 この規則違反を修正するには、推奨される代替用語でという用語を置き換えます。  
  
## <a name="when-to-suppress-warnings"></a>警告を抑制する状況  
 識別子の名前は意図的であり、推奨用語ではなく元の用語に特に関連して 場合だけは、この規則による警告を抑制します。  
  
## <a name="related-rules"></a>関連規則  
 [名前付けに関する警告](../code-quality/naming-warnings.md)
