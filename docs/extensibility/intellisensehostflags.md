---
title: IntelliSenseHostFlags |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IntellisenseHostFlags
helpviewer_keywords:
- IntelliSense, IntellisenseHostFlags enumeration
- IntellisenseHostFlags enumeration
ms.assetid: 0930640b-eb84-48ef-a8f7-d4268f55c99c
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 882410d68c671a83b13bd14026e5bea4c31cb37e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62861636"
---
# <a name="intellisensehostflags"></a>IntelliSenseHostFlags
IntelliSense のホストのフラグを指定します。

## <a name="syntax"></a>構文

```cpp
enum IntellisenseHostFlags
{
    IHF_READONLYCONTEXT      = 0x00000001
    IHF_NOSEPARATESUBJECT    = 0x00000002
    IHF_SINGLELINESUBJECT    = 0x00000004
    IHF_FORCECOMMITTOCONTEXT = 0x00000008
    IHF_OVERTYPE             = 0x00000010
};
```

### <a name="parameters"></a>パラメーター

|メンバー|説明|
|-------------|-----------------|
|`IHF_READONLYCONTEXT`|コンテキスト バッファーとは、読み取り専用です。|
|`IHF_NOSEPARATESUBJECT`|件名テキストはありません。 コンテキスト バッファーには、IntelliSense とターゲットが含まれています (意味`!IHF_READONLYCONTEXT`)。|
|`IHF_SINGLELINESUBJECT`|件名のテキストは、マルチ ラインことはできません。|
|`IHF_FORCECOMMITTOCONTEXT`|`CanCommitIntoReadOnlyBuffer` と同じ。|
|`IHF_OVERTYPE`|編集 (サブジェクトまたはコンテキスト) では、上書きモードで行う必要があります。|

## <a name="requirements"></a>必要条件
 SingleFileeditor.idl

## <a name="see-also"></a>関連項目
- <xref:Microsoft.VisualStudio.TextManager.Interop>