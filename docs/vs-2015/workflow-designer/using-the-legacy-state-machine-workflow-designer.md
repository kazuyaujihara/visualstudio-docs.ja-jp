---
title: 従来のステートマシンワークフローデザイナーを使用する |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
helpviewer_keywords:
- StateFinalizationActivity activity
- StateActivity activity
- SetStateActivity activity
- EventDrivenActivity activity
- state machine workflow designer
- state machine workflows, designer
- state machine workflows, activities
- StateInitializationActivity activity
ms.assetid: 2cd21123-35c2-4eaf-82f6-86fce7a8f04d
caps.latest.revision: 5
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 8c2b1ce1f1b2c6a16b5576880904feadf37a3e7b
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72606773"
---
# <a name="using-the-legacy-state-machine-workflow-designer"></a>従来のステート マシン ワークフロー デザイナーの使用
@No__t_1 または [!INCLUDE[vstecwinfx](../includes/vstecwinfx-md.md)] のいずれかを対象とする [!INCLUDE[vs2010](../includes/vs2010-md.md)] で新しいステートマシンワークフロープロジェクトを作成する場合は、**ステートマシンワークフローコンソールアプリケーション**または**ステートマシンワークフローライブラリ**(レガシ) のいずれかを使用できます。プロジェクトテンプレート。 これらのいずれかのステート マシン プロジェクト テンプレートを選択した場合、ステート マシン デザイナーが従来のワークフロー デザイナーのユーザー インターフェイスとして表示されます。 従来のステートマシンプロジェクトテンプレートの詳細については、「[方法: ステートマシンワークフローコンソールアプリケーションを作成する (レガシ)](../workflow-designer/how-to-create-state-machine-workflow-console-applications-legacy.md) 」および「[方法: ステートマシンワークフローライブラリを作成する (レガシ)](../workflow-designer/how-to-create-a-state-machine-workflow-library-legacy.md)」を参照してください。

 ステート マシン ワークフローは、ステート (状態) のセットで構成されます。 1 つのステートが初期状態として設定されます。 各ステートは特定のイベント セットを受信できます。 イベントに基づいて、別のステートへの移行を実行できます。 ステート マシン ワークフローには最終ステートを定義できます。 最終ステートに移行すると、ワークフローは完了します。

## <a name="state-machine-designer-views"></a>ステート マシン デザイナーのビュー
 ステート マシン デザイナーは自由度の高いデザイナーです。デザイン サーフェイス上でアクティビティを自由に移動することができます。 ステートマシンデザイナーには、*状態*ビューと*イベントドリブン*ビューの2つのビューがあります。

 ステート ビューには、ステート アクティビティ、およびステート アクティビティ内に格納されているイベントドリブン アクティビティが表示されます。 このビューでは、1 つのステートから別のステートへの移行が、1 つのステート内のイベントドリブン アクティビティから別のステートに伸びる線として表されます。 また、独自の線を描くことにより、移行を作成することもできます。 移行を描くには、イベントドリブン アクティビティを選択し、アクティビティ上のいずれかのハンドルを選択して、それをドラッグします。 この操作によって、線が描画されます。 次に、この線が移行先のステートに接続されて、2 つのステート間の移行を表します。

 イベントドリブン ビューにアクセスするには、いずれかのイベントドリブン アクティビティをダブルクリックします。 シーケンシャル ワークフロー デザイナーに似たデザイナーが表示されます。 デザイナー上部のナビゲーション バーには、表示されるイベントドリブン アクティビティまでのアクティビティ階層が示されます。 表示されている階層内のいずれかの要素をクリックすると、元のステート ビューに移動できます。 ステート ビューで 1 つのステートから別のステートへの移行を描画した後、そのアクティビティのイベントドリブン ビューを表示する場合は、設定済みのステート アクティビティがイベントドリブン アクティビティに自動的に追加されます。 設定済みのステート アクティビティのプロパティを変更すると、その変更が元のステート ビューに反映されます。

## <a name="state-machine-workflow-activities"></a>ステート マシン ワークフローのアクティビティ
 ステート マシン ワークフロー デザイナーで使用される主なアクティビティを次の表で説明します。

|ツールボックス名|アクティビティ|説明|
|------------------|--------------|-----------------|
|**状態**|[StateActivity](http://go.microsoft.com/fwlink?LinkID=65042)|ステートマシンの状態を表します。追加の**Stateactivity**アクティビティを含めることができます。 詳細については、「 [Stateactivity アクティビティの使用](http://go.microsoft.com/fwlink?LinkID=65083)」を参照してください。|
|**SetState**|[SetStateActivity](http://go.microsoft.com/fwlink?LinkID=65041)|新しいステート (状態) への移行を指定します。 詳細については、「 [SetStateActivity アクティビティの使用](http://go.microsoft.com/fwlink?LinkID=65082)」を参照してください。|
|**StateInitialization**|[StateInitializationActivity](http://go.microsoft.com/fwlink?LinkID=65044)|あるステートに移行する (他のアクティビティも同時に指定可) と実行されます。 詳細については、「 [StateInitialization アクティビティの使用](http://go.microsoft.com/fwlink?LinkID=65006)」を参照してください。|
|**StateFinalization**|[StateFinalizationActivity](http://go.microsoft.com/fwlink?LinkID=65043)|[Stateactivity](http://go.microsoft.com/fwlink?LinkID=65042)アクティビティを終了するときに、含まれているアクティビティを実行します。 詳細については、「 [StateFinalizationActivity アクティビティの使用](http://go.microsoft.com/fwlink?LinkID=65008)」を参照してください。|
|**EventDriven**|[EventDrivenActivity](http://go.microsoft.com/fwlink?LinkID=65029)|外部イベントによって実行開始されるステートに使用されます。 **EventDrivenActivity**アクティビティは、 [ieventactivity](http://go.microsoft.com/fwlink?LinkID=65032)インターフェイスを実装するアクティビティを、最初の子アクティビティとして持つ必要があります。 詳細については、「 [EventDrivenActivity アクティビティの使用](http://go.microsoft.com/fwlink?LinkID=65068)」を参照してください。|

 ステートマシンワークフローの主要なコンポーネントは、 [stateactivity](http://go.microsoft.com/fwlink?LinkID=65042)アクティビティです。 ステート マシン ワークフロー内のさまざまなポイントでイベントがキャプチャされると、イベントに関連したタスクを処理するさまざまなステートに移行します。 有効期間中、ワークフローはいくつかの異なるステート間を遷移します。 これらの状態は、 [Setstateactivity](http://go.microsoft.com/fwlink?LinkID=65041)アクティビティを使用して相互に接続します。

 新しい**Stateactivity**をワークフローデザインサーフェイスにドラッグすると、 [EventDrivenActivity](http://go.microsoft.com/fwlink?LinkID=65029)、 [StateInitializationActivity](http://go.microsoft.com/fwlink?LinkID=65044)、 [statefinalizationactivity](http://go.microsoft.com/fwlink?LinkID=65043)、またはその他の**stateactivity**アクティビティを追加できます。子アクティビティ。

> [!CAUTION]
> ステートマシンワークフローデザイナーを使用してワークフローを作成する場合は、 **[ドキュメントアウトライン]** ビューウィンドウでデザイン中のワークフローの構造を監視する必要があります。 **[ドキュメントアウトライン]** ビューウィンドウのステートマシンワークフローの構造のビューには、ワークフローマークアップファイル内のアクティビティの論理的なレイアウトが反映されます。 デザイン サーフェイスに表示されるワークフロー アクティビティの物理的レイアウトは、ワークフロー マークアップ ファイル内のアクティビティの論理的レイアウトを表さない可能性があります。
>
> **[ドキュメントアウトライン]** ウィンドウを開くには、 **[表示]** メニューの **[その他のウィンドウ]** をポイントし、 **[ドキュメントアウトライン]** を選択します。

## <a name="see-also"></a>参照
 [方法: ステートマシンワークフローコンソールアプリケーションを作成する (レガシ)](../workflow-designer/how-to-create-state-machine-workflow-console-applications-legacy.md) [方法: ステートマシンワークフローライブラリ (レガシ)](../workflow-designer/how-to-create-a-state-machine-workflow-library-legacy.md) [ステートマシン](http://go.microsoft.com/fwlink?LinkID=65016)ワークフローを使用して[stateactivity アクティビティを](http://go.microsoft.com/fwlink?LinkID=65083)作成する[StateInitializationActivity](http://go.microsoft.com/fwlink?LinkID=65006)アクティビティを使用した[StateFinalizationActivity アクティビティ](http://go.microsoft.com/fwlink?LinkID=65008)の使用[EventDrivenActivity アクティビティ](http://go.microsoft.com/fwlink?LinkID=65068)を使用した[setstateactivity](http://go.microsoft.com/fwlink?LinkID=65082)アクティビティの使用