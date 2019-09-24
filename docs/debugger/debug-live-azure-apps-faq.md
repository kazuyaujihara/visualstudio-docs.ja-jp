---
title: スナップショットのデバッグに関する FAQ | Microsoft Docs
ms.date: 11/07/2017
ms.topic: reference
helpviewer_keywords:
- debugger
ms.assetid: 944f1eb0-a74b-4d28-ae2b-a370cd869add
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ceda2dd4e85c8db5b66ef753a748977204b8caab
ms.sourcegitcommit: ea182703e922c74725045afc251bcebac305068a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71211214"
---
# <a name="frequently-asked-questions-for-snapshot-debugging-in-visual-studio"></a>Visual Studio でのスナップショットのデバッグについてよく寄せられる質問

スナップショット デバッガーを使用してライブ Azure アプリケーションをデバッグするときに考えられる質問の一覧を以下に示します。

#### <a name="what-is-the-performance-cost-of-taking-a-snapshot"></a>スナップショットの取得にはどのようなパフォーマンス コストがかかりますか?

スナップショット デバッガーがアプリのスナップショットをキャプチャすると、アプリのプロセスはフォークされ、フォークされたコピーは中断されます。 スナップショットをデバッグする場合、デバッグ対象はプロセスのフォークされたコピーです。 このプロセスにかかる時間はわずか 10 から 20 ミリ秒ですが、アプリのヒープ全体はコピーされません。 代わりに、ページ テーブルのみがコピーされ、書き込み時にコピーするページが設定されます。 ヒープ上のアプリのオブジェクトの一部が変更された場合は、それぞれのページがコピーされます。 各スナップショットのメモリ内コストが小さい理由はこのためです (ほとんどのアプリケーションでは数百キロバイト程度)。

#### <a name="what-happens-if-i-have-a-scaled-out-azure-app-service-multiple-instances-of-my-app"></a>スケールアウトされた Azure App Service (アプリの複数のインスタンス) があるとどうなりますか?

アプリのインスタンスが複数ある場合、スナップポイントはすべてのインスタンスに適用されます。 指定した条件で最初にヒットしたスナップポイントでのみ、スナップショットが作成されます。 複数のスナップポイントがある場合、後のスナップショットは最初のスナップショットを作成したものと同じインスタンスから取得されます。 出力ウィンドウに送信されたログポイントには、1 つのインスタンスのメッセージのみが表示されますが、アプリケーション ログに送信されたログポイントではすべてのインスタンスからメッセージが送信されます。

#### <a name="how-does-the-snapshot-debugger-load-symbols"></a>スナップショット デバッガーがシンボルを読み込む方法を教えてください。

スナップショット デバッガーを使用するには、ローカルのアプリケーションまたは Azure App Service にデプロイされているアプリケーションに一致するシンボルが必要です (埋め込みの PDB は現在サポートされていません)。スナップショット デバッガーでは、Azure App Service からシンボルが自動的にダウンロードされます。 Visual Studio 2017 バージョン 15.2 以降、Azure App Service にデプロイすると、アプリのシンボルもデプロイされます。

#### <a name="does-the-snapshot-debugger-work-against-release-builds-of-my-application"></a>スナップショット デバッガーはアプリケーションのリリース ビルドに対して動作しますか?

はい。スナップショット デバッガーはリリース ビルドに対して動作するように設計されています。 スナップポイントが関数に配置されると、その関数はデバッグ バージョンに再コンパイルされ、デバッグ可能になります。 スナップショット デバッガーを停止すると、関数はリリース ビルドのバージョンに戻ります。

#### <a name="can-logpoints-cause-side-effects-in-my-production-application"></a>ログポイントが運用アプリケーションに副作用を及ぼす可能性はありますか?

いいえ。アプリに追加したログ メッセージは仮想的に評価されます。 アプリケーションに副作用を引き起こすことはありません。 ただし、ログポイントでは一部のネイティブ プロパティにアクセスできない場合があります。

#### <a name="does-the-snapshot-debugger-work-if-my-server-is-under-load"></a>サーバーに負荷がかかっていてもスナップショット デバッガーは機能しますか?

はい。スナップショットのデバッグは、サーバーに負荷がかかっていても機能します。 サーバーの空きメモリが少ない状況になると、スナップショット デバッガーが調整され、スナップショットがキャプチャされなくなります。

#### <a name="how-do-i-uninstall-the-snapshot-debugger"></a>スナップショット デバッガーをアンインストールする方法を教えてください。

App Service からスナップショット デバッガー サイト拡張機能をアンインストールするには、次の手順を実行します。

