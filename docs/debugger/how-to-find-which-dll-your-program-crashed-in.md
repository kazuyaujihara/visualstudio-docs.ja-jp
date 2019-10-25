---
title: '方法: プログラムがクラッシュした DLL を検索する |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.debug.dll
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugger, DLL crashes
- Module List dialog box
- errors [debugger], DLL crashes
- Modules window
- debugging [Visual Studio], DLL crashes
- DLLs, load order of
ms.assetid: ecf62568-8b65-4a41-b8a4-e962ff2dfb71
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: bff4f164e16a65efe4ec3d1f057025168eab8cd2
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72733269"
---
# <a name="how-to-find-which-dll-your-program-crashed-in-c-c-visual-basic-f"></a>方法: プログラムがクラッシュした DLL を検索するC#( C++、、Visual Basic F#、)

 システム DLL または他の開発者が作成したコードを呼び出す部分でアプリケーションがクラッシュした場合、クラッシュが発生した DLL を確認する必要があります。 プログラム外の DLL でクラッシュが発生している場合は、 **[モジュール]** ウィンドウを使用してその場所を確認できます。

### <a name="to-find-where-a-crash-occurred-using-the-modules-window"></a>[モジュール] ウィンドウを使ってクラッシュの発生場所を確認するには

1. クラッシュが発生したアドレスをメモします。

    アドレスがエラーメッセージに表示されない場合は、別の方法を使用して DLL を識別することが必要になる場合があります。 システム DLL を使用していると思われる場合は、デバッグ時に Microsoft シンボルサーバーから[シンボルを読み込む](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)ことができます。 それ以外の場合は、代わりにヒープ情報を含む[ダンプファイルを作成](../debugger/using-dump-files.md)する必要があります。 ダンプファイルを作成するためのさまざまな[ツール](https://blogs.msdn.microsoft.com/andrehal/2009/12/31/what-is-a-dump-and-how-do-i-create-one/)が用意されています。

2. **[デバッグ]** メニューの **[ウィンドウ]** をポイントし、 **[モジュール]** をクリックします。

3. **[モジュール]** ウィンドウの **[アドレス]** 列に注目します。 必要に応じて、スクロール バーを使用します。

4. 列の上部にある **[アドレス]** ボタンをクリックして、DLL をアドレス順に並べ替えます。

5. 並べ替えたリストを検索して、アドレス範囲内にクラッシュ場所がある DLL を探します。

6. **[名前]** 列と **[パス]** 列で、DLL の名前とパスを確認します。

## <a name="see-also"></a>関連項目
- [DLL プロジェクトのデバッグ](../debugger/debugging-dll-projects.md)
- [方法 : [モジュール] ウィンドウを使用する](../debugger/how-to-use-the-modules-window.md)