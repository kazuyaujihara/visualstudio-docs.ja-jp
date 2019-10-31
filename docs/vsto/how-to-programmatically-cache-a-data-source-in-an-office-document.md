---
title: プログラムによる Office ドキュメント内のデータソースのキャッシュ
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office applications [Office development in Visual Studio], data
- datasets [Office development in Visual Studio], caching
- StartCaching method
- data caching [Office development in Visual Studio], programmatically
- data [Office development in Visual Studio], caching
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 241ce42c2d411fdaf611f3a7f2b52eb40c8c32a2
ms.sourcegitcommit: 40bd5b27f247a07c2e2514acb293b23d6ce03c29
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2019
ms.locfileid: "73189584"
---
# <a name="how-to-programmatically-cache-a-data-source-in-an-office-document"></a>方法: Office ドキュメント内のデータソースをプログラムによってキャッシュする
  プログラムを使用してデータオブジェクトをドキュメント内のデータキャッシュに追加するには、<xref:Microsoft.Office.Tools.Word.Document>、<xref:Microsoft.Office.Tools.Excel.Workbook>、<xref:Microsoft.Office.Tools.Excel.Worksheet>などのホスト項目の `StartCaching` メソッドを呼び出します。 ホスト項目の `StopCaching` メソッドを呼び出して、データキャッシュからデータオブジェクトを削除します。

 `StartCaching` メソッドと `StopCaching` メソッドはどちらもプライベートですが、IntelliSense に表示されます。

 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]

 `StartCaching` メソッドを使用してデータオブジェクトをデータキャッシュに追加する場合、データオブジェクトは、<xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute> 属性を使用して宣言する必要はありません。 ただし、データオブジェクトは、データキャッシュに追加する特定の要件を満たしている必要があります。 詳細については、「[データのキャッシュ](../vsto/caching-data.md)」を参照してください。

## <a name="to-programmatically-cache-a-data-object"></a>データオブジェクトをプログラムでキャッシュするには

1. データオブジェクトは、メソッドの内部ではなく、クラスレベルで宣言します。 この例では、プログラムでキャッシュする `dataSet1` という名前の <xref:System.Data.DataSet> を宣言していることを前提としています。

     [!code-csharp[Trin_VstcoreDataExcel#12](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#12)]
     [!code-vb[Trin_VstcoreDataExcel#12](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet1.vb#12)]

2. データオブジェクトをインスタンス化し、ドキュメントまたはワークシートインスタンスの `StartCaching` メソッドを呼び出して、データオブジェクトの名前を渡します。

     [!code-csharp[Trin_VstcoreDataExcel#13](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#13)]
     [!code-vb[Trin_VstcoreDataExcel#13](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet1.vb#13)]

## <a name="to-stop-caching-a-data-object"></a>データオブジェクトのキャッシュを停止するには

1. ドキュメントまたはワークシートインスタンスの `StopCaching` メソッドを呼び出し、データオブジェクトの名前を渡します。 この例では、キャッシュを停止する `dataSet1` という名前の <xref:System.Data.DataSet> があることを前提としています。

     [!code-csharp[Trin_VstcoreDataExcel#14](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#14)]
     [!code-vb[Trin_VstcoreDataExcel#14](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet1.vb#14)]

    > [!NOTE]
    > ドキュメントまたはワークシートの `Shutdown` イベントのイベントハンドラーから `StopCaching` を呼び出さないでください。 `Shutdown` イベントが発生した時点までに、データキャッシュを変更するには遅すぎます。 `Shutdown` イベントの詳細については、「 [Office プロジェクトのイベント](../vsto/events-in-office-projects.md)」を参照してください。

## <a name="see-also"></a>関連項目

- [データのキャッシュ](../vsto/caching-data.md)
- [方法: オフラインまたはサーバーで使用するデータをキャッシュする](../vsto/how-to-cache-data-for-use-offline-or-on-a-server.md)
- [方法: パスワードで保護されたドキュメントでデータをキャッシュする](../vsto/how-to-cache-data-in-a-password-protected-document.md)
- [サーバー上のドキュメントのデータにアクセスする](../vsto/accessing-data-in-documents-on-the-server.md)
- [データの保存](../data-tools/save-data-back-to-the-database.md)
