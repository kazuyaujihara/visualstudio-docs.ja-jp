---
title: プロジェクトを開くコマンド
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- file.openproject
- file.opensolution
helpviewer_keywords:
- op command
- File.OpenProject command
- Open Project command
ms.assetid: baa85f86-041b-49f4-9ced-0c397dc180e1
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5c84a2dcd99ef7cff9b5f37a1c69f235582a7973
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72666413"
---
# <a name="open-project-command"></a>OpenProject コマンド

既存のプロジェクトやソリューションを開きます。

## <a name="syntax"></a>構文

```cmd
File.OpenProject filename
```

## <a name="arguments"></a>引数

`filename`

必須です。 開くプロジェクトまたはソリューションの完全パスとファイル名。

> [!NOTE]
> `filename` 引数の構文の場合、空白を含むパスで引用符を使用する必要があります。

## <a name="remarks"></a>解説

オート コンプリートでは、入力された正しいパスとファイル名の検索を試みます。

デバッグ中にこのコマンドを使用することはできません。

## <a name="example"></a>例

次の例では、Visual Basic プロジェクト **Test1** が開きます。

```cmd
>File.OpenProject "C:\My Projects\Test1\Test1.vbproj"
```

## <a name="see-also"></a>関連項目

- [Visual Studio コマンド](../../ide/reference/visual-studio-commands.md)
- [コマンド ウィンドウ](../../ide/reference/command-window.md)
- [[検索/コマンド] ボックス](../../ide/find-command-box.md)
- [Visual Studio コマンドのエイリアス](../../ide/reference/visual-studio-command-aliases.md)