---
title: プロパティ&lt;プロパティ名&gt;削除することはできません |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
ms.assetid: 55873f74-7834-4ec1-8815-eeeb65618d87
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 50e91c47ef848eda51fe71c9dce09cd1ea4893a8
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68152094"
---
# <a name="the-property-ltproperty-namegt-cannot-be-deleted"></a>プロパティ&lt;プロパティ名&gt;を削除できません
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

プロパティ\<プロパティ名 > の間の継承に対する識別子のプロパティとして設定されているために削除できません\<クラス名 > と\<クラス名 >  
  
 選択されたプロパティは、エラー メッセージに示されているクラス間の継承に対する**識別子のプロパティ**として設定されています。 プロパティがデータ クラス間の継承構成に関与している場合、そのプロパティを削除することはできません。  
  
 **識別子のプロパティ**をデータ クラスの別のプロパティに設定して、目的のプロパティが正常に削除されるようにしてください。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
1. O/R デザイナーで、エラー メッセージに示されているデータ クラスを接続する継承線を選択します。  
  
2. **識別子** プロパティを別のプロパティに設定します。  
  
3. プロパティの削除を再試行します。  
  
## <a name="see-also"></a>関連項目  
 [方法: O/R デザイナーを使用して継承を構成します。](../data-tools/how-to-configure-inheritance-by-using-the-o-r-designer.md)   
 [データ クラスの継承 (O/R デザイナー)](../data-tools/data-class-inheritance-o-r-designer.md)   
 [チュートリアル: 単一テーブル継承を使用した LINQ to SQL クラスの作成 (O/R デザイナー)](../data-tools/walkthrough-creating-linq-to-sql-classes-by-using-single-table-inheritance-o-r-designer.md)
