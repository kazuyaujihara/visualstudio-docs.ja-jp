---
title: '方法: 作成します。既存の Vsct ファイルです。Ctc ファイル |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: devlang-csharp
ms.topic: conceptual
helpviewer_keywords:
- VSCT files, creating based on a .ctc file
ms.assetid: 700e80a4-c1e1-4178-af53-45e86dd2c08b
caps.latest.revision: 9
manager: jillfra
ms.openlocfilehash: 2d5ba5a271cd7132d9750fc0569b801022aeb932
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "60117857"
---
# <a name="how-to-create-a-vsct-file-from-an-existing-ctc-file"></a>方法: 作成します。既存の Vsct ファイルです。Ctc ファイル
既存のコマンドテーブルの .ctc ソース ファイルから XML ベースの .vsct ファイルを作成できます。 これにより、新しい XML ベースの [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] コマンド テーブル (VSCT) コンパイラ形式を利用できます。  
  
### <a name="to-create-a-vsct-file-from-a-ctc-file"></a>.ctc ファイルから .vsct ファイルを作成するには  
  
1. Perl 言語のコピーを取得します。  
  
2. 通常にある Perl スクリプト ConvertCTCToVSCT.pl のコピーを取得、  *\<Visual Studio SDK インストール パス >* \VisualStudioIntegration\Tools\bin フォルダー。  
  
3. 変換する .ctc ソース ファイルのコピーを取得します。  
  
4. 同じディレクトリにファイルを配置します。  
  
5. [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] のコマンド プロンプト ウィンドウで、そのディレクトリに移動します。  
  
6. 型  
  
    ```  
    perl.exe ConvertCTCtoVSCT.pl PkgCmd.ctc PkgCmd.vsct  
    ```  
  
     PkgCmd.ctc は .ctc ファイルの名前であり、PkgCmd.vsct は作成する .vsct ファイルの名前です。  
  
     新しい .vsct XML コマンド テーブル ソース ファイルが作成されます。 他の .vsct ファイルと同様に、Vsct.exe (VSCT コンパイラ) を使用してファイルをコンパイルできます。  
  
    > [!NOTE]
    >  XML コメントの書式を変更すると、.vsct ファイルの読みやすさを改善できます。  
  
## <a name="see-also"></a>関連項目  
 [方法: 作成します。Vsct ファイル](../extensibility/internals/how-to-create-a-dot-vsct-file.md)   
 [Visual Studio Command Table (.Vsct) ファイル](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)