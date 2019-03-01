---
title: 概要 (Debug Interface Access SDK) |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- user-defined types
- .dbg files
- modules
- interfaces [DIA SDK]
- DBG files
- procedures [DIA SDK]
- executable files
- COM objects, in DIA SDK
- compilands
- executable images
ms.assetid: 720b4479-a8bc-4fec-860e-80c1a0780405
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e459d4429d712a9ca4c245d581c6be3578711cd6
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56616753"
---
# <a name="overview-debug-interface-access-sdk"></a>概要 (Debug Interface Access SDK)
DIA SDK を使用して、Microsoft のデバッグ情報にアクセスします。 DIA SDK では、COM ベースの Microsoft デバッグ情報の形式が変更されるたびにコードを書き直す必要がなくなります API セットを提供します。 DIA SDK では以前のバージョンによって生成される .pdb ファイルと .dbg ファイルで設定されているデバッグ情報の一部から読み取ることもできます[!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)]5.0 以降のバージョン。

 DIA SDK 内の各インターフェイスは、それ以外の場合に記載されている場合を除く別の COM オブジェクトを表します。 追加のインターフェイス、およびその他のオブジェクトが作成、明示的なクエリを使用してなど[idiadatasource::opensession](../../debugger/debug-interface-access/idiadatasource-opensession.md)または[idiasession::findchildren](../../debugger/debug-interface-access/idiasession-findchildren.md)を呼び出すことではなく、`QueryInterface`で既存のインターフェイス ポインター。

## <a name="see-also"></a>関連項目
- [IDiaDataSource::openSession](../../debugger/debug-interface-access/idiadatasource-opensession.md)
- [IDiaSession::findChildren](../../debugger/debug-interface-access/idiasession-findchildren.md)
