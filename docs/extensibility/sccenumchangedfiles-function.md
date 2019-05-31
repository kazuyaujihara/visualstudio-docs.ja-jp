---
title: SccEnumChangedFiles 関数 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SccEnumChangedFiles
helpviewer_keywords:
- SccEnumChangedFiles function
ms.assetid: 76cac510-107b-4c1a-ba60-9c39b6db2e71
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 18eab5e5785ea003976c7e291028d5ff964177d8
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66351869"
---
# <a name="sccenumchangedfiles-function"></a>SccEnumChangedFiles 関数
ローカル ファイルの一覧を指定するには、この関数は、どのファイルとは異なるソース コードの管理データベースに対応するバージョンを決定します。

## <a name="syntax"></a>構文

```cpp
SCCRTN SccEnumChangedFiles(
   LPVOID  pContext,
   HWND    hWnd,
   LONG    cFiles,
   LPCSTR* lpFileNames,
   LONG*   plIsFileDifferent
);
```

### <a name="parameters"></a>パラメーター
 pContext

[in]ソース管理プラグインのコンテキストのポインター。

 hWnd

[in]ソース管理プラグインが提供される任意のダイアログ ボックスの親として使用できる IDE ウィンドウへのハンドル。

 cFiles

[in]指定されたファイル名の数、`lpFileNames`配列。 サイズを指定も`plIsFileDifferent`配列。

 lpFileNames

[in]チェックするローカル ファイル名の配列。

 plIsFileDifferent

[入力、出力]各ファイルの違いの状態を示す値の配列 (配列が少なくとも必要`cFiles`エントリ)。 0 以外では、ファイルが異なることを意味します。

## <a name="return-value"></a>戻り値
 この関数のソース管理プラグイン実装は、次の値のいずれかを返すが必要です。

|[値]|説明|
|-----------|-----------------|
|SCC_OK|操作が正常に完了しました。|
|SCC_UNSPECIFIEDERROR|一般エラーです。|

## <a name="see-also"></a>関連項目
- [ソース管理プラグイン API 関数](../extensibility/source-control-plug-in-api-functions.md)