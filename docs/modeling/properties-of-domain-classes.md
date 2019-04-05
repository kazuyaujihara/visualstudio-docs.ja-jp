---
title: ドメイン クラスのプロパティ
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- Domain-Specific Language, domain class
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: fb66a0d497c86091f689f119e57a5230f125e8de
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2019
ms.locfileid: "55938125"
---
# <a name="properties-of-domain-classes"></a>ドメイン クラスのプロパティ
ドメイン クラスでは、次の表に、プロパティがあります。 ドメイン クラスについては、[理解のモデル、クラスとリレーションシップ](../modeling/understanding-models-classes-and-relationships.md)を参照してください。 これらのプロパティを使用する方法の詳細については、[をカスタマイズすると、ドメイン固有言語を拡張する](../modeling/customizing-and-extending-a-domain-specific-language.md)を参照してください。

|プロパティ|説明|既定値|
|-|-|-|
|アクセス修飾子|ドメイン クラスのアクセスのレベル (`public` または `internal`)。|`public`|
|カスタム属性|このドメイン クラスから生成されるソース コードのクラスに属性を追加するために使用します。|\<none>|
|Double 型を生成します派生。|場合`True`、基底クラスと (オーバーライドによってカスタマイズをサポート) する部分クラスの両方が生成されます。 詳細については、[をオーバーライドすると、生成されたクラスを拡張する](../modeling/overriding-and-extending-the-generated-classes.md)を参照してください。|`False`|
|カスタム コンス トラクターがあります。|場合`True`、カスタム コンス トラクターは、ソース コードで提供されます。 詳細については、[をオーバーライドすると、生成されたクラスを拡張する](../modeling/overriding-and-extending-the-generated-classes.md)を参照してください。|`False`|
|継承修飾子|ドメイン クラスから生成されるソース コードのクラスの継承の種類について説明します (`none`、`abstract`または`sealed`)。|`none`|
|基本クラス|このドメイン クラスが派生の場合、基底クラスの名前。|\<none>|
|名前|このドメイン クラスの名前。|現在の名前|
|名前空間|このドメイン クラスの名前空間。|現在の名前空間|
|メモ|このドメイン クラスに関連付けられている非公式のメモ。|\<none>|
|説明|生成されたデザイナーの UI を文書化するために使用する説明。|\<none>|
|表示名|このドメイン クラスの生成されたデザイナーに表示される名前です。|\<none>|
|ヘルプ キーワード|このドメイン クラスの F1 ヘルプのインデックスを作成するために使用する省略可能なキーワード。|\<none>|

## <a name="see-also"></a>関連項目

- [ドメイン固有言語ツールの用語集](https://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)