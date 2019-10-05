---
title: CA1300:MessageBoxOption を指定します
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- SpecifyMessageBoxOptions
- CA1300
helpviewer_keywords:
- SpecifyMessageBoxOptions
- CA1300
ms.assetid: 9357a724-026e-4a3d-a03a-f14635064ec6
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 746475e60bbe72c4ebfc51f13d0b2d4d0552ff62
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71235190"
---
# <a name="ca1300-specify-messageboxoptions"></a>CA1300:MessageBoxOption を指定します

|||
|-|-|
|TypeName|SpecifyMessageBoxOptions|
|CheckId|CA1300|
|カテゴリ|Microsoft のグローバリゼーション|
|互換性に影響する変更点|なし|

## <a name="cause"></a>原因

メソッドは、引数を<xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=fullName> <xref:System.Windows.Forms.MessageBoxOptions?displayProperty=fullName>受け取らないメソッドのオーバーロードを呼び出します。

## <a name="rule-description"></a>規則の説明

右から左への読み取り順序を使用するカルチャに対してメッセージボックスを正しく表示するには、 [messageboxoptions](<xref:System.Windows.Forms.MessageBoxOptions.RightAlign>)を渡して、 <xref:System.Windows.Forms.MessageBox.Show%2A>メソッドにフィールドを[読み込みます](<xref:System.Windows.Forms.MessageBoxOptions.RtlReading>)。 格納し<xref:System.Windows.Forms.Control.RightToLeft%2A?displayProperty=fullName>ているコントロールのプロパティを調べて、右から左への読み取り順序を使用するかどうかを判断します。

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則違反を修正するには、引数を<xref:System.Windows.Forms.MessageBox.Show%2A> <xref:System.Windows.Forms.MessageBoxOptions>受け取るメソッドのオーバーロードを呼び出します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

右から左への読み取り順序を使用するカルチャに対してコードライブラリがローカライズされない場合は、この規則による警告を抑制しても安全です。

## <a name="example"></a>例

次の例は、カルチャの読み取り順序に適したオプションを持つメッセージボックスを表示するメソッドを示しています。 例をビルドするには、表示されていないリソースファイルが必要です。 例のコメントに従って、リソースファイルを使用せずに例をビルドし、右から左へ記述する機能をテストします。

[!code-vb[FxCop.Globalization.SpecifyMBOptions#1](../code-quality/codesnippet/VisualBasic/ca1300-specify-messageboxoptions_1.vb)]
[!code-csharp[FxCop.Globalization.SpecifyMBOptions#1](../code-quality/codesnippet/CSharp/ca1300-specify-messageboxoptions_1.cs)]

## <a name="see-also"></a>関連項目

- <xref:System.Resources.ResourceManager?displayProperty=fullName>
- [デスクトップ アプリケーションのリソース (.NET Framework)](/dotnet/framework/resources/index)