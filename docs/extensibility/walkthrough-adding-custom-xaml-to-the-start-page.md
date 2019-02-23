---
title: 'チュートリアル: カスタム XAML をスタート ページに追加する |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- custom start page
- xaml start page
ms.assetid: 9af4d5f9-1cfc-4221-aea7-c8cd3f7571a6
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
monikerRange: vs-2017
ms.openlocfilehash: 992937ea0c90e3734a38ba6f2e56b19918fd7375
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56709175"
---
# <a name="walkthrough-add-custom-xaml-to-the-start-page"></a>チュートリアル: カスタム XAML をスタート ページに追加します。

このチュートリアルでは、Web ブラウザーを含むカスタム Visual Studio スタート ページを作成する方法を示します。

## <a name="add-custom-xaml"></a>カスタム XAML を追加します。

1.  スタート ページを次の手順で作成[カスタム スタート ページを作成する](../extensibility/creating-a-custom-start-page.md)します。

2.  *MainWindow.xaml*ファイルで、検索、\<グリッド > セクション。

3.  追加、 \<TabControl > 要素と\<TabItem > 内で、\<グリッド > 要素は、次の例に示すようにします。

    ```xml
    <Grid>
        <TabControl>
            <TabItem Header="Bing" Height="Auto">
                <Frame Source="http://www.bing.com" />
            </TabItem>
        </TabControl>
    </Grid>
    ```

4.  1 秒あたりの追加\<TabItem > で、\<ボタン > 要素を新しいプロジェクトを開きます。

    ```xml
    <Grid>
        <TabControl>
            <TabItem Header="MyButton" Height="Auto">
                <Button Name="btnNewProj" Content="New Project"
                    Command="{x:Static vscom:VSCommands.ExecuteCommand}"
                    CommandParameter="File.NewProject" >
                </Button>
            </TabItem>
            <TabItem Header="Bing" Height="Auto">
                <Frame Source="http://www.bing.com" />
            </TabItem>
        </TabControl>
    </Grid>
    ```

## <a name="test-the-custom-start-page"></a>カスタム スタート ページをテストします。

1.  **F5**キーを押します。

     Visual Studio の実験用インスタンスのインストールが選択されていないカスタム スタート ページが表示されます。

2.  Visual Studio の実験用インスタンスを開き、**ツール/Options/環境**ページ。

3.  選択**スタートアップ**します。 **スタート ページのカスタマイズ**一覧で、、 *.xaml*ファイルを開き、をクリックして**OK**します。

4.  **[表示]** メニューの **[スタート ページ]** をクリックします。

5.  をクリックして、 **Bing**タブ。

     Bing web ページが表示されます。

6.  をクリックして、 **MyButton**タブ。

     表示する必要があります、 **MyProject**ボタンを開きます、**新しいプロジェクト**ダイアログ。

7.  実験用インスタンスを閉じます。

カスタム スタート ページを適用する**ツール** > **オプション** > **環境**、**スタートアップ**します。 **スタート ページのカスタマイズ**一覧で、、 *.xaml*ファイルを開き、をクリックして**OK**します。

## <a name="next-steps"></a>次の手順

これで、Visual Studio のスタート ページには、Web ブラウザーのタブと [MyButton] タブを表示するタブが含まれています。使用して、その他の機能を持つカスタム スタート ページを作成することができます、*コード ビハインド*ように、カスタムの .dll を追加するモデル[スタート ページにユーザー コントロールの追加](../extensibility/adding-user-control-to-the-start-page.md)します。 他のユーザーとカスタム スタート ページを共有するには、結果として得られる .vsix ファイルを発行することによって、 [Visual Studio ギャラリー](http://go.microsoft.com/fwlink/?LinkID=123847) Web サイト、または別の Web サイトやネットワーク共有です。 詳細については、「 [Deploying Custom Start Pages](../extensibility/deploying-custom-start-pages.md)」を参照してください。

## <a name="see-also"></a>関連項目

- [スタート ページをカスタマイズします。](../ide/customizing-the-start-page-for-visual-studio.md)
- [コンテナーの WPF コントロール](https://msdn.microsoft.com/library/a0177167-d7db-4205-9607-8ae316952566)