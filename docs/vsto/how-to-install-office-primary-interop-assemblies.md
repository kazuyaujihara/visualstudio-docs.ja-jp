---
title: '方法: Office プライマリ相互運用機能アセンブリをインストールする方法'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- primary interop assemblies [Office development in Visual Studio], installing
- Office primary interop assemblies, installing
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 4b6f701e3962a25e7239c829d409a3ad69a1833a
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63419603"
---
# <a name="how-to-install-office-primary-interop-assemblies"></a>方法: Office プライマリ相互運用機能アセンブリをインストールする方法
  Microsoft Office のインストール時に、Office のプライマリ相互運用機能アセンブリ (PIA) をインストールします。

## <a name="to-install-the-pias-when-you-install-office"></a>Office のインストール時に PIA をインストールするには

1. .NET Framework のバージョンが 2.0 以降であることを確認します。

2. Microsoft Office をインストールし、アプリケーションを拡張するための **.NET プログラミング サポート**の機能(この機能は既定のインストールに含まれています)が選択されていることを確認します。

    > [!WARNING]
    > 既定では、PIA はビルドするときにソリューションに埋め込まれるので、VSTO アドインまたはカスタマイズを使用する前提条件として PIA をユーザーに配布する必要はありません。

## <a name="see-also"></a>関連項目
- [Office プライマリ相互運用機能アセンブリ](../vsto/office-primary-interop-assemblies.md)
- [方法: プライマリ相互運用機能アセンブリを利用して Office アプリケーションします。](../vsto/how-to-target-office-applications-through-primary-interop-assemblies.md)
- [方法: Office ソリューションを開発するコンピューターを構成する方法](../vsto/how-to-configure-a-computer-to-develop-office-solutions.md)
- [Visual Studio Tools for Office ランタイム再頒布可能パッケージをインストールする方法](../vsto/how-to-install-the-visual-studio-tools-for-office-runtime-redistributable.md)
- [Office ソリューション開発の概要&#40;VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md)
- [はじめに &#40;Visual Studio での Office 開発&#41;](../vsto/getting-started-office-development-in-visual-studio.md)
