---
title: '方法: 停止した場合に MFC を呼び出した関数に戻る |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.mfc
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- functions [C++], debugging
- function calls, returning to calling function
- debugging [MFC], returning to calling function
- debugging [MFC], functions
- Break command
- programs, halting
- functions [debugger]
ms.assetid: d254a5a9-afbd-4923-9d7a-7422d824cabf
caps.latest.revision: 21
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: a86efc2e181a7f692e84244eecb2355783b188bb
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "60039372"
---
# <a name="how-to-get-back-to-the-function-that-called-mfc-if-halted"></a>方法: 停止した場合に MFC を呼び出した関数に戻る
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

注意]
>  実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。 設定を変更するには、[ツール] メニューの [設定のインポートとエクスポート] をクリックします。 詳細については、「 [Visual Studio での開発設定のカスタマイズ](http://msdn.microsoft.com/22c4debb-4e31-47a8-8f19-16f328d7dcd3)」を参照してください。  
  
 **[デバッグ]** メニューの **[中断]** コマンドでプログラムを中断した場合に MFC 内で実行が停止されたとします。そのとき、問題が自分自身で作成したコードにあることが明らかな場合は、[呼び出し履歴] ウィンドウを使用することにより、呼び出し元の関数に戻ることができます。 詳細については、「[方法 :[呼び出し履歴] ウィンドウの使用](../debugger/how-to-use-the-call-stack-window.md)に関するページをご覧ください。  
  
 コードがメッセージ ポンプ内で中断する場合があります。 この場合、呼び出し履歴にユーザー コードは存在しません。 この問題を回避するには、**[中断]** コマンドではなく、ブレークポイントを使用する必要があります。適宜、条件とヒット カウントを組み合わせて使用します。 詳細については、次を参照してください。[ブレークポイントとトレース ポイント](http://msdn.microsoft.com/fe4eedc1-71aa-4928-962f-0912c334d583))。  
  
### <a name="to-navigate-to-the-function-from-which-mfc-was-called"></a>MFC の呼び出し元の関数を参照するには  
  
- **[呼び出し履歴]** ウィンドウを使用します。  
  
## <a name="see-also"></a>関連項目  
 [ネイティブ コードのデバッグに関する FAQ](../debugger/debugging-native-code-faqs.md)   
 [ネイティブ コードのデバッグ](../debugger/debugging-native-code.md)
