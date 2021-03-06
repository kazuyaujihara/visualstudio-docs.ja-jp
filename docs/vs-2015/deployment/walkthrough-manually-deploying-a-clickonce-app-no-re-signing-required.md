---
title: 'チュートリアル: 手動で再署名が要求されるされないブランド情報を保持する ClickOnce アプリケーションの配置 |Microsoft Docs'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-deployment
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- branding
- preserved branding information
- ClickOnce deployment, manually
- multiple ClickOnce deployment and branding
- ClickOnce deployment, SDK tools
- customer deployments
- manual ClickOnce deployments
- manifests [ClickOnce]
- ClickOnce applications, deployed by others
ms.assetid: c21822fb-d4ee-42e4-b72d-41ee9786efe5
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: wpickett
ms.openlocfilehash: 2d6531a94a99e2a1c24d80e9f326d23fcc6c4ec3
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2018
ms.locfileid: "49252994"
---
# <a name="walkthrough-manually-deploying-a-clickonce-application-that-does-not-require-re-signing-and-that-preserves-branding-information"></a>チュートリアル : 再署名が不要で商標を保持する ClickOnce アプリケーションの手動配置
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

作成するときに、[!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)]アプリケーションと、それを発行する顧客に渡すを展開し、顧客は、配置マニフェストを更新して再署名に従来しました。 ほとんどの場合に推奨される方法ですが、.NET Framework 3.5 を使用すると、作成[!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)]新しい配置マニフェストを再生成することがなく、顧客によって展開できる展開します。 詳細については、次を参照してください。 [ClickOnce アプリケーションのテストの展開および Resigning なしの実稼働サーバー](../deployment/deploying-clickonce-applications-for-testing-and-production-servers-without-resigning.md)します。  
  
 作成するときに、[!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)]アプリケーションと、それを発行する顧客に渡すと展開、アプリケーション、お客様のブランド化を使用できますまたはブランド化を維持することができます。 たとえば、アプリケーションが独自のアプリケーションを 1 つである場合は、ブランド化を保持するためにする可能性があります。 場合は、アプリケーションは、顧客ごとにカスタマイズされた高、お客様のブランド化を使用する場合があります。 .NET Framework 3.5 では、展開するには、組織にアプリケーションに付与するとするブランド化を保持するために、パブリッシャー情報、およびセキュリティの署名を使用できます。 詳細については、次を参照してください。[を作成する ClickOnce アプリケーションの他のユーザー デプロイ](../deployment/creating-clickonce-applications-for-others-to-deploy.md)します。  
  
> [!NOTE]
>  このチュートリアルでデプロイ手動で作成するコマンド ライン ツール Mage.exe または MageUI.exe のグラフィカル ツールを使用します。 手動でデプロイの詳細については、次を参照してください。[チュートリアル: ClickOnce アプリケーションを手動で配置](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)します。  
  
## <a name="prerequisites"></a>必須コンポーネント  
 このチュートリアルの手順を実行するには、次のものが必要。  
  
-   Windows フォーム アプリケーションをデプロイする準備が完了したらです。 このアプリケーションは、WindowsFormsApp1 として参照されます。  
  
-   Visual Studio または Windows SDK。  
  
### <a name="to-deploy-a-clickonce-application-with-multiple-deployment-and-branding-support-using-mageexe"></a>複数の展開とブランド化のサポートが Mage.exe を使用して ClickOnce アプリケーションをデプロイするには  
  
1.  Visual Studio コマンド プロンプトを開き、[!INCLUDE[winsdkshort](../includes/winsdkshort-md.md)]コマンド プロンプト、および格納するディレクトリに変更、[!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)]ファイル。  
  
2.  配置の現在のバージョンにちなんだ名前のディレクトリを作成します。 初めてアプリケーションを展開する場合は、おそらくを選択します**1.0.0.0**します。  
  
    > [!NOTE]
    >  配置のバージョンは、アプリケーション ファイルのバージョンとは異なる可能性があります。  
  
3.  という名前のサブディレクトリを作成する**bin**し、実行可能ファイル、アセンブリ、リソース、およびデータ ファイルを含む、すべてのアプリケーション ファイルをコピーします。  
  
