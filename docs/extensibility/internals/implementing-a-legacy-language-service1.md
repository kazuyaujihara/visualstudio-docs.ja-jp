---
title: レガシ言語の Service1 を実装する |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- language services, managed
ms.assetid: df638f24-166d-4b80-be82-c9c39ca7a556
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 626838b0e82846f66b817465fca2df353af42dd5
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66315645"
---
# <a name="implementing-a-legacy-language-service"></a>従来の言語サービスを実装します。
構文の強調表示、かっこの一致、および IntelliSense の入力候補など、さまざまな機能をサポートする従来の言語サービスを実装するために、マネージ パッケージ フレームワーク (MPF) クラスを使用できます。

 従来の言語サービスは、VSPackage の一部として実装されますが、言語サービスの機能を実装する新しい方法は MEF 拡張機能を使用します。 言語サービスを実装する新しい方法の詳細についてを参照してください。[エディターと言語サービス拡張](../../extensibility/editor-and-language-service-extensions.md)します。

> [!NOTE]
> 新しいエディターの API をできるだけ早く使用を開始することをお勧めします。 言語サービスのパフォーマンスを向上させる、エディターの新機能を活用することができます。

## <a name="in-this-section"></a>このセクションの内容
- [従来の言語サービスの概要](../../extensibility/internals/legacy-language-service-overview.md)

 MPF でサポートされている言語サービスの機能の概要。

- [従来の言語サービスの実装](../../extensibility/internals/implementing-a-legacy-language-service2.md)

 MPF を使用して、言語サービスを実装するために必要なものについて説明します。

- [従来の言語サービスの登録](../../extensibility/internals/registering-a-legacy-language-service1.md)

 MPF ベースの言語サービスを登録するために必要な手順について説明します[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]します。

- [従来の言語サービスのパーサーとスキャナー](../../extensibility/internals/legacy-language-service-parser-and-scanner.md)

 MPF を使用して、言語サービスのすべての機能を実装するために必要な 2 つのパーサーをについて説明します。

- [チュートリアル: 従来の言語サービスの作成](../../extensibility/internals/walkthrough-creating-a-legacy-language-service.md)

 VSPackage で、MPF 言語サービスを実装するために必要な基本的な手順を示します。

- [チュートリアル: インストールされているコード スニペットの一覧の取得 (従来の実装)](../../extensibility/internals/walkthrough-getting-a-list-of-installed-code-snippets-legacy-implementation.md)

 インストールされているコード スニペットの一覧を取得する方法を示します。

- [従来の言語サービスの特徴](../../extensibility/internals/legacy-language-service-features1.md)

 MPF を使用して、言語サービスのすべての機能を実装するために行う必要がある内容が詳しくトピックへのリンクを提供します。