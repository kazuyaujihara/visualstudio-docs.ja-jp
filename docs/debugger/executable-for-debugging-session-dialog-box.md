---
title: デバッグ セッション ダイアログ ボックスの実行可能ファイル |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.debug.exefordebug
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- executable files, specifying when debugging
- DLLs, debugging
- debugger, Executable for Debugging Session dialog box
- Executable for Debugging Session dialog box
ms.assetid: c0ddbe32-b99f-4425-acf1-f48842804f56
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 41b93ae19afd54b6e22458d1ba12029d5bb93cf3
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56682792"
---
# <a name="executable-for-debugging-session-dialog-box"></a>[デバッグ セッションで実行可能] ダイアログ ボックス

このダイアログ ボックスは、ダイナミック リンク ライブラリ (DLL: Dynamic-Link Library) をデバッグするときに、実行可能ファイルが指定されていない場合に表示されます。 Visual Studio で DLL を直接起動することはできません。 代わりに、Visual Studio は、指定された実行可能ファイルを起動します。 実行可能ファイルによって呼び出された場合は、DLL をデバッグできます。

 **実行可能ファイル名**をデバッグしている DLL を呼び出す実行可能ファイルへのパス名を入力します。

 **プロジェクトにアクセスする URL (ATL Server のみ)** ATL Server の DLL をデバッグする場合の URL を入力、プロジェクトの場所します。

 入力した後、後続のデバッグ セッションを再入力する必要はありませんので、これらの設定がプロジェクト プロパティ ページに格納されます。 設定変更が必要な場合は [プロパティ ページ] を開いて値を変更できます。 デバッグ セッションで実行可能ファイルを指定する方法の詳細については、「[DLL のデバッグ](../debugger/how-to-debug-from-a-dll-project.md)」を参照してください。

## <a name="see-also"></a>関連項目

- [Visual Studio でのデバッグ](../debugger/index.md)
- [デバッガーでのはじめに](../debugger/debugger-feature-tour.md)