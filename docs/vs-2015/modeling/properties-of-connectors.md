---
title: コネクタのプロパティ |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: reference
helpviewer_keywords:
- Domain-Specific Language, connectors
ms.assetid: b1f24e8d-cdd7-4a5d-af37-1038f43b45c7
caps.latest.revision: 23
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 50e88a37e9d22fa99752864d1acbbeb4d15e6dab
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58963268"
---
# <a name="properties-of-connectors"></a>コネクタのプロパティ
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

コネクタは、生成されたデザイナーにおけるドメイン リレーションシップを表します。  
  
 詳細については、次を参照してください。[ドメイン固有言語を定義する方法](../modeling/how-to-define-a-domain-specific-language.md)します。 これらのプロパティを使用する方法の詳細については、次を参照してください。[をカスタマイズすると、ドメイン固有言語を拡張する](../modeling/customizing-and-extending-a-domain-specific-language.md)します。  
  
 コネクタでは、次の表に記載されているプロパティがあります。  
  
|プロパティ|説明|既定値|  
|--------------|-----------------|-------------|  
|色|このコネクタの色。|黒|  
|実線/点線スタイル|(実線、ダッシュ、ドット、DashDot、DashDotDot、またはカスタム) は、このコネクタの線の実線/点線スタイル。|[実線]|  
|ソース エンドのスタイル|(HollowArrow、EmptyArrow、FilledArrow、EmptyDiamond、FilledDiamond、または None) は、このコネクタのソース エンドのスタイル。|なし|  
|ターゲット エンドのスタイル|(HollowArrow、EmptyArrow、FilledArrow、EmptyDiamond、FilledDiamond、または None) は、このコネクタのターゲット エンドのスタイル。|なし|  
|テキストの色|このコネクタに関連付けられているテキスト デコレーターに使用される色。|黒|  
|太さ|このコネクタの線の太さがインチ単位で測定されます。|0.03125|  
|アクセス修飾子|クラスのアクセスのレベル (`public`または`internal`)。|Public|  
|カスタム属性|このコネクタから生成されるソース コードのクラスに属性を追加するために使用します。|\<none>|  
|Double 型を生成します派生。|場合`True`、基底クラスと (オーバーライドによってカスタマイズをサポート) する部分クラスの両方が生成されます。 詳細については、次を参照してください。[をオーバーライドすると、生成されたクラスを拡張する](../modeling/overriding-and-extending-the-generated-classes.md)します。|False|  
|カスタム コンストラクターがあります。|場合`True`、カスタム コンストラクターは、ソース コードで提供されます。 詳細については、次を参照してください。[をオーバーライドすると、生成されたクラスを拡張する](../modeling/overriding-and-extending-the-generated-classes.md)します。|False|  
|継承修飾子|コネクタから生成されるソース コードのクラスの継承の種類について説明します (`none`、`abstract`または`sealed`)。|none|  
|基本コネクタ|このコネクタの基本クラス。|(なし)|  
|名前|このコネクタの名前。|現在の名前|  
|名前空間|このコネクタに関連付けられた名前空間。|現在の名前空間|  
|ツールヒントの種類|(固定、変数、またはなし)、ツールヒントを定義する方法。 、しの値を固定する場合、`Fixed Tooltip Text`プロパティ、ツール ヒントとして使用されます。 変数の場合、ツールヒントがカスタム コードで定義します。|\<none>|  
|メモ|このコネクタに関連付けられている非公式のメモ。|\<none>|  
|ルーティング スタイル|コネクタのルーティングに使用されるスタイル。 A`Rectilinear`コネクタは、必要に応じて直角になります、`Straight`コネクタはありません。|直角|  
|プロパティとして公開されている色<br /><br /> プロパティとして公開される破線のスタイル<br /><br /> プロパティとして公開されている太さ<br /><br /> テキストの色を公開します。|場合`True`図形の規定されたプロパティを設定できます。 この設定は、シェイプの定義を右クリックし、クリックして**公開追加**します。|False|  
|説明|生成されたデザイナーを文書化するために使用します。|\<none>|  
|表示名|このコネクタの生成されたデザイナーに表示される名前です。|\<none>|  
|固定のツールヒント テキスト|固定のツールヒントに使用されるテキスト。|\<none>|  
|ヘルプ キーワード|この要素の F1 ヘルプのインデックスを作成するために使用するキーワードです。|\<none>|  
  
## <a name="see-also"></a>関連項目  
 [ドメイン固有言語ツールの用語集](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)
