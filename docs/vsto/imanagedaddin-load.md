---
title: IManagedAddin::Load
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords: ''
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 87fb34e90d36383f49b6369fb1dea4b9854c7300
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56604008"
---
# <a name="imanagedaddinload"></a>IManagedAddin::Load
  管理対象の VSTO アドインが読み込まれるときに呼び出されます。

## <a name="syntax"></a>構文

```csharp
HRESULT Load([in] BSTR bstrManifestURL,
             [in] IDispatch *pdispApplication);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*bstrManifestURL*|VSTO アドインのマニフェストの完全なパス。|
|*pdispApplication*|VSTO アドインの読み込みは、ホスト アプリケーションを表すへのポインター。|

## <a name="return-value"></a>戻り値
 メソッドが正常に完了したかどうかを示す HRESULT 値。

## <a name="remarks"></a>Remarks
 マニフェストは、VSTO アドインの読み込みに使用される情報を提供するファイル (通常は XML ファイル) です。 たとえば、マニフェストには、VSTO アドイン アセンブリの場所や、VSTO アドインが読み込まれるときにインスタンス化するエントリ ポイント クラスを指定できます。

 *BstrManifestURL*パラメーターには値が含まれています、`Manifest`の下のエントリ、 **HKEY_CURRENT_USER\Software\Microsoft\Office\\_\<アプリケーション名>_ \Addins\\_\<アドイン ID >_**  VSTO アドインのレジストリ キー。 詳細については、[IManagedAddin インターフェイス](../vsto/imanagedaddin-interface.md)を参照してください。

 読み込まれる VSTO アドインのアプリケーション ドメインやセキュリティ ポリシーの構成などのタスクを実行するように、 [IManagedAddIn::Load](../vsto/imanagedaddin-load.md) メソッドを実装します。

## <a name="see-also"></a>関連項目
- [IManagedAddin Interface](../vsto/imanagedaddin-interface.md)
- [IManagedAddin::Unload](../vsto/imanagedaddin-unload.md)
