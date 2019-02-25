---
title: CreatePkgDef ユーティリティ |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- package definition
- create pkgdef
- pkgdef
- createpkgdef
ms.assetid: c745cb76-47a6-49ff-9eed-16af0f748e35
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 96b0343cd088a8d608cd3503162bf7fa737b79f4
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56602443"
---
# <a name="createpkgdef-utility"></a>CreatePkgDef ユーティリティ
パラメーターとして Visual Studio 拡張機能の .dll ファイルを受け取り、作成、 *.pkgdef*付随するファイル、 *.dll*ファイル。 *.Pkgdef*ファイルには、拡張機能がインストールされている場合、システム レジストリに書き込まそれ以外の場合は、すべての情報が含まれています。

> [!NOTE]
>  自動的に Visual Studio SDK に含まれるプロジェクト テンプレートのほとんど作成 *.pkgdef*ビルド プロセスの一環としてファイル。 このドキュメントはパッケージを手動で作成または使用する既存のパッケージを変換する必要がある場合、 *.pkgdef*展開します。

## <a name="syntax"></a>構文

```
CreatePkgDef /out=<FileName> [/codebase] [/assembly] <AssemblyPath>
```

## <a name="arguments"></a>引数
 **/アウト =&lt;FileName&gt;** 必要です。 名前を設定、 *.pkgdef*の出力ファイルを&lt;FileName&gt;します。

 **/codebase** (省略可能)。 登録を強制的に、**コードベース**ユーティリティ。

 **/assembly**への登録の強制、**アセンブリ**ユーティリティ。

 **&lt;AssemblyPath&gt;** のパス、 *.dll*ファイルを生成する、 *.pkgdef*します。

## <a name="remarks"></a>Remarks
 使用して拡張機能の配置 *.pkgdef*ファイルには、Visual Studio の以前のバージョンのレジストリの要件が置き換えられます。

 *.Pkgdef*ファイルは、次の場所のいずれかでインストールする必要があります。

- *%localappdata%\Microsoft\Visual Studio\14.0\Extensions\\*

- *%vsinstalldir%\Common7\IDE\Extensions\\*

  インストール フォルダーがある場合 *%localappdata%\Microsoft\Visual Studio\14.0\Extensions\\*、拡張機能は、Visual Studio によって認識されますは既定で無効になります。 ユーザーを使用して、拡張機能を有効にできます**拡張機能と更新**します。

  インストール フォルダーがある場合 *%vsinstalldir%\Common7\IDE\Extensions\\*、拡張機能が既定で有効にします。

> [!NOTE]
>  **拡張機能と更新**ツールは VSIX パッケージの一部としてインストールされていない場合、拡張機能へのアクセスに使用できません。

## <a name="see-also"></a>関連項目
- [CreateExpInstance ユーティリティ](../../extensibility/internals/createexpinstance-utility.md)