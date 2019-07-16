---
title: '方法: スレッド ビューでスレッドを検索 |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- threads, searching
ms.assetid: 5609a9b3-c279-4426-9e2e-dd87896a6d6f
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: fd4014ca9eb99dce383b9de34e26794555b9fbef
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2019
ms.locfileid: "64798520"
---
# <a name="how-to-search-for-a-thread-in-threads-view"></a>方法: スレッド ビューでスレッドを検索する
スレッド ビューで特定のスレッドを検索するには、スレッド ID またはモジュールの文字列を使用して、検索条件として。 検索の最初の方向を指定することもできます。 ダイアログ ボックスのフィールドは、スレッドのツリーで選択されているスレッドの属性を紹介します。

### <a name="to-search-for-a-thread-in-threads-view"></a>スレッド ビューでスレッドを検索するには

1. そのため、ウィンドウを整列 Spy++ は、アクティブな[スレッド ビュー](../debugger/threads-view.md)ウィンドウが表示されます。

2. **検索**] メニューの [選択**スレッド**します。

    [スレッド検索 ダイアログ ボックス](../debugger/thread-search-dialog-box.md)が開きます。

3. 検索条件として、スレッド ID またはモジュールの文字列を入力します。

4. 値を指定しないすべてのフィールドをオフにします。

   > [!TIP]
   > モジュールによって所有されているすべてのスレッドを検索するには、オフ、**スレッド**でテキスト ボックスと、モジュールの種類の名前、**モジュール**ボックス。 使用して**次を検索**スレッドの検索を続行します。

5. 選択**を**または**ダウン**方向を検索します。

6. **[OK]** をクリックします。

   一致するスレッドが見つかると、スレッド ビュー ウィンドウで強調表示されます。