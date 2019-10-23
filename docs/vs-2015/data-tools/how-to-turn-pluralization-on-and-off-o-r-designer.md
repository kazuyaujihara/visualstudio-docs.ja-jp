---
title: '方法: 複数形化をオンまたはオフにする (O/R デザイナー) |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
ms.assetid: 9b693bc3-303a-40a9-97ee-9cef5ca3ae81
caps.latest.revision: 6
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: afe8c8a4429efb83c09d80a5dd00dfe08b0d63e3
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72665941"
---
# <a name="how-to-turn-pluralization-on-and-off-or-designer"></a>方法: 複数形化をオンおよびオフにする (O/R デザイナー)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

既定では、名前がで終わるか**サーバーエクスプローラー** **データベースエクスプローラー** / で始まるデータベースオブジェクトを[Visual Studio の LINQ to SQL ツール](../data-tools/linq-to-sql-tools-in-visual-studio2.md)にドラッグすると、生成されたエンティティクラスの名前が複数形から特異. この処理は、インスタンス化されたエンティティ クラスが単一のデータ レコードにマップされるという事実をより正確に表すために行われます。 たとえば、Customers テーブルを [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]に追加すると、Customer という名前のエンティティ クラスが生成されます。このクラスには、単一の顧客のみが保持されるためです。

> [!NOTE]
> 複数形化は、英語バージョンの Visual Studio でのみ、既定でオンになります。

 [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]

### <a name="to-turn-pluralization-on-and-off"></a>複数形化をオンまたはオフにするには

1. **[ツール]** メニューの **[オプション]** をクリックします。

2. **[オプション]** ダイアログ ボックスの **[データベース ツール]** を展開します。

> [!NOTE]
> **[データベース ツール]** ノードが表示されない場合は、 **[すべての設定を表示]** を選択します。

1. **[O/R デザイナー]** をクリックします。

2. **名前の複数形化**を**Enabled**に設定すると、クラス名を変更しないように [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)] を設定  = **False**になります。

3. **名前の複数形化**を  =  **Enabled**に**設定すると**、[!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)] に追加されたオブジェクトのクラス名に複数形化規則が適用されます。

## <a name="see-also"></a>参照
 Visual studio[の LINQ to SQL ツール](../data-tools/linq-to-sql-tools-in-visual-studio2.md) [LINQ to SQL](https://msdn.microsoft.com/library/73d13345-eece-471a-af40-4cc7a2f11655) [visual studio でのデータへのアクセス](../data-tools/accessing-data-in-visual-studio.md)
