---
title: SccSetOption 関数 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SccSetOption
helpviewer_keywords:
- SccSetOption function
ms.assetid: 4b5e6666-c24c-438a-a9df-9c52f58f8175
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: f48cb84a64c036b373308dfe29bfaf5d2e028b91
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72720553"
---
# <a name="sccsetoption-function"></a>SccSetOption 関数
この関数は、ソース管理プラグインの動作を制御するオプションを設定します。

## <a name="syntax"></a>構文

```cpp
SCCRTN SccSetOption(
   LPVOID pvContext,
   LONG   nOption,
   LONG   dwVal
);
```

#### <a name="parameters"></a>パラメーター
 pvContext

からソース管理プラグインのコンテキスト構造。

 いいえ

から設定するオプション。

 dwVal

からオプションの設定。

## <a name="return-value"></a>戻り値
 この関数のソース管理プラグインの実装では、次の値のいずれかが返されることが想定されています。

|[値]|説明|
|-----------|-----------------|
|SCC_OK|オプションが正常に設定されました。|
|SCC_I_SHARESUBPROJOK|@No__t_0 が `SCC_OPT_SHARESUBPROJ` た場合に返されます。ソース管理プラグインでは、IDE でターゲットフォルダーを設定できます。|
|SCC_E_OPNOTSUPPORTED|オプションが設定されていないため、依存しないようにする必要があります。|

## <a name="remarks"></a>Remarks
 IDE は、この関数を呼び出して、ソース管理プラグインの動作を制御します。 最初のパラメーターである `nOption` は、設定される値を示します。2番目のパラメーター `dwVal` は、その値の処理方法を示します。 このプラグインは、`pvContext``,` に関連付けられたこの情報を格納するので、IDE は[Sccinitialize](../extensibility/sccinitialize-function.md)を呼び出した後にこの関数を呼び出す必要があります ( [Sccopenproject](../extensibility/sccopenproject-function.md)の各呼び出しの後では必ずしも必要ではありません)。

 オプションとその値の概要:

|`nOption`|`dwValue`|説明|
|---------------|---------------|-----------------|
|`SCC_OPT_EVENTQUEUE`|`SCC_OPT_EQ_DISABLE`<br /><br /> `SCC_OPT_EQ_ENABLE`|バックグラウンドイベントキューを有効または無効にします。|
|`SCC_OPT_USERDATA`|任意の値|[Optnamechangepfn](../extensibility/optnamechangepfn.md)コールバック関数に渡されるユーザー値を指定します。|
|`SCC_OPT_HASCANCELMODE`|`SCC_OPT_HCM_NO`<br /><br /> `SCC_OPT_HCM_YES`|IDE が現在操作のキャンセルをサポートしているかどうかを示します。|
|`SCC_OPT_NAMECHANGEPFN`|[Optnamechangepfn](../extensibility/optnamechangepfn.md)コールバック関数へのポインター|名前変更コールバック関数へのポインターを設定します。|
|`SCC_OPT_SCCCHECKOUTONLY`|`SCC_OPT_SCO_NO`<br /><br /> `SCC_OPT_SCO_YES`|IDE で、ソース管理ユーザーインターフェイスを使用して手動でファイルのチェックアウトを許可するか、ソース管理プラグインを通じてのみチェックアウトする必要があるかを示します。|
|`SCC_OPT_SHARESUBPROJ`|N/A|ソース管理プラグインで IDE でローカルプロジェクトフォルダーを指定できる場合、プラグインは `SCC_I_SHARESUBPROJOK` を返します。|

## <a name="scc_opt_eventqueue"></a>SCC_OPT_EVENTQUEUE
 @No__t_0 が `SCC_OPT_EVENTQUEUE` 場合、IDE はバックグラウンド処理を無効 (または再有効化) しています。 たとえば、コンパイル中に、IDE はソース管理プラグインに対して、任意の種類のアイドル状態の処理を停止するように指示する場合があります。 コンパイル後、プラグインのイベントキューを最新の状態に保つために、バックグラウンド処理を再び有効にします。 @No__t_1 の `SCC_OPT_EVENTQUEUE` 値に対応するために、`dwVal`、`SCC_OPT_EQ_ENABLE` および `SCC_OPT_EQ_DISABLE` の2つの値を使用できます。

