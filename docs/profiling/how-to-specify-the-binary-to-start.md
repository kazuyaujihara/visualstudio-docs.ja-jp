---
title: '方法: 開始するバイナリを指定する | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.performance.property.itemlaunch
helpviewer_keywords:
- profiling tools, launching
- performance tools, launching
- performance sessions, launching
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a03bf203e5078bdbdf6327ec7bda186613a25c03
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62996136"
---
# <a name="how-to-specify-the-binary-to-start"></a>方法: 開始するバイナリを指定する

DLL などのバイナリをプロファイルするには、**[\<Target> プロパティ ページ]** ダイアログ ボックスに情報を入力する必要があります。 この情報は、DLL プロジェクトの呼び出し元アプリケーションの場所を示します。

1. **パフォーマンス エクスプローラー**で、対象のバイナリを右クリックし、**[プロパティ]** をクリックします。

2. **[プロパティ ページ]** ダイアログ ボックスで、**[起動]** プロパティをクリックします。

3. **[プロジェクト プロパティのオーバーライド]** チェック ボックスを選択します。

4. **[起動する実行可能ファイル]** テキスト ボックスで、ファイルの場所を指定します。

5. **[引数]** テキスト ボックスで、アプリケーションを起動するのに必要な引数を指定します。

6. **[作業ディレクトリ]** テキスト ボックスで、ディレクトリの場所を指定します。

7. **[OK]** をクリックします。

## <a name="see-also"></a>関連項目

[パフォーマンス セッションの構成](../profiling/configuring-performance-sessions.md)