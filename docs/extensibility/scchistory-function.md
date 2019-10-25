---
title: SccHistory 関数 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SccHistory
helpviewer_keywords:
- SccHistory function
ms.assetid: a636d9d3-47c1-4b48-ac6b-bcfde19d6cf9
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 0ce0b38b8e602688875549edbac671e664809482
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72721252"
---
# <a name="scchistory-function"></a>SccHistory 関数
この関数は、指定されたファイルの履歴を表示します。

## <a name="syntax"></a>構文

```cpp
SCCRTN SccHistory(
   LPVOID    pvContext,
   HWND      hWnd,
   LONG      nFiles,
   LPCSTR*   lpFileNames,
   LONG      fOptions,
   LPCMDOPTS pvOptions
);
```

#### <a name="parameters"></a>パラメーター
 `pvContext`

からソース管理プラグインのコンテキスト構造。

 `hWnd`

からソース管理プラグインが提供するすべてのダイアログボックスの親として使用できる IDE ウィンドウへのハンドル。

 `nFiles`

から@No__t_0 配列に指定されたファイルの数。

 `lpFileName`

からファイルの完全修飾名の配列。

 `fOptions`

からコマンドフラグ (現在使用されていません)。

 `pvOptions`

からソース管理プラグイン固有のオプション。

## <a name="return-value"></a>戻り値
 この関数のソース管理プラグインの実装では、次の値のいずれかが返されることが想定されています。

|[値]|説明|
|-----------|-----------------|
|SCC_OK|バージョン履歴が正常に取得されました。|
|SCC_I_RELOADFILE|ソース管理システムは、履歴のフェッチ中に (たとえば、古いバージョンのバージョンを取得することによって) ディスク上のファイルを実際に変更したので、IDE がこのファイルを再読み込みする必要があります。|
|SCC_E_FILENOTCONTROLLED|ファイルがソース管理下にありません。|
|SCC_E_OPNOTSUPPORTED|ソース管理システムでは、この操作はサポートされていません。|
|SCC_E_NOTAUTHORIZED|ユーザーはこの操作を実行できません。|
|SCC_E_ACCESSFAILURE|ネットワークまたは競合の問題が原因で、ソース管理システムへのアクセスで問題が発生しました。 再試行することをお勧めします。|
|SCC_E_PROJNOTOPEN|プロジェクトが開かれていません。|
|SCC_E_NONSPECIFICERROR|不特定のエラーです。 ファイル履歴を取得できませんでした。|

## <a name="remarks"></a>Remarks
 ソース管理プラグインは、`hWnd` を親ウィンドウとして使用して、各ファイルの履歴を表示する独自のダイアログボックスを表示できます。 または、 [Sccopenproject](../extensibility/sccopenproject-function.md)に提供されている省略可能なテキスト出力コールバック関数を使用することもできます (サポートされている場合)。

 特定の状況では、この呼び出しの実行中に検査対象のファイルが変更される可能性があることに注意してください。 たとえば、[[!INCLUDE[vsvss](../extensibility/includes/vsvss_md.md)] 履歴] コマンドを使用すると、ユーザーは古いバージョンのファイルを取得できます。 このような場合、ソース管理プラグインは、ファイルを再読み込みする必要があることを IDE に警告するために `SCC_I_RELOAD` を返します。

> [!NOTE]
> ソース管理プラグインがファイルの配列に対してこの機能をサポートしていない場合は、最初のファイルのファイル履歴のみを表示できます。

## <a name="see-also"></a>関連項目
- [ソース管理プラグインの API 関数](../extensibility/source-control-plug-in-api-functions.md)
- [SccOpenProject](../extensibility/sccopenproject-function.md)