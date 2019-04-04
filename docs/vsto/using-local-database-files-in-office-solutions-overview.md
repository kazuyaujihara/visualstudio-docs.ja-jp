---
title: Office ソリューションの概要でのローカル データベース ファイルを使用します。
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office applications [Office development in Visual Studio], data
- data [Office development in Visual Studio], local
- local data [Office development in Visual Studio]
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: ea260a6286c8a923d56ab7a5088b55de57004489
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56645538"
---
# <a name="use-local-database-files-in-office-solutions-overview"></a>Office ソリューションの概要でのローカル データベース ファイルを使用します。
  SQL Server Express などのデータベース ファイルを含めることができます (*.mdf*) ファイルまたは Microsoft Office の Access (*.mdb*)、Office ソリューションでのファイル。 これにより、エンドユーザーを一元的なデータベースを保守する必要がない状況、1 台のコンピューターのみで使用されるローカル inventory ソリューションの例ではローカル データベースを維持するためにできます。

 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]

## <a name="import-the-database-file-into-a-project"></a>データベース ファイルをプロジェクトにインポートします。
 プロジェクトには、データベース ファイルをインポートするには、使用、**データ ソース構成ウィザード**データベース ファイルに基づくデータ ソースを作成します。 ウィザードでは、データベース ファイルと型指定されたデータセットをプロジェクトに追加します。

## <a name="deploy-the-database-file"></a>データベース ファイルを展開します。
 **データ ソース構成ウィザード**相対パスを使用して、ローカル データベース ファイルへの接続を作成します。 これにより、ファイルの相対位置を保持している場合に、1 台のコンピューターから、ソリューションを別にコピーすることができます。

 ソリューションをサーバーに配置して、ドキュメントをエンドユーザーに配布も手動でデータベース ファイルを配布して、ドキュメントを基準と同じ位置にインストールする必要があります。 つまり、そのユーザーは、データベース ファイルを移動もしない限り、エンド ユーザーが自分のコンピューターで、新しい場所にドキュメントを移動できないことです。

## <a name="local-database-files-and-caching-the-dataset"></a>ローカル データベース ファイルと、データセットのキャッシュ
 Microsoft Office Excel および Microsoft Office Word のドキュメント レベルのソリューションでは、属性を持つデータセットのインスタンスをマークすることで、ドキュメント内のデータセットをキャッシュできます<xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute>します。 追加すると、データベース ファイル、プロジェクトを使用して、**データ ソース構成ウィザード**、型指定されたデータセットが自動的にプロジェクトに追加されます。 適用する必要はありません<xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute>、このデータセットにデータがローカル ユーザーのコンピューターに既にあるためです。 詳細については、[データ キャッシュ](../vsto/caching-data.md)を参照してください。

## <a name="see-also"></a>関連項目
- [Office ソリューションでのコントロールにデータをバインドします。](../vsto/binding-data-to-controls-in-office-solutions.md)
- [方法: データベースからデータをドキュメントに読み込む](../vsto/how-to-populate-documents-with-data-from-a-database.md)
- [方法: ホスト コントロールからのデータでデータ ソースを更新します。](../vsto/how-to-update-a-data-source-with-data-from-a-host-control.md)
- [Office ソリューションのデプロイ](../vsto/deploying-an-office-solution.md)
- [キャッシュ データ](../vsto/caching-data.md)
