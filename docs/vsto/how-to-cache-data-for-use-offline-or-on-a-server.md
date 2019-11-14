---
title: '方法: オフラインまたはサーバーで使用するデータをキャッシュする'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data caching [Office development in Visual Studio], server use
- Office applications [Office development in Visual Studio], data
- datasets [Office development in Visual Studio], caching
- offline data [Office development in Visual Studio]
- data [Office development in Visual Studio], caching
- data caching [Office development in Visual Studio], offline use
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 551d27cf8d40f2e6e9c996b031fa6c4e0a233355
ms.sourcegitcommit: 40bd5b27f247a07c2e2514acb293b23d6ce03c29
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2019
ms.locfileid: "73189567"
---
# <a name="how-to-cache-data-for-use-offline-or-on-a-server"></a>方法: オフラインまたはサーバーで使用するデータをキャッシュする
  データ項目がドキュメントにキャッシュされるようにマークして、オフラインで使用できるようにすることができます。 これにより、ドキュメントがサーバーに格納されている場合に、ドキュメント内のデータを他のコードで操作することも可能になります。

 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]

 データ項目がコード内で宣言されている場合、または **[プロパティ]** ウィンドウでプロパティを設定することによって <xref:System.Data.DataSet>を使用している場合は、データ項目がキャッシュされるようにマークすることができます。 <xref:System.Data.DataSet> または <xref:System.Data.DataTable>ではないデータ項目をキャッシュする場合は、ドキュメントにキャッシュされている条件を満たしていることを確認します。 詳細については、「[データのキャッシュ](../vsto/caching-data.md)」を参照してください。

> [!NOTE]
> Visual Basic を使用して作成されたデータセット **([** **データソース**] ウィンドウまたは**ツールボックス**から**ドラッグして**、 **CacheInDocument**プロパティが True に設定されているデータセットを含む)) には、キャッシュ内の名前の先頭にアンダースコアが付いています。 たとえば、データセットを作成して**customers**という名前を指定した場合、<xref:Microsoft.VisualStudio.Tools.Applications.CachedDataItem> 名はキャッシュ内の顧客になります **(_s)** 。 このキャッシュされた項目にアクセスするために <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> を使用する場合は、**顧客**ではなく**顧客**を指定する必要があります。

### <a name="to-cache-data-in-the-document-using-code"></a>コードを使用してドキュメントのデータをキャッシュするには

1. データ項目のパブリックフィールドまたはプロパティをプロジェクトのホスト項目クラスのメンバーとして宣言します。たとえば、Word プロジェクトの `ThisDocumen`t クラスや、Excel プロジェクトの `ThisWorkbook` クラスなどです。

2. <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute> 属性をメンバーに適用して、データ項目がドキュメントのデータキャッシュに格納されるようにマークします。 次の例では、この属性を <xref:System.Data.DataSet>のフィールド宣言に適用します。

     [!code-csharp[Trin_VstcoreDataExcel#11](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#11)]
     [!code-vb[Trin_VstcoreDataExcel#11](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet1.vb#11)]

3. データ項目のインスタンスを作成し、必要に応じてデータベースから読み込むコードを追加します。

     データ項目は、最初に作成されたときにのみ読み込まれます。その後、キャッシュはドキュメントと共に保持されます。更新するには、他のコードを記述する必要があります。

### <a name="to-cache-a-dataset-in-the-document-by-using-the-properties-window"></a>プロパティウィンドウを使用してドキュメント内のデータセットをキャッシュするには

1. Visual Studio デザイナーのツールを使用して、データセットをプロジェクトに追加します。たとえば、 **[データソース]** ウィンドウを使用してプロジェクトにデータソースを追加します。

2. データセットのインスタンスをまだ作成していない場合は作成し、デザイナーでインスタンスを選択します。

3. **[プロパティ]** ウィンドウで、 **CacheInDocument**プロパティを**True**に設定します。

     詳細については、「 [Office プロジェクトのプロパティ](../vsto/properties-in-office-projects.md)」を参照してください。

4. **[プロパティ]** ウィンドウで、 **[修飾子]** プロパティを**Public** (既定では**Internal**) に設定します。

## <a name="see-also"></a>関連項目
- [データのキャッシュ](../vsto/caching-data.md)
- [方法: Office ドキュメント内のデータソースをプログラムによってキャッシュする](../vsto/how-to-programmatically-cache-a-data-source-in-an-office-document.md)
- [方法: パスワードで保護されたドキュメントでデータをキャッシュする](../vsto/how-to-cache-data-in-a-password-protected-document.md)
- [サーバー上のドキュメントのデータにアクセスする](../vsto/accessing-data-in-documents-on-the-server.md)
- [データの保存](../data-tools/save-data-back-to-the-database.md)
