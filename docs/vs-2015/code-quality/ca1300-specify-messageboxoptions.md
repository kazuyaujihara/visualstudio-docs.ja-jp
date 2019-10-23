---
title: 'CA1300: MessageBoxOptions | を指定します。Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- SpecifyMessageBoxOptions
- CA1300
helpviewer_keywords:
- SpecifyMessageBoxOptions
- CA1300
ms.assetid: 9357a724-026e-4a3d-a03a-f14635064ec6
caps.latest.revision: 21
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 3e21866fce69f768d927882d3ddd47ae3e431265
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72663604"
---
# <a name="ca1300-specify-messageboxoptions"></a>CA1300: MessageBoxOption を指定します
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|SpecifyMessageBoxOptions|
|CheckId|CA1300|
|カテゴリ|Microsoft のグローバリゼーション|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因
 メソッドは、<xref:System.Windows.Forms.MessageBoxOptions?displayProperty=fullName> 引数を受け取らない <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=fullName> メソッドのオーバーロードを呼び出します。

## <a name="rule-description"></a>規則の説明
 右から左への読み取り順序を使用するカルチャに対してメッセージボックスを正しく表示するには、<xref:System.Windows.Forms.MessageBoxOptions> 列挙体の <xref:System.Windows.Forms.MessageBoxOptions> メンバーと <xref:System.Windows.Forms.MessageBoxOptions> メンバーを <xref:System.Windows.Forms.MessageBox.Show%2A> メソッドに渡す必要があります。 格納しているコントロールの <xref:System.Windows.Forms.Control.RightToLeft%2A?displayProperty=fullName> プロパティを調べて、右から左への読み取り順序を使用するかどうかを判断します。

## <a name="how-to-fix-violations"></a>違反の修正方法
 この規則違反を修正するには、<xref:System.Windows.Forms.MessageBoxOptions> 引数を受け取る <xref:System.Windows.Forms.MessageBox.Show%2A> メソッドのオーバーロードを呼び出します。

## <a name="when-to-suppress-warnings"></a>警告を抑制する状況
 右から左への読み取り順序を使用するカルチャに対してコードライブラリがローカライズされない場合は、この規則による警告を抑制しても安全です。

## <a name="example"></a>例
 次の例は、カルチャの読み取り順序に適したオプションを持つメッセージボックスを表示するメソッドを示しています。 例をビルドするには、表示されていないリソースファイルが必要です。 例のコメントに従って、リソースファイルを使用せずに例をビルドし、右から左へ記述する機能をテストします。

 [!code-csharp[FxCop.Globalization.SpecifyMBOptions#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Globalization.SpecifyMBOptions/cs/FxCop.Globalization.SpecifyMBOptions.cs#1)]
 [!code-vb[FxCop.Globalization.SpecifyMBOptions#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Globalization.SpecifyMBOptions/vb/FxCop.Globalization.SpecifyMBOptions.vb#1)]

## <a name="see-also"></a>参照
 [デスクトップアプリでのリソースの](https://msdn.microsoft.com/library/8ad495d4-2941-40cf-bf64-e82e85825890)<xref:System.Resources.ResourceManager?displayProperty=fullName>
