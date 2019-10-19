---
title: '方法: 要素の CLR 属性を設定する'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.dsltools.EditAttributesDialog
helpviewer_keywords:
- Domain-Specific Language, custom attrributes
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 07957bd267eba457749eb17a99b1099b8d32be97
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72661149"
---
# <a name="how-to-set-clr-attributes-on-an-element"></a>方法: 要素の CLR 属性を設定する
カスタム属性は、ドメイン要素、図形、コネクタ、および図に追加できる特殊な属性です。 @No__t_0 クラスから継承する任意の属性を追加できます。

### <a name="to-add-a-custom-attribute"></a>カスタム属性を追加するには

1. **DSL エクスプローラー**で、カスタム属性を追加する要素を選択します。

2. **[プロパティ]** ウィンドウで、 **[カスタム属性]** プロパティの横にある参照ボタン (. **[..]** ) をクリックします。

     **[属性の編集]** ダイアログボックスが表示されます。

3. **名前** 列で  **\<add 属性 >** をクリックし、属性の名前を入力します。 ENTER キーを押します。

4. 属性名の下の行には、かっこが表示されます。 この行で、属性のパラメーターの型 (`string` など) を入力し、enter キーを押します。

5. [**名前] プロパティ**列に、適切な名前 (`MyString` など) を入力します。

6. **[OK]** をクリックします。

     **カスタム属性**プロパティの属性が次の形式で表示されるようになりました。

     `[` *AttributeName* `(` *ParameterName* `=`*型*`)]`

## <a name="see-also"></a>参照

- [ドメイン固有言語ツールの用語集](https://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)