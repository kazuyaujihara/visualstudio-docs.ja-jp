---
title: テキスト テンプレートでのエスケープ シーケンスの使用
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- text templates, escape sequences
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4e03f5eafc00b8431725ed06da10371a93692fb5
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72662919"
---
# <a name="use-escape-sequences-in-text-templates"></a>テキストテンプレートでのエスケープシーケンスの使用

テキストテンプレートでエスケープシーケンスを使用して、テキストテンプレートタグを生成しC#たり (コードのみ)、制御文字と引用符をエスケープしたりすることができます。

標準コードブロックの開いたり閉じたりするタグを出力ファイルに出力するには、次のようにタグをエスケープします。

```
\<# ... \#>
```

他のテキストテンプレートディレクティブとコードブロックタグでも同じことができます。

テキストテンプレートタグをエスケープするために使用する文字列がテキストブロックに含まれている場合は、次のエスケープシーケンスを使用できます。

- テキストテンプレートタグの前に偶数のエスケープ (\\) 文字が付いている場合、テンプレートパーサーはエスケープ文字の半分を含み、シーケンスをテキストテンプレートタグとして含みます。 たとえば、テキストテンプレートに4つのエスケープ文字がある場合、生成されたファイルには2つの "\\" 文字があります。

- テキストテンプレートタグの前にエスケープ文字 (\\) が奇数個ある場合、テンプレートパーサーには、"\\" 文字の半分とタグ自体 (\< # または # >) が含まれます。 タグは、テキストテンプレートタグとは見なされません。

- エスケープ (\\) 文字が、制御文字または引用符をエスケープした場所以外の任意のシーケンス内に出現するC#場合 (のみ)、文字が直接出力されます。

## <a name="see-also"></a>関連項目

- [方法: エスケープ シーケンスを使用してテンプレートからテンプレートを生成する](../modeling/how-to-generate-templates-from-templates-by-using-escape-sequences.md)