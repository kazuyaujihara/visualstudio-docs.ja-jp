---
title: '方法: 共通出力ディレクトリへのビルド |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- output directory
- builds [Visual Studio], common directory
- common directory
ms.assetid: 1fcc2c48-07cb-4c4f-9556-36945e7dfc4e
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: bd3d32873b98187f2a24a0e31e8d24ae8b0a6a01
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "54805433"
---
# <a name="how-to-build-to-a-common-output-directory"></a>方法 : 共通出力ディレクトリへのビルド
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

既定では、[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] は、ソリューションの各プロジェクトを、そのソリューション内の独自のフォルダーにビルドします。 プロジェクトのビルド出力パスを変更して、すべての出力を強制的に同じフォルダーに配置することができます。  
  
### <a name="to-place-all-solution-outputs-in-a-common-directory"></a>すべてのソリューション出力を共通ディレクトリに配置するには  
  
1.  ソリューションのいずれかのプロジェクトをクリックします。  
  
2.  **[プロジェクト]** メニューの **[プロパティ]** をクリックします。  
  
3.  プロジェクトの種類に応じて、**[コンパイル]** タブまたは **[ビルド]** タブのいずれかをクリックし、**[出力パス]** をそのソリューションのすべてのプロジェクトで使用するフォルダーに設定します。  
  
4.  ソリューションのすべてのプロジェクトに対して、手順 1 から 3 を繰り返します。  
  
## <a name="see-also"></a>関連項目  
 [コードのコンパイルとビルド](../ide/compiling-and-building-in-visual-studio.md)   
 [方法 : ビルド出力ディレクトリを変更する](../ide/how-to-change-the-build-output-directory.md)
