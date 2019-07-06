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
ms.openlocfilehash: 813f06f55b6ae8f03a8d5a8e452ca05c4fe2054c
ms.sourcegitcommit: 32144a09ed46e7223ef7dcab647a9f73afa2dd55
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/05/2019
ms.locfileid: "67586841"
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

1. Visual Studio で Cloud Explorer または Azure portal を通じて、App Service をオフにします。
1. App Service の Kudu サイト (つまり yourappservice.**scm**.azurewebsites.net) にアクセスし、 **[サイト拡張機能]** に移動します。
1. スナップショット デバッガー サイト拡張機能の [X] をクリックして削除します。

#### <a name="why-are-ports-opened-during-a-snapshot-debugger-session"></a>スナップショット デバッガー セッション中にポートが開かれるのはなぜですか?

Azure で取得されたスナップショットをデバッグするために、スナップショット デバッガーでは一連のポートを開く必要があります。これらは、リモート デバッグに必要なポートと同じです。 [ポートの一覧については、こちらを参照してください](../debugger/remote-debugger-port-assignments.md)。

#### <a name="how-do-i-disable-the-remote-debugger-extension"></a>リモート デバッガーの拡張機能を無効にする方法は?

App services:
1. App Service の Azure portal を使用してリモート デバッガーの拡張機能を無効にします。
2. Azure portal >、アプリケーション サービスのリソース ブレード >*アプリケーションの設定*
3. 移動し、*デバッグ*セクションし、をクリックして、*オフ*ボタン*リモート デバッグ*。

