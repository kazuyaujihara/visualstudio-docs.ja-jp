---
title: '方法: 複数形化をオンおよびオフにする (O-R デザイナー)'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 9b693bc3-303a-40a9-97ee-9cef5ca3ae81
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: 578a6333d1206553db50ce81f2f499da0481456d
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72648338"
---
# <a name="how-to-turn-pluralization-on-and-off-or-designer"></a>方法: 複数形化をオンおよびオフにする (O/R デザイナー)
既定では、名前がで終わるか、**サーバーエクスプローラー**または**データベースエクスプローラー**の名前を持つデータベースオブジェクトを[Visual Studio の LINQ to SQL ツール](../data-tools/linq-to-sql-tools-in-visual-studio2.md)にドラッグすると、生成されたエンティティクラスの名前が複数形から特異. この処理は、インスタンス化されたエンティティ クラスが単一のデータ レコードにマップされるという事実をより正確に表すために行われます。 たとえば、`Customers` テーブルを**O/R デザイナー**に追加すると `Customer` という名前のエンティティクラスが生成されます。これは、クラスが1人の顧客に対してのみデータを保持するためです。

> [!NOTE]
> 複数形化は、英語バージョンの Visual Studio でのみ、既定でオンになります。

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

### <a name="to-turn-pluralization-on-and-off"></a>複数形化をオンまたはオフにするには

1. **[ツール]** メニューの **[オプション]** をクリックします。

2. **[オプション]** ダイアログ ボックスの **[データベース ツール]** を展開します。

    > [!NOTE]
    > **[データベース ツール]** ノードが表示されない場合は、 **[すべての設定を表示]** を選択します。

3. **[O/R デザイナー]** をクリックします。

4. **名前の複数形化**を**Enabled**に設定すると、クラス名を変更しないように**O/R デザイナー**を設定  = **False**になります。

5. **複数形化の名前**を  =  **Enabled**に**設定する**と、 **O/R デザイナー**に追加されたオブジェクトのクラス名に複数形化規則が適用されます。

## <a name="see-also"></a>関連項目

- [Visual Studio の LINQ to SQL ツール](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
- [LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index)
- [Visual Studio でのデータへのアクセス](../data-tools/accessing-data-in-visual-studio.md)