---
title: 'チュートリアル: 網かけによるレンダリング エラーのデバッグ |Microsoft Docs'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 01875b05-cc7b-4add-afba-f2b776f86974
caps.latest.revision: 17
author: MikeJo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5d65c3d2525533e5881b4626941e43fb302ce2aa
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/16/2018
ms.locfileid: "51733192"
---
# <a name="walkthrough-debugging-rendering-errors-due-to-shading"></a>チュートリアル: 網かけによるレンダリング エラーのデバッグ
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

このチュートリアルでは、 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] のグラフィックス診断を使用して、シェーダーのバグが原因で正しくない色が指定されたオブジェクトを調べる方法を示します。  
  
 このチュートリアルでは、次の方法を示します。  
  
-   問題を示すピクセルを識別するために、グラフィックスのログのドキュメントを調査する。  
  
-   **[グラフィックス ピクセル履歴]** ウィンドウを使用して、ピクセルの状態をより詳しく調査する。  
  
-   **HLSL デバッガー** を使用して、ピクセルと頂点シェーダーを調査する。  
  
## <a name="scenario"></a>シナリオ  
 オブジェクトに正しくない色が指定される問題は、一般的に、頂点シェーダーからピクセル シェーダーに渡される情報が正しくないまたは不完全な場合に発生します。  
  
 このシナリオでは、最近、アプリにオブジェクトとそれを変換する新しい頂点シェーダーとピクセル シェーダーを追加して、オブジェクトに独自の外観を設定したものとします。 テスト中にアプリを実行すると、オブジェクトは黒一色で表示されます。 グラフィックス診断を使うと、問題点をグラフィックス ログにキャプチャし、アプリのデバッグを実行できます。 問題は、アプリケーションでは次のように見えます。  
  
 ![オブジェクトは間違った色でレンダリングされます。](../debugger/media/gfx-diag-demo-render-error-shader-problem.png "gfx_diag_demo_render_error_shader_problem")  
  
## <a name="investigation"></a>調査  
 グラフィックス診断ツールを使うと、グラフィックス ログのドキュメントを読み込んで、テスト中にキャプチャされたフレームを調査できます。  
  
#### <a name="to-examine-a-frame-in-a-graphics-log"></a>グラフィックス ログのフレームを調査するには  
  
1. [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]で、モデルの欠落を表すフレームを含むグラフィックス ログを読み込みます。 新しいグラフィックス ログのドキュメント ウィンドウが [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]に表示されます。 このウィンドウの上部には、選んだフレームのレンダー ターゲットの出力が表示されます。 下部の **[フレーム一覧]** には、キャプチャされた各フレームの縮小版が表示されます。  
  
2. **[フレーム一覧]** で、オブジェクトが正しく表示されていないフレームを選びます。 レンダー ターゲットが更新され、選択したフレームが反映されます。 このシナリオでは、グラフィックのログのドキュメント ウィンドウは次のようになります。  
  
    ![Visual Studio に使用される、グラフィックス ログ ドキュメント。](../debugger/media/gfx-diag-demo-render-error-shader-step-1.png "gfx_diag_demo_render_error_shader_step_1")  
  
   問題を示しているフレームを選んだら、 **[グラフィックス ピクセル履歴]** ウィンドウを使用してそのフレームを診断できます。 **[グラフィックス ピクセル履歴]** ウィンドウに、特定のピクセルに影響を与えていた可能性があるプリミティブとそのシェーダーと、それらがレンダー ターゲットにどのような影響を与えていたかが、時系列順に表示されます。  
  
#### <a name="to-examine-a-pixel"></a>ピクセルを調査するには  
  
1. **[グラフィックス ピクセル履歴]** ウィンドウを開きます。 **[グラフィックス診断]** ツール バーで、 **[ピクセル履歴]** を選びます。  
  
2. 調査するピクセルを選びます。 グラフィックスのログのドキュメント ウィンドウで、正しくない色が指定されたオブジェクトでいずれかのピクセルを選びます。  
  
    ![ピクセルを選択すると、その履歴に関する情報が表示されます。](../debugger/media/gfx-diag-demo-render-error-shader-step-2.png "gfx_diag_demo_render_error_shader_step_2")  
  
    **[グラフィックス ピクセル履歴]** ウィンドウが更新され、選んだピクセルが反映されます。 このシナリオでは、 **[グラフィックス ピクセル履歴]** ウィンドウは次のように表示されます。  
  
    ![ピクセル履歴は、1 つの DrawIndexed イベントを示しています。](../debugger/media/gfx-diag-demo-render-error-shader-step-3.png "gfx_diag_demo_render_error_shader_step_3")  
  
    ピクセル シェーダーの結果は完全に不透明な黒 (0, 0, 0, 1) で表示されること、また、 **[出力マージャー]** によってこれと **[前]** のピクセルの色が結合されるため、 **[結果]** も完全に不透明な黒で表示されることにご注意ください。  
  
   正しくない色が指定されたピクセルを調べて、ピクセル シェーダーの出力が予期していた色ではなかった場合は、HLSL デバッガーを使用してピクセル シェーダーを調べて、オブジェクトの色に何が起こったのかを確認できます。 HLSL デバッガーを使用して、実行中の HLSL 変数の状態を調べ、HLSL コードをステップスルーし、ブレークポイントを設定することによって、問題の診断に役立てることができます。  
  
