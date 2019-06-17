---
title: SccBackgroundGet 関数 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SccBackgroundGet
helpviewer_keywords:
- SccBackgroundGet function
ms.assetid: 69817e52-b9ac-4f4d-820b-2cc9c384f0dc
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d0805e91f5386f101917ee988e9e0d23d066f48d
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66334024"
---
# <a name="sccbackgroundget-function"></a>SccBackgroundGet 関数
この関数は、ソース管理から各指定されたファイルのユーザーの操作なしで取得します。

## <a name="syntax"></a>構文

```cpp
SCCRTN SccBackgroundGet(
   LPVOID  pContext,
   LONG    nFiles,
   LPCSTR* lpFileNames,
   LONG    dwFlags,
   LONG    dwBackgroundOperationID
);
```

### <a name="parameters"></a>パラメーター
 pContext

[in]ソース管理プラグインのコンテキストのポインター。

 nFiles

[in]指定されたファイルの数、`lpFileNames`配列。

 lpFileNames

[入力、出力]取得するファイルの名前の配列。

> [!NOTE]
> 名前は、完全修飾のローカル ファイル名である必要があります。

 dwFlags

[in]コマンドのフラグ (`SCC_GET_ALL`、 `SCC_GET_RECURSIVE`)。

 dwBackgroundOperationID

[in]この操作に関連付けられた一意の値。

## <a name="return-value"></a>戻り値
 この関数のソース管理プラグイン実装は、次の値のいずれかを返すが必要です。

|[値]|説明|
|-----------|-----------------|
|SCC_OK|操作が正常に完了しました。|
|SCC_E_BACKGROUNDGETINPROGRESS|バック グラウンド取得が既に進行中 (ソース管理プラグインを返すこの同時バッチ操作がサポートしない場合にのみ)。|
|SCC_I_OPERATIONCANCELED|操作が完了する前に取り消されました。|

## <a name="remarks"></a>Remarks
 この関数は常にソース管理プラグインが読み込まれているものと異なるスレッドで呼び出されます。 この関数は戻りますが完了するまでは必要ありません。ただし、その複数回と共に呼び出せる複数同時にすべてのファイルのリスト。

 使用、`dwFlags`引数が同じ、 [SccGet](../extensibility/sccget-function.md)します。

## <a name="see-also"></a>関連項目
- [ソース管理プラグイン API 関数](../extensibility/source-control-plug-in-api-functions.md)
- [SccGet](../extensibility/sccget-function.md)