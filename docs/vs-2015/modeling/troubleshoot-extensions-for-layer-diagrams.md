---
title: レイヤー図の拡張機能のトラブルシューティング |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: troubleshooting
helpviewer_keywords:
- layer diagrams, extension errors
- layer diagrams, troubleshooting extensions
ms.assetid: 1fda4f8a-38b8-482b-87b8-eade1a4e5662
caps.latest.revision: 27
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: ba45ba733f5447523b6793d4f5e2946c3507c82e
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "60098690"
---
# <a name="troubleshoot-extensions-for-layer-diagrams"></a>レイヤー図の拡張機能のトラブルシューティング
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

このトピックでは、レイヤー モデル拡張機能を作成するときに発生する可能性のある問題について説明します。  
  
#### <a name="when-i-press-f5-to-debug-my-extension-my-commands-gesture-handlers-validation-extensions-or-custom-properties-do-not-appear-on-layer-diagrams-in-the-experimental-instance-of-includevsprvsincludesvsprvs-mdmd"></a>F5 キーを押して拡張機能をデバッグするとき、コマンド、ジェスチャ ハンドラー、検証拡張機能、またはカスタム プロパティが、[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] の実験用インスタンスのレイヤー図に表示されない  
  
1. 実験用インスタンスで拡張機能ソリューションを開きます[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]、し、**ビルド** メニューのをクリックして**ソリューションのリビルド**します。  
  
2. キーを押して**F5**または**CTRL + F5**の実験用インスタンスを起動する[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]します。 レイヤー図を開き、拡張機能をテストします。  
  
   必要に応じて、次の手順に進みます。  
  
#### <a name="an-old-version-of-my-extension-runs"></a>拡張機能の古いバージョンが実行る  
  
1. [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] の実験用インスタンスが実行していないことを確認します。  
  
2. 次のフォルダーの削除: %LocalAppData%\Microsoft\VisualStudio\\[バージョン] \ComponentModelCache  
  
   > [!NOTE]
   >  %Localappdata% は通常*DriveName*: \Users\\*UserName*\AppData\Local です。  
  
   必要に応じて、次の手順に進みます。  
  
#### <a name="an-old-version-of-my-validation-results-appears-or-my-validation-method-is-not-called"></a>古いバージョンの検証結果が表示される、または検証メソッドが呼び出されない  
  
1. 実験用インスタンスで[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]の**ビルド** メニューのをクリックして**ソリューションのクリーン**します。 これにより、前に行った検証分析のキャッシュされている結果がクリアされます。  
  
2. モデルのレイヤーがコード要素と関連付けられていること、および少なくとも 1 つの依存関係リンクがモデルに存在することを確認します。 検証する項目がない場合、検証は呼び出されません。  
  
3. 検証メソッドは別のプロセスで実行するので、標準のブレークポイントは検証メソッドでは機能しない場合があります。 メソッドをステップ実行する場合は、`System.Diagnostics.Debugger.Launch()` の呼び出しを挿入する必要があります。  
  
4. **Source.extension.vsixmanifest** 、レイヤー検証プロジェクトの両方を追加したことを確認します、 **MEF コンポーネント**項目と**カスタム拡張機能の種類**] の [**コンテンツ**します。  
  
## <a name="see-also"></a>関連項目  
 [レイヤー図を拡張する](../modeling/extend-layer-diagrams.md)
