---
title: 従来の言語サービスでのアウトラインと隠し文字 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- outlining, supporting in native code
ms.assetid: 252c5221-2e64-461c-8dcf-b622e400e0be
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: abe608036e8531415aab11300eb9583ffaca9021
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66314865"
---
# <a name="outlining-and-hidden-text-in-a-legacy-language-service"></a>従来の言語サービスでのアウトラインと隠し文字
アウトライン表示できるようになりますテキスト行のシーケンスを 1 行に折りたたみます。 たとえば、C++ では、すべてのメソッドをメソッドのシグネチャのみを示す、1 行に折りたたむできます。 非表示のテキストは、表示または非表示にできるテキスト行のシーケンスです。

## <a name="in-this-section"></a>このセクションの内容
- [方法: 従来の言語サービスでのアウトラインのサポート](../../extensibility/internals/how-to-support-outlining-in-a-legacy-language-service.md)

 実装する方法について説明します

- [方法: 従来の言語サービスでの隠し文字サポートの提供](../../extensibility/internals/how-to-provide-hidden-text-support-in-a-legacy-language-service.md)

 非表示のテキスト領域の目的について説明し、非表示のテキスト領域を実装する方法について説明します。

- [方法: 従来の言語サービスでのアウトラインの拡張サポートの提供](../../extensibility/internals/how-to-provide-expanded-outlining-support-in-a-legacy-language-service.md)

 お使いの言語をサポートしている以外のアウトラインのサポートを拡張する 2 つのオプションについて説明します、*定義に折りたたむ*コマンド。