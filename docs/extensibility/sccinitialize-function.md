---
title: SccInitialize 関数 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SccInitialize
helpviewer_keywords:
- SccInitialize function
ms.assetid: 5bc0d28b-2c68-4d43-9e51-541506a8f76e
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 552ec06a4eabf55872358fc8e5d731e47c1eb6ca
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72721181"
---
# <a name="sccinitialize-function"></a>SccInitialize 関数
この関数は、ソース管理プラグインを初期化し、統合開発環境 (IDE: integrated development environment) に機能と制限を提供します。

## <a name="syntax"></a>構文

```cpp
SCCRTN SccInitialize (
   LPVOID* ppvContext,
   HWND    hWnd,
   LPCSTR  lpCallerName,
   LPSTR   lpSccName,
   LPLONG  lpSccCaps,
   LPSTR   lpAuxPathLabel,
   LPLONG  pnCheckoutCommentLen,
   LPLONG  pnCommentLen
);
```

#### <a name="parameters"></a>パラメーター
 `ppvContext`

からソース管理プラグインは、コンテキスト構造へのポインターをここに配置できます。

 `hWnd`

からソース管理プラグインが提供するすべてのダイアログボックスの親として使用できる IDE ウィンドウへのハンドル。

 `lpCallerName`

からソース管理プラグインを呼び出すプログラムの名前。

 `lpSccName`

[入力、出力]ソース管理プラグインが独自の名前を格納するバッファー (`SCC_NAME_LEN` を超えないようにする)。

 `lpSccCaps`

入出力ソース管理プラグインの機能フラグを返します。

 `lpAuxPathLabel`

[入力、出力][Sccopenproject](../extensibility/sccopenproject-function.md)によって返された `lpAuxProjPath` パラメーターを記述する文字列と[Sccgetprojpath](../extensibility/sccgetprojpath-function.md) (`SCC_AUXLABEL_LEN` を超えることはできません) をソース管理プラグインが配置するバッファー。

 `pnCheckoutCommentLen`

入出力チェックアウトコメントに許容される最大長を返します。

 `pnCommentLen`

入出力他のコメントに許容される最大長を返します。

## <a name="return-value"></a>戻り値
 この関数のソース管理プラグインの実装では、次の値のいずれかが返されることが想定されています。

|[値]|説明|
|-----------|-----------------|
|SCC_OK|ソース管理の初期化に成功しました。|
|SCC_E_INITIALIZEFAILED|システムを初期化できませんでした。|
|SCC_E_NOTAUTHORIZED|ユーザーは、指定された操作を実行できません。|
|SCC_E_NONSPECFICERROR|不特定のエラーです。ソース管理システムが初期化されませんでした。|

## <a name="remarks"></a>Remarks
 IDE は、ソース管理プラグインを最初に読み込むときに、この関数を呼び出します。 これにより、IDE が呼び出し元の名前などの特定の情報をプラグインに渡すことができます。 また、IDE は、コメントの最大許容長やプラグインの機能など、特定の情報を取得します。

 @No__t_0 が `NULL` ポインターを指しています。 ソース管理プラグインは、独自に使用する構造体を割り当て、その構造体へのポインターを `ppvContext` に格納できます。 IDE は、このポインターを他のすべての VSSCI API 関数に渡します。これにより、プラグインは、グローバルストレージに頼らずに、プラグインの複数のインスタンスをサポートすることなく、コンテキスト情報を使用できるようになります。 [Sccuninitialize](../extensibility/sccuninitialize-function.md)の解除が呼び出されたときに、この構造体の割り当てを解除する必要があります。

 @No__t_0 パラメーターと `lpSccName` パラメーターを使用すると、IDE とソース管理プラグインで名前を交換できます。 これらの名前は、複数のインスタンスを区別するためだけに使用できます。また、実際にはメニューやダイアログボックスに表示される場合もあります。

 @No__t_0 パラメーターは、ソリューションファイルに格納され、 [Sccopenproject](../extensibility/sccopenproject-function.md)への呼び出しでソース管理プラグインに渡される補助プロジェクトパスを識別するためのコメントとして使用される文字列です。 [!INCLUDE[vsvss](../extensibility/includes/vsvss_md.md)] は、"SourceSafe プロジェクト:" という文字列を使用します。その他のソース管理プラグインでは、この特定の文字列を使用しないようにする必要があります。

 @No__t_0 パラメーターを指定すると、プラグインの機能を示す bitflags を格納するための場所がソース管理プラグインに与えられます。 (機能のビットフラグの完全な一覧については、「[機能フラグ](../extensibility/capability-flags.md)」を参照してください)。 たとえば、プラグインが呼び出し元から提供されるコールバック関数に結果を書き込むことを計画している場合、プラグインは機能ビット SCC_CAP_TEXTOUT を設定します。 これにより、IDE がバージョン管理の結果のウィンドウを作成するように通知されます。

## <a name="see-also"></a>関連項目
- [ソース管理プラグインの API 関数](../extensibility/source-control-plug-in-api-functions.md)
- [SccUninitialize](../extensibility/sccuninitialize-function.md)
- [SccOpenProject](../extensibility/sccopenproject-function.md)
- [機能フラグ](../extensibility/capability-flags.md)