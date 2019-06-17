---
title: CreateExpInstance ユーティリティ |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- experimental builds
- experimental hive
- experimental instance
- createexpinstance
- createexpinst
ms.assetid: 03779774-9401-49ae-997c-0c3ab25ed0d5
caps.latest.revision: 13
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 7d778f0f31a7651412915a898bff9e4bdfe6c55f
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58975540"
---
# <a name="createexpinstance-utility"></a>CreateExpInstance ユーティリティ
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

リセットするを作成するには、CreateExpInstance ユーティリティを使用するか、Visual Studio の実験用インスタンスを削除します。 実験用インスタンスを使用して、デバッグおよび基になる製品を変更することがなく Visual Studio 拡張機能をテストすることができます。  
  
## <a name="syntax"></a>構文  
  
```  
CreateExpInstance.exe [/Create | /Reset | /Clean] /VSInstance=VsInstance /RootSuffix=Suffix  
```  
  
#### <a name="parameters"></a>パラメーター  
 /作成します。  
 実験用インスタンスを作成します。  
  
 /リセットします。  
 実験用のインスタンスを削除し、新しく作成します。  
  
 /Clean  
 実験用インスタンスを削除します。  
  
 /VSInstance  
 コピーする基本の Visual Studio インスタンスが含まれているディレクトリの名前。  
  
 /RootSuffix  
 実験用インスタンス ディレクトリの名前に付加するサフィックス。  
  
## <a name="remarks"></a>Remarks  
 Visual Studio 拡張機能を使用しているときに既定の実験用インスタンスを開き、現在の拡張機能をインストールして F5 キーを押します。 実験用インスタンスが使用できない場合、既定の設定である Visual Studio を作成します。  
  
 実験用インスタンスの既定の場所は、Visual Studio のバージョン番号に依存します。 たとえば、Visual Studio 2015 で、場所は、%localappdata%\Microsoft\VisualStudio\14.0Exp\ ディレクトリの場所のすべてのファイルがそのインスタンスの一部と見なされます。 既定の場所にディレクトリ名が変更されない限り、任意の追加の実験用インスタンスは Visual Studio によって読み込まれません。  
  
 Visual Studio 実験用インスタンスを開くときに、システム レジストリにアクセスしません。 これは、レジストリ ハイブの実験用のバージョンを使用すると、Visual Studio の以前のバージョンによって異なります。  
  
 CreateExpInstance ユーティリティには、VsRegEx ユーティリティが置き換えられます。  
  
 次の例では、Visual Studio の既定の実験用インスタンスをリセットします。  
  
 **CreateExpInstance.exe /Reset /VSInstance=14.0 /RootSuffix=Exp**  
  
## <a name="see-also"></a>関連項目  
 [製品のリリース](../../misc/releasing-a-visual-studio-integration-product.md)
