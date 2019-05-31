---
title: CreateExpInstance ユーティリティ |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- experimental builds
- experimental hive
- experimental instance
- createexpinstance
- createexpinst
ms.assetid: 03779774-9401-49ae-997c-0c3ab25ed0d5
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ed03833b6c109ca78feb86c1cfe41fa453022c66
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66341913"
---
# <a name="createexpinstance-utility"></a>CreateExpInstance ユーティリティ
使用して、 **CreateExpInstance**ユーティリティを作成、リセット、または Visual Studio の実験用インスタンスを削除します。 実験用インスタンスを使用して、デバッグおよび基になる製品を変更することがなく Visual Studio 拡張機能をテストすることができます。

## <a name="syntax"></a>構文

```
CreateExpInstance.exe [/Create | /Reset | /Clean] /VSInstance=VsInstance /RootSuffix=Suffix
```

## <a name="parameters"></a>パラメーター
 **/作成**実験用インスタンスを作成します。

 **/リセット**、実験用インスタンスを削除し、新しく作成します。

 **/クリーン**実験用インスタンスを削除します。

 **/VSInstance**をコピーする基本の Visual Studio インスタンスを含むディレクトリの名前。

 **/RootSuffix**実験用インスタンス ディレクトリの名前に付加するサフィックス。

## <a name="remarks"></a>Remarks
 Visual Studio 拡張機能を使用しているときに既定の実験用インスタンスを開き、現在の拡張機能をインストールして F5 キーを押します。 実験用インスタンスが使用できない場合、既定の設定である Visual Studio を作成します。

 実験用インスタンスの既定の場所は、Visual Studio のバージョン番号に依存します。 たとえば、Visual Studio 2015 の場所は *%localappdata%\Microsoft\VisualStudio\14.0Exp\\* します。 ディレクトリの場所のすべてのファイルは、そのインスタンスの一部と見なされます。 既定の場所にディレクトリ名が変更されない限り、任意の追加の実験用インスタンスは Visual Studio によって読み込まれません。

 Visual Studio 実験用インスタンスを開くときに、システム レジストリにアクセスしません。 これは、レジストリ ハイブの実験用のバージョンを使用すると、Visual Studio の以前のバージョンによって異なります。

 **CreateExpInstance**ユーティリティ置換、 **VsRegEx**ユーティリティ。

 次の例では、Visual Studio の既定の実験用インスタンスをリセットします。

 **CreateExpInstance.exe /Reset /VSInstance=14.0 /RootSuffix=Exp**

## <a name="see-also"></a>関連項目
- [VSPackage](../../extensibility/internals/vspackages.md)