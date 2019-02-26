---
title: IDebugArrayObject2 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugArrayObject2 interface
ms.assetid: be6e504d-4ab3-4141-a61b-0953ee0e038e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 89130c43e38bc53e0efeb93325df94e7076d9ef1
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56691957"
---
# <a name="idebugarrayobject2"></a>IDebugArrayObject2
> [!IMPORTANT]
>  Visual Studio 2015 での式エバリュエーターの実装には、この方法は非推奨とされます。 CLR 式エバリュエーターの実装方法の詳細についてを参照してください[CLR 式エバリュエーター](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators)と[マネージ式エバリュエーターのサンプル](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)します。

 マネージ配列オブジェクトを表し、でき、式エバリュエーター、配列のベース インデックス (下限) を確認するには、(EE)。

## <a name="syntax"></a>構文

```
IDebugArrayObject2 : IDebugArrayObject
```

## <a name="notes-for-implementers"></a>実装についてのメモ
 これは、マネージ デバッグ エンジン (DE) によって実装されます。

## <a name="methods"></a>メソッド
 メソッドだけでなく、 [IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md)インターフェイスでは、このインターフェイスは、次のメソッドを実装します。

|メソッド|説明|
|------------|-----------------|
|[GetBaseIndices](../../../extensibility/debugger/reference/idebugarrayobject2-getbaseindices.md)|配列の次元数を指定されたインデックスごとに、基本のインデックス (下限) を取得します。|
|[HasBaseIndices](../../../extensibility/debugger/reference/idebugarrayobject2-hasbaseindices.md)|配列に基本のインデックス (下限) が定義されているかどうかを判断します。|

## <a name="remarks"></a>Remarks
 式エバリュエーターでは、このインターフェイスを使用して、解析ツリー内のマネージ配列を表します。

## <a name="requirements"></a>必要条件
 ヘッダー:Ee.h

 名前空間: Microsoft.VisualStudio.Debugger.Interop

 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll