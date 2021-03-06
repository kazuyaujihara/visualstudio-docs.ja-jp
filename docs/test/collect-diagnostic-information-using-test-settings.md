---
title: Visual Studio でテスト設定を使用して診断情報を収集する
ms.date: 10/03/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, configuring run settings
ms.assetid: 0c86918b-cd63-4468-8f49-6d547a1276dc
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 0b2d44d0fa50a4d733f62845d54116cceb2f2016
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2018
ms.locfileid: "49865350"
---
# <a name="collect-diagnostic-information-using-test-settings"></a>テスト設定を使用して診断情報を収集する

テストを実行するときに、Visual Studio で*テストの設定*を使用して、追加のデータを収集できます。 たとえば、テストを実行しながら、ビデオ記録を作成する場合があります。 用意されている診断データ アダプターでは、次の作業を行うことができます。

-   各 UI 操作ステップをテキスト形式で収集する

-   再生用に各 UI 操作を記録する

-   システム情報を収集する

-   イベント ログ データを収集する

-   再現不可能なバグの特定に役立つ IntelliTrace データを収集する

また、診断データ アダプターを使用して、テスト コンピューターの動作を変更することもできます。 たとえば、Visual Studio のテストの設定により、さまざまなネットワーク トポロジのボトルネックをエミュレートして、チームのアプリケーションのパフォーマンスを評価できます。

## <a name="use-test-settings-with-visual-studio"></a>Visual Studio でテストの設定を使用する

Visual Studio を使用して単体テスト、コード化された UI テスト、Web パフォーマンス テスト、またはロード テストを実行するには、テストを実行するときに使用するテストの設定を構成および選択します。 リモートでテストを実行したり、データを収集したり、テスト コンピューターに影響を与えたりするには、テストの設定で使用するテスト コントローラーを指定する必要があります。 テスト コントローラーには、テストの設定の各ロールに使用できるエージェントが含まれます。

## <a name="diagnostic-data-adapter-details"></a>診断データ アダプターの詳細

次の表は、ローカル コンピューター ロールまたはリモート コンピューター ロールで使用できるように診断データ アダプターを構成するさまざまな方法の概要を示しています。

