---
title: DSL 定義のプロパティ
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- Domain-Specific Language, definition file
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1ae26dc54c8f57348ed00196d86629e3515a1835
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72748339"
---
# <a name="properties-of-a-dsl-definition"></a>DSL 定義のプロパティ
DslDefinition プロパティは、バージョン番号付けなど *、ドメイン固有言語*定義のプロパティを定義します。 DslDefinition プロパティは、*ドメイン固有言語デザイナー*でダイアグラムの空いている領域をクリックすると、 **[プロパティ]** ウィンドウに表示されます。

 詳細については、「[ドメイン固有言語を定義する方法](../modeling/how-to-define-a-domain-specific-language.md)」を参照してください。 これらのプロパティの使用方法の詳細については、「[ドメイン固有言語のカスタマイズと拡張](../modeling/customizing-and-extending-a-domain-specific-language.md)」を参照してください。

 DslDefinition には、次の表に示すプロパティがあります。

|property|説明|既定|
|-|-|-|
|アクセス修飾子|ドメインクラスのアクセス修飾子が public か internal かを決定します。|public|
|カスタム属性|ドメインクラスのカスタム定義属性。<br /><br /> **メモ**属性を追加するには、[参照] ボタンを使用します。|\<none>|
|会社名|システムレジストリ内の現在の会社名の名前。|現在の会社名|
|名|このドメインクラスの名前。|現在の名前|
|Namespace|このドメインクラスに関連付けられている名前空間。|現在の名前空間|
|パッケージ Guid|この DSL 用に生成された Visual Studio パッケージの guid。|\<none>|
|パッケージ名前空間|この DSL 用に生成された Visual Studio パッケージの名前空間。|\<none>|
|製品名|この DSL 用に生成された Visual Studio パッケージに登録される製品の名前。|\<none>|
|ノート|このドメインクラスに関連付けられているメモ。|\<none>|
|説明|このドメインクラスの説明です。|\<none>|
|[表示名]|このドメインクラスの生成されたデザイナーに表示される名前。|\<none>|
|ヘルプ キーワード|このドメインクラスに関連付けられているヘルプキーワード。|\<none>|
|Build|このドメイン固有言語定義のインクリメンタルビルド番号。|0|
|メジャーバージョン|このドメイン固有言語定義の増分メジャービルド番号。|1|
|マイナーバージョン|このドメイン固有言語定義の増分マイナービルド番号。|0|
|Revision|このドメイン固有言語定義の増分リビジョンビルド番号。|0|

## <a name="see-also"></a>関連項目

- [ドメイン固有言語ツールの用語集](https://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)