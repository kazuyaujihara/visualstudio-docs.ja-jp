---
title: CA2232:Mark の Windows フォームのエントリ ポイントを stathread に設定します |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- MarkWindowsFormsEntryPointsWithStaThread
- CA2232
helpviewer_keywords:
- CA2232
- MarkWindowsFormsEntryPointsWithStaThread
ms.assetid: a3c95130-8e7f-4419-9fcd-b67d077e8efb
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: d486189b557c0c1146be68e6c0328cb49d5ed291
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58977635"
---
# <a name="ca2232-mark-windows-forms-entry-points-with-stathread"></a>CA2232:Windows フォームのエントリ ポイントを STAThread に設定します
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|MarkWindowsFormsEntryPointsWithStaThread|
|CheckId|CA2232|
|カテゴリ|Microsoft.Usage|
|互換性に影響する変更点|中断なし|

## <a name="cause"></a>原因
 アセンブリ参照、<xref:System.Windows.Forms>名前空間、およびそのエントリ ポイントでマークされていない、<xref:System.STAThreadAttribute?displayProperty=fullName>属性。

## <a name="rule-description"></a>規則の説明
 <xref:System.STAThreadAttribute> COM アプリケーションのモデルのスレッドがシングル スレッド アパートメントであることを示します。 この属性は、Windows フォームを使用するすべてのアプリケーションのエントリ ポイントに指定する必要があります。省略すると、Windows コンポーネントが正常に機能しないことがあります。 属性が存在しない場合、アプリケーションは、Windows フォームのサポートされていないマルチ スレッド アパートメント モデルを使用します。

> [!NOTE]
>  [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] アプリケーション フレームワークを使用するプロジェクトをマークする必要はありません、 **Main**メソッドを stathread に設定します。 [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]コンパイラが自動的にことができます。

## <a name="how-to-fix-violations"></a>違反の修正方法
 このルールの違反を修正するには、追加、<xref:System.STAThreadAttribute>エントリ ポイントに属性します。 場合、<xref:System.MTAThreadAttribute?displayProperty=fullName>属性が存在する、それを削除します。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 .NET Compact framework 開発している場合、この規則による警告を抑制するのには安全では、<xref:System.STAThreadAttribute>属性は不要であり、サポートされていません。

## <a name="example"></a>例
 次の例では、正しい使用法<xref:System.STAThreadAttribute>します。

 [!code-csharp[FxCop.Usage.StaThread#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.StaThread/cs/FxCop.Usage.StaThread.cs#1)]
 [!code-vb[FxCop.Usage.StaThread#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.StaThread/vb/FxCop.Usage.StaThread.vb#1)]
