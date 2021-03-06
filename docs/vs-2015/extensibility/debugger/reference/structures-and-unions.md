---
title: 構造体と共用体 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- structures [Visual Studio SDK]
ms.assetid: 9ff0a8f8-1ee6-4fdd-8b80-206436ff589b
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ab670d64f82f76170e83ff75a52d30a3bf4eae5e
ms.sourcegitcommit: af428c7ccd007e668ec0dd8697c88fc5d8bca1e2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/16/2018
ms.locfileid: "51755186"
---
# <a name="structures-and-unions"></a>構造体と共用体
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

構造体と共用体では、Visual Studio Debugging SDK を次に示します。  
  
 [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md)  
 システム ID または GUID 可能性のあるプロセス ID を指定します。  
  
 [BP_CONDITION](../../../extensibility/debugger/reference/bp-condition.md)  
 ブレークポイントが発生する条件をについて説明します。  
  
 [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md)  
 場所、プログラム、およびスレッドなど、エラー ブレークポイントの解決方法について説明します。  
  
 [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md)  
 ブレークポイントの位置を記述するために使用する構造体の型を指定します。  
  
 [BP_LOCATION_CODE_ADDRESS](../../../extensibility/debugger/reference/bp-location-code-address.md)  
 コード内のアドレスのブレークポイントの場所を記述するコンポーネントを定義します。  
  
 [BP_LOCATION_CODE_CONTEXT](../../../extensibility/debugger/reference/bp-location-code-context.md)  
 デバッグ中のプログラム内のアドレスに直接バインドされているブレークポイントの場所について説明します。  
  
 [BP_LOCATION_CODE_FILE_LINE](../../../extensibility/debugger/reference/bp-location-code-file-line.md)  
 コード ソース ファイル内の行のブレークポイントの場所について説明します。  
  
 [BP_LOCATION_CODE_FUNC_OFFSET](../../../extensibility/debugger/reference/bp-location-code-func-offset.md)  
 コード内の関数のブレークポイントの位置をについて説明します。  
  
 [BP_LOCATION_CODE_STRING](../../../extensibility/debugger/reference/bp-location-code-string.md)  
 IDE から、ユーザーは入力文字列に基づくコードのブレークポイントを設定するために使用します。  
  
 [BP_LOCATION_DATA_STRING](../../../extensibility/debugger/reference/bp-location-data-string.md)  
 IDE から、ユーザーが入力できる文字列に基づくデータ ブレークポイントを設定するために使用します。  
  
 [BP_LOCATION_RESOLUTION](../../../extensibility/debugger/reference/bp-location-resolution.md)  
 特定の位置にブレークポイントの解決方法をについて説明します。  
  
 [BP_PASSCOUNT](../../../extensibility/debugger/reference/bp-passcount.md)  
 既に通過した後に発生するブレークポイントとなる、カウントと条件について説明します。  
  
 [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)  
 ブレークポイントを実装するために必要な情報が含まれています。  
  
 [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md)  
 ブレークポイントを実装するために必要な情報が含まれています (と同じ、 [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)構造体には、仕入先の GUID、制約、およびトレース ポイントの情報が含まれています)。  
  
 [BP_RESOLUTION_CODE](../../../extensibility/debugger/reference/bp-resolution-code.md)  
 コードのブレークポイントの場所について説明します。  
  
 [BP_RESOLUTION_DATA](../../../extensibility/debugger/reference/bp-resolution-data.md)  
 データ ブレークポイントのバインドの結果について説明します。  
  
 [BP_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md)  
 コードのブレークポイントまたは データ ブレークポイントのバインドされたブレークポイント情報について説明します。  
  
 [BP_RESOLUTION_LOCATION](../../../extensibility/debugger/reference/bp-resolution-location.md)  
 ブレークポイント解像度の位置の構造を指定します。  
  
 [BSTR_ARRAY](../../../extensibility/debugger/reference/bstr-array.md)  
 文字列の配列について説明します。  
  
 [BUILT_TYPE](../../../extensibility/debugger/reference/built-type.md)  
 メタデータから取得したフィールドの種類に関する情報を指定します。  
  
 [CODE_PATH](../../../extensibility/debugger/reference/code-path.md)  
 関数またはメソッドの呼び出しについて説明します。  
  
 [COMPUTER_INFO](../../../extensibility/debugger/reference/computer-info.md)  
 デバッガーが実行されているコンピューターをについて説明します。  
  
 [CONST_GUID_ARRAY](../../../extensibility/debugger/reference/const-guid-array.md)  
 Guid のリストについて説明します。  
  
 [CONTEXT_INFO](../../../extensibility/debugger/reference/context-info.md)  
 メモリのコンテキストまたはコードのコンテキストについて説明します。  
  
 [DEBUG_ADDRESS](../../../extensibility/debugger/reference/debug-address.md)  
 デバッグ中のプログラムでは、住所をについて説明します。  
  
 [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md)  
 さまざまな種類のアドレスの数のいずれかを表します。  
  
 [DEBUG_CUSTOM_VIEWER](../../../extensibility/debugger/reference/debug-custom-viewer.md)  
 カスタム ビューアーを識別するか、ビジュアライザーを入力します。  
  
 [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md)  
 名前、型、および値を持つ階層的な性質のオブジェクトをさらに説明するデバッグ プロパティについて説明します。  
  
 [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md)  
 参照を記述します。  
  
 [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md)  
 [逆アセンブリ] には、IDE の表示について説明します。  
  
 [EXCEPTION_INFO](../../../extensibility/debugger/reference/exception-info.md)  
 例外またはデバッグ中のプログラムによってスローされた実行時エラーについて説明します。  
  
 [FIELD_INFO](../../../extensibility/debugger/reference/field-info.md)  
 ローカル変数、パラメーター、またはその他のフィールドについて説明します。  
  
 [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md)  
 スタック フレームをについて説明します。  
  
 [GUID_ARRAY](../../../extensibility/debugger/reference/guid-array.md)  
 使用可能なデバッグ エンジンの一意の識別子の配列について説明します。  
  
 [JMC_CODE_SPEC](../../../extensibility/debugger/reference/jmc-code-spec.md)  
 モジュールの JustMyCode 情報を設定するために使用します。  
  
 [MACHINE_INFO](../../../extensibility/debugger/reference/machine-info.md)  
 特定のコンピューターについて説明します。  
  
 [METADATA_ADDRESS_ARRAYELEM](../../../extensibility/debugger/reference/metadata-address-arrayelem.md)  
 配列内の配列要素をについて説明します。  
  
 [METADATA_ADDRESS_FIELD](../../../extensibility/debugger/reference/metadata-address-field.md)  
 クラスまたは構造体のフィールドのアドレスをについて説明します。  
  
 [METADATA_ADDRESS_LOCAL](../../../extensibility/debugger/reference/metadata-address-local.md)  
 (通常関数またはメソッド) のスコープ内でローカル変数のアドレスをについて説明します。  
  
 [METADATA_ADDRESS_METHOD](../../../extensibility/debugger/reference/metadata-address-method.md)  
 クラスのメソッドのアドレスをについて説明します。  
  
 [METADATA_ADDRESS_PARAM](../../../extensibility/debugger/reference/metadata-address-param.md)  
 メソッドまたは関数のパラメーターについて説明します。  
  
 [METADATA_ADDRESS_RETVAL](../../../extensibility/debugger/reference/metadata-address-retval.md)  
 メソッドまたは関数からの戻り値をについて説明します。  
  
 [METADATA_TYPE](../../../extensibility/debugger/reference/metadata-type.md)  
 メタデータから取得したフィールドの種類について説明します。  
  
 [MODULE_INFO](../../../extensibility/debugger/reference/module-info.md)  
 特定のモジュール (DLL、exe ファイルまたはアセンブリ) について説明します。  
  
 [MODULE_SYMBOL_SEARCH_INFO](../../../extensibility/debugger/reference/module-symbol-search-info.md)  
 検索したシンボルの検索パスに関する状態情報をについて説明します。  
  
 [NATIVE_ADDRESS](../../../extensibility/debugger/reference/native-address.md)  
 ネイティブのアドレスをについて説明します。  
  
 [PDB_TYPE](../../../extensibility/debugger/reference/pdb-type.md)  
 PDB シンボルから取得したフィールドの種類について説明します。  
  
 [PENDING_BP_STATE_INFO](../../../extensibility/debugger/reference/pending-bp-state-info.md)  
 コードの場所にバインドする準備が整っているブレークポイントの状態について説明します。  
  
 [PROCESS_INFO](../../../extensibility/debugger/reference/process-info.md)  
 プロセスをについて説明します。  
  
 [PROGRAM_NODE_ARRAY](../../../extensibility/debugger/reference/program-node-array.md)  
 説明の一覧[IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)プログラム ノードを表すオブジェクト。  
  
 [PROVIDER_PROCESS_DATA](../../../extensibility/debugger/reference/provider-process-data.md)  
 コンピューターで実行中のプロセスについて説明します。  
  
 [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md)  
 指定されたテキストの行と列の場所について説明します。  
  
 [THREADPROPERTIES](../../../extensibility/debugger/reference/threadproperties.md)  
 スレッドのプロパティについて説明します。  
  
 [TYPE_INFO](../../../extensibility/debugger/reference/type-info.md)  
 フィールドの型について説明します。  
  
 [UNMANAGED_ADDRESS_PHYSICAL](../../../extensibility/debugger/reference/unmanaged-address-physical.md)  
 物理アドレスをについて説明します。  
  
 [UNMANAGED_ADDRESS_THIS_RELATIVE](../../../extensibility/debugger/reference/unmanaged-address-this-relative.md)  
 アドレスに対して相対的なをについて説明します、`this`ポインター (`Me` Visual Basic で)。  
  
## <a name="requirements"></a>必要条件  
 ヘッダー: msdbg.h、sh.h、または ee.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 アセンブリ: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>関連項目  
 [API リファレンス](../../../extensibility/debugger/reference/api-reference-visual-studio-debugging.md)

