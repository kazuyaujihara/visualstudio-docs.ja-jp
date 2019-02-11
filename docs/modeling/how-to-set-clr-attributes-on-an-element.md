---
title: '方法: 要素の CLR 属性を設定する'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.dsltools.EditAttributesDialog
helpviewer_keywords:
- Domain-Specific Language, custom attrributes
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b890a5d3d5c48ad3841075a8ae818d2d37d44f98
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2019
ms.locfileid: "55946627"
---
# <a name="how-to-set-clr-attributes-on-an-element"></a>方法: 要素の CLR 属性を設定する
カスタム属性は、ドメイン要素、図形、コネクタ、およびダイアグラムを追加できる特別な属性です。 継承する任意の属性を追加することができます、`System.Attribute`クラス。

### <a name="to-add-a-custom-attribute"></a>カスタム属性を追加するには

1.  **DSL エクスプ ローラー**、カスタム属性を追加する要素を選択します。

2.  **プロパティ**ウィンドウ、次へ を**カスタム属性**プロパティで、参照 をクリックします (**...**) アイコン。

     **属性の編集** ダイアログ ボックスが表示されます。

3.  **名前**列、 をクリックして**\<属性の追加 >** 属性の名前を入力します。 ENTER キーを押します。

4.  属性名の下にある行は、かっこを示しています。 この行に入力属性のパラメーターの型 (たとえば、 `string`)、し、ENTER キーを押します。

5.  **Name プロパティ**列で、たとえば、適切な名前を入力`MyString`します。

6.  **[OK]** をクリックします。

     **カスタム属性**プロパティは、次の形式で属性を表示するようになりました。

     `[` *AttributeName* `(` *ParameterName* `=` *Type* `)]`

## <a name="see-also"></a>関連項目

- [ドメイン固有言語ツールの用語集](https://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)