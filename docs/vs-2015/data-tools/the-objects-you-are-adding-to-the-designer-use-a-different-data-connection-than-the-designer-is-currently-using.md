---
title: デザイナーに追加しようとしているオブジェクトは、デザイナーが現在使用しているものとは異なるデータ接続を使用しています。Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
ms.assetid: 332ed2f3-3377-4d51-8e3b-fdb98231978e
caps.latest.revision: 7
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: d9ec76446aff930475ea5e3ca0133e11b3798b0c
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72672302"
---
# <a name="the-objects-you-are-adding-to-the-designer-use-a-different-data-connection-than-the-designer-is-currently-using"></a>デザイナーに追加する対象のオブジェクトは、デザイナーが現在使用しているのとは異なるデータ接続を使用しています
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

デザイナーに追加する対象のオブジェクトは、デザイナーが現在使用しているのとは異なるデータ接続を使用しています。 デザイナーが使用している接続に置き換えますか?

 @No__t_0 ([!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]) に項目を追加すると、すべての項目が1つの共有データ接続を使用します。 (デザインサーフェイスは、サーフェイス上のすべてのオブジェクトに対して単一の接続を使用する <xref:System.Data.Linq.DataContext> を表します)。デザイナーで現在使用されているデータ接続とは異なるデータ接続を使用するオブジェクトをデザイナーに追加すると、このメッセージが表示されます。 このエラーを解決するために、既存の接続を維持するように選択できます。 その場合、選択したオブジェクトは追加されません。 別の方法として、オブジェクトを追加し、<xref:System.Data.Linq.DataContext> 接続を新しい接続にリセットすることもできます。

> [!NOTE]
> **[はい]** をクリックすると、[!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)] のすべてのエンティティクラスが新しい接続にマップされます。

### <a name="to-replace-the-existing-connection-with-the-connection-used-by-the-selected-object"></a>選択したオブジェクトで使用されている接続で既存の接続を置換するには

- **[はい]** をクリックします。

     選択したオブジェクトが [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]に追加され、DataContext.Connection が新しい接続に設定されます。

### <a name="to-continue-to-use-the-existing-connection-and-cancel-adding-the-selected-object"></a>既存の接続を引き続き使用し、選択したオブジェクトの追加を取り消すには

- **[いいえ]** をクリックします。

     操作がキャンセルされます。 DataContext.Connection は、既存の接続に設定されたままになります。

## <a name="see-also"></a>関連項目
 [Visual Studio LINQ to SQL の ](../data-tools/linq-to-sql-tools-in-visual-studio2.md) [LINQ to SQL ツール](https://msdn.microsoft.com/library/73d13345-eece-471a-af40-4cc7a2f11655)