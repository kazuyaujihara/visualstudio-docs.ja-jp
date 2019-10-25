---
title: SccRunScc 関数 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SccRunScc
helpviewer_keywords:
- SccRunScc function
ms.assetid: bbe7c931-b17a-4779-9cf6-59e5f9f0c172
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e577af3ce70280b81681cb72295c3511dd3ab4a4
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72720547"
---
# <a name="sccrunscc-function"></a>SccRunScc 関数
この関数は、ソース管理の管理ツールを呼び出します。

## <a name="syntax"></a>構文

```cpp
SCCRTN SccRunScc(
   LPVOID  pvContext,
   HWND    hWnd,
   LONG    nFiles,
   LPCSTR* lpFileNames
);
```

#### <a name="parameters"></a>パラメーター
 pvContext

からソース管理プラグインのコンテキスト構造。

 hWnd

からソース管理プラグインが提供するすべてのダイアログボックスの親として使用できる IDE ウィンドウへのハンドル。

 nFiles

から@No__t_0 配列に指定されたファイルの数。

 lpFileNames 名

から選択されたファイル名の配列。

## <a name="return-value"></a>戻り値
 この関数のソース管理プラグインの実装では、次の値のいずれかが返されることが想定されています。

|[値]|説明|
|-----------|-----------------|
|SCC_OK|ソース管理の管理ツールが正常に呼び出されました。|
|SCC_I_OPERATIONCANCELED|操作が取り消されました。|
|SCC_E_INITIALIZEFAILED|ソース管理システムを初期化できませんでした。|
|SCC_E_ACCESSFAILURE|ネットワークまたは競合の問題が原因で、ソース管理システムへのアクセスで問題が発生しました。|
|SCC_E_CONNECTIONFAILURE|ソース管理システムに接続できませんでした。|
|SCC_E_FILENOTCONTROLLED|選択されたファイルはソース管理下にありません。|
|SCC_E_NONSPECIFICERROR|不特定のエラーです。|

## <a name="remarks"></a>Remarks
 この関数を使用すると、呼び出し元は、外部管理ツールを使用して、ソース管理システムのすべての機能にアクセスできます。 ソース管理システムにユーザーインターフェイスがない場合、ソース管理プラグインは、必要な管理機能を実行するためのインターフェイスを実装できます。

 この関数は、現在選択されているファイルのカウントとファイル名の配列を使用して呼び出されます。 管理ツールでサポートされている場合は、ファイルの一覧を使用して、管理インターフェイスでファイルを事前に指定できます。それ以外の場合、リストは無視してかまいません。

 通常、この関数は、ユーザーが **ファイル** -> **ソース管理** メニューから **起動 \<Source コントロールサーバー >** を選択したときに呼び出されます。 この**起動**メニューオプションは、レジストリエントリを設定することによって、常に無効にしたり、非表示にしたりすることができます。 詳細については[、「方法: ソース管理プラグインをインストール](../extensibility/internals/how-to-install-a-source-control-plug-in.md)する」を参照してください。 この関数は、 [Sccinitialize](../extensibility/sccinitialize-function.md)が `SCC_CAP_RUNSCC` 機能ビットを返す場合にのみ呼び出されます (この機能の詳細については、「[機能フラグ](../extensibility/capability-flags.md)」を参照してください)。

## <a name="see-also"></a>関連項目
- [ソース管理プラグインの API 関数](../extensibility/source-control-plug-in-api-functions.md)
- [方法: ソース管理プラグインのインストール](../extensibility/internals/how-to-install-a-source-control-plug-in.md)
- [機能フラグ](../extensibility/capability-flags.md)
- [SccInitialize](../extensibility/sccinitialize-function.md)