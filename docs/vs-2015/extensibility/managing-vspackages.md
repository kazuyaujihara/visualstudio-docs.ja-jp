---
title: Vspackage の管理 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- VSPackages, autoloading
- VSPackages, delayed loading
- delay loading
- VSPackages, loading
ms.assetid: 386e0ce5-4107-4164-b0cd-1cf43eb5e7cf
caps.latest.revision: 36
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 0b56ab490342cfbda9c16408aa0937abd80728c9
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "68194380"
---
# <a name="managing-vspackages"></a>VSPackage の管理
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

ほとんどの場合は、プロジェクトと項目テンプレートの登録し、パッケージを自動的に読み込むため、Vspackage の管理について心配する必要はありません。 ただし、状況によっては、パッケージを管理するためにさらに詳しくを学習する必要があります。  
  
## <a name="using-the-experimental-instance"></a>実験用インスタンスを使用します。  
 実験用インスタンスの詳細についてを参照してください。 [、実験用インスタンス](../extensibility/the-experimental-instance.md)します。  
  
## <a name="registering-and-unregistering-vspackages"></a>VSPackage の登録と登録解除  
 登録し、Vspackage とその他の種類の拡張機能の登録を解除する方法については、次を参照してください。[の登録および登録を解除する Vspackage](../extensibility/registering-and-unregistering-vspackages.md)します。  
  
## <a name="loading-a-vspackage"></a>VSPackage の読み込み  
 Vspackage は、autoload 特定 CMDUICONTEXT GUID の電源がオンに設定できます。 詳細については、次を参照してください。 [Vspackage の読み込み](../extensibility/loading-vspackages.md)します。  
  
## <a name="using-asyncpackage-to-load-vspackages-in-the-background"></a>AsyncPackage を使用して、バック グラウンドで Vspackage をロードするには  
 AsyncPackage クラスは、Visual Studio での UI の応答性の向上のバック グラウンド スレッドで読み込むパッケージを使用できます。 詳細については、「[方法 :AsyncPackage を使用して、バック グラウンドで Vspackage を読み込む](../extensibility/how-to-use-asyncpackage-to-load-vspackages-in-the-background.md)します。  
  
## <a name="rule-based-ui-context-for-extensions"></a>拡張機能のルール ベースの UI コンテキスト  
 ルール ベースの UI コンテキストを使用する UI コンテキストがアクティブになるし、関連付けられている Vspackage が読み込まれる正確な条件を定義する拡張機能の作成者。 詳細については、「[方法 :Visual Studio 拡張機能のルール ベースの UI コンテキストを使用して](../extensibility/how-to-use-rule-based-ui-context-for-visual-studio-extensions.md)します。  
  
## <a name="troubleshooting-vspackages"></a>VSPackage のトラブルシューティング  
 読み込まれないか、エラーが発生する Vspackage のトラブルシューティングの手法を確認します。[VSPackage のトラブルシューティング](../extensibility/troubleshooting-vspackages.md)  
  
## <a name="see-also"></a>関連項目  
 [VSPackage](../extensibility/internals/vspackages.md)
