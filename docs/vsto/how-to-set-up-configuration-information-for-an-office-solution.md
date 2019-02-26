---
title: '方法: Office ソリューションの構成情報を設定します。'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- solutions [Office development in Visual Studio], configuration files
- configuration files [Office development in Visual Studio]
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 159708bfad49e6a4a303363c6a0e9dd83b23d8e7
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56632018"
---
# <a name="how-to-set-up-configuration-information-for-an-office-solution"></a>方法: Office ソリューションの構成情報を設定します。
  構成ファイルを使用して、Office ソリューションに固有の設定を構成することができます。 アセンブリ バインディング ポリシー、リモート処理オブジェクト、デバッグ、およびトレースの設定などの設定を指定することができます。

 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]

 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]

### <a name="to-add-a-configuration-file-to-your-office-project"></a>Office プロジェクトに構成ファイルを追加するには

1. **[プロジェクト]** メニューの **[新しい項目の追加]** をクリックします。

2. **カテゴリ**ウィンドウで、をクリックして**全般**します。

3. **テンプレート**ペインで、**アプリケーション構成ファイル**します。

4. **名前**ボックスに、アセンブリと、拡張機能として、同じ名前を入力 *.config*します。たとえば、Excel プロジェクト アセンブリの構成ファイルと呼ばれる*ExcelWorkbook1.dll*という名前になります*ExcelWorkbook1.dll.config*します。

5. **[追加]** をクリックします。

6. アプリケーション構成ファイルのスキーマに従って、構成ファイルを作成します。 詳細については、次を参照してください。 [、.NET Framework の構成ファイル スキーマ](/dotnet/framework/configure-apps/file-schema/index)します。

   Office プロジェクトを構成ファイルを使用するための特別な考慮事項はありません。

## <a name="see-also"></a>関連項目
- [.NET Framework の構成ファイル スキーマ](/dotnet/framework/configure-apps/file-schema/index)
- [Office ソリューションの設計と作成](../vsto/designing-and-creating-office-solutions.md)
- [Office ソリューションのデプロイ](../vsto/deploying-an-office-solution.md)
