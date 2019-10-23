---
title: データセットを XML として保存する |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- XML [Visual Basic], datasets
- data [Visual Studio], saving as XML
- datasets [Visual Basic], saving as XML
- saving data
ms.assetid: 68b8327c-ae05-49ff-b9ba-99183e70b52c
caps.latest.revision: 14
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: e64c3c17934e5cdc5d6ca1f510c7164b86a77c1a
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72652856"
---
# <a name="save-a-dataset-as-xml"></a>データセットを XML として保存する
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

データセット内の XML データには、データセットの使用可能な XML メソッドを呼び出すことによってアクセスできます。 XML 形式でデータを保存するには、<xref:System.Data.DataSet.GetXml%2A> メソッドまたは <xref:System.Data.DataSet> の <xref:System.Data.DataSet.WriteXml%2A> メソッドのいずれかを呼び出すことができます。

 @No__t_0 メソッドを呼び出すと、XML として書式設定されたデータセット内のすべてのデータテーブルのデータを含む文字列が返されます。

 @No__t_0 メソッドを呼び出すと、指定したファイルに XML 形式のデータが送信されます。

### <a name="to-save-the-data-in-a-dataset-as-xml-to-a-variable"></a>データセットのデータを XML として変数に保存するには

- @No__t_0 メソッドは、<xref:System.String> を返します。これは <xref:System.String> 型の変数を宣言し、<xref:System.Data.DataSet.GetXml%2A> メソッドの結果を割り当てることを意味します。

     [!code-csharp[VbRaddataSaving#12](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Class1.cs#12)]
     [!code-vb[VbRaddataSaving#12](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Class1.vb#12)]

### <a name="to-save-the-data-in-a-dataset-as-xml-to-a-file"></a>データセットのデータを XML としてファイルに保存するには

- @No__t_0 メソッドにはいくつかのオーバーロードがあります。 次のコードは、データをファイルに保存する方法を示しています。変数を宣言し、ファイルを保存する有効なパスを割り当てます。

     [!code-csharp[VbRaddataSaving#13](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataSaving/CS/Class1.cs#13)]
     [!code-vb[VbRaddataSaving#13](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataSaving/VB/Class1.vb#13)]

## <a name="see-also"></a>参照
 [データをデータベースに保存する](../data-tools/save-data-back-to-the-database.md)
