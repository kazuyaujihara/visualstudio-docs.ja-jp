---
title: Azure Cloud Services のデバッグのオプション | Microsoft Docs
description: Azure Cloud Services のデバッグ
services: visual-studio-online
documentationcenter: n/a
author: mikejo
manager: douge
editor: ''
ms.assetid: 80755da7-8350-4f5c-97ce-2962beabb36d
ms.service: visual-studio-online
ms.devlang: multiple
ms.topic: article
ms.tgt_pltfrm: multiple
ms.workload: na
origin.date: 03/18/2017
ms.date: 05/11/2018
ms.author: v-junlch
ms.openlocfilehash: 3b489b97551e5b5522cb58868b34dee4d9e5fb7b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62963651"
---
# <a name="learn-the-various-ways-to-debug-an-azure-cloud-service"></a>Azure クラウド サービスをデバッグするためのさまざまな方法を理解する
この記事では、Azure クラウド サービスをデバッグするさまざまな方法へのリンクを提供します。 

## <a name="debugging-an-azure-cloud-service-in-visual-studio"></a>Visual Studio で Azure クラウド サービスをデバッグする
Azure コンピューティング エミュレーターを使用してローカル コンピューターでクラウド サービスをデバッグすれば、時間とコストの節約になります。 サービスをデプロイする前にローカルでデバッグすると、コンピューティング時間の料金を支払うことなく、信頼性とパフォーマンスを改善できます。 ただし、一部には Azure でクラウド サービスを実行した場合にのみ発生するエラーもあります。 Azure でクラウド サービスを実行するときにのみ発生するエラーは、サービスの発行時にリモート デバッグを有効にしてから、ロール インスタンスにデバッガーをアタッチすることでデバッグできます。 詳細については、「 [ローカル コンピューターでクラウド サービスをデバッグする](vs-azure-tools-debug-cloud-services-virtual-machines.md#debug-your-cloud-service-on-your-local-computer)」を参照してください。

## <a name="using-intellitrace"></a>IntelliTrace の使用 
Visual Studio Enterprise を使用して .NET Framework 4.5 を対象とするロールを作成する場合は、Visual Studio から Azure クラウド サービスをデプロイする時点で IntelliTrace を有効にすることができます。 IntelliTrace が提供するログを使用すると、Azure で実行しているかのようにアプリケーションを Visual Studio でデバッグすることができます。 詳細については、「 [IntelliTrace および Visual Studio を使用した発行済みのクラウド サービスのデバッグ](http://go.microsoft.com/fwlink/p/?LinkId=623016)」を参照してください。

## <a name="remote-debugging"></a>リモート デバッグ 
Visual Studio からクラウド サービスをデプロイするときに、そのリモート デバッグを有効にできます。 デプロイメントのリモート デバッグを有効にすると、各ロール インスタンスを実行する仮想マシンにリモート デバッグ サービスがインストールされます。 `msvsmon.exe` をはじめとするこれらのサービスは、パフォーマンスに影響せず、追加コストも発生しません。 詳細については、「 [Azure でクラウド サービスをデバッグする](vs-azure-tools-debug-cloud-services-virtual-machines.md#debug-a-cloud-service-in-azure)」を参照してください。

## <a name="next-steps"></a>次の手順
- [Visual Studio での Azure クラウド サービスまたは仮想マシンのデバッグ](./vs-azure-tools-debug-cloud-services-virtual-machines.md) - Azure クラウド サービスをデバッグする方法の詳細を説明します。

<!-- Update_Description: update metedata properties -->