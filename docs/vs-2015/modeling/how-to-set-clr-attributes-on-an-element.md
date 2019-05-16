---
title: '方法: 要素の CLR 属性の設定 |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
f1_keywords:
- vs.dsltools.EditAttributesDialog
helpviewer_keywords:
- Domain-Specific Language, custom attrributes
ms.assetid: b3db3c74-920c-4701-9544-6f75cbe8b7c9
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: f9af25934a40c01c6b4cfd48dcd7419bddf322d3
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65698028"
---
# <a name="how-to-set-clr-attributes-on-an-element"></a>方法: 要素の CLR 属性を設定する
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

カスタム属性は、ドメイン要素、図形、コネクタ、およびダイアグラムを追加できる特別な属性です。 継承する任意の属性を追加することができます、`System.Attribute`クラス。  
  
### <a name="to-add-a-custom-attribute"></a>カスタム属性を追加するには  
  
1. **DSL エクスプ ローラー**、カスタム属性を追加する要素を選択します。  
  
2. **プロパティ**ウィンドウ、次へ を**カスタム属性**プロパティで、参照 をクリックします (**...**) アイコン。  
  
     **属性の編集** ダイアログ ボックスが表示されます。  
  
3. **名前**列、 をクリックして **\<属性の追加>** 属性の名前を入力します。 ENTER キーを押します。  
  
4. 属性名の下にある行は、かっこを示しています。 この行に入力属性のパラメーターの型 (たとえば、 `string`)、し、ENTER キーを押します。  
  
5. **Name プロパティ**列で、たとえば、適切な名前を入力`MyString`します。  
  
6. **[OK]** をクリックします。  
  
     **カスタム属性**プロパティは、次の形式で属性を表示するようになりました。  
  
     `[` *AttributeName* `(` *ParameterName* `=` *Type* `)]`  
  
## <a name="see-also"></a>関連項目  
 [ドメイン固有言語ツールの用語集](https://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)
