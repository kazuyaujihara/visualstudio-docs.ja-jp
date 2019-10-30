---
title: SccOpenProject 関数 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SccOpenProject
helpviewer_keywords:
- SccOpenProject function
ms.assetid: d609510b-660a-46d7-b93d-2406df20434d
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a6aa4a715f8d1b87aa831f6a315f07a19e5d4f46
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72721056"
---
# <a name="sccopenproject-function"></a>SccOpenProject 関数
この関数は、既存のソース管理プロジェクトを開くか、新しいプロジェクトを作成します。

## <a name="syntax"></a>構文

```cpp
SCCRTN SccOpenProject (
   LPVOID        pvContext,
   HWND          hWnd,
   LPSTR         lpUser,
   LPCSTR        lpProjName,
   LPCSTR        lpLocalProjPath,
   LPSTR         lpAuxProjPath,
   LPCSTR        lpComment,
   LPTEXTOUTPROC lpTextOutProc,
   LONG          dwFlags
);
```

#### <a name="parameters"></a>パラメーター
 pvContext

からソース管理プラグインのコンテキスト構造。

 hWnd

からソース管理プラグインが提供するすべてのダイアログボックスの親として使用できる IDE ウィンドウへのハンドル。

 lpUser

[入力、出力]ユーザーの名前 (NULL 終端文字を含む、SCC_USER_SIZE を超えることはできません)。

 lpProjName

からプロジェクトの名前を識別する文字列。

 lpLocalProjPath

からプロジェクトの作業フォルダーへのパス。

 lpAuxProjPath

[入力、出力]\(NULL 終端文字を含む) プロジェクトを識別する補助文字列 (SCC_AUXPATH_SIZE を超えることはできません)。

 lpComment

から作成する新しいプロジェクトにコメントを追加します。

 lpTextOutProc

からソース管理プラグインからのテキスト出力を表示するオプションのコールバック関数。

 dwFlags

からプロジェクトがソース管理プラグインに対して不明な場合に、新しいプロジェクトを作成する必要があるかどうかを通知します。 値は `SCC_OP_CREATEIFNEW` との組み合わせにすることができ `SCC_OP_SILENTOPEN.`

## <a name="return-value"></a>戻り値
 この関数のソース管理プラグインの実装では、次の値のいずれかが返されることが想定されています。

|[値]|説明|
|-----------|-----------------|
|SCC_OK|プロジェクトを開く操作に成功します。|
|SCC_E_INITIALIZEFAILED|プロジェクトを初期化できませんでした。|
|SCC_E_INVALIDUSER|ユーザーは、ソース管理システムにログインできませんでした。|
|SCC_E_COULDNOTCREATEPROJECT|呼び出しの前にプロジェクトが存在しませんでした。 `SCC_OPT_CREATEIFNEW` フラグが設定されましたが、プロジェクトを作成できませんでした。|
|SCC_E_PROJSYNTAXERR|プロジェクトの構文が無効です。|
|SCC_E_UNKNOWNPROJECT|プロジェクトがソース管理プラグインに対して不明であり、`SCC_OPT_CREATEIFNEW` フラグが設定されていません。|
|SCC_E_INVALIDFILEPATH|ファイルパスが無効であるか、使用できません。|
|SCC_E_NOTAUTHORIZED|ユーザーはこの操作を実行できません。|
|SCC_E_ACCESSFAILURE|ネットワークまたは競合の問題が原因で、ソース管理システムへのアクセスで問題が発生しました。 再試行することをお勧めします。|
|SCC_E_NONSPECFICERROR|不特定のエラーです。ソース管理システムが初期化されませんでした。|

## <a name="remarks"></a>コメント
 IDE はユーザー名 (`lpUser`) を渡すことができます。または、単に空の文字列へのポインターを渡すこともできます。 ユーザー名がある場合は、ソース管理プラグインで既定値として使用する必要があります。 ただし、名前が渡されなかった場合、またはログインが指定された名前で失敗した場合は、プラグインによってユーザーにログインを求めるメッセージが表示され、有効なログイン`.` を受信したときに `lpUser` に有効な名前が返されます。これは、プラグインによってユーザー名の文字列が変更されるためです。IDE は常にサイズのバッファー (`SCC_USER_LEN`+ 1 または SCC_USER_SIZE のバッファーを割り当てます。これには null 終端文字のスペースが含まれます)。

