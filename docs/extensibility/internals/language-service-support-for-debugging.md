---
title: デバッグのための言語サービスのサポート |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugger, language support
- language services, debugging support
ms.assetid: 7a44067f-a410-4a6a-84d2-bda5184140bc
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 18856d2f3a6359a3be019e4e97e63832e896c2a9
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56604744"
---
# <a name="language-service-support-for-debugging"></a>デバッグのための言語サービスのサポート
言語サービスが使用して、デバッガーをサポートする機能を提供できる、<xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageDebugInfo>インターフェイス。 これらの機能は、ブレークポイントの検証と式のリストを指定、 **[自動変数]** ウィンドウ。

 ただし、式エバリュエーターを使用する言語をデバッグする必要があります。 式エバリュエーターではデバッグ中に値を生成するために式を評価する責任を負います。 CLR 式エバリュエーターの実装方法の詳細については、参照してください。

-   [CLR 式エバリュエーター](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators)

-   [マネージ式エバリュエーターのサンプル](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)

## <a name="compiler-output"></a>コンパイラ出力
 コンパイラの型は、お使いの言語のデバッグを実装するために必要事項を決定します。 コンパイラは、Windows オペレーティング システムを対象とし、デバッグ エンジンを Visual Studio に統合されているネイティブ コードとプログラムをデバッグすることができます、.pdb ファイルを書き込みます。 場合、 Microsoft intermediate language (MSIL) を生成するコンパイラ、デバッグ エンジンは、Visual Studio にも統合されているマネージ コードでプログラムをデバッグできます。 独自のオペレーティング システムまたは別のランタイム環境をコンパイラが対象とする場合は、デバッグ エンジンを記述する必要があります。

 お使いの言語のデバッグの実装の詳細については、次を参照してください。 [Getting Started](../../extensibility/debugger/getting-started-with-debugger-extensibility.md)で Visual Studio Debugging SDK。