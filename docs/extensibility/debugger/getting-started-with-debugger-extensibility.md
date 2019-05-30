---
title: デバッガーの拡張性の概要 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- getting started, Debugging SDK
- debugging [Debugging SDK], getting started
- Debugging SDK, getting started
ms.assetid: d6ce6f43-1409-4bf7-93cd-f3464ca23504
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 99e2dabf18d3d00034d65a94c41f2e435ad64114
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66350013"
---
# <a name="get-started-with-debugger-extensibility"></a>デバッガーの拡張性を概要します。
[!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)]の作成し、カスタマイズのデバッガーのコンポーネント内からプログラムをデバッグするために使用する必要のある情報を提供します、[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]環境。

 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] デバッグと広範な使いやすさの前に行われるテストから派生した機能強化が追加[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]デバッガー。 使用することができます[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]をステップ実行するか、多言語アプリケーションでは、デバッグ、稼働中のアプリケーションと多言語ソリューションのデバッグ中に変数の編集を実装できます。

 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] デバッグして、実行されたプロセス外の - デバッグ中のプログラムでは、さほど、アプリケーションのプロセス空間では、そのため。 その結果、デバッグ、プログラムの影響を与えずに、デバッガーで対話するコンポーネントを記述しやすくなります。

 最適に使用する、 [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)]、次のものでは、理解しておく必要があります。

- [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]統合開発環境 (IDE)

- C++ プログラミング言語

- ATL COM

## <a name="in-this-section"></a>このセクションの内容
 [デバッガーを拡張するためのロードマップ](../../extensibility/debugger/roadmap-for-extending-the-debugger.md)で、コンパイラとその出力によって、製品でのデバッグの実装プロセスについて説明します。

 [デバッガーのコンポーネント](../../extensibility/debugger/debugger-components.md)の概要、[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]デバッグ エンジン (DE)、式エバリュエーター (EE) およびシンボル ハンドラー (SH) のコンポーネントをデバッグします。

 [デバッガーの概念](../../extensibility/debugger/debugger-concepts.md)デバッグ アーキテクチャの主要な概念について説明します。

 [デバッガー コンテキスト](../../extensibility/debugger/debugger-contexts.md)デバッグ エンジン (DE) が同時にして動作し、コード、ドキュメント、および式の評価コンテキスト内で方法について説明します。 3 つのコンテキスト、場所、位置、またはそれに関連する評価ごとに説明します。

 [タスクのデバッグ](../../extensibility/debugger/debugging-tasks.md)さまざまなプログラムの起動や式の評価などのタスクのデバッグへのリンクが含まれています。