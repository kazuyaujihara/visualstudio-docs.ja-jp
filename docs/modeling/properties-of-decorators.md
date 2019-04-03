---
title: デコレーターのプロパティ
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- Domain-Specific Language, decorators
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 76129141ed293281eeb3179a654f470bcf608bdf
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2019
ms.locfileid: "55907582"
---
# <a name="properties-of-decorators"></a>デコレーターのプロパティ
デコレーターは、アイコン、テキスト、または図形またはコネクタを図に表示される展開/折りたたみの山かっこです。 デコレーターの 3 種類のプロパティを次の表に示します。 一部のプロパティには、シェイプのデコレータでのみ、またはコネクタのデコレーターでのみが表示されます。

 詳細については、[ドメイン固有言語を定義する方法](../modeling/how-to-define-a-domain-specific-language.md)を参照してください。 これらのプロパティを使用する方法の詳細については、[をカスタマイズすると、ドメイン固有言語を拡張する](../modeling/customizing-and-extending-a-domain-specific-language.md)を参照してください。

## <a name="expandcollapse-decorator"></a>デコレータの展開/折りたたみ

|プロパティ|説明|既定値|
|-|-|-|
|DisplayName|生成されたデザイナーに表示されるデコレータの名前。|折りたたみデコレータを展開します。|
|名前|デコレータの名前。|ExpandCollapseDecorator|
|メモ|このデコレータに関連付けられている非公式のメモ。|\<none>|
|HorizontalOffset|(インチ単位)、デコレーターの既定の位置を基準とした水平オフセット。 (図形にのみ。)|0|
|Verticaloffset があります。|(インチ単位)、デコレーターの既定の位置を基準とした垂直オフセット。 (図形にのみ。)|0|
|OffsetFromLine|インチ単位で、既定位置を基準として、コマンドラインからのデコレーターのオフセット。 (コネクタでのみ。)|0|
|OffsetFromShape|インチ単位で、既定位置を基準として、図形からのデコレーターのオフセット。 (コネクタでのみ。)|0|
|位置|デコレーターの既定の位置。|SourceTop|

## <a name="icon-decorator"></a>デコレーターのアイコン

|プロパティ|説明|既定値|
|-|-|-|
|DefaultIcon|表示されるアイコンまたはイメージ ファイルのパス。|\<none>|
|DisplayName|生成されたデザイナーに表示されるデコレータの名前。|デコレーターのアイコン|
|名前|デコレータの名前。|IconDecorator|
|メモ|デコレータに関連付けられている非公式のメモ。|\<none>|
|HorizontalOffset|(インチ単位)、デコレーターの既定の位置を基準とした水平オフセット。 (図形にのみ。)|0|
|Verticaloffset があります。|(インチ単位)、デコレーターの既定の位置を基準とした垂直オフセット。 (図形にのみ。)|0|
|OffsetFromLine|インチ単位で、既定位置を基準として、コマンドラインからのデコレーターのオフセット。 (コネクタでのみ。)|0|
|OffsetFromShape|インチ単位で、既定位置を基準として、図形からのデコレーターのオフセット。 (コネクタでのみ。)|0|
|位置|デコレーターの既定の位置。|SourceTop|

## <a name="textdecorator"></a>TextDecorator

|プロパティ|説明|既定値|
|-|-|-|
|DefaultText|表示される既定のテキスト。|group1|
|DisplayName|生成されたデザイナーに表示されるデコレータの名前。|group1|
|FontSize|デコレーターに表示されるテキストのフォント サイズ。|8|
|FontStyle|デコレーターに表示されるテキストのフォント スタイル。|Regular|
|名前|デコレータの名前。|group1|
|メモ|デコレータに関連付けられている非公式のメモ。|\<none>|
|HorizontalOffset|(インチ単位)、デコレーターの既定の位置を基準とした水平オフセット。 (図形にのみ。)|0|
|Verticaloffset があります。|(インチ単位)、デコレーターの既定の位置を基準とした垂直オフセット。 (図形にのみ。)|0|
|OffsetFromLine|インチ単位で、既定位置を基準として、コマンドラインからのデコレーターのオフセット。 (コネクタでのみ。)|0|
|OffsetFromShape|インチ単位で、既定位置を基準として、図形からのデコレーターのオフセット。 (コネクタでのみ。)|0|
|位置|デコレーターの既定の位置。|TargetBottom|

## <a name="see-also"></a>関連項目

- [ドメイン固有言語ツールの用語集](https://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)