---
title: データセットを XML として保存する
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- XML [Visual Basic], datasets
- data [Visual Studio], saving as XML
- datasets [Visual Basic], saving as XML
- saving data
ms.assetid: 68b8327c-ae05-49ff-b9ba-99183e70b52c
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: 5b3aa23cb0fde98b4da4225b8e255b7cd6e7aef5
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72641354"
---
# <a name="save-a-dataset-as-xml"></a>データセットを XML として保存する

データセットの使用可能な XML メソッドを呼び出すことによって、データセット内の XML データにアクセスします。 XML 形式でデータを保存するには、<xref:System.Data.DataSet.GetXml%2A> メソッドまたは <xref:System.Data.DataSet> の <xref:System.Data.DataSet.WriteXml%2A> メソッドのいずれかを呼び出すことができます。

@No__t_0 メソッドを呼び出すと、XML として書式設定されたデータセット内のすべてのデータテーブルのデータを含む文字列が返されます。

@No__t_0 メソッドを呼び出すと、指定したファイルに XML 形式のデータが送信されます。

## <a name="to-save-the-data-in-a-dataset-as-xml-to-a-variable"></a>データセットのデータを XML として変数に保存するには

- <xref:System.Data.DataSet.GetXml%2A> メソッドは <xref:System.String> を返します。 @No__t_0 型の変数を宣言し、<xref:System.Data.DataSet.GetXml%2A> メソッドの結果を代入します。

     [!code-vb[VbRaddataSaving#12](../data-tools/codesnippet/VisualBasic/save-a-dataset-as-xml_1.vb)]
     [!code-csharp[VbRaddataSaving#12](../data-tools/codesnippet/CSharp/save-a-dataset-as-xml_1.cs)]

## <a name="to-save-the-data-in-a-dataset-as-xml-to-a-file"></a>データセットのデータを XML としてファイルに保存するには

- @No__t_0 メソッドにはいくつかのオーバーロードがあります。 変数を宣言し、ファイルを保存する有効なパスを割り当てます。 次のコードは、データをファイルに保存する方法を示しています。

     [!code-vb[VbRaddataSaving#13](../data-tools/codesnippet/VisualBasic/save-a-dataset-as-xml_2.vb)]
     [!code-csharp[VbRaddataSaving#13](../data-tools/codesnippet/CSharp/save-a-dataset-as-xml_2.cs)]

## <a name="see-also"></a>関連項目

- [データをデータベースに保存する](../data-tools/save-data-back-to-the-database.md)