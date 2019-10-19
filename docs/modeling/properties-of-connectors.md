---
title: コネクタのプロパティ
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- Domain-Specific Language, connectors
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2244b191bac2456886368992d1dc8f1c571dc227
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72658259"
---
# <a name="properties-of-connectors"></a>コネクタのプロパティ
コネクタは、生成されたデザイナーのドメインリレーションシップを表します。

 詳細については、「[ドメイン固有言語を定義する方法](../modeling/how-to-define-a-domain-specific-language.md)」を参照してください。 これらのプロパティの使用方法の詳細については、「[ドメイン固有言語のカスタマイズと拡張](../modeling/customizing-and-extending-a-domain-specific-language.md)」を参照してください。

 コネクタには、次の表に示すプロパティがあります。

|property|説明|既定|
|-|-|-|
|Color|このコネクタの色。|黒|
|破線のスタイル|このコネクタの線の破線スタイル (実線、ダッシュ、ドット、ダッシュドット、ダッシュ Dotドット、またはカスタム)。|[実線]|
|ソースエンドのスタイル|このコネクタのソースエンドのスタイル (Microsoft.visualstudio.modeling.diagrams.connectorarrowstyle.hollowarrow、EmptyArrow、Fil Arrow、Emptyarrow、Fil 菱形、または None)。|None|
|ターゲットエンドのスタイル|このコネクタのターゲットエンドのスタイル (Microsoft.visualstudio.modeling.diagrams.connectorarrowstyle.hollowarrow、EmptyArrow、Fil Arrow、Emptyarrow、Fil 菱形、または None)。|None|
|テキストの色|このコネクタに関連付けられているテキストデコレーターに使用される色です。|黒|
|太さ|このコネクタの線の太さ (インチ単位)。|0.03125|
|アクセス修飾子|クラスのアクセスレベル (`public` または `internal`)。|Public|
|カスタム属性|このコネクタから生成されるソースコードクラスに属性を追加するために使用します。|\<none>|
|2つの派生を生成します|@No__t_0 場合、基本クラスと部分クラス (オーバーライドによるカスタマイズをサポートする) の両方が生成されます。 詳細については、「[生成されたクラスのオーバーライドと拡張](../modeling/overriding-and-extending-the-generated-classes.md)」を参照してください。|False|
|カスタムコンストラクターがある|@No__t_0 すると、カスタムコンストラクターがソースコードに提供されます。 詳細については、「[生成されたクラスのオーバーライドと拡張](../modeling/overriding-and-extending-the-generated-classes.md)」を参照してください。|False|
|継承修飾子|コネクタから生成されるソースコードクラスの継承の種類 (`none`、`abstract` または `sealed`) について説明します。|none|
|基本コネクタ|このコネクタの基本クラス。|(なし)|
|名|このコネクタの名前。|現在の名前|
|Namespace|このコネクタに関連付けられている名前空間。|現在の名前空間|
|ツールヒントの種類|ツールヒントがどのように定義されているか (fixed、variable、none)。 固定されている場合は、`Fixed Tooltip Text` プロパティの値がツールヒントとして使用されます。変数の場合、ツールヒントはカスタムコードで定義されます。|\<none>|
|ノート|このコネクタに関連付けられている非公式のメモ。|\<none>|
|ルーティングのスタイル|コネクタのルーティングに使用されるスタイルです。 @No__t_0 コネクタを使用すると、必要に応じて直角になります。`Straight` コネクタにはありません。|直角|
|プロパティとして公開された色<br /><br /> プロパティとして公開される破線のスタイル<br /><br /> プロパティとして公開された太さ<br /><br /> テキストの色を公開します|@No__t_0 した場合、ユーザーは図形の指定されたプロパティを設定できます。 これを設定するには、図形定義を右クリックし、 **[公開の追加]** をクリックします。|False|
|説明|生成されたデザイナーを文書化するために使用します。|\<none>|
|[表示名]|このコネクタの生成されたデザイナーに表示される名前。|\<none>|
|固定ツールヒントのテキスト|固定のツールヒントに使用されるテキスト。|\<none>|
|ヘルプ キーワード|この要素の F1 ヘルプのインデックスを作成するために使用されるキーワード。|\<none>|

## <a name="see-also"></a>参照

- [ドメイン固有言語ツールの用語集](https://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)