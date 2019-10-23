---
title: ドメイン クラスのプロパティ
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- Domain-Specific Language, domain class
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 23437983950efb8e86aaadd391e96b0e7d0c0a6c
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72658212"
---
# <a name="properties-of-domain-classes"></a>ドメイン クラスのプロパティ
ドメインクラスには、次の表に示すプロパティがあります。 ドメインクラスの詳細については、「[モデル、クラス、およびリレーションシップ](../modeling/understanding-models-classes-and-relationships.md)について」を参照してください。 これらのプロパティの使用方法の詳細については、「[ドメイン固有言語のカスタマイズと拡張](../modeling/customizing-and-extending-a-domain-specific-language.md)」を参照してください。

|property|説明|既定|
|-|-|-|
|アクセス修飾子|ドメイン クラスのアクセスのレベル (`public` または `internal`)。|`public`|
|カスタム属性|このドメインクラスから生成されるソースコードクラスに属性を追加するために使用します。|\<none>|
|2つの派生を生成します|@No__t_0 場合、基本クラスと部分クラス (オーバーライドによるカスタマイズをサポートする) の両方が生成されます。 詳細については、「[生成されたクラスのオーバーライドと拡張](../modeling/overriding-and-extending-the-generated-classes.md)」を参照してください。|`False`|
|カスタムコンストラクターがある|@No__t_0 すると、カスタムコンストラクターがソースコードに提供されます。 詳細については、「[生成されたクラスのオーバーライドと拡張](../modeling/overriding-and-extending-the-generated-classes.md)」を参照してください。|`False`|
|継承修飾子|ドメインクラス (`none`、`abstract` または `sealed`) から生成されるソースコードクラスの継承の種類について説明します。|`none`|
|基本クラス|このドメインクラスが派生している場合は、基本クラスの名前。|\<none>|
|名|このドメインクラスの名前。|現在の名前|
|Namespace|このドメインクラスの名前空間。|現在の名前空間|
|ノート|このドメインクラスに関連付けられている非公式のメモ。|\<none>|
|説明|生成されたデザイナーの UI を文書化するために使用される説明。|\<none>|
|[表示名]|このドメインクラスの生成されたデザイナーに表示される名前。|\<none>|
|ヘルプ キーワード|このドメインクラスの F1 ヘルプのインデックス作成に使用される省略可能なキーワードです。|\<none>|

## <a name="see-also"></a>参照

- [ドメイン固有言語ツールの用語集](https://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)