---
title: デコレーター | のプロパティMicrosoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: reference
helpviewer_keywords:
- Domain-Specific Language, decorators
ms.assetid: f6322fe5-dc08-4d32-a6b3-0bd18879136d
caps.latest.revision: 25
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: cb837c9b3d465d229f64fac08dac02af8d50f5fa
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72652018"
---
# <a name="properties-of-decorators"></a>デコレーターのプロパティ
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

デコレーターは、図の図形またはコネクタに表示されるアイコン、テキスト、または展開/折りたたみの山かっこです。 次の表は、3種類のデコレータのプロパティを示しています。 一部のプロパティは、図形デコレーターまたはコネクタデコレーターにのみ表示されます。

 詳細については、「[ドメイン固有言語を定義する方法](../modeling/how-to-define-a-domain-specific-language.md)」を参照してください。 これらのプロパティの使用方法の詳細については、「[ドメイン固有言語のカスタマイズと拡張](../modeling/customizing-and-extending-a-domain-specific-language.md)」を参照してください。

## <a name="expandcollapse-decorator"></a>デコレータの展開/折りたたみ

|property|説明|既定|
|--------------|-----------------|-------------|
|DisplayName|生成されたデザイナーに表示されるデコレータの名前。|折りたたみデコレータの展開|
|名|デコレータの名前。|ExpandCollapseDecorator|
|ノート|このデコレータに関連付けられている非公式のメモ。|\<none>|
|System.windows.controls.primitives.iscrollinfo.horizontaloffset|デコレータの既定の位置を基準とする水平方向のオフセット (インチ単位)。 (図形のみ)。|0|
|System.windows.controls.primitives.popup.verticaloffset|デコレータの既定の位置を基準とする垂直方向のオフセット (インチ単位)。 (図形のみ)。|0|
|OffsetFromLine|既定の位置を基準とした、線からのデコレータのオフセット (インチ単位)。 (コネクタの場合のみ)。|0|
|OffsetFromShape|形状からの、既定の位置を基準とする、インチ単位の、デコレータのオフセット。 (コネクタの場合のみ)。|0|
|位置|デコレータの既定の位置。|Microsoft.visualstudio.modeling.diagrams.connectordecoratorposition.sourcetop|

## <a name="icon-decorator"></a>アイコンデコレータ

|property|説明|既定|
|--------------|-----------------|-------------|
|DefaultIcon|表示するアイコンまたはイメージファイルのパス。|\<none>|
|DisplayName|生成されたデザイナーに表示されるデコレータの名前。|アイコンデコレータ|
|名|デコレータの名前。|IconDecorator|
|ノート|デコレータに関連付けられている非公式のメモ。|\<none>|
|System.windows.controls.primitives.iscrollinfo.horizontaloffset|デコレータの既定の位置を基準とする水平方向のオフセット (インチ単位)。 (図形のみ)。|0|
|System.windows.controls.primitives.popup.verticaloffset|デコレータの既定の位置を基準とする垂直方向のオフセット (インチ単位)。 (図形のみ)。|0|
|OffsetFromLine|既定の位置を基準とした、線からのデコレータのオフセット (インチ単位)。 (コネクタの場合のみ)。|0|
|OffsetFromShape|形状からの、既定の位置を基準とする、インチ単位の、デコレータのオフセット。 (コネクタの場合のみ)。|0|
|位置|デコレータの既定の位置。|Microsoft.visualstudio.modeling.diagrams.connectordecoratorposition.sourcetop|

## <a name="textdecorator"></a>TextDecorator

|property|説明|既定|
|--------------|-----------------|-------------|
|DefaultText|表示される既定のテキスト。|group1|
|DisplayName|生成されたデザイナーに表示されるデコレータの名前。|group1|
|FontSize|デコレータに表示されるテキストのフォントサイズ。|8|
|FontStyle|デコレータに表示されるテキストのフォントスタイル。|Regular|
|名|デコレータの名前。|group1|
|ノート|デコレータに関連付けられている非公式のメモ。|\<none>|
|System.windows.controls.primitives.iscrollinfo.horizontaloffset|デコレータの既定の位置を基準とする水平方向のオフセット (インチ単位)。 (図形のみ)。|0|
|System.windows.controls.primitives.popup.verticaloffset|デコレータの既定の位置を基準とする垂直方向のオフセット (インチ単位)。 (図形のみ)。|0|
|OffsetFromLine|既定の位置を基準とした、線からのデコレータのオフセット (インチ単位)。 (コネクタの場合のみ)。|0|
|OffsetFromShape|形状からの、既定の位置を基準とする、インチ単位の、デコレータのオフセット。 (コネクタの場合のみ)。|0|
|位置|デコレータの既定の位置。|Microsoft.visualstudio.modeling.diagrams.connectordecoratorposition.targetbottom|

## <a name="see-also"></a>参照
 [ドメイン固有言語ツールの用語集](https://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)
