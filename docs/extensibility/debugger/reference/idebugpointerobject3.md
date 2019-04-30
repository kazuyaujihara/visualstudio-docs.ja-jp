---
title: IDebugPointerObject3 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
helpviewer_keywords:
- IDebugPointerObject3 interface
ms.assetid: 11d26af4-1079-435e-96fa-d5269cbea8eb
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 4ff3a5f9143b80a3cd3ca095677f9bc2c71c0d10
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63413398"
---
# <a name="idebugpointerobject3"></a>IDebugPointerObject3
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

> [!IMPORTANT]
> Visual Studio 2015 での式エバリュエーターの実装には、この方法は非推奨とされます。 CLR 式エバリュエーターの実装方法の詳細についてを参照してください[CLR 式エバリュエーター](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators)と[マネージ式エバリュエーターのサンプル](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)します。  
  
 解析ツリーでポインターを表し、拡張、 **IDebugPointerObject**インターフェイス。  
  
## <a name="syntax"></a>構文  
  
```  
IDebugPointerObject3 : IDebugPointerObject  
```  
  
## <a name="notes-for-implementers"></a>実装についてのメモ  
 式エバリュエーター (EE) は、このインターフェイスを実装します。  
  
## <a name="methods"></a>メソッド  
 メソッドだけでなく、 [IDebugPointerObject](../../../extensibility/debugger/reference/idebugpointerobject.md)インターフェイスでは、このインターフェイスは、次のメソッドを実装します。  
  
|メソッド|説明|  
|------------|-----------------|  
|[GetPointerAddress](../../../extensibility/debugger/reference/idebugpointerobject3-getpointeraddress.md)|ポインターのアドレスを取得します。|  
  
## <a name="requirements"></a>必要条件  
 ヘッダー:Ee.h  
  
 名前空間: Microsoft.VisualStudio.Debugger.Interop  
  
 アセンブリ:Microsoft.VisualStudio.Debugger.Interop.dll
