---
title: '方法: シンボル情報をシリアル化する | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Performance.General
helpviewer_keywords:
- profiling tools, serializing symbol information
- performance tools, serializing symbol information
ms.assetid: 9e0da706-6325-4073-83d1-aeab3b7c137a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 3b88268ba0ed8b1c324eda08ec3db969e088f279
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62539253"
---
# <a name="how-to-serialize-symbol-information"></a>方法: シンボル情報をシリアル化する
アプリケーションの分析に必要なシンボルをシリアル化できます。 シンボルをシリアル化すると、.*vsp* ファイルにシンボルが追加されます。 シンボル情報を .*vsp* ファイルに追加すると、他のユーザーは元のシンボルにアクセスすることなく、パフォーマンス レポートを分析できるようになります。 シンボルがシリアル化されない場合は、元のインストルメント化された .*exe* ファイルおよび .*pdb* ファイルで .*vsp* ファイルを分析する必要があります。

### <a name="to-automatically-serialize-symbol-information"></a>シンボル情報を自動的にシリアル化するには

1. **[ツール]** メニューの **[オプション]** をクリックします。

     **[オプション]** ダイアログ ボックスが表示されます。

2. **[パフォーマンス ツール]** をクリックします。

3. **[全般設定]** で **[シンボル情報を自動的にシリアル化]** を選択します。

## <a name="see-also"></a>関連項目
- [パフォーマンス セッションの構成](../profiling/configuring-performance-sessions.md)
- [方法: Windows シンボル情報を参照する](../profiling/how-to-reference-windows-symbol-information.md)
- [方法: 分析されたレポート ファイルを保存する](/previous-versions/visualstudio/visual-studio-2010/bb763106\(v\=vs.100\))