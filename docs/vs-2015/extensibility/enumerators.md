---
title: 列挙子 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control plug-ins, enumerators
ms.assetid: a60030c5-e1d1-47e1-84bb-cbfe838ab479
caps.latest.revision: 20
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 65a03a8dc741ec86aca3137f49cd753722ede215
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58975045"
---
# <a name="enumerators"></a>列挙子
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

このセクションでは、ソース管理プラグインが認識する必要がありますソース コントロールのプラグイン API で列挙子のデータ型を示します。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [コマンド コード](../extensibility/command-code-enumerator.md)  
 オプションを列挙、 [SccGetCommandOptions](../extensibility/sccgetcommandoptions-function.md)と[SccPopulateList](../extensibility/sccpopulatelist-function.md)関数。  
  
 [[メッセージ]](../extensibility/message-enumerator.md)  
 印刷のコールバックを使用するフラグの列挙[LPTEXTOUTPROC](../extensibility/lptextoutproc.md)します。  
  
 [ファイルの状態コード](../extensibility/file-status-code-enumerator.md)  
 ソース管理下にあるファイルの状態を指定する名前付き定数の値が含まれています。  
  
 [ディレクトリの状態コード](../extensibility/directory-status-code-enumerator.md)  
 ソース管理下のディレクトリの状態を指定する名前付き定数の値が含まれています。  
  
## <a name="related-sections"></a>関連項目  
 [ソース管理プラグインの作成](../extensibility/internals/creating-a-source-control-plug-in.md)  
 ソース管理プラグインの SDK を定義し、含まれているリソースについて説明します。  
  
 [SccGetCommandOptions](../extensibility/sccgetcommandoptions-function.md)  
 指定したコマンドの詳細設定オプションのユーザーに求めます。  
  
 [SccPopulateList](../extensibility/sccpopulatelist-function.md)  
 現在の状態のファイルの一覧を検証します。 また、使用して、`pfnPopulate`ファイルでの条件が一致しない場合に、呼び出し元に通知するため、`nCommand`します。  
  
 [LPTEXTOUTPROC](../extensibility/lptextoutproc.md)  
 によって使用されるコールバック関数について説明します[SccOpenProject](../extensibility/sccopenproject-function.md) ide プラグインのソース管理からのメッセージを表示します。  
  
 [ソース管理プラグイン](../extensibility/source-control-plug-ins.md)  
 ソース管理プラグイン API のすべての要素の完全な一覧を提供します。
