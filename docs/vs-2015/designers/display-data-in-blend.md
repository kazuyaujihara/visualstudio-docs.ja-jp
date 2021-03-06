---
title: Blend におけるデータの表示 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 87d31b6c-4607-4121-bb7d-cfc80390ab93
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 96784fbd5fa4934246a58aa76e4938ceea1bc826
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2018
ms.locfileid: "49231271"
---
# <a name="display-data-in-blend"></a>Blend におけるデータの表示
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

ページのレイアウトをカスタマイズする際、デザイナーでサンプル データを表示できます。 サンプル データは最初から、または既存のクラスを使用して生成できます。 また、アプリの実行時にアプリに表示される *ライブ データ* にも接続できます。  
  
 **このトピックの内容**  
  
-   [サンプル データの生成](#Scratch)  
  
-   [クラスからサンプル データを生成する](#Existing)  
  
-   [WPF アプリケーションでライブ データを表示する](#LiveWPF)  
  
-   [ストアまたは Phone アプリでライブ データを表示する](#LiveStore)  
  
##  <a name="Scratch"></a> サンプル データの生成  
 サンプル データを生成するには、XAML ドキュメントを開きます。 **[データ]** パネルで、**[サンプル データの作成]** ![](../designers/media/30540d76-7256-43ce-b5d9-4b2edf3d339f.png "30540d76-7256-43ce-b5d9-4b2edf3d339f") ボタン、**[新しいサンプル データ]** の順に選びます。  
  
 **[データ]** パネルでデータ構造を定義してから、いずれかのページの UI 要素にバインドします。  
  
 ![](../designers/media/496d7ebc-fe46-42f6-95a8-57b0e5be5d49.png "496d7ebc-fe46-42f6-95a8-57b0e5be5d49")  
  
 アプリの実行時にページにサンプル データを表示する場合は、**[データ ソース オプション]** ![](../designers/media/ae1fd260-4f84-420d-b196-45fde357d81d.png "ae1fd260-4f84-420d-b196-45fde357d81d") を選んでから、**[アプリケーション実行中に有効にする]** を選びます。  
  
 ![](../designers/media/05d5356d-91bb-4e6b-b3f7-29b76852c4b3.png "05d5356d-91bb-4e6b-b3f7-29b76852c4b3")  
  
 **短いビデオを見る:** ![インストール済みフィーチャーの構成](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [一からサンプル データを作成する](http://www.bing.com/videos/search?q=blend%20data&qs=n&form=QBVR&pq=blend%20data&sc=8-7&sp=-1&sk=#view=detail&mid=F8F2449A76956D480FD2F8F2449A76956D480FD2)。  
  
 **短いビデオを見る:** ![インストール済みフィーチャーの構成](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [Blend でデータ バインドを作成する](https://www.youtube.com/watch?v=LSwPB6CAvjg)。  
  
##  <a name="Existing"></a> クラスからサンプル データを生成する  
 データの構造を記述するクラスを既に作成した場合は、そこからサンプル データを生成できます。  
  
 クラスからサンプル データを生成するには、XAML ドキュメントを開いてから、**[データ]** パネルで **[サンプル データの作成]** ![](../designers/media/30540d76-7256-43ce-b5d9-4b2edf3d339f.png "30540d76-7256-43ce-b5d9-4b2edf3d339f") ボタン、**[クラスからのサンプル データの作成]** の順にクリックします。  
  
 **短いビデオを見る:** ![インストール済みフィーチャーの構成](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [クラスからサンプル データを作成する](http://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=video&cd=1&cad=rja&uact=8&ved=0CB0QtwIwAA&url=http%3A%2F%2Fchannel9.msdn.com%2FShows%2FInside%2BWindows%2BPhone%2FIWP54--Windows-Phone-Data-Binding-and-the-Magic-of-XAML&ei=F1oHVNryM4ysogSJ2oDYDw&usg=AFQjCNEYvw1WA1rdF7bfpj5RwMLUs7RCVg)。  
  
 **短いビデオを見る:** ![インストール済みフィーチャーの構成](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [Blend でデータ バインドを作成する](https://www.youtube.com/watch?v=LSwPB6CAvjg)。  
  
##  <a name="LiveWPF"></a> WPF アプリケーションでライブ データを表示する  
 **短いビデオを見る:** ![インストール済みフィーチャーの構成](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [オブジェクト データ ソースを作成する](http://www.bing.com/videos/watch/video/using-an-objectdatasource-in-expression-blend/qmavx0xg)。  
  
 **短いビデオを見る:** ![インストール済みフィーチャーの構成](../designers/media/bldadminconsoleinitialconfigicon.PNG "BldAdminConsoleInitialConfigIcon") [XML データ ソースを作成する](https://www.youtube.com/watch?v=RjQueappjqk&feature=youtube_gdata)。  
  
##  <a name="LiveStore"></a> ストアまたは Phone アプリでライブ データを表示する  
 「 [データとファイルの操作 (XAML)](http://msdn.microsoft.com/library/windows/apps/xaml/br229562.aspx)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [Blend for Visual Studio を使用して UI を作成する](../designers/creating-a-ui-by-using-blend-for-visual-studio.md)



