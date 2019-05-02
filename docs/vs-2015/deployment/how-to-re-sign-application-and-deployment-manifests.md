---
title: '方法: アプリケーション マニフェストおよび配置マニフェストに再署名 |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- Office applications, signing manifests
- deploying applications [ClickOnce], signing manifests
- deploying applications, signing manifests
- ClickOnce deployment, signing manifests
- Office development in Visual Studio, signing manifests
ms.assetid: d53bceb9-4d3b-4c22-b909-8f370e7231fb
caps.latest.revision: 19
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: adc2347e6928a841a0a2c24d1d786be8edcbc4ac
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "60045784"
---
# <a name="how-to-re-sign-application-and-deployment-manifests"></a>方法: アプリケーション マニフェストと配置マニフェストの再署名
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Windows フォーム アプリケーション、Windows Presentation Foundation アプリケーション (xbap)、Office ソリューション用アプリケーション マニフェストの配置プロパティを変更したら、両方のアプリケーションを再署名する必要があり、配置マニフェストに、証明書。 このプロセスによって、改ざんされたファイルがエンド ユーザーのコンピューターにインストールされないようにすることができます。  
  
 マニフェストを再署名が別のシナリオは、お客様が、アプリケーションに署名して、配置マニフェストに、独自の証明書です。  
  
