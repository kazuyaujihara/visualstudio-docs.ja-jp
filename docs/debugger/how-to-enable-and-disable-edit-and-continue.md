---
title: '方法: 有効にして、エディット コンティニュを無効にする |Microsoft Docs'
ms.custom: seodec18
ms.date: 10/04/2018
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- /INCREMENTAL linker option
- Apply Code Changes command
- Edit and Continue, disabling
- code changes, applying in break mode
- INCREMENTAL linker option
- Edit and Continue, enabling
- break mode, applying code changes
- Edit and Continue, applying code changes
- Step command
- Go command
ms.assetid: fd961a1c-76fa-420d-ad8f-c1a6c003b0db
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- dotnet
- cplusplus
ms.openlocfilehash: 3bee60a54576ab816c63cf60f2226ebbbaf50c44
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63388487"
---
# <a name="how-to-enable-and-disable-edit-and-continue-c-vb-c"></a>方法: 有効にして、エディット コンティニュを無効にする (C#、VB、 C++)

無効にするか、有効にする**エディット コンティニュ**Visual Studio で**オプション**デザイン時にダイアログ ボックス。 **エディット コンティニュ**はデバッグ ビルドでのみ動作します。 詳細については、「[エディット コンティニュ](../debugger/edit-and-continue.md)」を参照してください。

ネイティブの c++**エディット コンティニュ**を使用する必要があります、`/INCREMENTAL`オプション。 C++ では、機能要件の詳細については、この参照してください[ブログの投稿](https://devblogs.microsoft.com/cppblog/c-edit-and-continue-in-visual-studio-2015-update-3/)と[エディット コンティニュ (Visual C)](../debugger/edit-and-continue-visual-cpp.md)します。

**有効または、エディット コンティニュを無効にします。**

1. デバッグ セッションの場合は、デバッグを停止 (**デバッグ** > **デバッグの停止**または**Shift**+**F5**).

1. **ツール** > **オプション**> (または**デバッグ** > **オプション**) > **のデバッグ** > **全般**、**エディット コンティニュ**右側のウィンドウで。

    > [!NOTE]
    > IntelliTrace が有効になっている場合に、IntelliTrace イベントと呼び出し情報の両方を収集すると、エディット コンティニュが無効になります。 詳細については、次を参照してください。 [IntelliTrace](../debugger/intellitrace.md)します。

1. C++ コードのことを確認します**を有効にするネイティブ エディット コンティニュ**を選択すると、し、追加のオプションを設定します。
    - **[コンティニュに変更を適用する (ネイティブのみ)]**

      選択した場合、Visual Studio は自動的にコンパイルし、中断状態からデバッグを続行する場合は、コードの変更を適用します。 それ以外の場合を使用して変更を適用できます**デバッグ** > **コード変更を適用**します。

    - **[古いコードの警告を表示する (ネイティブのみ)]**

      選択した場合、古いコードに関する警告を示します。

1. **[OK]** をクリックします。
