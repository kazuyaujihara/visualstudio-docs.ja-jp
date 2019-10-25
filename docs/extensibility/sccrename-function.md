---
title: SccRename 関数 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SccRename
helpviewer_keywords:
- SccRename function
ms.assetid: b467ade6-a1db-4c0b-b60f-7850ec4f79eb
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 30b2928653507b670160c72ca3ce09a0227a4170
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72720768"
---
# <a name="sccrename-function"></a>SccRename 関数
この関数は、ソース管理システム内のファイルの名前を変更します。

## <a name="syntax"></a>構文

```cpp
SCCRTN SccRename(
   LPVOID pvContext,
   HWND   hWnd,
   LPCSTR lpFileName,
   LPCSTR lpNewName
);
```

#### <a name="parameters"></a>パラメーター
 pvContext

からソース管理プラグインのコンテキスト構造。

 hWnd

からソース管理プラグインが提供するすべてのダイアログボックスの親として使用できる IDE ウィンドウへのハンドル。

 lpFileName

から名前が変更されたファイルの完全修飾ファイル名。

 lpNewName

から完全修飾された新しい名前。 ディレクトリパスが異なる場合、ファイルはあるサブディレクトリから別のサブディレクトリに移動されています。

## <a name="return-value"></a>戻り値
 この関数のソース管理プラグインの実装では、次の値のいずれかが返されることが想定されています。

|[値]|説明|
|-----------|-----------------|
|SCC_OK|名前の変更操作が正常に完了しました。|
|SCC_E_PROJNOTOPEN|プロジェクトがソース管理下で開かれていません。|
|SCC_E_FILENOTCONTROLLED|ファイルがソース管理下にありません。|
|SCC_E_ACCESSFAILURE|ネットワークまたは競合の問題が原因で、ソース管理システムへのアクセスで問題が発生しました。|
|SCC_E_NOTAUTHORIZED|この操作を完了する権限がユーザーにありません。|
|SCC_E_COULDNOTCREATEPROJECT|名前変更プロセスの一部としてプロジェクトを作成できませんでした。|
|SCC_E_OPNOTPERFORMED|操作は実行されませんでした。|
|SCC_E_NONSPECIFICERROR|指定されていないか、一般的なエラーが発生しました。|

## <a name="remarks"></a>Remarks
 この関数を使用すると、ファイルの名前を変更したり、ソース管理システム内のある場所から別の場所にファイルを移動したりすることができます。 ソース管理プラグインがディスク上のファイルにアクセスしようとすることはできません。 ローカルファイルの名前を変更するのは IDE の役割です。

## <a name="see-also"></a>関連項目
- [ソース管理プラグインの API 関数](../extensibility/source-control-plug-in-api-functions.md)