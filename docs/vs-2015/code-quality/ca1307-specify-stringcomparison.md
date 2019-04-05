---
title: CA1307:StringComparison の指定 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1307
- SpecifyStringComparison
helpviewer_keywords:
- CA1307
- SpecifyStringComparison
ms.assetid: 9b0d5e71-1683-4a0d-bc4a-68b2fbd8af71
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 292e174feeb123c640306bc8ef3ffedd7e8847f6
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58974890"
---
# <a name="ca1307-specify-stringcomparison"></a>CA1307:StringComparison の指定
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|SpecifyStringComparison|
|CheckId|CA1307|
|カテゴリ|Microsoft.Globalization|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因
 文字列比較操作が設定されていないメソッドのオーバー ロードを使用して、<xref:System.StringComparison>パラメーター。

## <a name="rule-description"></a>規則の説明
 多くの文字列操作、最も重要な<xref:System.String.Compare%2A>と<xref:System.String.Equals%2A>メソッドを受け入れるオーバー ロードを提供する、<xref:System.StringComparison>列挙値をパラメーターとして。

 オーバー ロードされるたびに行うためにかかるが存在する場合、<xref:System.StringComparison>パラメーターをこのパラメーターを受け取らないオーバー ロードではなくために使用する必要があります。 コードはこのパラメーターを明示的に設定するではわかりやすくなり、保守が簡単に多くの場合です。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則違反を解決するを受け取るオーバー ロードする文字列比較メソッドを変更、<xref:System.StringComparison>列挙体をパラメーターとして。 例: 変更`String.Compare(str1, str2)`に`String.Compare(str1, str2, StringComparison.Ordinal)`します。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 限定されたローカル ユーザーのためのものでは、ライブラリまたはアプリケーションと、ためにローカライズされないときは、この規則による警告を非表示にも安全です。

## <a name="see-also"></a>関連項目
 [グローバリゼーションに関する警告](../code-quality/globalization-warnings.md) [CA1309:StringComparison を使用します](../code-quality/ca1309-use-ordinal-stringcomparison.md)