4.  Mage.exe への呼び出しを使用してアプリケーション マニフェストを生成します。  
  
    ```  
    mage -New Application -ToFile 1.0.0.0\WindowsFormsApp1.exe.manifest -Name "Windows Forms App 1" -Version 1.0.0.0 -FromDirectory 1.0.0.0\bin -UseManifestForTrust true -Publisher "A. Datum Corporation"  
    ```  
  
5.  デジタル証明書をアプリケーション マニフェストに署名します。  
  
    ```  
    mage -Sign WindowsFormsApp1.exe.manifest -CertFile mycert.pfx  
    ```  
  
6.  Mage.exe への呼び出しで配置マニフェストを生成します。 既定では、Mage.exe ではマーク、[!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)]その it を両方オンラインで実行できるように、オフライン インストールされているアプリケーションとして展開します。 アプリケーションで使用できるように、ユーザーがオンラインの場合にのみ使用して、`-i`引数の値を持つ`f`します。 このアプリケーションは、複数のデプロイ機能を活用するための除外、 `-providerUrl` Mage.exe への引数。 (を除くより前のバージョン 3.5 では、.NET Framework のバージョンで`-providerUrl`のオフライン アプリケーションがエラーになります)。  
  
    ```  
    mage -New Deployment -ToFile WindowsFormsApp1.application -Name "Windows Forms App 1" -Version 1.0.0.0 -AppManifest 1.0.0.0\WindowsFormsApp1.manifest   
    ```  
  
7.  配置マニフェストに署名しません。  
  
8.  すべてのファイルをネットワーク上のアプリケーションをデプロイすると、顧客に提供します。  
  
9. この時点では、顧客は彼自身の自動生成された証明書で配置マニフェストに署名する必要があります。 たとえば、顧客企業 Adventure Works という名前の場合は、MakeCert.exe ツールを使用して自己署名証明書を生成彼できます。 次に、Mage.exe を渡すことができる PFX ファイルに、MakeCert.exe によって作成されたファイルを結合するのに Pvk2pfx.exe ツールを使用します。  
  
    ```  
    makecert -r -pe -n "CN=Adventure Works" -sv MyCert.pvk MyCert.cer  
    pvk2pfx.exe -pvk MyCert.pvk -spc MyCert.cer -pfx MyCert.pfx  
    ```  
  
10. 次に、顧客は、配置マニフェストに署名するのにこの証明書を使用します。  
  
    ```  
    mage -Sign WindowsFormsApp1.application -CertFile MyCert.pfx  
    ```  
  
11. お客様は、ユーザーにアプリケーションをデプロイします。  
  
### <a name="to-deploy-a-clickonce-application-with-multiple-deployment-and-branding-support-using-mageuiexe"></a>複数の展開とブランド化のサポートが MageUI.exe を使用して ClickOnce アプリケーションをデプロイするには  
  
1.  Visual Studio コマンド プロンプトを開き、[!INCLUDE[winsdkshort](../includes/winsdkshort-md.md)]コマンド プロンプト、および格納するディレクトリに移動し、[!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)]ファイル。  
  
2.  という名前のサブディレクトリを作成する**bin**し、実行可能ファイル、アセンブリ、リソース、およびデータ ファイルを含む、すべてのアプリケーション ファイルをコピーします。  
  
3.  配置の現在のバージョンにちなんだ名前のサブディレクトリを作成します。 初めてアプリケーションを展開する場合は、おそらくを選択します**1.0.0.0**します。  
  
    > [!NOTE]
    >  配置のバージョンは、アプリケーション ファイルのバージョンとは異なる可能性があります。  
  
4.  移動、 \\ **bin**手順 2. で作成したディレクトリにディレクトリ。  
  
5.  MageUI.exe のグラフィック ツールを起動します。  
  
    ```  
    MageUI.exe  
    ```  
  
6.  選択して新しいアプリケーション マニフェストを作成する**ファイル**、**新規**、 **Application Manifest**  メニューから。  
  
7.  既定の**名前** タブで、このデプロイの名前とバージョン番号を入力します。 値を指定することも、**パブリッシャー**、どちらを使用するアプリケーションのショートカット リンク、[スタート] メニューのフォルダー名として配置されるとき。  
  
8.  選択、**アプリケーション オプション** タブでをクリックし、**信頼情報用のアプリケーション マニフェストを使用して**します。 これにより、このブランドのサードパーティ製[!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)]アプリケーション。  
  
