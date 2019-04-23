---
title: '方法: 作成します。既存の Vsct ファイルです。Cto ファイル |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: devlang-csharp
ms.topic: conceptual
helpviewer_keywords:
- VSCT files, creating based on a .cto file
ms.assetid: 847717c9-477d-4ac9-8b2c-2da878912478
caps.latest.revision: 11
manager: jillfra
ms.openlocfilehash: 83608d768940158dcdab427a557577677e56f7c8
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "60056173"
---
# <a name="how-to-create-a-vsct-file-from-an-existing-cto-file"></a>方法: 作成します。既存の Vsct ファイルです。Cto ファイル
既存のバイナリ .cto ファイルから XML ベースの .vsct ファイルを作成できます。 これを行うことで、新しいコマンド テーブル コンパイラ形式を活用できます。 このプロセスは、.ctc ファイルから .cto ファイルをコンパイルした場合でも機能します。 .vsct ファイルを編集して、別の .cto ファイルにコンパイルできます。  
  
### <a name="to-create-a-vsct-file-from-a-cto-file"></a>.cto ファイルから .vsct ファイルを作成するには  
  
1. .Cto ファイルと、対応する .ctsym ファイルのコピーを取得します。  
  
2. ファイルを Vsct.exe コンパイラと同じディレクトリに配置します。  
  
3. Visual Studio コマンド プロンプトで、.cto ファイルと .ctsym ファイルが保存されているディレクトリに移動します。  
  
4. 「 **vsct.exe** _ctofilename_**.cto** _vsctfilename_**.vsct -S**_symfilename_**.ctsym**」と入力します。  
  
     `ctofilename` には .cto ファイルの名前、`vsctfilename` には作成する vsct ファイルの名前、`symfilename` には .ctsym ファイルの名前を入力します。  
  
     このプロセスによって、新しい .vsct XML コマンド テーブル コンパイラ ファイルが作成されます。 他の .vsct ファイルと同様に、vsct.exe (vsct コンパイラ) を使用して、ファイルを編集およびコンパイルできます。  
  
## <a name="see-also"></a>関連項目  
 [方法: 作成します。Vsct ファイル](../extensibility/internals/how-to-create-a-dot-vsct-file.md)   
 [Visual Studio Command Table (.Vsct) ファイル](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)