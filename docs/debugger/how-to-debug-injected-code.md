---
title: '方法: 挿入されたコードのデバッグ |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.injected
dev_langs:
- CSharp
- VB
- FSharp
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
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 479df9e5761066248b8657d9656132b072bddb13
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2018
ms.locfileid: "49866078"
---
# <a name="how-to-debug-injected-code"></a>方法 : 挿入されたコードをデバッグする
> [!NOTE]
>  実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。 設定を変更するには、[ツール] メニューの [設定のインポートとエクスポート] をクリックします。 詳細については、「[Visual Studio IDE のカスタマイズ](../ide/personalizing-the-visual-studio-ide.md)」を参照してください。  
  
 属性を使用すると、C++ でのプログラミングが簡単になります。 詳細については、次を参照してください。[概念](/cpp/windows/attributed-programming-concepts)します。 一部の属性は、コンパイラによって直接解釈されます。 プログラム ソースにコードを挿入するタイプの属性もあります。この場合、コンパイラは、コードが挿入されてからプログラム ソースをコンパイルします。 このようにコードが挿入されることにより、実際に記述するコードの量が減り、プログラミングがいっそう簡単になります。 しかし、挿入されたコードの実行中に、バグが発生してアプリケーションが正しく動作しなくなる場合があります。 このような場合は、挿入されたコードを確認する必要があります。 Visual Studio では、次の 2 つの方法で、挿入されたコードを参照できます。  
  
- 挿入されたコードを表示することができます、**逆アセンブル**ウィンドウ。  
  
- 使用して[/Fx](/cpp/build/reference/fx-merge-injected-code)、元と挿入されたコードを含むマージされたソース ファイルを作成することができます。  
  
  **逆アセンブル**ウィンドウには、ソース コードおよび属性によって挿入されたコードに対応するアセンブリ言語命令が表示されます。 さらに、**逆アセンブル**ウィンドウは、ソース コードの注釈を表示できます。  
  
### <a name="to-turn-on-source-annotation"></a>ソースの注釈を表示するには  
  
-   右クリックし、**逆アセンブル**ウィンドウで、選択**ソース コードの表示**ショートカット メニューから。  
  
     挿入されたコードを検索するショートカット メニューを使用するには、ソース ウィンドウ内の属性の場所がわかっている場合、**逆アセンブル**ウィンドウ。  
  
### <a name="to-view-injected-code"></a>挿入されたコードを表示するには  
  
1.  デバッガーは中断モードである必要があります。  
  
2.  ソース コード ウィンドウで、挿入されたコードを表示する対象の属性の直前にカーソルを置きます。  
  
3.  右クリックして選択**アセンブルを**ショートカット メニューから。  
  
     属性の場所が現在の実行ポイントに近い場合は選択できます、**逆アセンブル**ウィンドウから、**デバッグ**メニュー。  
  
### <a name="to-view-the-disassembly-code-at-the-current-execution-point"></a>現在の実行ポイントにあるコードを表示するには  
  
1.  デバッガーは中断モードである必要があります。  
  
2.  **デバッグ** メニューの 選択**Windows**、 をクリック**逆アセンブル**します。  
  
## <a name="see-also"></a>関連項目  
 [デバッガーのセキュリティ](../debugger/debugger-security.md)   
 [ネイティブ コードのデバッグ](../debugger/debugging-native-code.md)