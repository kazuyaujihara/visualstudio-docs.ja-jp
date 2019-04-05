---
title: ドメイン リレーションシップのプロパティ
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- Domain-Specific Language, domain relationships
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a2693994c9ead711f3bb536d0e37f485bc00047b
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2019
ms.locfileid: "55938177"
---
# <a name="properties-of-domain-relationships"></a>ドメイン リレーションシップのプロパティ
次の表に、プロパティは、ドメイン リレーションシップに関連付けられます。 ドメイン リレーションシップについては、[理解のモデル、クラスとリレーションシップ](../modeling/understanding-models-classes-and-relationships.md)を参照してください。 これらのプロパティを使用する方法の詳細については、[をカスタマイズすると、ドメイン固有言語を拡張する](../modeling/customizing-and-extending-a-domain-specific-language.md)を参照してください。

|プロパティ|説明|既定値|
|-|-|-|
|アクセス修飾子|ドメイン リレーションシップのアクセスのレベル (`public`または`internal`)。|`public`|
|カスタム属性|ドメイン リレーションシップから生成されるソース コードのクラスに属性を追加するために使用します。|\<none>|
|Double 型を生成します派生。|場合`True`、基底クラスと (オーバーライドによってカスタマイズをサポート) する部分クラスの両方が生成されます。 詳細については、[をオーバーライドすると、生成されたクラスを拡張する](../modeling/overriding-and-extending-the-generated-classes.md)を参照してください。|`False`|
|カスタム コンス トラクターがあります。|場合`True`、カスタム コンス トラクターがソース コードで提供されることを示します。 詳細については、[をオーバーライドすると、生成されたクラスを拡張する](../modeling/overriding-and-extending-the-generated-classes.md)を参照してください。|`False`|
|継承修飾子|ドメイン リレーションシップから生成されるソース コードのクラスの継承の種類について説明します (`none`、`abstract`または`sealed`)。|\<none>|
|重複を許可します。|場合`True`、同じ 2 つの要素間、ドメイン リレーションシップの重複リンクが作成されます。|`False`|
|基本リレーションシップ|ドメイン リレーションシップを派生の場合、ドメイン リレーションシップのベース リレーションシップ。|\<none>|
|埋め込みは|場合`True`、ドメイン リレーションシップが埋め込みリレーションシップ。 場合`False`リレーションシップの参照リレーションシップです。|\<both>|
|名前|ドメイン リレーションシップの名前。|現在の名前|
|名前空間|ドメイン リレーションシップに関連付けられた名前空間。|現在の名前空間|
|メモ|ドメイン リレーションシップに関連付けられている非公式のメモ。|\<none>|
|説明|コードを文書化するために使用しては、生成されたデザイナーの UI で使用する説明。|\<none>|
|表示名|ドメイン リレーションシップに対して生成されたデザイナーに表示される名前です。|\<none>|
|ヘルプ キーワード|ドメイン リレーションシップの F1 ヘルプのインデックスを作成するために使用する省略可能なキーワード。|\<none>|

## <a name="see-also"></a>関連項目

- [ドメイン固有言語ツールの用語集](https://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)