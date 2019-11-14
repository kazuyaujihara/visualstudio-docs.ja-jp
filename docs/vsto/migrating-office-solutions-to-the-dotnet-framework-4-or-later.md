---
title: Office ソリューションを .NET Framework 4 以降に移行する
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
ms.openlocfilehash: b9531f0495bd0dc0a9f095ff71fdfd84fc8d1380
ms.sourcegitcommit: 40bd5b27f247a07c2e2514acb293b23d6ce03c29
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2019
ms.locfileid: "73189780"
---
# <a name="migrate-office-solutions-to-the-net-framework-4-or-later"></a>Office ソリューションを .NET Framework 4 以降に移行する
  Office プロジェクトのターゲットフレームワークを以前のバージョンの .NET Framework から [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] またはそれ以降に変更する場合は、開発およびエンドユーザーのコンピューターで引き続きソリューションを実行するために、いくつかの追加の手順が必要になることがあります。 詳細については、「 [.NET Framework 4 または .NET Framework 4.5 に移行する Office プロジェクトの実行に必要な変更](../vsto/required-changes-to-run-office-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md)」を参照してください。

 さらに、プロジェクトがコンパイルされなくなる場合があります。 Office プロジェクトの一部の機能は、.NET Framework のバージョンに応じてプログラミング モデルが異なっています。 Office プロジェクトのターゲット フレームワークを旧バージョンの .NET Framework から [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 以降に変更する場合は、プロジェクトに対して次のコード変更を加える必要があります。

- [.NET Framework 4 または .NET Framework 4.5 に移行する Excel プロジェクトおよび Word プロジェクトを更新する](../vsto/updating-excel-and-word-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md)

- [.NET Framework 4 または .NET Framework 4.5 に移行する Office プロジェクトのリボンのカスタマイズを更新する](update-ribbon-customizations-in-office-projects-to-migrate-to-dotnet-framework-4-or-4-5.md)

- [.NET Framework 4 または .NET Framework 4.5 に移行する Outlook プロジェクトのフォーム領域を更新する](../vsto/updating-form-regions-in-outlook-projects-that-you-migrate-to-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md)

  Office プロジェクトのターゲット フレームワークは、そのプロジェクトを旧バージョンの Visual Studio からアップグレードすると変更されます。 詳細については、「 [Office ソリューションのアップグレードと移行](../vsto/upgrading-and-migrating-office-solutions.md)」を参照してください。

  [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 以降を対象とする Office プロジェクトの一部の機能のプログラミングモデルが異なる理由の詳細については、「 [.NET Framework 4 を対象とする office プロジェクトのデザインの変更」また](../vsto/changes-to-the-design-of-office-projects-that-target-the-dotnet-framework-4-or-the-dotnet-framework-4-5.md)は「4.5 とビジュアルの .NET Framework」を参照してください。 [Studio Tools for Office runtime の概要](../vsto/visual-studio-tools-for-office-runtime-overview.md)。

## <a name="see-also"></a>関連項目
- [Office ソリューションの設計と作成](../vsto/designing-and-creating-office-solutions.md)
- [方法: .NET Framework のバージョンをターゲットにする](../ide/visual-studio-multi-targeting-overview.md)
- [Office ソリューションで発生したエラーのトラブルシューティング](../vsto/troubleshooting-errors-in-office-solutions.md)
- [Office ソリューションでのエラーの追加サポート](../vsto/additional-support-for-errors-in-office-solutions.md)
