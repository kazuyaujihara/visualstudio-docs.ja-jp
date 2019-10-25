---
title: ソース管理プラグインを検索するためのキーとして使用される文字列 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- source control plug-ins, strings used for finding
ms.assetid: c1e31f76-42a1-4c3d-afb2-664044ef12fd
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 07962ff9e0f9371b1fc308a35600a6819602b4f5
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72719449"
---
# <a name="strings-used-as-keys-for-finding-a-source-control-plug-in"></a>ソース管理プラグインを検索するためのキーとして使用される文字列
次の文字列は、ソース管理プラグインに関する情報を検索するためにレジストリにアクセスするためのキーです。

 `STR_SCC_PROVIDER_REG_LOCATION`、`STR_PROVIDERREGKEY`、`STR_SCCPROVIDERPATH`、および `STR_SCCPROVIDERNAME` は、Visual Studio のソース管理プラグインとして DLL を登録するために使用されるレジストリキーまたは値です。

 `SCC_PROJECTNAME_KEY`、`SCC_PROJECTAUX_KEY`、`SCC_KEY, SCC_FILE_SIGNATURE`、および `SCC_STATUS_FILE` は、MSSCCPRJ.SCC の形式を説明するために使用されます。SCC ファイル。

## <a name="string-keys-and-values"></a>文字列のキーと値

|キー|[値]|
|---------|-----------|
|`STR_SCC_PROVIDER_REG_LOCATION`|Software\SourceCodeControlProvider|
|`STR_PROVIDERREGKEY`|ProviderRegKey|
|`STR_SCCPROVIDERPATH`|SCCServerPath|
|`STR_SCCPROVIDERNAME`|SCCServerName|
|`STR_SCC_INI_SECTION`|ソースコード管理|
|`STR_SCC_INI_KEY`|SourceCodeControlProvider|
|`SCC_PROJECTNAME_KEY`|SCC_Project_Name|
|`SCC_PROJECTAUX_KEY`|SCC_Aux_Path|
|`SCC_STATUS_FILE`|MSSCCPRJ.SCC.SCC|
|`SCC_KEY`|SCC|
|`SCC_FILE_SIGNATURE`|ソースコード管理ファイル|
|`SCC_NSE`|名前空間の拡張|
|`SCC_NSE_PREFIX`|廃棄プレフィックス|
|`SCC_NSE_DisableOpenSCC`|DisableOpenFromSourceControl|
|`STR_SCCHELPCOLLECTION`|HelpCollection|
|`STR_UI_LANGUAGE`|UILanguage|
|`STR_SRCSAFE_ROOT_KEY`|Software\Microsoft\SourceSafe|

## <a name="see-also"></a>関連項目
- [ソース管理プラグイン](../extensibility/source-control-plug-ins.md)
- [方法: ソース管理プラグインのインストール](../extensibility/internals/how-to-install-a-source-control-plug-in.md)
- [MSSCCPRJ.SCC File](../extensibility/mssccprj-scc-file.md)