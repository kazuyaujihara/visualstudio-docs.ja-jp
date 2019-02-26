---
title: IDebugClassField |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugClassField
helpviewer_keywords:
- IDebugClassField interface
ms.assetid: 49358cbc-8973-4862-9dcc-79b1248e6712
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 681a426cc95ead710fbb8dab151bb5a23b6f1206
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56703852"
---
# <a name="idebugclassfield"></a>IDebugClassField
このインターフェイスは、型としてクラスを表します。

## <a name="syntax"></a>構文

```
IDebugClassField : IDebugContainerField
```

## <a name="notes-for-implementers"></a>実装についてのメモ
 シンボル プロバイダーを実装する同一のオブジェクトにこのインターフェイスを実装する、 [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)インターフェイス。 このインターフェイスは、クラス型を表す特殊化です。

## <a name="notes-for-callers"></a>呼び出し元のノート
 インターフェイスの数がこのインターフェイスを含むを返すことができるメソッドを持つ[IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)、 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)、および[IDebugCustomAttribute](../../../extensibility/debugger/reference/idebugcustomattribute.md)します。 また、使用する[QueryInterface](/cpp/atl/queryinterface)からこのインターフェイスを取得する、 [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)インターフェイスの場合、 [GetKind](../../../extensibility/debugger/reference/idebugfield-getkind.md)メソッドは、フラグを返します`FIELD_TYPE_CLASS`します。

## <a name="methods-in-vtable-order"></a>Vtable 順序のメソッド
 メソッドだけでなく、 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)と[IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)インターフェイスでは、このインターフェイスは、次を実装します。

|メソッド|説明|
|------------|-----------------|
|[EnumBaseClasses](../../../extensibility/debugger/reference/idebugclassfield-enumbaseclasses.md)|このクラスの基底クラスの列挙子を作成します。|
|[DoesInterfaceExist](../../../extensibility/debugger/reference/idebugclassfield-doesinterfaceexist.md)|特定のインターフェイスは、クラスで定義されているかどうかを決定します。|
|[EnumNestedClasses](../../../extensibility/debugger/reference/idebugclassfield-enumnestedclasses.md)|このクラスの入れ子になったクラスの列挙子を作成します。|
|[GetEnclosingClass](../../../extensibility/debugger/reference/idebugclassfield-getenclosingclass.md)|このクラスの外側のクラスを取得します。|
|[EnumInterfacesImplemented](../../../extensibility/debugger/reference/idebugclassfield-enuminterfacesimplemented.md)|このクラスによって実装されるインターフェイスの列挙子を作成します。|
|[EnumConstructors](../../../extensibility/debugger/reference/idebugclassfield-enumconstructors.md)|このクラスのコンス トラクターの列挙子を作成します。|
|[GetDefaultIndexer](../../../extensibility/debugger/reference/idebugclassfield-getdefaultindexer.md)|既定のインデクサーの名前を取得します。|
|[EnumNestedEnums](../../../extensibility/debugger/reference/idebugclassfield-enumnestedenums.md)|このクラスの入れ子になった列挙子の列挙子を作成します。|

## <a name="requirements"></a>必要条件
 ヘッダー: sh.h

 名前空間: Microsoft.VisualStudio.Debugger.Interop

 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>関連項目
- [シンボルプロバイダーのインターフェイス](../../../extensibility/debugger/reference/symbol-provider-interfaces.md)
- [IDebugContainerField](../../../extensibility/debugger/reference/idebugcontainerfield.md)