#### <a name="to-examine-the-pixel-shader"></a>ピクセル シェーダーを調査するには  
  
1. ピクセル シェーダーのデバッグを開始します。 **[グラフィックス ピクセル履歴]** ウィンドウで、オブジェクトのプリミティブの下、 **[ピクセル シェーダー]** の横にある **[デバッグ開始]** ボタンを選びます。  
  
2. このシナリオでは、ピクセル シェーダーは頂点シェーダーの色を渡すのみであるため、ピクセル シェーダーが問題の原因ではないことが容易に確認できます。  
  
3. `input.color`にポインターを置きます。 値が完全に不透明な黒 (0、0、0、1) であることにご注意ください。  
  
    !["Input"の"color"メンバーは黒です。](../debugger/media/gfx-diag-demo-render-error-shader-step-5.png "gfx_diag_demo_render_error_shader_step_5")  
  
    このシナリオでは、ピクセル シェーダーが操作するための色情報を頂点シェーダーが適切に指定していないことが原因で、正しい色が使用されない可能性があることが調査によってわかりました。  
  
   頂点シェーダーが適切な情報をピクセル シェーダーに提供していないことを確認したら、次の手順では頂点シェーダーを調査します。  
  
#### <a name="to-examine-the-vertex-shader"></a>頂点シェーダーを調査するには  
  
1. 頂点シェーダーのデバッグを開始します。 **[グラフィックス ピクセル履歴]** ウィンドウで、オブジェクトのプリミティブの下、 **[頂点シェーダー]** の横にある **[デバッグ開始]** ボタンを選びます。  
  
2. 頂点シェーダーの出力構造体 (ピクセル シェーダーに入力される部分) を探します。 このシナリオでは、この構造体の名前は `output`です。 頂点シェーダー コードを調べて、おそらく他のユーザーがデバッグしたことが原因で、 `color` 構造体の `output` メンバーが完全に不透明な黒に明示的に設定されていることを確認します。  
  
3. 色のメンバーが入力構造からコピーされないことを確認します。 `output.color` 構造が返される直前に `output` の値が完全に不透明な黒に設定されているため、 `output` の値が前の行で正しく初期化されていないことを確認することをお勧めします。 `output.color` の値を観察しながら、`output.color` を黒に設定する行に達するまで頂点シェーダー コードをステップスルーします。 黒に設定されるまで `output.color` の値は初期化されないことにご注意ください。 これにより、 `output.color` を黒に設定するコードの行を削除するのではなく、修正する必要があることが確認できます。  
  
    !["Output.color"の値は黒です。](../debugger/media/gfx-diag-demo-render-error-shader-step-7.png "gfx_diag_demo_render_error_shader_step_7")  
  
   レンダリングの問題の原因が、頂点シェーダーがピクセル シェーダーに適切な色の値を指定していないことであることを確認したら、この情報を使用して問題を解決できます。 このシナリオでは、頂点シェーダーの次のコードを変更することで問題を解決できます。  
  
```  
output.color = float3(0.0f, 0.0f, 0.0f);  
```  
  
 から  
  
```hlsl  
output.color = input.color;  
```  
  
 このコードは、オブジェクトの頂点から頂点色を修正なしで渡します。より複雑な頂点シェーダーでは、渡す前に色が修正される場合があります。 修正された頂点シェーダー コードは次のようになります。  
  
 ![修正された頂点シェーダー コード。](../debugger/media/gfx-diag-demo-render-error-shader-step-8.png "gfx_diag_demo_render_error_shader_step_8")  
  
 コードを修正したら、それをリビルドし、もう一度アプリを実行してレンダリングの問題が解決されたことを確認します。  
  
 ![オブジェクトは正しい色でレンダリングされます。](../debugger/media/gfx-diag-demo-render-error-shader-resolution.png "gfx_diag_demo_render_error_shader_resolution")



