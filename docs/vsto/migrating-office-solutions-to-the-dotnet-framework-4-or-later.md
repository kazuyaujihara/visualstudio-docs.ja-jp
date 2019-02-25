---
title: .NET Framework 4 またはそれ以降の Office ソリューションを移行します。
ms.date: 02/02/2017
ms.topic: conceptual
f1_keywords:
- VST.Project.TargetFrameworkWarning
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office projects [Office development in Visual Studio], migrating to .NET Framework 4
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 729fafd1f6dfdf889293c9686f455be8de5a81fc
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56643718"
---
# <a name="migrate-office-solutions-to-the-net-framework-4-or-later"></a>.NET Framework 4 またはそれ以降の Office ソリューションを移行します。
  Office プロジェクトのターゲット フレームワークを変更するかどうか、[!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)]または後で、.NET Framework の以前のバージョンから追加の手順がありますソリューションを開発およびエンドユーザーのコンピューターで実行を続行するために必要です。 詳細については、「[.NET Framework 4 または .NET Framework 4.5 に移行する Office プロジェクトの実行に必要な変更](../vsto/required-changes-to-run-office-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md)」を参照してください。

 さらに、プロジェクトがコンパイルされなくなる場合があります。 Office プロジェクトの一部の機能は、.NET Framework のバージョンに応じてプログラミング モデルが異なっています。 Office プロジェクトのターゲット フレームワークを旧バージョンの .NET Framework から [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 以降に変更する場合は、プロジェクトに対して次のコード変更を加える必要があります。

- [.NET Framework 4 または .NET Framework 4.5 に移行する Excel および Word プロジェクトの更新](../vsto/updating-excel-and-word-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md)

- [.NET Framework 4 または .NET Framework 4.5 に移行する Office プロジェクトのリボンのカスタマイズの更新](/visualstudio/vsto/update-ribbon-customizations-in-office-projects-to-migrate-to-dotnet-framework-4-or-4-5)

- [.NET Framework 4 または .NET Framework 4.5 に移行する Outlook プロジェクトのフォーム領域の更新](../vsto/updating-form-regions-in-outlook-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md)

  Office プロジェクトのターゲット フレームワークは、そのプロジェクトを旧バージョンの Visual Studio からアップグレードすると変更されます。 詳細については、次を参照してください。[アップグレードし、Office ソリューションの移行](../vsto/upgrading-and-migrating-office-solutions.md)します。

  Office プロジェクトの一部の機能が対象とする場合、さまざまなプログラミング モデルをある理由の詳細については、[!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)]後を参照してくださいまたは[を .NET Framework 4 または .NET Framework 4.5を対象とするOfficeプロジェクトの設計変更。](../vsto/changes-to-the-design-of-office-projects-that-target-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md)と[Visual Studio Tools for Office runtime の概要](../vsto/visual-studio-tools-for-office-runtime-overview.md)します。

## <a name="see-also"></a>関連項目
- [Office ソリューションの設計と作成](../vsto/designing-and-creating-office-solutions.md)
- [方法: ターゲット .NET Framework のバージョン](../ide/how-to-target-a-version-of-the-dotnet-framework.md)
- [Office ソリューションのエラーをトラブルシューティングします。](../vsto/troubleshooting-errors-in-office-solutions.md)
- [Office ソリューションのエラーのための追加サポート](../vsto/additional-support-for-errors-in-office-solutions.md)