## <a name="scc_opt_hascancelmode"></a>SCC_OPT_HASCANCELMODE
 @No__t_0 の値が `SCC_OPT_HASCANCELMODE` 場合、IDE ではユーザーが長い操作を取り消すことができます。 @No__t_0 を `SCC_OPT_HCM_NO` (既定値) に設定すると、IDE にキャンセルモードがないことが示されます。 ユーザーがキャンセルできるようにするには、ソース管理プラグインが独自の [キャンセル] ボタンを提供している必要があります。 `SCC_OPT_HCM_YES` は、IDE が操作を取り消す機能を提供することを示します。そのため、SCC プラグインでは、独自の [キャンセル] ボタンを表示する必要はありません。 IDE が `dwVal` を `SCC_OPT_HCM_YES` に設定している場合は、`SCC_MSG_STATUS` に応答し、`lpTextOutProc` コールバック関数に送信されたメッセージを `DOCANCEL` する準備があります (「 [Lptextoutproc](../extensibility/lptextoutproc.md)」を参照してください)。 IDE でこの変数が設定されていない場合、プラグインはこれら2つのメッセージを送信しません。

## <a name="scc_opt_namechangepfn"></a>SCC_OPT_NAMECHANGEPFN
 NOption が `SCC_OPT_NAMECHANGEPFN` に設定されていて、ソース管理プラグインと IDE の両方で許可されている場合、プラグインは実際にソース管理操作中にファイルの名前変更や移動を行うことができます。 @No__t_0 は、 [Optnamechangepfn](../extensibility/optnamechangepfn.md)型の関数ポインターに設定されます。 ソース管理操作中に、プラグインはこの関数を呼び出して、3つのパラメーターを渡すことができます。 これらは、ファイルの古い名前 (完全修飾パスを持つ)、そのファイルの新しい名前 (完全修飾パス)、および IDE に関連する情報へのポインターです。 IDE は、`nOption` を `SCC_OPT_USERDATA` に設定し、データを指す `dwVal` を使用して、この最後のポインターで `SccSetOption` を呼び出します。 この関数のサポートは省略可能です。 この機能を使用する VSSCI プラグは、関数ポインターとユーザーデータ変数を `NULL` に初期化する必要があります。また、名前を指定していない限り、rename 関数を呼び出すことはできません。 また、指定された値を保持するように準備するか、`SccSetOption` の新しい呼び出しに応じて変更する必要があります。 これは、ソース管理コマンド操作の途中では発生しませんが、コマンド間で発生する可能性があります。

## <a name="scc_opt_scccheckoutonly"></a>SCC_OPT_SCCCHECKOUTONLY
 NOption が `SCC_OPT_SCCCHECKOUTONLY` に設定されている場合、IDE は、現在開いているプロジェクト内のファイルがソース管理システムのユーザーインターフェイスを介して手動でチェックアウトされないことを示します。 代わりに、ファイルをチェックアウトするには、IDE コントロールのソース管理プラグインを使用する必要があります。 @No__t_0 が `SCC_OPT_SCO_NO` に設定されている場合、ファイルはプラグインによって通常どおりに処理される必要があり、ソース管理 UI からチェックアウトできます。 @No__t_0 が `SCC_OPT_SCO_YES` に設定されている場合、プラグインのみがファイルのチェックアウトを許可され、ソース管理システムの UI を呼び出すことはできません。 これは、ide に "擬似ファイル" が含まれている可能性があります。この場合、IDE でのみチェックアウトするのが理にかなっています。

## <a name="scc_opt_sharesubproj"></a>SCC_OPT_SHARESUBPROJ
 @No__t_0 が `SCC_OPT_SHARESUBPROJ` に設定されている場合、IDE はソース管理プラグインがソース管理からファイルを追加するときに、指定したローカルフォルダーを使用できるかどうかをテストします。 @No__t_0 パラメーターの値は、この場合には関係ありません。 プラグインで、 [Sccaddfromscc](../extensibility/sccaddfromscc-function.md)が呼び出されたときにソース管理からファイルが追加されるローカルの保存先フォルダーを IDE で指定できる場合、プラグインは、`SccSetOption` 関数が呼び出されたときに `SCC_I_SHARESUBPROJOK` を返す必要があります。 次に IDE は、`SccAddFromScc` 関数の `lplpFileNames` パラメーターを使用して、コピー先フォルダーを渡します。 プラグインは、このコピー先フォルダーを使用して、ソース管理から追加されたファイルを配置します。 @No__t_1 オプションが設定されているときにプラグインが `SCC_I_SHARESUBPROJOK` を返さない場合、IDE では、プラグインが現在のローカルフォルダーにのみファイルを追加できることを前提としています。

## <a name="see-also"></a>関連項目
- [ソース管理プラグインの API 関数](../extensibility/source-control-plug-in-api-functions.md)
- [SccInitialize](../extensibility/sccinitialize-function.md)
- [SccOpenProject](../extensibility/sccopenproject-function.md)
- [SccAddFromScc](../extensibility/sccaddfromscc-function.md)
- [LPTEXTOUTPROC](../extensibility/lptextoutproc.md)
- [OPTNAMECHANGEPFN](../extensibility/optnamechangepfn.md)