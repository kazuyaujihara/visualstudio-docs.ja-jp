---
title: CV_CFL_LANG |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CV_CFL_LANG enumeration
ms.assetid: 4e8e0613-ad02-4de9-9f46-e4753c5b0251
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1f02545f1c19b57e46af302fbc0b2abaa7445612
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56646344"
---
# <a name="cvcfllang"></a>CV_CFL_LANG
アプリケーションまたはリンクされているモジュールのソース コードの言語を指定します。

## <a name="syntax"></a>構文

```C++
typedef enum CV_CFL_LANG {
    CV_CFL_C       = 0x00,
    CV_CFL_CXX     = 0x01,
    CV_CFL_FORTRAN = 0x02,
    CV_CFL_MASM    = 0x03,
    CV_CFL_PASCAL  = 0x04,
    CV_CFL_BASIC   = 0x05,
    CV_CFL_COBOL   = 0x06,
    CV_CFL_LINK    = 0x07,
    CV_CFL_CVTRES  = 0x08,
    CV_CFL_CVTPGD  = 0x09,
    CV_CFL_CSHARP  = 0x0A,
    CV_CFL_VB      = 0x0B,
    CV_CFL_ILASM   = 0x0C,
    CV_CFL_JAVA    = 0x0D,
    CV_CFL_JSCRIPT = 0x0E,
    CV_CFL_MSIL    = 0x0F,
    CV_CFL_HLSL    = 0x10
} CV_CFL_LANG;
```

## <a name="elements"></a>Elements
CV_CFL_C アプリケーションの言語は C です。

CV_CFL_CXX アプリケーションの言語は C++ です。

CV_CFL_FORTRAN アプリケーション言語では、FORTRAN です。

CV_CFL_MASM アプリケーション言語では、Microsoft Macro Assembler です。

CV_CFL_PASCAL アプリケーション言語では、pascal 形式です。

CV_CFL_BASIC アプリケーションの言語には BASIC です。

CV_CFL_COBOL アプリケーション言語では、COBOL です。

CV_CFL_LINK アプリケーションは、リンカーによって生成されたモジュールです。

CV_CFL_CVTRES アプリケーションとは、変換 CVTRES ツールを使用して、リソース モジュールです。

CV_CFL_CVTPGD アプリケーションは、CVTPGD ツールで生成された最適化 POGO モジュールです。

CV_CFL_CSHARP アプリケーション言語はC#します。

CV_CFL_VB アプリケーション言語とは、Visual Basic です。

CV_CFL_ILASM アプリケーションの言語は、中間言語アセンブリ (つまり、共通言語ランタイム (CLR) アセンブリ) です。

Java は CV_CFL_JAVA アプリケーションの言語です。

CV_CFL_JSCRIPT アプリケーション言語では、Jscript です。

CV_CFL_MSIL アプリケーションの言語は、不明な Microsoft 中間言語 (MSIL)、結果を使用する可能性があります、 [/LTCG (リンク時コード生成)](/cpp/build/reference/ltcg-link-time-code-generation)スイッチします。

CV_CFL_HLSL アプリケーション言語では、High Level Shader Language が。

## <a name="remarks"></a>解説
この列挙体の値が呼び出しによって返される、 [idiasymbol::get_language](../../debugger/debug-interface-access/idiasymbol-get-language.md)メソッド。

## <a name="requirements"></a>要件
ヘッダー: cvconst.h

## <a name="see-also"></a>関連項目
- [列挙型と構造体](../../debugger/debug-interface-access/enumerations-and-structures.md)
- [IDiaSymbol::get_language](../../debugger/debug-interface-access/idiasymbol-get-language.md)
