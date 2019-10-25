---
title: ドキュメントの警告
ms.date: 09/16/2019
ms.topic: reference
f1_keywords:
- vs.codeanalysis.documentationrules
helpviewer_keywords:
- documentation warnings
- managed code analysis warnings, documentation warnings
- warnings, documentation
author: mavasani
ms.author: mavasani
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4946c69bbbe4bf1c240967ebd93ef58cfa79e333
ms.sourcegitcommit: 8589d85cc10710ef87e6363a2effa5ee5610d46a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2019
ms.locfileid: "72807097"
---
# <a name="documentation-warnings"></a>ドキュメントの警告

ドキュメント警告は、外部から参照可能な Api に[XML ドキュメントコメント](/dotnet/csharp/codedoc)を適切に使用して、適切にドキュメント化されたライブラリを作成することをサポートしています。

## <a name="in-this-section"></a>このセクションの内容

| 規則 | 説明 |
| - | - |
| [CA1200: プレフィックスで cref タグを使用しないようにします](../code-quality/ca1200.md) | XML ドキュメントタグの[cref](/dotnet/csharp/programming-guide/xmldoc/cref-attribute)属性は、"コード参照" を意味します。 タグの内部テキストが、型、メソッド、プロパティなど、コード要素であることを指定します。 コンパイラで参照が検証されないようにするため、プレフィックス付きの `cref` タグは使用しないでください。 また、Visual Studio 統合開発環境 (IDE: integrated development environment) が、リファクタリング中にこれらのシンボル参照を検索および更新できないようにします。 |

## <a name="see-also"></a>関連項目

- [コード分析の警告](../code-quality/code-analysis-for-managed-code-warnings.md)
