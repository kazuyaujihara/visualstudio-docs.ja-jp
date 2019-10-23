---
title: SccQueryInfo 関数 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SccQueryInfo
helpviewer_keywords:
- SccQueryInfo function
ms.assetid: 3973d336-a9b7-41a2-a4e6-bb8184a96aaf
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 5807eb6b695e140350696436a8bba351687f4a24
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72720832"
---
# <a name="sccqueryinfo-function"></a>SccQueryInfo 関数
この関数は、ソース管理下で選択された一連のファイルのステータス情報を取得します。

## <a name="syntax"></a>構文

```cpp
SCCRTN SccQueryInfo(
   LPVOID  pvContext,
   LONG    nFiles,
   LPCSTR* lpFileNames,
   LPLONG  lpStatus
);
```

#### <a name="parameters"></a>パラメーター
 pvContext

からソース管理プラグインのコンテキスト構造。

 nFiles

から@No__t_0 配列に指定されたファイルの数と `lpStatus` 配列の長さ。

 lpFileNames 名

からクエリ対象のファイルの名前の配列。

 lpStatus

[入力、出力]ソース管理プラグインが各ファイルの状態フラグを返す配列。 詳細については、「[ファイルのステータスコード](../extensibility/file-status-code-enumerator.md)」を参照してください。

## <a name="return-value"></a>戻り値
 この関数のソース管理プラグインの実装では、次の値のいずれかが返されることが想定されています。

|[値]|説明|
|-----------|-----------------|
|SCC_OK|クエリが成功しました。|
|SCC_E_ACCESSFAILURE|ネットワークまたは競合の問題が原因で、ソース管理システムへのアクセスに問題が発生しました。 再試行することをお勧めします。|
|SCC_E_PROJNOTOPEN|プロジェクトがソース管理下で開かれていません。|
|SCC_E_NONSPECIFICERROR|不特定のエラーです。|

## <a name="remarks"></a>Remarks
 @No__t_0 が空の文字列の場合、現在更新するステータス情報はありません。 それ以外の場合は、ステータス情報が変更された可能性があるファイルの完全なパス名です。

 戻り値の配列には、`SCC_STATUS_xxxx` ビットのビットマスクを指定できます。 詳細については、「[ファイルのステータスコード](../extensibility/file-status-code-enumerator.md)」を参照してください。 ソース管理システムは、すべてのビット型をサポートしていない場合があります。 たとえば、`SCC_STATUS_OUTOFDATE` が提供されていない場合、ビットは設定されません。

 この関数を使用してファイルをチェックアウトする場合は、次の `MSSCCI` 状態の要件に注意してください。

- `SCC_STATUS_OUTBYUSER` は、現在のユーザーがファイルをチェックアウトしたときに設定されます。

- `SCC_STATUS_OUTBYUSER` が設定されていない限り、`SCC_STATUS_CHECKEDOUT` を設定することはできません。

- `SCC_STATUS_CHECKEDOUT` は、指定した作業ディレクトリにファイルがチェックアウトされている場合にのみ設定されます。

- ファイルが現在のユーザーによって作業ディレクトリ以外のディレクトリにチェックアウトされている場合、`SCC_STATUS_OUTBYUSER` が設定されますが、`SCC_STATUS_CHECKEDOUT` は設定されません。

## <a name="see-also"></a>関連項目
- [ソース管理プラグインの API 関数](../extensibility/source-control-plug-in-api-functions.md)
- [ファイルの状態コード](../extensibility/file-status-code-enumerator.md)