---
title: CA1500:変数名はフィールド名と同一にすることはできません
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- VariableNamesShouldNotMatchFieldNames
- CA1500
helpviewer_keywords:
- VariableNamesShouldNotMatchFieldNames
- CA1500
ms.assetid: fa0e5029-79e9-4a33-8576-787ac3c26c39
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: fbc3fbeac6d01b718af2022a09bddb92e9c7c2c6
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71234572"
---
# <a name="ca1500-variable-names-should-not-match-field-names"></a>CA1500:変数名はフィールド名と同一にすることはできません

|||
|-|-|
|TypeName|VariableNamesShouldNotMatchFieldNames|
|CheckId|CA1500|
|カテゴリ|Microsoft の保守容易性|
|互換性に影響する変更点|フィールドと同じ名前を持つパラメーターで発生した場合は、次のようになります。<br /><br /> -非互換性-加えられた変更に関係なく、パラメーターを宣言するフィールドとメソッドの両方がアセンブリの外部に表示されない場合。<br />-中断-フィールドの名前を変更すると、アセンブリの外部に表示される場合があります。<br />-中断-パラメーターの名前を変更すると、そのパラメーターを宣言するメソッドがアセンブリの外部に表示される可能性があります。<br /><br /> フィールドと同じ名前を持つローカル変数でが発生した場合は、次のようになります。<br /><br /> -中断されていない-行った変更に関係なく、アセンブリの外部にフィールドを表示できない場合。<br />-非互換性-ローカル変数の名前を変更し、フィールドの名前を変更しない場合。<br />-中断-フィールドの名前を変更すると、アセンブリの外部に表示される場合があります。|

## <a name="cause"></a>原因

インスタンスメソッドは、宣言する型のインスタンスフィールドと名前が一致するパラメーターまたはローカル変数を宣言します。 規則に違反するローカル変数をキャッチするには、デバッグ情報を使用してテストされたアセンブリをビルドし、関連付けられているプログラムデータベース (.pdb) ファイルを使用できるようにする必要があります。

## <a name="rule-description"></a>規則の説明

インスタンスフィールドの名前がパラメーターまたはローカル変数名と一致する場合、インスタンスフィールドは、メソッド本体の内部`this`で`Me` ( [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]in) キーワードを使用してアクセスされます。 コードを維持する場合は、この違いを忘れがちであり、パラメーター/ローカル変数がインスタンスフィールドを参照していることを前提として、エラーが発生します。 これは特に長いメソッド本体の場合に当てはまります。

## <a name="how-to-fix-violations"></a>違反の修正方法

この規則違反を修正するには、パラメーター/変数またはフィールドのいずれかの名前を変更します。

## <a name="when-to-suppress-warnings"></a>警告を非表示にする場合

この規則による警告は抑制しないでください。

## <a name="example"></a>例

次の例は、規則の2つの違反を示しています。

[!code-vb[FxCop.Maintainability.VarMatchesField#1](../code-quality/codesnippet/VisualBasic/ca1500-variable-names-should-not-match-field-names_1.vb)]
[!code-csharp[FxCop.Maintainability.VarMatchesField#1](../code-quality/codesnippet/CSharp/ca1500-variable-names-should-not-match-field-names_1.cs)]