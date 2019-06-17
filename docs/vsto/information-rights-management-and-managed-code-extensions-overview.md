---
title: 情報の rights management とマネージ コード拡張機能
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Information Rights Management [Office development in Visual Studio]
- workbooks [Office development in Visual Studio], restricted permissions
- IRM [Office development in Visual Studio]
- documents [Office development in Visual Studio], restricted permissions
- rights management [Office development in Visual Studio]
- Office documents [Office development in Visual Studio, restricted permissions
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: ca8f9d77681e3f11312e5e908a58ac2e292f581b
ms.sourcegitcommit: 13ab9a5ab039b070b9cd9251d0b83dd216477203
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2019
ms.locfileid: "66177741"
---
# <a name="information-rights-management-and-managed-code-extensions-overview"></a>Information rights management とマネージ コード拡張機能の概要
  Microsoft Office Word および Microsoft Office Excel は、Information Rights Management (IRM)、承認されていないユーザーを表示したり、機密情報を変更したりするのに役立つ機能を提供します。 Information Rights Management の動作方法について詳しくは、特定の Office アプリケーションのヘルプを参照してください。

 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]

## <a name="run-code-behind-documents-with-restricted-permissions"></a>制限されたアクセス許可を持つドキュメントの分離コードを実行します。
 ドキュメントまたは既定では、IRM を使用するブックで、ソリューションが含まれている場合 Word および Excel できない場合、コードを実行します。 ドキュメントの作成者であるか、フル コントロール アクセス権がある場合は、ソリューションが機能するように既定値を変更できます。 詳細については、「[方法 :制限されたアクセス許可を持つドキュメントの背後で実行するコードの許可](../vsto/how-to-permit-code-to-run-behind-documents-with-restricted-permissions.md)します。

 IRM は使用できない<xref:Microsoft.VisualStudio.Tools.Applications.Runtime.ServerDocument>を取得またはドキュメントにキャッシュされているデータを操作します。

## <a name="end-users-to-restrict-permissions-to-documents-that-use-managed-code-extensions"></a>エンドユーザーがマネージ コード拡張機能を使用するドキュメントへのアクセス許可を制限するには
 IRM を使用すると、アクセス許可を制限して、ソリューション内のドキュメントまたはブックにフル コントロール アクセス権を持つユーザーことができます。 などの会計部門にエンドユーザーがワークシートに、データベースからデータを自動的に設定するソリューションを使用する場合そのユーザーが自分の部門内のユーザーにのみアクセスの変更と他のユーザーへの読み取りアクセスを許可する可能性があります。 ユーザーは、制限されたアクセス許可を追加するときに、既定では、ワークシートの背後にあるコードを実行できず、ワークシートは、データは設定されません。

 オブジェクト モデルへのプログラムによるアクセスを許可する既定のアクセス許可の設定を変更すると、問題を解決するには、ドキュメントまたはブックにフル コントロール アクセス権を持つユーザーがあります。 詳細については、「[方法 :制限されたアクセス許可を持つドキュメントの背後で実行するコードの許可](../vsto/how-to-permit-code-to-run-behind-documents-with-restricted-permissions.md)します。

## <a name="see-also"></a>関連項目
- [ドキュメント レベルのソリューションでドキュメントの保護](../vsto/document-protection-in-document-level-solutions.md)
- [Office ドキュメントのパスワード保護](../vsto/password-protection-on-office-documents.md)
- [セキュリティで保護された Office ソリューション](../vsto/securing-office-solutions.md)
- [Office ソリューションのデプロイ](../vsto/deploying-an-office-solution.md)
- [Office ソリューションの設計と作成](../vsto/designing-and-creating-office-solutions.md)
