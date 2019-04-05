---
title: 拡張機能の更新 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- update package
- update extension
- new package version
ms.assetid: 93f79774-7b79-4dd6-94ad-13698f72c257
caps.latest.revision: 15
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 321dca309476ecba80c0293f100ed64e7bb1cc4e
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "59002602"
---
# <a name="how-to-update-a-visual-studio-extension"></a>方法: Visual Studio の拡張機能を更新する
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

使用して、システムに Visual Studio 拡張機能を更新する**拡張機能と更新**更新されたバージョンをインストールします。 VSIX マニフェストのバージョン番号をインクリメントして更新されるとは、拡張機能の更新バージョンを作成する場合を示すことができます。

 同じ入力方向の拡張機能の VSIX マニフェストであるときに更新プログラムがインストールされている`ID`として 1 つずつインストールしより高度な`Version`数。 場合、`Version`番号は、同じまたは低い、パッケージをインストールすることはできません。 場合、`ID`値が一致しない場合、まだインストールされていないパッケージは、別個の拡張機能として認識します。

 開発中に競合を防ぐため、進行中で拡張機能の以前のバージョンをアンインストールしてもアンインストールまたは競合する可能性があるその他のすべての拡張機能を無効にお勧めします。

### <a name="to-update-an-extension-on-your-system"></a>システムに拡張機能を更新するには

1.  **[ツール]** メニューの **[拡張機能と更新プログラム]** をクリックします。

2.  左側のウィンドウで次のようにクリックします。**更新**します。

3.  中央のペインで、インストールする更新プログラムをクリックします。

     更新された拡張機能のバージョン番号は、その他の情報と共に、右側のウィンドウに表示されます。

4.  右側のウィンドウの下部には、次のようにクリックします。 **Update**します。

### <a name="to-publish-an-update-of-an-extension"></a>拡張機能の更新を発行するには

1.  Visual Studio で、拡張機能を更新するためのソリューションを開きます。 変更を行います。

    > [!IMPORTANT]
    >  未署名のすべてのユーザー拡張機能は自動的に更新されません。 常に、拡張機能に署名する必要があります。

2.  **ソリューション エクスプ ローラー**source.extension.manifest を開きます。

3.  マニフェスト デザイナーでの番号の値を増やす、**バージョン**フィールド。

4.  ソリューションを保存してビルドします。

5.  (プロジェクトの \bin\Debug\ フォルダー) に新しい .vsix ファイルをアップロード、 [Visual Studio Marketplace](https://marketplace.visualstudio.com/) Web サイト。

     拡張機能の以前のバージョンを持つユーザーが開いたとき**拡張機能と更新プログラム**、新しいバージョンが表示されます、**更新**ツールが自動的に更新プログラムを探すように設定されている、一覧表示します。

     有効にまたはの下部にある更新プログラムの自動チェックを無効にすることができます、**更新**ウィンドウ (**使用可能な更新プログラムの自動検出を有効または無効に**)、変更、**の確認更新プログラム**設定**ツール/オプション/環境/拡張機能と更新**します。

    > [!NOTE]
    >  Visual Studio 2015 更新プログラム 2 より、ユーザー単位の拡張機能を自動更新するか、すべてのユーザー拡張機能を更新するか、両方を行うか (初期設定) 指定できます (**[ツール]、[オプション]、[環境]、[拡張機能と更新プログラム]**)。

## <a name="see-also"></a>関連項目
 [VSIX パッケージの構造](../extensibility/anatomy-of-a-vsix-package.md)[の検索と Visual Studio 拡張機能の使用](../ide/finding-and-using-visual-studio-extensions.md)
