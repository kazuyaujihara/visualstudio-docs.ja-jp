---
title: '方法: (クラス デザイナー) のプロジェクトにクラス ダイアグラムを追加する |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- class diagrams, creating
- Class Designer [Visual Studio], opening
ms.assetid: 0eac1b54-2711-4e4b-9654-a0c429c08c8f
caps.latest.revision: 43
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 3ab062ea6f7dfac6001d016704d627c716079989
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54760267"
---
# <a name="how-to-add-class-diagrams-to-projects-class-designer"></a>方法: プロジェクトにクラス ダイアグラムを追加する (クラス デザイナー)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

クラスおよび他の型の設計、編集およびリファクタリングを行うには、クラス ダイアグラムを Visual C# .NET、Visual Basic .NET、または C++ プロジェクトに追加します。 プロジェクト内のコードの異なる部分を視覚化するには、複数のクラス ダイアグラムをプロジェクトに追加します。  
  
 複数のアプリでコードを共有しているプロジェクトからは、クラス ダイアグラムを作成できません。 UML クラス ダイアグラムを作成するには、「[UML モデリング プロジェクトおよびダイアグラムを作成する](../modeling/create-uml-modeling-projects-and-diagrams.md)」を参照してください。  
  
### <a name="to-add-a-blank-class-diagram-to-a-project"></a>プロジェクトに空のクラス ダイアグラムを追加するには  
  
1.  ソリューション エクスプローラーで、プロジェクト名を右クリックします。 次に、**[新しい項目の追加]** または **[追加]**、**[新しい項目]** をクリックします。  
  
2.  テンプレートの一覧から、**[クラス ダイアグラム]** を選択します。 Visual C++ のプロジェクトの場合、このテンプレートを見つけるには、**[テンプレート]** の下にある **[ユーティリティ]** を探します。  
  
     クラス デザイナーでクラス ダイアグラムが開き、ソリューション エクスプローラーのプロジェクト階層に .cd 拡張子付きのファイルとして表示されます。 図形や線をダイアグラムにドラッグするには、クラス デザイナーのツールボックスを使用します。  
  
3.  複数のクラス ダイアグラムを追加するには、この手順を繰り返します。  
  
### <a name="to-add-a-class-diagram-based-on-existing-types"></a>既存の型に基づいてクラス ダイアグラムを追加するには  
  
1.  ソリューション エクスプローラーで、クラス ファイル コンテキスト メニューを開き、**[クラス ダイアグラムの表示]** をクリックします。  
  
     - または -  
  
     **[クラス ビュー]** で、名前空間または型のコンテキスト メニューを開き、**[クラス ダイアグラムで表示]** を選択します。  
  
### <a name="to-display-the-contents-of-a-complete-project-in-a-class-diagram"></a>クラス ダイアグラムに完全なプロジェクトの内容を表示するには  
  
1.  ソリューション エクスプローラーまたはクラス ビューで、プロジェクトを右クリックし、**[表示]** を選択してから **[クラス ダイアグラムの表示]** を選択します。  
  
     自動設定されたクラス ダイアグラムが作成されます。  
  
## <a name="see-also"></a>関連項目
 [方法: クラス デザイナーを使用して型を作成する](../ide/how-to-create-types-by-using-class-designer.md)   
 [方法: 既存の型を表示する (クラス デザイナー)](../ide/how-to-view-existing-types-class-designer.md)   
 [クラスおよび型のデザイン (クラス デザイナー)](../ide/designing-classes-and-types-class-designer.md)   
 [型およびリレーションシップの表示 (クラス デザイナー)](../ide/viewing-types-and-relationships-class-designer.md)   
 [クラス ダイアグラムの使用 (クラス デザイナー)](../ide/working-with-class-diagrams-class-designer.md)