9. 選択、**ファイル** タブでをクリックし、**参照**アプリケーション ディレクトリのテキスト ボックスの横にあるボタンをクリックします。  
  
10. 手順 2. で作成したアプリケーション ファイルを含むディレクトリを選択し、をクリックして**OK**フォルダーの選択 ダイアログ ボックスにします。  
  
11. をクリックして、 **Populate**ファイルの一覧にすべてのアプリケーション ファイルを追加するボタンをクリックします。 アプリケーションには、複数の実行可能ファイルが含まれている場合は、スタートアップ アプリケーションとしては、この展開のメイン実行可能ファイルをマークをオンに**エントリ ポイント**から、**ファイルの種類**ドロップダウン リスト。 (アプリケーションには、1 つの実行可能ファイルのみが含まれる、MageUI.exe は対象として設定する。)  
  
12. 選択、**必要なアクセス許可**タブし、アプリケーションをアサートする必要がある信頼のレベルを選択します。 既定値は**完全信頼**、ほとんどのアプリケーションに適したされます。  
  
13. 選択**ファイル**、**保存**メニューのおよびアプリケーション マニフェストを保存します。 保存すると、アプリケーション マニフェストに署名するように促されます。  
  
14. 場合は、ファイル システム上のファイルとして格納されている証明書がある場合を使用して、**証明書ファイルと符号**し、省略記号を使用して、ファイル システムから証明書を選択します (**...**) ボタンをクリックします。  
  
     - または -  
  
     証明書がコンピューターからアクセスできる証明書ストアに保持されている場合は、選択、**格納された証明書オプションを使用してサインイン**、表示された一覧から証明書を選択します。  
  
15. 選択**ファイル**、**新規**、**配置マニフェスト**、配置マニフェストを作成するメニューから、次に、**名前** タブで、指定、名前とバージョン番号 (**1.0.0.0**この例では)。  
  
16. 切り替えて、**更新**タブをクリックし、このアプリケーションを更新する頻度を指定します。 アプリケーションで使用する場合、 [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] Deployment API 自体は、更新プログラムのチェックをオフにチェック ボックスをオン**アプリケーションの更新プログラムを確認する必要があります**します。  
  
17. 切り替えて、**アプリケーション参照**タブ。クリックして設定のこのタブで値をすべて事前、 **マニフェストの**前の手順で作成したボタンをクリックし、アプリケーション マニフェストを選択します。  
  
18. 選択**保存**と配置マニフェストをディスクに保存します。 保存すると、アプリケーション マニフェストに署名するように促されます。 クリックして**キャンセル**署名せずにマニフェストを保存します。  
  
19. お客様には、すべてのアプリケーション ファイルを提供します。  
  
20. この時点では、顧客は彼自身の自動生成された証明書で配置マニフェストに署名する必要があります。 たとえば、顧客企業 Adventure Works という名前の場合は、MakeCert.exe ツールを使用して自己署名証明書を生成彼できます。 次に、Pvk2pfx.exe ツールを使用して、MageUI.exe に渡すことが PFX ファイルに、MakeCert.exe によって作成されたファイルを結合します。  
  
    ```  
    makecert -r -pe -n "CN=Adventure Works" -sv MyCert.pvk MyCert.cer  
    pvk2pfx.exe -pvk MyCert.pvk -spc MyCert.cer -pfx MyCert.pfx  
    ```  
  
21. 生成された証明書を使って、顧客はようになりました MageUI.exe で配置マニフェストを開き、保存、配置マニフェストを署名します。 署名 ダイアログ ボックスが表示されたら、選択**証明書ファイルと符号**オプション、およびディスクに保存していますが、PFX ファイルを選択します。  
  
22. お客様は、ユーザーにアプリケーションをデプロイします。  
  
## <a name="next-steps"></a>次の手順  
  
## <a name="see-also"></a>関連項目  
 [Mage.exe (マニフェストの生成および編集ツール)](http://msdn.microsoft.com/library/77dfe576-2962-407e-af13-82255df725a1)   
 [MageUI.exe (マニフェスト生成および編集ツールのグラフィカル クライアント)](http://msdn.microsoft.com/library/f9e130a6-8117-49c4-839c-c988f641dc14)   
 [Makecert.exe (証明書作成ツール)](http://msdn.microsoft.com/library/b0343f8e-9c41-4852-a85c-f8a0c408cf0d)



