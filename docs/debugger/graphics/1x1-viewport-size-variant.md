---
title: 1 x 1 ビューポート サイズ バリアント |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 3dbc3247-00f5-4644-8ff9-72e9febcf09a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a5b2c96b11c2075ce88b43cdebc34b905141c973
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62848743"
---
# <a name="1x1-viewport-size-variant"></a>1x1 ビューポイント サイズ バリアント
すべてのレンダー ターゲットでビューポートのディメンションを 1x1 ピクセルに減らします。

## <a name="interpretation"></a>解釈
 ビューポートを小さくでは、網掛けする必要があるピクセルの数を減らします。 ビューポートを小さくする必要がある頂点の数を削減しませんが、処理します。 ビューポートのディメンションを 1x1 ピクセルに設定すると、アプリケーションでピクセルのシェーディングを効果的に除去することができます。

 このバリアントでは、大規模なパフォーマンスの向上を示している場合、アプリが多すぎるのフィル レートを使用していることを示す場合します。 さらの解像度は、ターゲット プラットフォームに対して高すぎる可能性がありますか、アプリは、後で上書きされるピクセルの膨大な時間シェーディングを費やすことができました、別名*オーバー ドロー*します。 小さなフレーム バッファーまたはアルファブレンディングを減らすには、アプリのパフォーマンスが向上します。

## <a name="remarks"></a>Remarks
 `ID3D11DeviceContext::OMSetRenderTargets` または `ID3D11DeviceContext::RSSetViewports` への呼び出しが行われるたびに、ビューポートのディメンションは 1x1 ピクセルにリセットされます。

## <a name="example"></a>例
 このバリアントは、次のコードで再現ことができます。

```cpp
D3D11_VIEWPORT viewport;
viewport.TopLeftX = 0;
viewport.TopLeftY = 0;
viewport.Width = 1;
viewport.Height = 1;
d3d_context->RSSetViewports(1, &viewport);
```
