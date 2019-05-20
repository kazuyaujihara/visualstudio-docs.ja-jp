---
title: '方法: インターフェイスを実装する (クラス デザイナー) |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- interfaces [Visual Studio], implementing
- interfaces [Visual Studio]
ms.assetid: 81d2cf46-7f60-448c-83e3-1d16bb88ca36
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 1b437fb34902783002baedee992a21ee61a86c2e
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65685623"
---
# <a name="how-to-implement-an-interface-class-designer"></a>方法: インターフェイスを実装する (クラス デザイナー)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

クラス デザイナーのクラス ダイアグラム上で、インターフェイス メソッド用のコードを提供するクラスに接続して、インターフェイスを実装できます。 クラス デザイナーによってインターフェイス実装が生成され、インターフェイスとクラス間の関係が継承関係として表示されます。 インターフェイスとクラスの間に継承線を描画するか、インターフェイスをクラス ビューからドラッグすることにより、インターフェイスを実装できます。  
  
> [!TIP]
> インターフェイスは、他の型を作成するのと同じ方法で作成できます。 インターフェイスが存在していてもクラス ダイアグラムに表示されていない場合は、最初にインターフェイスを表示します。 詳細については、「[方法 :クラス デザイナーを使用して型を作成する](../ide/how-to-create-types-by-using-class-designer.md)と[方法。既存の型 (クラス デザイナー) を表示](../ide/how-to-view-existing-types-class-designer.md)します。  
  
### <a name="to-implement-an-interface-by-drawing-an-inheritance-line"></a>継承線を描画してインターフェイスを実装するには  
  
1. クラス ダイアグラムで、インターフェイスおよびインターフェイスを実装するクラスを表示します。  
  
2. クラスとインターフェイスから継承線を描画します。  
  
    クラスにアタッチされたロリポップが表示され、インターフェイス名が表示されたラベルによって継承関係が示されます。 Visual Studio は、すべてのインターフェイス メンバーのスタブを生成します。  
  
   詳細については、「[方法 :型 (クラス デザイナー) の間の継承を作成](../ide/how-to-create-inheritance-between-types-class-designer.md)です。  
  
### <a name="to-implement-an-interface-from-the-class-view-window"></a>[クラス ビュー] ウィンドウからインターフェイスを実装するには  
  
1. クラス ダイアグラムで、インターフェイスを実装するクラスを表示します。  
  
2. クラス ビューを開き、インターフェイスを探します。  
  
    > [!TIP]
    > クラス ビューが開いていない場合は、**[表示]** メニューから開きます。 クラス ビューの詳細については、「[クラスとそのメンバーを表示する](https://msdn.microsoft.com/71e9e8f3-261a-4e0c-87bf-5ec48b8bf333)」を参照してください。  
  
3. インターフェイス ノードをダイアグラムのクラスの図形にドラッグします。  
  
     クラスにアタッチされたロリポップが表示され、インターフェイス名が表示されたラベルによって継承関係が示されます。 Visual Studio は、すべてのインターフェイス メンバーのスタブを生成します。この時点で、インターフェイスが実装されます。  
  
## <a name="see-also"></a>関連項目
 [方法: クラス デザイナーを使用して型を作成します。](../ide/how-to-create-types-by-using-class-designer.md)   
 [方法: 既存の型 (クラス デザイナー) を表示します。](../ide/how-to-view-existing-types-class-designer.md)   
 [方法: 型 (クラス デザイナー) の間の継承を作成します。](../ide/how-to-create-inheritance-between-types-class-designer.md)   
 [クラスおよび型のリファクタリング (クラス デザイナー)](../ide/refactoring-classes-and-types-class-designer.md)
