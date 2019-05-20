---
title: '方法: 混合モードでデバッグ |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- debugging DLLs
- debugging [Visual Studio], mixed-mode
- mixed-mode debugging
ms.assetid: 2859067d-7fcc-46b0-a4df-8c2101500977
caps.latest.revision: 32
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: c5e2dd4ea0000eefdbd9f74c8fa97c4c63e06fab
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65681142"
---
# <a name="how-to-debug-in-mixed-mode"></a>方法: 混合モードでデバッグします。
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

ここでは、マネージド コードとネイティブ コードの両方をデバッグする方法について説明します。これは、混合モード デバッグとも呼ばれます。 DLL またはアプリケーションがネイティブ コードで記述されているかどうかによって、2 つのデバッグ シナリオがあります。  
  
- DLL を呼び出す呼び出し元のアプリケーションがネイティブ コードで記述されている。 この場合は、DLL がマネージド DLL であり、マネージド デバッガーとネイティブ デバッガーの両方を有効にしてデバッグする必要があります。 これを確認するには、 **\<プロジェクト > プロパティ ページ** ダイアログ ボックス。 DLL プロジェクトからデバッグを開始するか、呼び出し元のアプリケーション プロジェクトからデバッグを開始するかによって、確認方法は異なります。  
  
- DLL を呼び出す呼び出し元のアプリケーションがマネージド コードで記述され、DLL がネイティブ コードで記述されている。  
  
> [!NOTE]
> 実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。 設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。 詳細については、「 [Visual Studio での開発設定のカスタマイズ](https://msdn.microsoft.com/22c4debb-4e31-47a8-8f19-16f328d7dcd3)」を参照してください。  
  
### <a name="to-enable-mixed-mode-debugging"></a>混合モードのデバッグを有効にするには  
  
1. **ソリューション エクスプ ローラー**プロジェクトを選択します。  
  
2. **[表示]** メニューの **[プロパティ ページ]** をクリックします。  
  
3. **\<プロジェクト > プロパティ ページ** ダイアログ ボックスで、展開、**構成プロパティ**ノードをクリックして**デバッグ**します。  
  
4. **[デバッガーの種類]** を **[混合]** または **[自動]** に設定します。  
  
## <a name="see-also"></a>関連項目  
 [方法: DLL プロジェクトからデバッグする](../debugger/how-to-debug-from-a-dll-project.md)
