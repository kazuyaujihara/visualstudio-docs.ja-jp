---
title: CA2232:Windows フォームのエントリ ポイントを STAThread に設定します
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- MarkWindowsFormsEntryPointsWithStaThread
- CA2232
helpviewer_keywords:
- CA2232
- MarkWindowsFormsEntryPointsWithStaThread
ms.assetid: a3c95130-8e7f-4419-9fcd-b67d077e8efb
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: dd3f5b76015a3a54ee085b5cc2dd532920ff0795
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68920174"
---
# <a name="ca2232-mark-windows-forms-entry-points-with-stathread"></a>CA2232:Windows フォームのエントリ ポイントを STAThread に設定します

|||
|-|-|
|TypeName|MarkWindowsFormsEntryPointsWithStaThread|
|CheckId|CA2232|
|Category|Microsoft.Usage|
|互換性に影響する変更点|中断なし|

## <a name="cause"></a>原因
アセンブリが<xref:System.Windows.Forms>名前空間を参照し、そのエントリポイントが<xref:System.STAThreadAttribute?displayProperty=fullName>属性でマークされていません。

## <a name="rule-description"></a>規則の説明
 <xref:System.STAThreadAttribute>アプリケーションの COM スレッドモデルがシングルスレッドアパートメントであることを示します。 この属性は、Windows フォームを使用するすべてのアプリケーションのエントリ ポイントに指定する必要があります。省略すると、Windows コンポーネントが正常に機能しないことがあります。 属性が存在しない場合、アプリケーションは、Windows フォームでサポートされていないマルチスレッドアパートメントモデルを使用します。

> [!NOTE]
> [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]アプリケーションフレームワークを使用するプロジェクトでは、 **Main**メソッドをスレッドでマークする必要はありません。 コンパイラ[!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]は自動的にこれを行います。

## <a name="how-to-fix-violations"></a>違反の修正方法
この規則違反を修正するには、エントリ<xref:System.STAThreadAttribute>ポイントに属性を追加します。 属性が<xref:System.MTAThreadAttribute?displayProperty=fullName>存在する場合は、削除します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合
<xref:System.STAThreadAttribute>属性が不要でサポートされていない .NET Compact Framework を開発している場合は、この規則からの警告を抑制することが安全です。

## <a name="example"></a>例
次の例は、の<xref:System.STAThreadAttribute>正しい使用方法を示しています。

[!code-csharp[FxCop.Usage.StaThread#1](../code-quality/codesnippet/CSharp/ca2232-mark-windows-forms-entry-points-with-stathread_1.cs)]
[!code-vb[FxCop.Usage.StaThread#1](../code-quality/codesnippet/VisualBasic/ca2232-mark-windows-forms-entry-points-with-stathread_1.vb)]