1. Visual Studio の Cloud Explorer または Azure portal のいずれかを使用して、App Service をオフにします。
1. App Service の Kudu サイト (つまり yourappservice.**scm**.azurewebsites.net) にアクセスし、 **[サイト拡張機能]** に移動します。
1. スナップショット デバッガー サイト拡張機能の [X] をクリックして削除します。

#### <a name="why-are-ports-opened-during-a-snapshot-debugger-session"></a>スナップショット デバッガー セッション中にポートが開かれるのはなぜですか?

Azure で取得されたスナップショットをデバッグするために、スナップショット デバッガーでは一連のポートを開く必要があります。これらは、リモート デバッグに必要なポートと同じです。 [ポートの一覧については、こちらを参照してください](../debugger/remote-debugger-port-assignments.md)。

#### <a name="how-do-i-disable-the-remote-debugger-extension"></a>リモートデバッガー拡張機能を無効に操作方法ますか?

App Services の場合:
1. App Service の Azure portal を使用してリモートデバッガー拡張機能を無効にします。
2. アプリケーションサービスのリソースブレード > アプリケーションの*設定*を > Azure portal
3. [*デバッグ*] セクションに移動し、[*リモートデバッグ*] の [*オフ*] をクリックします。

AKS の場合:
1. Dockerfile を更新して、 [Docker イメージの Visual Studio スナップショットデバッガー](https://github.com/Microsoft/vssnapshotdebugger-docker)に対応するセクションを削除します。
2. 変更された Docker イメージをリビルドして再デプロイします。

仮想マシンまたは仮想マシンスケールセットの場合、リモートデバッガー拡張機能、証明書、KeyVaults、および受信 NAT プールを次のように削除します。

1. リモートデバッガー拡張機能の削除

   仮想マシンと仮想マシンスケールセットのリモートデバッガーを無効にするには、いくつかの方法があります。

      - Cloud Explorer を使用してリモートデバッガーを無効にする

         - 仮想マシンリソースを Cloud Explorer >、デバッグを無効に > ます (Cloud Explorer の仮想マシンスケールセットには、デバッグの無効化は存在しません)。

      - PowerShell スクリプトまたはコマンドレットを使用してリモートデバッガーを無効にする

         バーチャルマシンの場合:

         ```powershell
         Remove-AzVMExtension -ResourceGroupName $rgName -VMName $vmName -Name Microsoft.VisualStudio.Azure.RemoteDebug.VSRemoteDebugger
         ```

         仮想マシンスケールセットの場合:

         ```powershell
         $vmss = Get-AzVmss -ResourceGroupName $rgName -VMScaleSetName $vmssName
         $extension = $vmss.VirtualMachineProfile.ExtensionProfile.Extensions | Where {$_.Name.StartsWith('VsDebuggerService')} | Select -ExpandProperty Name
         Remove-AzVmssExtension -VirtualMachineScaleSet $vmss -Name $extension
         ```

      - Azure portal を使用してリモートデバッガーを無効にする
         - 仮想マシン/仮想マシンスケールセットのリソース > ブレードの Azure portal > の拡張機能
         - VisualStudio 拡張機能をアンインストールしてください。

         > [!NOTE]
         > 仮想マシンスケールセット-ポータルでは、デバッガーのリスナーポートを削除することはできません。 Azure PowerShell を使用する必要があります。 詳細については、以下を参照してください。

2. 証明書と Azure KeyVault を削除する

   仮想マシンまたは仮想マシンスケールセット用のリモートデバッガー拡張機能をインストールすると、クライアントとサーバーの両方の証明書が作成され、Azure 仮想マシン/仮想マシンスケールセットリソースを使用して VS クライアントを認証します。

   - クライアント証明書

      この証明書は、Cert:/CurrentUser/My/にある自己署名証明書です。

      ```
      Thumbprint                                Subject
      ----------                                -------

      1234123412341234123412341234123412341234  CN=ResourceName
      ```

      この証明書をコンピューターから削除する方法の1つは、PowerShell を使用することです。

      ```powershell
      $ResourceName = 'ResourceName' # from above
      Get-ChildItem -Path Cert:\CurrentUser\My | Where-Object {$_.Subject -match $ResourceName} | Remove-Item
      ```

   - サーバー証明書
      - 対応するサーバー証明書の拇印は、Azure KeyVault にシークレットとしてデプロイされます。 VS は、仮想マシンまたは仮想マシンスケールセットのリソースに対応するリージョンで、プレフィックス MSVSAZ * を使用して KeyVault の検索または作成を試みます。 そのリージョンにデプロイされたすべての仮想マシンまたは仮想マシンスケールセットのリソースは、同じ KeyVault を共有します。
      - サーバー証明書の拇印シークレットを削除するには、Azure portal にアクセスし、リソースをホストしているのと同じリージョンで MSVSAZ * KeyVault を見つけます。 ラベルが付けられているシークレットを削除します`remotedebugcert<<ResourceName>>`
      - また、PowerShell を使用して、リソースからサーバーシークレットを削除する必要があります。

      仮想マシンの場合:

      ```powershell
      $vm.OSProfile.Secrets[0].VaultCertificates.Clear()
      Update-AzVM -ResourceGroupName $rgName -VM $vm
      ```

      仮想マシンスケールセットの場合:

      ```powershell
      $vmss.VirtualMachineProfile.OsProfile.Secrets[0].VaultCertificates.Clear()
      Update-AzVmss -ResourceGroupName $rgName -VMScaleSetName $vmssName -VirtualMachineScaleSet $vmss
      ```

3. すべてのデバッガーリスナー受信 NAT プールを削除します (仮想マシンスケールセットのみ)

   リモートデバッガーには、scaleset のロードバランサーに適用されるデバッガーリスナーのバインド済み NAT プールが導入されています。

   ```powershell
   $inboundNatPools = $vmss.VirtualMachineProfile.NetworkProfile.NetworkInterfaceConfigurations.IpConfigurations.LoadBalancerInboundNatPools
   $inboundNatPools.RemoveAll({ param($pool) $pool.Id.Contains('inboundNatPools/DebuggerListenerNatPool-') }) | Out-Null

   if ($LoadBalancerName)
   {
      $lb = Get-AzLoadBalancer -ResourceGroupName $ResourceGroup -name $LoadBalancerName
      $lb.FrontendIpConfigurations[0].InboundNatPools.RemoveAll({ param($pool) $pool.Id.Contains('inboundNatPools/DebuggerListenerNatPool-') }) | Out-Null
      Set-AzLoadBalancer -LoadBalancer $lb
   }
   ```

#### <a name="how-do-i-disable-snapshot-debugger"></a>スナップショットデバッガーを無効に操作方法ますか?

App Service の場合:
1. App Service の Azure portal でスナップショットデバッガーを無効にします。
2. アプリケーションサービスのリソースブレード > アプリケーションの*設定*を > Azure portal
3. Azure portal の次のアプリ設定を削除し、変更を保存します。
   - INSTRUMENTATIONENGINE_EXTENSION_VERSION
   - SNAPSHOTDEBUGGER_EXTENSION_VERSION

   > [!WARNING]
   > アプリケーションの設定を変更すると、アプリの再起動が開始されます。 アプリケーション設定の詳細については、「 [Azure portal での App Service アプリの構成](/azure/app-service/web-sites-configure)」を参照してください。

AKS の場合:
1. Dockerfile を更新して、 [Docker イメージの Visual Studio スナップショットデバッガー](https://github.com/Microsoft/vssnapshotdebugger-docker)に対応するセクションを削除します。
2. 変更された Docker イメージをリビルドして再デプロイします。

仮想マシン/仮想マシンスケールセットの場合:

スナップショットデバッガーを無効にするには、いくつかの方法があります。
- 仮想マシン/仮想マシンスケールセットのリソース > Cloud Explorer して、診断を無効に >

- 仮想マシン/仮想マシンスケールセットのリソースブレードを Azure portal > 拡張機能を > > Microsoft.insights.vmdiagnosticssettings 拡張機能をアンインストールします。

- [Az powershell](https://docs.microsoft.com/powershell/azure/overview)の Powershell コマンドレット

   仮想マシン:

   ```powershell
      Remove-AzVMExtension -ResourceGroupName $rgName -VMName $vmName -Name Microsoft.Insights.VMDiagnosticsSettings
   ```

   仮想マシンスケールセット:

   ```powershell
      $vmss = Get-AzVmss -ResourceGroupName $rgName -VMScaleSetName $vmssName
      Remove-AzVmssExtension -VirtualMachineScaleSet $vmss -Name Microsoft.Insights.VMDiagnosticsSettings
   ```

## <a name="see-also"></a>関連項目

- [Visual Studio でのデバッグ](../debugger/index.yml)
- [スナップショットデバッガーを使用したライブ ASP.NET アプリのデバッグ](../debugger/debug-live-azure-applications.md)
- [スナップショットデバッガーを使用したライブ ASP.NET Azure 仮想マシンの仮想マシンスケールセットのデバッグ](../debugger/debug-live-azure-virtual-machines.md)
- [スナップショットデバッガーを使用して live ASP.NET Azure Kubernetes をデバッグする](../debugger/debug-live-azure-kubernetes.md)
- [スナップショットデバッグのトラブルシューティングと既知の問題](../debugger/debug-live-azure-apps-troubleshooting.md)