> [!NOTE]
> IDE が実行する必要のある最初のアクションは、`SccOpenProject` 関数または[Sccgetprojpath](../extensibility/sccgetprojpath-function.md)を呼び出すことができます。 このため、両方に同じ `lpUser` パラメーターがあります。

 `lpAuxProjPath` と`lpProjName` は、ソリューションファイルから読み取られるか、または `SccGetProjPath` 関数の呼び出しから返されます。 これらのパラメーターには、ソース管理プラグインによってプロジェクトに関連付けられ、プラグインにのみ意味がある文字列が含まれています。 このような文字列がソリューションファイルに含まれておらず、ユーザーが参照するように求められていない場合 (`SccGetProjPath` 関数を通じて文字列が返される場合)、IDE は `lpAuxProjPath` と `lpProjName`の両方に空の文字列を渡します。また、次の場合は、これらの値がプラグインによって更新されることを想定します。この関数はを返します。

 `lpTextOutProc` は、コマンドの結果の出力を表示するために IDE によってソース管理プラグインに提供されるコールバック関数へのポインターです。 このコールバック関数の詳細については、「 [Lptextoutproc](../extensibility/lptextoutproc.md)」を参照してください。

> [!NOTE]
> ソース管理プラグインがこの機能を利用することを意図している場合は、 [Sccinitialize](../extensibility/sccinitialize-function.md)で `SCC_CAP_TEXTOUT` フラグを設定する必要があります。 このフラグが設定されていない場合、または IDE がこの機能をサポートしていない場合は、`lpTextOutProc` が `NULL`されます。

 `dwFlags` パラメーターは、開いているプロジェクトが現在存在していないイベントの結果を制御します。 2つの bitflags、`SCC_OP_CREATEIFNEW` と `SCC_OP_SILENTOPEN`で構成されます。 開いているプロジェクトが既に存在する場合、この関数は単にプロジェクトを開き、`SCC_OK`を返します。 プロジェクトが存在せず、`SCC_OP_CREATEIFNEW` フラグがオンの場合、ソース管理プラグインは、ソース管理システムでプロジェクトを作成して開き、`SCC_OK`を返すことができます。 プロジェクトが存在しない場合、`SCC_OP_CREATEIFNEW` フラグがオフの場合、プラグインは `SCC_OP_SILENTOPEN` フラグを確認する必要があります。 このフラグがオンになっていない場合は、プラグインによってユーザーにプロジェクト名の入力が求められることがあります。 このフラグがオンの場合、プラグインは単に `SCC_E_UNKNOWNPROJECT`を返す必要があります。

## <a name="calling-order"></a>呼び出し順序
 通常のイベントでは、最初に[Sccinitialize](../extensibility/sccinitialize-function.md)を呼び出してソース管理セッションを開きます。 セッションは、`SccOpenProject`の呼び出しの後に、その他のソース管理プラグイン API 関数の呼び出しで構成され、 [Scccloseproject](../extensibility/scccloseproject-function.md)の呼び出しで終了します。 このようなセッションは、 [Sccuninitialize](../extensibility/sccuninitialize-function.md)解除が呼び出される前に何度も繰り返される場合があります。

 ソース管理プラグインが `SccInitialize`で `SCC_CAP_REENTRANT` ビットを設定した場合、上記のセッションシーケンスは並列で何度も繰り返される可能性があります。 さまざまな `pvContext` 構造は、一度に1つの開いているプロジェクトに各 `pvContext` が関連付けられている、さまざまなセッションを追跡します。 `pvContext` パラメーターに基づいて、プラグインは特定の呼び出しで参照されているプロジェクトを特定できます。 機能ビット `SCC_CAP_REENTRANT` が設定されていない場合、非再入可能なソース管理プラグインは、複数のプロジェクトで作業できるように制限されます。

> [!NOTE]
> `SCC_CAP_REENTRANT` ビットは、ソース管理プラグイン API のバージョン1.1 で導入されました。 バージョン1.0 では設定されていないか、または無視され、すべてのバージョン1.0 ソース管理プラグインは再入可能でないと見なされます。

## <a name="see-also"></a>関連項目
- [ソース管理プラグインの API 関数](../extensibility/source-control-plug-in-api-functions.md)
- [SccCloseProject](../extensibility/scccloseproject-function.md)
- [SccGetProjPath](../extensibility/sccgetprojpath-function.md)
- [SccInitialize](../extensibility/sccinitialize-function.md)
- [SccUninitialize](../extensibility/sccuninitialize-function.md)
- [文字列長の制限](../extensibility/restrictions-on-string-lengths.md)
- [LPTEXTOUTPROC](../extensibility/lptextoutproc.md)