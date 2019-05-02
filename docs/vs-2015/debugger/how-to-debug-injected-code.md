---
title: '方法: 挿入されたコードのデバッグ |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.injected
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- assembly language, viewing
- debugging [C++], viewing assembly code
- debugging [C++], injected code
- debugging [C++], enabling source annotation
- injected code
- Show Source Code command [debugger]
- debugging [C++], using attributes
- disassembly code, debugging
ms.assetid: a1b4104d-d49e-451f-a91e-e39ceaf35875
caps.latest.revision: 20
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: b7b411574dcf65bdd1ec64c1fc51bd1813f09abb
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63432339"
---
# <a name="how-to-debug-injected-code"></a>方法: 挿入されたコードをデバッグする
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

注意]
> 実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。 設定を変更するには、[ツール] メニューの [設定のインポートとエクスポート] をクリックします。 詳細については、「 [Visual Studio での開発設定のカスタマイズ](http://msdn.microsoft.com/22c4debb-4e31-47a8-8f19-16f328d7dcd3)」を参照してください。  
  
 属性を使用すると、C++ でのプログラミングが簡単になります。 詳細については、次を参照してください。[概念](http://msdn.microsoft.com/library/563e7e7c-65e1-44f4-b0b2-da04a6c1bc9e)します。 一部の属性は、コンパイラによって直接解釈されます。 プログラム ソースにコードを挿入するタイプの属性もあります。この場合、コンパイラは、コードが挿入されてからプログラム ソースをコンパイルします。 このようにコードが挿入されることにより、実際に記述するコードの量が減り、プログラミングがいっそう簡単になります。 しかし、挿入されたコードの実行中に、バグが発生してアプリケーションが正しく動作しなくなる場合があります。 このような場合は、挿入されたコードを確認する必要があります。 Visual Studio では、次の 2 つの方法で、挿入されたコードを参照できます。  
  
- 挿入されたコードを **[逆アセンブリ]** ウィンドウに表示できます。  
  
- [/Fx](http://msdn.microsoft.com/library/14f0e301-3bab-45a3-bbdf-e7ce66f20560) を使用して、元のコードと挿入されたコードをマージしたソース ファイルを作成できます。  
  
  **[逆アセンブリ]** ウィンドウには、ソース コードと、属性によって挿入されたコードに対応するアセンブリ言語命令が表示されます。 また、**[逆アセンブリ]** ウィンドウには、ソース コードの注釈を表示することもできます。  
  
### <a name="to-turn-on-source-annotation"></a>ソースの注釈を表示するには  
  
- **[逆アセンブリ]** ウィンドウを右クリックし、ショートカット メニューの **[ソース コードの表示]** を選びます。  
  
     ソース ウィンドウ内の属性の位置がわかっている場合は、ショートカット メニューを使用して、その属性が挿入したコードを **[逆アセンブリ]** ウィンドウに表示できます。  
  
### <a name="to-view-injected-code"></a>挿入されたコードを表示するには  
  
1. デバッガーは中断モードである必要があります。  
  
2. ソース コード ウィンドウで、挿入されたコードを表示する対象の属性の直前にカーソルを置きます。  
  
3. 右クリックし、ショートカット メニューの **[逆アセンブリを表示]** を選択します。  
  
     属性の位置が現在の実行ポイントに近い場合は、**[デバッグ]** メニューの **[逆アセンブリ]** ウィンドウを選択できます。  
  
### <a name="to-view-the-disassembly-code-at-the-current-execution-point"></a>現在の実行ポイントにあるコードを表示するには  
  
1. デバッガーは中断モードである必要があります。  
  
2. **[デバッグ]** メニューの **[Windows]** を選び、**[逆アセンブリ]** をクリックします。  
  
## <a name="see-also"></a>関連項目  
 [デバッガーのセキュリティ](../debugger/debugger-security.md)   
 [ネイティブ コードのデバッグ](../debugger/debugging-native-code.md)
