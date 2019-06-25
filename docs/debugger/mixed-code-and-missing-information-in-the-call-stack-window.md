---
title: 混合コードと不足情報、呼び出し履歴 ウィンドウ |Microsoft Docs
ms.date: 11/04/2016
ms.topic: troubleshooting
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
- SQL
helpviewer_keywords:
- managed code, stepping
- Call Stack window, mixed-mode debugging
- Call Stack window, troubleshooting
- native frames
- managed call stacks
- mixed-mode debugging, call stack
- stepping, out of managed code
ms.assetid: dd628427-e8d6-4fc2-b524-9d6393ea5376
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 025591ffea4d6746f87e5f1240cd226fa291d116
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62905510"
---
# <a name="mixed-code-and-missing-information-in-the-call-stack-window"></a>[呼び出し履歴] ウィンドウの混合コードと不足情報
マネージド コードとネイティブ コードの呼び出し履歴には違いがあるため、コードの種類が混在する場合、呼び出し履歴にすべてを表示できるとは限りません。 ネイティブ コードがマネージド コードを呼び出すと、**[呼び出し履歴]** ウィンドウで以下の不具合が生じます。

- マネージド コードのすぐ上にあるネイティブ フレームが、**[呼び出し履歴]** ウィンドウに表示されない場合があります。 詳細については、「[方法 :ネイティブ フレームが [呼び出し履歴] ウィンドウに見つからないときにマネージド コードからステップ アウトする](../debugger/how-to-step-out-of-managed-code-when-native-frames-are-missing-from-the-call-stack-window.md)」を参照してください。

- デバッガーの外部で起動された混合モード アプリケーションでは、**[呼び出し履歴]** ウィンドウにマネージド コードだけが表示され、ネイティブ フレームがまったく表示されない場合があります。

  上の 2 つの不具合はめったに発生しません。 ネイティブ コードによるマネージド コードの呼び出しでは、ほとんどの場合、正しい呼び出し履歴が表示されます。

## <a name="see-also"></a>関連項目
- [方法: [呼び出し履歴] ウィンドウを使用する](../debugger/how-to-use-the-call-stack-window.md)