For AKS:
1. 更新に対応するセクションを削除する、Dockerfile、 [Docker イメージでの Visual Studio Snapshot Debugger](https://github.com/Microsoft/vssnapshotdebugger-docker)します。
2. リビルドして変更された Docker イメージを再デプロイします。

仮想マシン/仮想マシン スケール セットを削除、リモート デバッガーの拡張機能、証明書、KeyVaults と受信 NAT プールには、次のようにします。

1. リモート デバッガーの拡張機能を削除します。

   仮想マシンと仮想マシン スケール セット用のリモート デバッガーを無効にするいくつかの方法はあります。

      - クラウド エクスプ ローラーからリモート デバッガーを無効にします。

         - クラウド エクスプ ローラー > 仮想マシン リソース > デバッグを無効にする (デバッグを無効にするが存在しない仮想マシン スケール セットで Cloud Explorer の)。

      - リモート デバッガーでは、PowerShell スクリプト/コマンドレットを無効にします。

         仮想マシン。

         ```powershell
         Remove-AzVMExtension -ResourceGroupName $rgName -VMName $vmName -Name Microsoft.VisualStudio.Azure.RemoteDebug.VSRemoteDebugger
         ```

         仮想マシン スケール セット。

         ```powershell
         $vmss = Get-AzVmss -ResourceGroupName $rgName -VMScaleSetName $vmssName
         $extension = $vmss.VirtualMachineProfile.ExtensionProfile.Extensions | Where {$_.Name.StartsWith('VsDebuggerService')} | Select -ExpandProperty Name
         Remove-AzVmssExtension -VirtualMachineScaleSet $vmss -Name $extension
         ```

      - Azure ポータルでリモート デバッガーを無効にします。
         - Azure portal >、仮想マシン/仮想マシン スケール セットのリソース ブレード > 拡張機能
         - Microsoft.VisualStudio.Azure.RemoteDebug.VSRemoteDebugger 拡張機能をアンインストールします。

         > [!NOTE]
         > 仮想マシン スケール セットでは、ポータルは許可されません DebuggerListener ポートを削除します。 Azure PowerShell を使用する必要があります。 詳細については、以下を参照してください。

2. 証明書を削除し、Azure key Vault

   仮想マシンまたは仮想マシン スケール セットのリモート デバッガーの拡張機能をインストールするときに、Azure の仮想マシンで VS クライアントを認証するクライアントとサーバーの両方の証明書の作成/仮想マシン スケール セット リソース。

   - クライアント証明書

      この証明書が証明書にある自己署名証明書:/CurrentUser/マイ/

      ```
      Thumbprint                                Subject
      ----------                                -------

      1234123412341234123412341234123412341234  CN=ResourceName
      ```

      PowerShell を使用して、コンピューターからこの証明書を削除する方法の 1 つは、します。

      ```powershell
      $ResourceName = 'ResourceName' # from above
      Get-ChildItem -Path Cert:\CurrentUser\My | Where-Object {$_.Subject -match $ResourceName} | Remove-Item
      ```

   - サーバー証明書
      - 対応するサーバー証明書の拇印は、Azure key Vault にシークレットとしてデプロイされます。 VS が検索または MSVSAZ * は、仮想マシンに対応するリージョンでのプレフィックスを key Vault を作成することも仮想マシン スケール セット リソース。 すべての仮想マシンまたは仮想マシン スケール セットのリージョンにデプロイされたリソースはそのため、同じ key Vault が共有されます。
      - サーバー証明書の拇印のシークレットを削除するには、Azure portal に移動し、リソースをホストしているのと同じリージョンに MSVSAZ * KeyVault を検索します。 ラベルを付ける必要がありますシークレットを削除します。 `remotedebugcert<<ResourceName>>`
      - PowerShell を使用して、リソースからサーバー シークレットを削除する必要があります。

      仮想マシン。

      ```powershell
      $vm.OSProfile.Secrets[0].VaultCertificates.Clear()
      Update-AzVM -ResourceGroupName $rgName -VM $vm
      ```

      仮想マシン スケール セット。

      ```powershell
      $vmss.VirtualMachineProfile.OsProfile.Secrets[0].VaultCertificates.Clear()
      Update-AzVmss -ResourceGroupName $rgName -VMScaleSetName $vmssName -VirtualMachineScaleSet $vmss
      ```

3. DebuggerListener 受信 NAT プール (仮想マシン スケール セットのみ) をすべて削除します。

   リモート デバッガーには、スケール セットのロード バランサーに適用される DebuggerListener 着信 NAT プールが導入されています。

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

#### <a name="how-do-i-disable-snapshot-debugger"></a>スナップショット デバッガーを無効にする方法は?

App service:
1. App Service の Azure portal を使用してスナップショット デバッガーを無効にします。
2. Azure portal >、アプリケーション サービスのリソース ブレード >*アプリケーションの設定*
3. Azure portal で次のアプリ設定を削除し、変更を保存します。
   - INSTRUMENTATIONENGINE_EXTENSION_VERSION
   - SNAPSHOTDEBUGGER_EXTENSION_VERSION

   > [!WARNING]
   > アプリケーション設定への変更では、アプリの再起動を開始します。 アプリケーション設定の詳細については、次を参照してください。 [、Azure portal で App Service アプリを構成する](/azure/app-service/web-sites-configure)します。

For AKS:
1. 更新に対応するセクションを削除する、Dockerfile、 [Docker イメージでの Visual Studio Snapshot Debugger](https://github.com/Microsoft/vssnapshotdebugger-docker)します。
2. リビルドして変更された Docker イメージを再デプロイします。

仮想マシン/仮想マシン スケール セット。

スナップショット デバッガーを無効にするいくつかの方法はあります。
- クラウド エクスプ ローラー >、仮想マシン/仮想マシン スケール セット リソース > 診断を無効にします。

- Azure portal >、仮想マシン/仮想マシン スケール セットのリソース ブレード > 拡張機能 > Microsoft.Insights.VMDiagnosticsSettings のアンインストールの拡張機能

- PowerShell コマンドレットから[Az PowerShell](https://docs.microsoft.com/powershell/azure/overview)

   仮想マシンの場合:

   ```powershell
      Remove-AzVMExtension -ResourceGroupName $rgName -VMName $vmName -Name Microsoft.Insights.VMDiagnosticsSettings
   ```

   仮想マシン スケールを設定します。

   ```powershell
      $vmss = Get-AzVmss -ResourceGroupName $rgName -VMScaleSetName $vmssName
      Remove-AzVmssExtension -VirtualMachineScaleSet $vmss -Name Microsoft.Insights.VMDiagnosticsSettings
   ```

## <a name="see-also"></a>関連項目

- [Visual Studio でのデバッグ](../debugger/index.md)
- [スナップショット デバッガーを使用して、ライブ ASP.NET アプリをデバッグします。](../debugger/debug-live-azure-applications.md)
- [スナップショット デバッガーを使用して、ライブの ASP.NET Azure の仮想 Machines\Virtual マシン スケール セットをデバッグします。](../debugger/debug-live-azure-virtual-machines.md)
- [スナップショット デバッガーを使用して、ライブの ASP.NET Azure Kubernetes デバッグします。](../debugger/debug-live-azure-kubernetes.md)
- [スナップショットのデバッグのトラブルシューティングと既知の問題](../debugger/debug-live-azure-apps-troubleshooting.md)
