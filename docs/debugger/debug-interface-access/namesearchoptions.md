---
title: NameSearchOptions |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NameSearchOptions enumeration
ms.assetid: 67dfbede-2678-47df-b664-5c49841d0b9b
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f9c2b06e8d89405b38afe2b740ce860a78bc46cc
ms.sourcegitcommit: 044bb54cb4552c8f4651feb11d62e52726117e75
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "68661809"
---
# <a name="namesearchoptions"></a>NameSearchOptions
シンボルとファイル名の検索オプションを指定します。

## <a name="syntax"></a>構文

```C++
enum NameSearchOptions {
    nsNone,
    nsfCaseSensitive     = 0x1,
    nsfCaseInsensitive   = 0x2,
    nsfFNameExt          = 0x4,
    nsfRegularExpression = 0x8,
    nsfUndecoratedName   = 0x10,

// For backward compatibility:
    nsCaseSensitive           = nsfCaseSensitive,
    nsCaseInsensitive         = nsfCaseInsensitive,
    nsFNameExt                = nsfCaseInsensitive | nsfFNameExt,
    nsRegularExpression       = nsfRegularExpression | nsfCaseSensitive,
    nsCaseInRegularExpression = nsfRegularExpression | nsfCaseInsensitive
};
```

## <a name="elements"></a>Elements
`nsNone` オプションは指定されていません。

`nsfCaseSensitive`大文字と小文字が区別される名前の一致を適用します。

`nsfCaseInsensitive`大文字と小文字を区別しない名前の一致を適用します。

`nsfFNameExt`名前をパスとして扱い、ファイル名を適用します。 ext 名と一致します。

`nsfRegularExpression`アスタリスク (*) と疑問符 (?) をワイルドカードとして使用して、大文字と小文字を区別した名前の一致を適用します。 (その他の一般的な正規表現文字はサポートされていません)。

`nsfUndecoratedName`非装飾名と装飾名の両方を持つシンボルにのみ適用されます。

## <a name="remarks"></a>Remarks
この列挙の値は、次のメソッドに渡されます。

- [IDiaSession::findChildren](../../debugger/debug-interface-access/idiasession-findchildren.md)

- [IDiaSession::findFile](../../debugger/debug-interface-access/idiasession-findfile.md)

- [IDiaSymbol::findChildren](../../debugger/debug-interface-access/idiasymbol-findchildren.md)

## <a name="requirements"></a>必要条件
ヘッダー: dia2

## <a name="see-also"></a>関連項目
- [列挙型と構造体](../../debugger/debug-interface-access/enumerations-and-structures.md)
- [IDiaSession::findChildren](../../debugger/debug-interface-access/idiasession-findchildren.md)
- [IDiaSession::findFile](../../debugger/debug-interface-access/idiasession-findfile.md)
- [IDiaSymbol::findChildren](../../debugger/debug-interface-access/idiasymbol-findchildren.md)
