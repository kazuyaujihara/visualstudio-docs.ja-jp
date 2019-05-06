---
title: Visual C/C++カスタム ビジュアライザーの互換性
ms.date: 01/28/2019
ms.prod: visual-studio-dev16
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- debugging assertions
- assertions, debugging
- assertions, assertion failures
- Assertion Failed dialog box
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
monikerRange: '>= vs-2019'
ms.openlocfilehash: 32e38dd3bba8a1127d8756972b73e8b47a514f1b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62901167"
---
# <a name="visual-cc-custom-visualizer-compatibility"></a>Visual C/C++カスタム ビジュアライザーの互換性

Visual Studio 2019、ビジュアルで起動C++そのメモリを消費するコンポーネントをホストするための外部の 64 ビット プロセスを使用する、強化されたデバッガーが含まれています。 この更新では、Visual C に特定の拡張機能の一部として/C++式エバリュエーターを更新して、新しいデバッガーに対応できるようにする必要があります。

従来の C を使用して現在場合/C++ EE アドインまたは C/C++カスタム ビジュアライザーは、オフにできますこの外部プロセスの使用量に移動して**ツール** > **オプション** > **デバッグ**にしてからオフ**ロード デバッグ記号は、外部プロセス (ネイティブのみ) で**します。 このオプションを選択解除した場合は、IDE (devenv.exe) プロセス内でのメモリ使用量が大幅に増加が発生します。 そのため、大規模なプロジェクトをデバッグする場合は、このデバッグ オプションの互換性を確保する、拡張機能の所有者を使用することをお勧めします。

従来の C の所有者/C++ EE アドインまたは C/C++カスタム ビジュアライザーは、上のワーカー プロセスの拡張機能の読み込みを選択の詳細についてを見つけることができます、 [Concord 機能拡張サンプル wiki](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Worker-Process-Remoting)します。 検索することも、 [C/C++カスタム ビジュアライザー サンプル](https://github.com/Microsoft/ConcordExtensibilitySamples/tree/master/CppCustomVisualizer)します。