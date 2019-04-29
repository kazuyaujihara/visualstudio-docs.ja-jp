---
title: 使用可能なソースがありません |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.debug.nosource
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- No Source Code Available for the Current Location dialog box
ms.assetid: ed0732bc-4b8c-490f-adb1-af06869a2a6b
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 85d1d1307a119fa23bf7ba015130ab9c7b6f69d5
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62905220"
---
# <a name="no-source-available"></a>使用できるソースはありません
表示しようとしているコードのソース コードがプロジェクトに含まれていません。 原因として、**[呼び出し履歴]** ウィンドウまたは **[スレッド]** ウィンドウで、ソース コードのないモジュールをダブルクリックしたことが考えられます。 デバッグは継続できますが、ソース ウィンドウを使ってブレークポイントを設定したり、この場所で他のアクションを実行したりすることはできません。 ブレークポイントを設定する必要があるときは、代わりに **[逆アセンブリ]** ウィンドウを使用します。

 [ソリューション  プロパティ ページ] で、デバッガーがソース ファイルを検索するディレクトリを変更したり、選択されたソース ファイルをデバッガーが無視したりするように設定できます。 参照してください[デバッグ ソース ファイル、一般的なプロパティは、ソリューション プロパティ ページ ダイアログ ボックス](../debugger/debug-source-files-common-properties-solution-property-pages-dialog-box.md)します。

 **ソース コードを検索する参照**ソース コードを検索して参照できるダイアログ ボックスを開くには、このリンクをクリックします。

 **[逆アセンブルを表示する**起動、**逆アセンブル] ウィンドウ**します。

 **見つからないソース ファイルの逆アセンブルが常に表示**を表示するには、このオプションを選択、**逆アセンブル ウィンドウ**自動的にソースが使用できない場合。 この設定は、**[オプション]** ダイアログ ボックス、**[デバッグ]** カテゴリ、**[全般]** ページで、**[ソースがない場合は逆アセンブルの表示]** をオンまたはオフにすることによっても変更できます。

## <a name="see-also"></a>関連項目
- [[デバッグ ソース ファイル] ([ソリューション プロパティ ページ] ダイアログ ボックス - [共通プロパティ])](../debugger/debug-source-files-common-properties-solution-property-pages-dialog-box.md)
- [シンボルとソース コードの管理](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)
- [SOS.dll (SOS デバッガー拡張)](/dotnet/framework/tools/sos-dll-sos-debugging-extension)