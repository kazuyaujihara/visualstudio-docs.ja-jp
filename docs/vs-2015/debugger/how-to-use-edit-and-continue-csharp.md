---
title: '方法: エディット コンティニュを使用 (C#) |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- Edit and Continue [C#], about Edit and Continue
ms.assetid: 40e136d8-a08c-43bd-b313-fb821c55eb3c
caps.latest.revision: 22
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: c52540c8e639adcd8ceec6b4da79fb87cff18386
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58974275"
---
# <a name="how-to-use-edit-and-continue-c"></a>方法: エディット コンティニュを使用する (C#)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

C# のエディット コンティニュを使用すると、デバッグ中に中断モードでコードに変更を加えることができます。 デバッグ セッションを停止したり再開したりしなくても、変更を適用できます。  
  
 エディット コンティニュは自動的に呼び出されます、中断モードに変更し、デバッガーの実行を選択コマンドなど、**続行**、**手順**、または**次のステートメントの設定**、か、デバッガー ウィンドウで関数を評価します。  
  
> [!NOTE]
>  Compact Framework、最適化されたコード、ネイティブ コードとマネージ コードの混合コード、または SQL Server の共通言語ランタイム (CLR: Common Language Runtime) との統合コードのデバッグ時は、エディット コンティニュはサポートされません。 これらのシナリオのいずれかでコード変更を適用しようとすると、エディット コンティニュがサポートされないことを説明するダイアログ ボックスが表示されます。  
  
### <a name="to-invoke-edit-and-continue-automatically"></a>エディット コンティニュを自動的に呼び出すには  
  
1.  中断モードで、ソース コードを変更します。  
  
2.  **デバッグ** メニューのをクリックして**続行**、**手順**、または**次のステートメントの設定**か、デバッガー ウィンドウで関数を評価します。  
  
     新しいコードがコンパイルされ、その新しいコードでデバッグが続行されます。 エディット コンティニュでサポートされない変更もあります。 詳細については、次を参照してください。[サポートされているコード変更 (C#)](../debugger/supported-code-changes-csharp.md)します。  
  
### <a name="to-enabledisable-edit-and-continue"></a>[エディット コンティニュ] を有効または無効にするには  
  
1.  **[ツール]** メニューの **[オプション]** をクリックします。  
  
2.  **オプション** ダイアログ ボックスで、展開、**デバッグ**ノード、および選択**エディット コンティニュ**します。  
  
3.  **オプション** ダイアログ ボックス**エディット コンティニュ**ページ、オンまたはオフ、**編集を有効にして続行**チェック ボックスをオンします。  
  
     デバッグ セッションを再開すると、この設定が有効になります。  
  
## <a name="see-also"></a>関連項目  
 [エディット コンティニュ (Visual C#)](../debugger/edit-and-continue-visual-csharp.md)   
 [サポートされているコードの変更 (C#)](../debugger/supported-code-changes-csharp.md)   
 [エディット コンティニュのエラーと警告 (C#)](../misc/edit-and-continue-errors-and-warnings-csharp.md)