|テストの設定で使用される診断データ アダプター|ローカル コンピューター上の手動テスト|自動テスト|手動テスト: ロール セットと環境を使用したデータの収集|メモ|
|-|-|-|-|-|
|**IntelliTrace およびテストの影響用の ASP.NET クライアント プロキシ:** このプロキシを使用すると、IntelliTrace 診断データ アダプターとテスト影響診断データ アダプターでクライアントから Web サーバーへの http 呼び出しに関する情報を収集できます。|[はい]|[はい]|[はい]|-   これは、IntelliTrace またはテストの影響のいずれかの診断データ アダプターがクライアント ロールに選択されているときのみ使用してください。|
|**ASP.NET プロファイラー:** ASP.NET Web アプリケーションのパフォーマンス データを収集する、ASP.NET プロファイリングを含むテストの設定を作成できます。|×|○ (メモを参照)|×|-   この診断データ アダプターは、Visual Studio からロード テストを実行する場合にのみサポートされます。|
|**コード カバレッジ:** テストでカバーされるコードの範囲を調べるために使用するコード カバレッジ情報を含むテストの設定を作成できます。|×|○ (メモを参照)|×|-   コード カバレッジは、Visual Studio または *mstest.exe* から自動テストを実行するときにのみ、テストを実行するコンピューターからのみ使用できます。 リモートの収集はサポートされていません。<br />-   IntelliTrace 情報も収集するようにテストの設定を構成した場合、コード カバレッジ データの収集は実行されません。 **注:**  この診断データ アダプターは、Visual Studio のテスト設定のみに適用できます。 Microsoft Test Manager のテスト設定には使用されません。 また、このアダプターは、Visual Studio 2010 テスト プロジェクトとの互換性を目的としています。 **注:**  コード カバレッジは、自動テストが Microsoft Test Manager から実行されるか、レガシ MSTest ランナーを使用して Visual Studio からリモートの Test Agent で実行されるときに、互換性のために適用されます。|
|**イベント ログ:** イベント ログ収集を指定し、これをテスト結果に含めるようにテストの設定を構成できます。|[はい]|[はい]|[はい]||
|**IntelliTrace:**: *IntelliTrace* 用に診断データ アダプターを構成するときに、特定の診断トレース情報を収集するように構成すると、再現が難しいバグを分離できます。 これにより、この情報を含む IntelliTrace ファイルが作成されます。 IntelliTrace ファイルの拡張子は *.iTrace* です。 テストが失敗した場合は、バグを作成できます。 テスト結果と共に保存される IntelliTrace ファイルがこのバグに自動的にリンクされます。 IntelliTrace ファイルにデータが収集されることによって、コードのエラーを再現して診断するために必要な時間が短縮され、この結果、デバッグの生産性が向上します。 この IntelliTrace ファイルから、別のコンピューターでローカル セッションをシミュレートできます。 これにより、バグを再現できない危険性が減少します。|[はい]|[はい]|[はい]|-   IntelliTrace データの収集を有効にすると、コード カバレッジ データの収集は実行されません。<br />-   Web クライアント ロールに IntelliTrace を使用する場合は、[IntelliTrace およびテストの影響用の ASP.NET クライアント プロキシ] 診断データ アダプターを選択する必要もあります。<br />-   サポートされる IIS のバージョンは、IIS 7.0、IIS 7.5、および IIS 8.0 のみです。|
|**ネットワーク エミュレーション:** テストの設定を使用して、テストに対して人為的なネットワーク負荷をかけることを指定できます。 ネットワーク エミュレーションでは、ダイヤルアップなどの特定のネットワーク接続の速度をエミュレートすることにより、マシンに対する通信に影響を与えます。 |Ｘ|○ (メモを参照)|×|クライアント ロールまたはサーバー ロールに対してネットワーク エミュレーション診断データ アダプターを使用できます。 これらのロールは相互に通信を行うため、このアダプターを両方のロールに使用する必要はありません。 **注:**  この診断データ アダプターは、Visual Studio のテスト設定のみに適用できます。 Microsoft Test Manager のテスト設定には使用されません。 **注:**  ネットワーク接続の速度を向上させるためにネットワーク エミュレーションを使用することはできません。 **警告:**  ネットワーク エミュレーション診断データ アダプターをテストの設定に含め、それをローカル コンピューター上で使用する場合は、ネットワーク エミュレーション ドライバーをコンピューターのネットワーク アダプターのいずれかにバインドする必要もあります。 ネットワーク エミュレーション診断データ アダプターが正常に動作するためには、ネットワーク エミュレーション ドライバーが必要です。 ネットワーク エミュレーション ドライバーは、次の 2 つの方法でインストールされ、アダプターにバインドされます。 <ul><li>**Microsoft Visual Studio Test Agent と共にインストールされるネットワーク エミュレーション ドライバー:** Visual Studio Test Agent は、リモート コンピューターとローカル コンピューターの両方で使用できます。 Visual Studio Test Agent のインストール プロセスに、ネットワーク エミュレーション ドライバーをネットワーク カードにバインドする構成手順が含まれています。 詳細については、[テスト エージェントのインストールと構成](../test/lab-management/install-configure-test-agents.md)に関するページを参照してください。</li><li>**Microsoft Visual Studio Test Professional と共にインストールされるネットワーク エミュレーション ドライバー:** ネットワーク エミュレーションを初めて使用するときに、ネットワーク エミュレーション ドライバーをネットワーク カードにバインドするよう求められます。</li></ul> Visual Studio Test Agent をインストールせずに、ローカル コンピューターのコマンド ラインからネットワーク エミュレーション ドライバーをインストールすることもできます。この場合、**VSTestConfig NETWORKEMULATION /install** コマンドを使用します。**警告:**  ネットワーク エミュレーション アダプターは、ロード テストでは無視されます。 ロード テストでは、ロード テスト シナリオのネットワーク ミックスで指定された設定が使用されます。|
|**システム情報:** テストを実行するコンピューターのシステム情報を含めるようにテストの設定を構成できます。|[はい]|[はい]|[はい]||
|**テスト影響:** テスト ケースの実行時にアプリケーション コードのどのメソッドが使用されたかについての情報を収集できます。 これを、開発者が加えたアプリケーション コードの変更と合わせて使用することにより、このような開発上の変更によって影響を受けたテストを判別できます。|[はい]|[はい]|[はい]|-   Web クライアント ロールにテストの影響のデータを収集している場合は、[IntelliTrace およびテストの影響用の ASP.NET クライアント プロキシ] 診断データ アダプターを選択する必要もあります。<br />-   サポートされる IIS のバージョンは、IIS 7.0、IIS 7.5、および IIS 8.0 のみです。|
|**ビデオ レコーダー:** テストの実行時にデスクトップ セッションのビデオ記録を作成できます。 ビデオは、再現するのが困難なアプリケーション上の懸案事項をチーム メンバーが特定するのに役立ちます。|[はい]|○ (メモを参照)|[はい]|-   テスト エージェント ソフトウェアがサービスではなくプロセスとして実行されるようにした場合、自動テストの実行時にビデオ記録を作成できます。|