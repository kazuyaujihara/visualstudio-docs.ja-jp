---
title: '方法: メンバー表記と関連付け表記 (クラス デザイナー) の間の変更 |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- notation, member
- association notation
- member notation
- notation, association
ms.assetid: 65881c5a-d251-4a36-ad0d-73d088436092
caps.latest.revision: 25
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 2c0e691cd162a52dc598f9d3dc4d9a04e0f8f008
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63439290"
---
# <a name="how-to-change-between-member-notation-and-association-notation-class-designer"></a>方法: メンバー表記と関連付け表記の間で変更する (クラス デザイナー)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

クラス デザイナーでは、クラス ダイアグラムで 2 つの型の間の関連付けの関係が表される方法を、メンバー表記から関連付け表記に、またはその逆に、変更できます。 関連行として表示されるメンバーは、多くの場合、型の関連をわかりやすく視覚化します。  
  
> [!NOTE]
> 関連付けの関係は、メンバー プロパティまたはフィールドとして表すことができます。 メンバー表記を関連付け表記に変更するには、一方の型に別の型のメンバーが含まれている必要があります。 関連付け表記をメンバー表記に変更するには、2 つの型が関連行によって接続されている必要があります。 詳細については、「[方法 :型 (クラス デザイナー) の間の関連付けを作成](../ide/how-to-create-associations-between-types-class-designer.md)です。 プロジェクトに複数のクラス ダイアグラムが含まれている場合、ダイアグラムでの関連付けの関係の表示方法に対する変更は、そのダイアグラムだけに適用されます。 別のダイアグラムでの関連付けの関係の表示方法を変更するには、そのダイアグラムを開くか表示して、次の手順を実行します。  
  
### <a name="to-change-member-notation-to-association-notation"></a>メンバー表記を関連付け表記に変更するには  
  
1. ソリューション エクスプローラーのプロジェクト ノードから、クラス ダイアグラム (.cd) ファイルを開きます。  
  
2. クラス ダイアグラムの型の図形で、メンバー プロパティまたは関連付けを表すフィールドを右クリックして、**[関連として表示]** を選びます。  
  
    > [!TIP]
    > 型の図形にプロパティまたはフィールドが表示されていない場合は、図形のコンパートメントが折りたたまれている可能性があります。 型の図形を展開するには、コンパートメントの名前をダブルクリックするか、または型の図形を右クリックして **[展開]** を選びます。  
  
     型の図形のコンパートメントにメンバーが表示されなくなり、2 つの型を接続する関連行が表示されます。 関連行のラベルには、プロパティまたはフィールドの名前が表示されます。  
  
### <a name="to-change-association-notation-to-member-notation"></a>関連付け表記をメンバー表記に変更するには  
  
- クラス ダイアグラムで関連行を右クリックし、**[プロパティとして表示]** または **[フィールドとして表示]** を選びます。  
  
     関連行が表示されなくなり、ダイアグラムの型の図形内の適切なコンパートメントにプロパティが表示されます。  
  
## <a name="see-also"></a>関連項目  
 [方法: 型 (クラス デザイナー) の間の継承を作成します。](../ide/how-to-create-inheritance-between-types-class-designer.md)   
 [方法: 型 (クラス デザイナー) の間の継承を表示](../ide/how-to-view-inheritance-between-types-class-designer.md)   
 [型およびリレーションシップの表示 (クラス デザイナー)](../ide/viewing-types-and-relationships-class-designer.md)   
 [方法: コレクションの関連付けをビジュアル化する (クラス デザイナー)](../ide/how-to-visualize-a-collection-association-class-designer.md)
