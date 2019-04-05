---
title: DSL 定義のプロパティ
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- Domain-Specific Language, definition file
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e63a5ab794261a395fb091016f177ffca9d35692
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2019
ms.locfileid: "55911586"
---
# <a name="properties-of-a-dsl-definition"></a>DSL 定義のプロパティ
DslDefinition プロパティ定義*ドメイン固有言語*バージョン番号などのプロパティを定義します。 DslDefinition プロパティに表示されます、**プロパティ**ウィンドウでは、図の空いている領域をクリックすると、*ドメイン固有言語デザイナー*します。

 詳細については、[ドメイン固有言語を定義する方法](../modeling/how-to-define-a-domain-specific-language.md)を参照してください。 これらのプロパティを使用する方法の詳細については、[をカスタマイズすると、ドメイン固有言語を拡張する](../modeling/customizing-and-extending-a-domain-specific-language.md)を参照してください。

 DslDefinition は次の表にプロパティを持ちます。

|プロパティ|説明|既定値|
|-|-|-|
|アクセス修飾子|ドメイン クラスのアクセス修飾子が public か internal かを判断します。|public|
|カスタム属性|カスタムでは、ドメイン クラスに属性を定義します。<br /><br /> **注**属性を追加する参照ボタンを使用します。|\<none>|
|会社名|現在の会社名、システム レジストリの名前。|現在の会社名|
|名前|このドメイン クラスの名前。|現在の名前|
|名前空間|このドメイン クラスに関係する、名前空間。|現在の名前空間|
|パッケージ Guid|この DSL 用に生成された Visual Studio パッケージの guid。|\<none>|
|パッケージの Namespace|この DSL 用に生成された Visual Studio パッケージの名前空間。|\<none>|
|製品名|この DSL 用に生成された Visual Studio パッケージを登録する製品の名前。|\<none>|
|メモ|このドメイン クラスに関連するメモします。|\<none>|
|説明|このドメイン クラスの説明です。|\<none>|
|表示名|このドメイン クラスの生成されたデザイナーに表示される名前です。|\<none>|
|ヘルプ キーワード|このドメイン クラスに関連付けられているヘルプ キーワード。|\<none>|
|ビルド|このドメイン固有言語定義のインクリメンタル ビルド番号。|0|
|メジャー バージョン|このドメイン固有言語定義の増分のメジャー ビルド番号。|1|
|マイナー バージョン|このドメイン固有言語定義の増分のマイナー ビルド番号。|0|
|Revision|増分のリビジョンは、このドメイン固有言語定義の番号をビルドします。|0|

## <a name="see-also"></a>関連項目

- [ドメイン固有言語ツールの用語集](https://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)