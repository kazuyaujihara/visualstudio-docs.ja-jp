---
title: CommandName 要素 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- CommandName element (VSCT XML schema)
- VSCT XML schema elements, CommandName
ms.assetid: a338b767-aa7e-4536-9908-e19a50ab60ac
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 4b792e7bbe1efaa1158cc517cd96494049e2b9e2
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2019
ms.locfileid: "66337256"
---
# <a name="commandname-element"></a>CommandName 要素
`CommandName`要素がキーボードのカテゴリに表示されるテキストを指定します、**オプション**ダイアログ ボックスで、および、**コマンド**の一覧で、**カスタマイズ**ダイアログボックス。

## <a name="syntax"></a>構文

```
<CommandName>MyCommand</CommandName>
```

## <a name="attributes-and-elements"></a>属性と要素
 以降のセクションでは、属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性
 なし。

### <a name="child-elements"></a>子要素
 なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[文字列の要素](../extensibility/strings-element.md)|など、テキスト要素をグループ化`ButtonText`と`CommandName`します。|

## <a name="see-also"></a>関連項目
- [Visual Studio コマンド テーブル (.vsct) ファイル](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)