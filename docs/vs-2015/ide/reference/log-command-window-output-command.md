---
title: Log Command Window Output コマンド | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- tools.logcommandwindowoutput
helpviewer_keywords:
- log Command window output command
- View.LogCommandWindowOutput command
ms.assetid: d4ecec35-5af4-4954-8d60-2cd24583fbb4
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: c48c61177f80be00532347d3c49173aae54c7109
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2018
ms.locfileid: "49266397"
---
# <a name="log-command-window-output-command"></a>LogCommandWindowOutput コマンド
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
**[コマンド]** ウィンドウの入出力をすべてファイルにコピーします。  
  
## <a name="syntax"></a>構文  
  
```  
Tools.LogCommandWindowOutput [filename] [/on|/off] [/overwrite]  
```  
  
## <a name="arguments"></a>引数  
 `filename`  
 任意。 ログ ファイルの名前。 既定では、ユーザーのプロファイル フォルダーにファイルが作成されます。 ファイル名が既に存在する場合、ログは、既存のファイルの末尾に追加されます。 ファイルが指定されていない場合は、指定された最後のファイルが使用されます。 以前のファイルが存在しない場合、cmdline.log と呼ばれる既定のログ ファイルが作成されます。  
  
> [!TIP]
>  ログ ファイルの保存先を変更するには、ファイルの完全パスを入力します。パスに空白が含まれる場合は、パスを引用符で囲みます。  
  
## <a name="switches"></a>スイッチ  
 /on  
 任意。 指定したファイルで **[コマンド]** ウィンドウのログの作成を開始し、ファイルに新しい情報を追加します。  
  
 /off  
 任意。 **[コマンド]** ウィンドウのログの作成を停止します。  
  
 /overwrite  
 任意。 `filename` 引数に指定したファイル名が既存のファイルと同じ場合は、既存のファイルが上書きされます。  
  
## <a name="remarks"></a>Remarks  
 ファイルを指定しない場合、既定では、ファイル cmdline.log が作成されます。 既定では、このコマンドのエイリアスは Log です。  
  
## <a name="examples"></a>使用例  
 次の例では、新規のログ ファイル cmdlog を作成して、コマンドのログを開始します。  
  
```  
>Tools.LogCommandWindowOutput cmdlog  
```  
  
 次の例では、コマンドのログを停止します。  
  
```  
>Tools.LogCommandWindowOutput /off  
```  
  
 次の例では、以前のログ ファイルを使用してコマンドのログを再開します。  
  
```  
>Tools.LogCommandWindowOutput /on  
```  
  
## <a name="see-also"></a>関連項目  
 [Visual Studio のコマンド](../../ide/reference/visual-studio-commands.md)   
 [コマンド ウィンドウ](../../ide/reference/command-window.md)   
 [[検索/コマンド] ボックス](../../ide/find-command-box.md)   
 [Visual Studio Command Aliases](../../ide/reference/visual-studio-command-aliases.md)



