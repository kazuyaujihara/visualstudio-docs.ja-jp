---
title: '方法: テストおよびデバッグのビジュアライザー |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- visualizers, testing
- visualizers, debugging
- debugging [Visual Studio], visualizers
ms.assetid: 5cc12ce8-c819-48e4-b487-98d403001b28
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f0353234e5a266ca1a344ce7bc304f27d8c3af95
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62906285"
---
# <a name="how-to-test-and-debug-a-visualizer"></a>方法: ビジュアライザーをテストおよびデバッグする
ビジュアライザーを記述したら、デバッグとテストを行う必要があります。

テスト方法の 1 つとして、ビジュアライザーを Visual Studio にインストールし、デバッガー ウィンドウから呼び出します。 (「[方法: ビジュアライザーをインストールする](../debugger/how-to-install-a-visualizer.md)」を参照してください。)この方法では、Visual Studio のインスタンスをもう 1 つ使用してビジュアライザーの追加とデバッグを行う必要があります。デバッグ対象のビジュアライザーは、デバッガーの最初のインスタンス内で実行されます。

ビジュアライザーのデバッグをより簡単に行うには、ビジュアライザーをテスト ドライバーから実行します。 ビジュアライザー API では、*ビジュアライザー開発ホスト*と呼ばれるこのようなドライバーを簡単に作成できます。

### <a name="to-create-a-visualizer-development-host"></a>ビジュアライザー開発ホストを作成するには

1. デバッガー側のクラスに <xref:Microsoft.VisualStudio.DebuggerVisualizers.VisualizerDevelopmentHost> オブジェクトを作成する静的メソッドを含め、その Show メソッドを呼び出します。

    ```csharp
    public static void TestShowVisualizer(object objectToVisualize)
    {
        VisualizerDevelopmentHost myHost = new VisualizerDevelopmentHost(objectToVisualize, typeof(DebuggerSide));
        myHost.ShowVisualizer();
    }
    ```

    ホストの構築に使用するパラメーターは、ビジュアライザーに表示されるデータ オブジェクト (`objectToVisualize`) とデバッガー側のクラスの型です。

2. `TestShowVisualizer` を呼び出すための次のステートメントを追加します。 クラス ライブラリにビジュアライザーを作成した場合は、そのクラス ライブラリを呼び出す実行可能ファイルを作成し、このステートメントをその実行可能ファイルに配置します。

    ```csharp
    DebuggerSide.TestShowVisualizer(myString);
    ```

    詳細な例では、次を参照してください。[チュートリアル。C# でビジュアライザーを記述する](../debugger/walkthrough-writing-a-visualizer-in-csharp.md)します。

## <a name="see-also"></a>関連項目
- [チュートリアル: C# でビジュアライザーを記述する](../debugger/walkthrough-writing-a-visualizer-in-csharp.md)
- [方法: ビジュアライザーをインストールする](../debugger/how-to-install-a-visualizer.md)
- [カスタム ビジュアライザーを作成する](../debugger/create-custom-visualizers-of-data.md)
