---
title: UWP アプリでプリフェッチされたコンテンツを使用したデバッグ |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- uwp
ms.openlocfilehash: 693c63e7d1094974643d17c3899a7c7c93f9f5d0
ms.sourcegitcommit: 752f03977f45169585e407ef719450dbe219b7fc
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2019
ms.locfileid: "56315795"
---
# <a name="debug-uwp-apps-using-prefetched-content-in-visual-studio"></a>プリフェッチされたコンテンツを使用して、Visual Studio で UWP アプリをデバッグします。
  
 UWP アプリの応答性が向上するには、アプリの web ページやイメージなど、一部の web コンテンツを事前に Windows を要求することができます[WinINet](/windows/desktop/WinInet/about-wininet)キャッシュします。 この機能をプリフェッチと呼びます。 これは起動時に使用されるコンテンツに特に効果的ですが、他の頻繁に使用するコンテンツをプリフェッチすることもできます。 [Windows.Networking.BackgroundTransfer.ContentPrefetcher](/uwp/api/Windows.Networking.BackgroundTransfer.ContentPrefetcher) クラスのメソッドを使用すると、プリロードするコンテンツの URI を指定できます。 アプリに ContentPrefetcher 機能を追加する方法の例については、Windows SDK の「[Content prefetch sample](https://code.msdn.microsoft.com/windowsapps/ContentPrefetcher-Sample-432c8309)」 (コンテンツのプリフェッチの例) を参照してください。  
  
 Windows は、プリフェッチを行う必要がある場合およびダウンロードするリソースを決定するためにヒューリスティックを使用します。 このヒューリスティックでは、システム ネットワークおよび電力条件、ユーザー アプリの使用履歴、および以前のプリフェッチの結果を考慮します。 Visual Studio では、**Trigger Windows Store App Prefetch** コマンドを使用することで、Windows に ContentPrefetcher ヒューリスティックを無視させ、さらに指定されたすべての Web コンテンツをプリロードさせることができます。 これは、既知の状態 (読み込まれている、または読み込まれていない) でプリフェッチするコンテンツでアプリの動作またはパフォーマンスをテストする場合に役立ちます。  
  
## <a name="to-force-preloading-of-contentprefetcher-specified-resources"></a>ContentPrefetcher で指定されるリソースのプリロードを強制するには  
 この手順では、ContentPrefetcher 機能が既に設定されていて、アプリ プロジェクトでプリロードするコンテンツ URI が指定されていると仮定しています。 指定されたリソースが新しいまたは変更されている場合にコンテンツのプリロードを強制するには、**Trigger Windows Store App Prefetch** コマンドを選択する前にアプリを開始および停止する必要があります。 まず、アプリを実行して、URI を登録します。 **Trigger Windows Store App Prefetch** コマンドによって、ContentPrefetcher がコンテンツをダウンロードし、キャッシュに追加するように強制されます。 アプリの後続の実行で、コンテンツがプリロードされたと見なすことができます。  
  
1. アプリを開始して、アプリでプリフェッチ コンテンツ URI を登録します。 **[デバッグ]** メニューで、**[デバッグの開始]** を選択します (キーボード ショートカット: F5 キー)。  
  
2. **[デバッグ]** メニューで、**[デバッグの停止]** を選択します (キーボード ショートカット: Shift + F5 キー)。  
  
3. **[デバッグ]** メニューで、**[その他のデバッグ ターゲット]** をクリックし、**[Windows ストア アプリ プリフェッチのトリガー]** をクリックします。  
  
   プリフェチした Web リソースでアプリをデバッグ、テスト、または分析できるようになりました。  
  
> [!NOTE]
>  指定された Web コンテンツを追加または変更するたびにこの手順を繰り返します。  
  
## <a name="see-also"></a>関連項目  
 [ブログの投稿: プリフェッチ Windows ストア アプリ用 Visual Studio 2013 Update 2 をトリガーします。](https://devblogs.microsoft.com/devops/triggering-prefetch-for-windows-store-apps-in-visual-studio-2013-update-2/)