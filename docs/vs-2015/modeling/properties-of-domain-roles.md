---
title: Domain Roles | のプロパティMicrosoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: reference
ms.assetid: 5a7bb18c-638e-45e8-9d79-9aa6a9e14b0e
caps.latest.revision: 11
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: a0cddfb3d5c95e5636e9dac069106e3010bedff8
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72671468"
---
# <a name="properties-of-domain-roles"></a>ドメイン ロールのプロパティ
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

次の表のプロパティは、ドメインロールに関連付けられています。 ドメインロールの詳細については、「[モデル、クラス、およびリレーションシップ](../modeling/understanding-models-classes-and-relationships.md)について」を参照してください。 これらのプロパティの使用方法の詳細については、「[ドメイン固有言語のカスタマイズと拡張](../modeling/customizing-and-extending-a-domain-specific-language.md)」を参照してください。

|property|説明|既定|
|--------------|-----------------|-------------|
|コレクション型|このロールの複数要素の接続性が 0.. * または 1. の場合。\*、このプロパティは、リンクのコレクションを格納するために使用されるジェネリック型をカスタマイズします。|`(none)`  -  <xref:Microsoft.VisualStudio.Modeling.LinkedElementCollection%601> が使用されています|
|カスタム属性|ここで指定する属性は、生成されるコードクラスに属性として追加されます。|\<none>|
|プロパティが参照可能|@No__t_0 の場合、リレーションシップの複数要素の接続性が 0 ..1 または 1 ..1 の場合、 **[プロパティ]** ウィンドウでユーザーがロールプロパティを参照できます。 プロパティは、リレーションシップリンクのもう一方の端の要素の名前を表示します。|`True`|
|プロパティジェネレーター|@No__t_0 すると、このロールのロールプロパティが生成されます。これを使用して、プログラムコード内のリレーションシップを走査できます。 この値を false に設定すると、ドメインリレーションシップの静的メソッドを使用して、より効率的な方法でリレーションシップを走査できます。|`True`|
|プロパティ Getter アクセス修飾子|生成されたプロパティ (`public`、`internal`、`private`、`protected`、または `protected internal`) の getter のアクセス修飾子。|`public`|
|プロパティ Setter アクセス修飾子|生成されたプロパティ (`public`、`internal`、`private`、`protected`、または `protected internal`) のセッターのアクセス修飾子。|`public`|
|複数要素の接続性|反対のロール (`0..1`、`1..1`、`0..*`、または `1..*`) を再生できるモデル要素の数。 多重度が `0..*` または `1..*` の場合、生成されたプロパティはコレクションを表します。それ以外の場合、生成されるプロパティは1つのモデル要素を表します。|リレーションシップの種類と、リレーションシップのソースロールまたはターゲットロールであるかどうかによって異なります。|
|名|ドメインロールの名前。 このプロパティに空白を含めることはできません。|このロールのロールプレーヤーのドメインクラスの名前。|
|コピーの伝達|`DoNotPropagateCopy`-コピーされたロールプレーヤーには、このリンクのコピーはありません。<br /><br /> `PropagateCopyToLinkOnly`-コピーされたリンクは、既存の反対のロールプレーヤーを指します。<br /><br /> `PropagateCopyToLinkAndOppositeRolePlayer`-コピーされたリンクは、反対側のロールプレーヤーのコピーを指します。|埋め込みのソースロールの `PropagateCopyToLinkAndOppositeRolePlayer`。<br /><br /> 他のロールの `DoNotPropagateCopy` します。<br /><br /> 詳細については、「[コピー動作のカスタマイズ](../modeling/customizing-copy-behavior.md)」を参照してください。|
|削除の伝達|関連付けられたリンクが削除されたときにこのロールを再生する要素を削除するには、`True` します。|埋め込みロールのターゲットの `True`。<br /><br /> 他のロールの `False` します。<br /><br /> 詳細については、「[削除動作のカスタマイズ](../modeling/customizing-deletion-behavior.md)」を参照してください。|
|プロパティ名|ロールプレーヤーのコードで生成されたプロパティの名前。 この名前に空白を含めることはできません。|このロールがゼロ対一または一対一の複数要素の接続性を持つ場合の、反対側のロールの名前。それ以外の場合は、反対側のロールの複数化名。|
|ロールプレーヤー|リレーションシップでこのロールを再生できる要素のドメインクラス。 このプロパティは読み取り専用です。|このロールのロールプレーヤーのドメインクラス。|
|ノート|ドメインロールに関連付けられている非公式のメモ。|\<none>|
|カテゴリ|生成されたデザイナーの **[プロパティ]** ウィンドウに生成されたプロパティが表示されるカテゴリ。 このプロパティが空の場合、生成されたプロパティは [その**他**] カテゴリの下に表示されます。|\<none>|
|説明|コードをドキュメント化するために使用される説明。生成されたデザイナーの UI で使用されます。<br /><br /> この説明は、ロールプレーヤークラスで生成されたプロパティの Intellisense ツールヒントに表示されます。|*ロールの完全な名前を `Description for` します*。|
|[表示名]|生成されたデザイナーに表示されるドメインロールの名前。|Name プロパティの調整された値。|
|ヘルプ キーワード|ドメインロールの F1 ヘルプのインデックス作成に使用される省略可能なキーワードです。|\<none>|
|プロパティの表示名|生成されたデザイナーに表示される、生成されたロールプロパティの名前。|プロパティ名プロパティの調整された値。|

> [!NOTE]
> 表示名の既定値は、関連付けられているプロパティ値に基づいています。各大文字の前に小文字の前にスペースを挿入し、その後に別の大文字の文字が続く場合は、その前にスペースを挿入します。

## <a name="see-also"></a>参照
 [ドメイン リレーションシップのプロパティ](../modeling/properties-of-domain-relationships.md)
