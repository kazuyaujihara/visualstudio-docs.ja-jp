---
title: MSBuild 16.0 の新機能 | Microsoft Docs
ms.date: 03/11/2019
ms.topic: conceptual
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
monikerRange: '>=vs-2019'
ms.openlocfilehash: 9fb23c8a48493056c9a37f510cefea3cc3374095
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62777907"
---
# <a name="whats-new-in-msbuild-160"></a>MSBuild 16.0 の新機能

この記事では、MSBuild 16.0 で更新された機能とプロパティについて説明します。 詳細なリリース ノート (ドラフトのみ) については、[MSBuild 16.0](https://gist.github.com/rainersigwald/009627466f03964d0028e16fda633d9c) をご覧ください。

## <a name="changed-path"></a>変更されたパス

 MSBuild は Visual Studio の各バージョンの *\Current* フォルダーにインストールされます。 例: *C:\Program Files (x86)\Microsoft Visual Studio\Current\Enterprise\MSBuild*。 次の PowerShell モジュールを使用して MSBuild を検索することもできます: [vssetup.powershell](https://github.com/Microsoft/vssetup.powershell)。

## <a name="changed-properties"></a>変更されたプロパティ

 新しいバージョン番号に伴い、次の MSBuild プロパティが更新されました。

- `MSBuildToolsVersion`: このバージョンのツールでは "Current" になります。 アセンブリのバージョンは、Visual Studio 2017 と同じ (15.1.0.0) です。

- `VisualStudioVersion`: このバージョンのツールでは "16.0" になります。

## <a name="updates"></a>更新

MSBuild (および Visual Studio) では、.NET Framework 4.7.2 が対象とされるようになりました。 MSBuild API の新しい機能を使用したい場合は、ご利用のアセンブリもアップグレードする必要があります。ただし、既存のコードは引き続き機能します。

## <a name="see-also"></a>関連項目
- [MSBuild](../msbuild/msbuild.md)