## <a name="re-signing-the-application-and-deployment-manifests"></a>再署名、アプリケーションおよび配置マニフェストします。  
 この手順では、アプリケーションのマニフェスト ファイル (.manifest) に変更が既に行われたことを前提としています。 詳細については、「[方法 :展開のプロパティを変更する](http://msdn.microsoft.com/66052a3a-8127-4964-8147-2477ef5d1472)します。  
  
#### <a name="to-re-sign-the-application-and-deployment-manifests-with-mageexe"></a>Mage.exe を使用してマニフェストに、アプリケーションおよび配置を再署名するには  
  
1. 開く、 **Visual Studio コマンド プロンプト**ウィンドウ。  
  
2. マニフェスト ファイルに署名するが含まれるフォルダーにディレクトリを変更します。  
  
3. アプリケーション マニフェスト ファイルの署名には、次のコマンドを入力します。 ManifestFileName をマニフェスト ファイルと、拡張の名前に置き換えます。 証明書を証明書ファイルの相対パスまたは完全修飾パスに置き換え、パスワードを証明書のパスワードに置き換えます。  
  
    ```  
    mage -sign ManifestFileName.manifest -CertFile Certificate -Password Password  
    ```  
  
     たとえば、アドインによって、Windows フォーム アプリケーションでは、または Windows Presentation Foundation ブラウザー アプリケーションのアプリケーション マニフェストに署名するには、次のコマンドを実行できます。 Visual Studio によって作成された一時的な証明書は実稼働環境に展開するため推奨されません。  
  
    ```  
    mage -sign WindowsFormsApplication1.exe.manifest -CertFile ..\WindowsFormsApplication1_TemporaryKey.pfx  
    mage -sign ExcelAddin1.dll.manifest -CertFile ..\ExcelAddIn1_TemporaryKey.pfx  
    mage -sign WpfBrowserApplication1.exe.manifest -CertFile ..\WpfBrowserApplication1_TemporaryKey.pfx  
    ```  
  
4. 更新し、前の手順のようにプレース ホルダー名を置き換えて、配置マニフェスト ファイルを署名するには、次のコマンドを入力します。  
  
    ```  
    mage -update DeploymentManifest -appmanifest ApplicationManifest -CertFile Certificate -Password Password  
    ```  
  
     たとえば、更新、および Excel のアドインで、Windows フォーム アプリケーション、または Windows Presentation Foundation ブラウザー アプリケーションの配置マニフェストに署名するには、次のコマンドを実行できます。  
  
    ```  
    mage -update WindowsFormsApplication1.application -appmanifest WindowsFormsApplication1.exe.manifest -CertFile ..\WindowsFormsApplication1_TemporaryKey.pfx  
    mage -update ExcelAddin1.vsto -appmanifest ExcelAddin1.dll.manifest -CertFile ..\ExcelAddIn1_TemporaryKey.pfx  
    mage -update WpfBrowserApplication1.xbap -appmanifest WpfBrowserApplication1.exe.manifest -CertFile ..\WpfBrowserApplication1_TemporaryKey.pfx  
    ```  
  
5. 必要に応じて、マスター展開マニフェストをコピー (発行\\*appname*.application) バージョンの展開ディレクトリに (publish\Application ファイル\\*appname*_*バージョン*)。  
  
## <a name="updating-and-re-signing-the-application-and-deployment-manifests"></a>更新およびアプリケーション マニフェストと配置マニフェストに再署名  
 この手順は、アプリケーション マニフェスト (.manifest)、ファイルの変更が既に行われたことが、更新されたその他のファイルがあることを前提とします。 ファイルが更新されると、ファイルを表すハッシュも更新する必要があります。  
  
#### <a name="to-update-and-re-sign-the-application-and-deployment-manifests-with-mageexe"></a>Mage.exe を使用してマニフェストを更新し、アプリケーションおよび配置に再署名するには  
  
1. 開く、 **Visual Studio コマンド プロンプト**ウィンドウ。  
  
2. マニフェスト ファイルに署名するが含まれるフォルダーにディレクトリを変更します。  
  
3. 発行の出力フォルダー内のファイルから、.deploy ファイル拡張子を削除します。  
  
4. 更新されたファイル用の新しいハッシュで、アプリケーション マニフェストを更新して、アプリケーション マニフェスト ファイルに署名するには、次のコマンドを入力します。 ManifestFileName をマニフェスト ファイルと、拡張の名前に置き換えます。 証明書を証明書ファイルの相対パスまたは完全修飾パスに置き換え、パスワードを証明書のパスワードに置き換えます。  
  
    ```  
    mage -update ManifestFileName.manifest -CertFile Certificate -Password Password  
    ```  
  
     たとえば、アドインによって、Windows フォーム アプリケーションでは、または Windows Presentation Foundation ブラウザー アプリケーションのアプリケーション マニフェストに署名するには、次のコマンドを実行できます。 Visual Studio によって作成された一時的な証明書は実稼働環境に展開するため推奨されません。  
  
    ```  
    mage -update WindowsFormsApplication1.exe.manifest -CertFile ..\WindowsFormsApplication1_TemporaryKey.pfx  
    mage -update ExcelAddin1.dll.manifest -CertFile ..\ExcelAddIn1_TemporaryKey.pfx  
    mage -update WpfBrowserApplication1.exe.manifest -CertFile ..\WpfBrowserApplication1_TemporaryKey.pfx  
    ```  
  
5. 更新し、前の手順のようにプレース ホルダー名を置き換えて、配置マニフェスト ファイルを署名するには、次のコマンドを入力します。  
  
    ```  
    mage -update DeploymentManifest -appmanifest ApplicationManifest -CertFile Certificate -Password Password  
    ```  
  
     たとえば、更新、および Excel のアドインで、Windows フォーム アプリケーション、または Windows Presentation Foundation ブラウザー アプリケーションの配置マニフェストに署名するには、次のコマンドを実行できます。  
  
    ```  
    mage -update WindowsFormsApplication1.application -appmanifest WindowsFormsApplication1.exe.manifest -CertFile ..\WindowsFormsApplication1_TemporaryKey.pfx  
    mage -update ExcelAddin1.vsto -appmanifest ExcelAddin1.dll.manifest -CertFile ..\ExcelAddIn1_TemporaryKey.pfx  
    mage -update WpfBrowserApplication1.xbap -appmanifest WpfBrowserApplication1.exe.manifest -CertFile ..\WpfBrowserApplication1_TemporaryKey.pfx  
    ```  
  
6. ただし、アプリケーションおよび配置マニフェスト ファイル、ファイルに .deploy ファイル拡張子を追加します。  
  
7. 必要に応じて、マスター展開マニフェストをコピー (発行\\*appname*.application) バージョンの展開ディレクトリに (publish\Application ファイル\\*appname*_*バージョン*)。  
  
## <a name="see-also"></a>関連項目  
 [ClickOnce アプリケーションのセキュリティ](../deployment/securing-clickonce-applications.md)   
 [ClickOnce アプリケーションのコード アクセス セキュリティ](../deployment/code-access-security-for-clickonce-applications.md)   
 [ClickOnce と Authenticode](../deployment/clickonce-and-authenticode.md)   
 [信頼されたアプリケーションの配置の概要](../deployment/trusted-application-deployment-overview.md)   
 [方法: ClickOnce のセキュリティ設定を有効にします。](../deployment/how-to-enable-clickonce-security-settings.md)   
 [方法: ClickOnce アプリケーションのセキュリティ ゾーンを設定します。](../deployment/how-to-set-a-security-zone-for-a-clickonce-application.md)   
 [方法: ClickOnce アプリケーションのカスタム アクセス許可の設定](../deployment/how-to-set-custom-permissions-for-a-clickonce-application.md)   
 [方法: 制限されたアクセス許可を使用して ClickOnce アプリケーションをデバッグします。](../deployment/how-to-debug-a-clickonce-application-with-restricted-permissions.md)   
 [方法: ClickOnce アプリケーション用のクライアント コンピューターに信頼された発行元を追加します。](../deployment/how-to-add-a-trusted-publisher-to-a-client-computer-for-clickonce-applications.md)   
 [方法: ClickOnce 信頼プロンプトの動作を構成する](../deployment/how-to-configure-the-clickonce-trust-prompt-behavior.md)
