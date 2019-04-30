---
title: '方法: ClickOnce 配置用の詳細ログ ファイルの指定 |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- logs, ClickOnce deployment
- ClickOnce deployment, logging
ms.assetid: 0807a28d-2e40-4a51-ab10-308d808ded6b
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 78fa278952004348e035a675a1e159b2164285b1
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63441607"
---
# <a name="how-to-specify-verbose-log-files-for-clickonce-deployments"></a>方法: ClickOnce 配置用の詳細ログ ファイルを指定する
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

[!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] すべてのデプロイ アクティビティのログ ファイルを保持します。 これらのログ記録に関連するインストール、初期化、更新、およびアンインストールの詳細、[!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)]展開します。 詳細を向上させるを[!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)]レジストリ エディターを使用して、これらのログ ファイルへの書き込み (**regedit.exe**) 詳細レベルを指定します。  
  
> [!CAUTION]
> レジストリ エディターを正しく使用する場合、オペレーティング システムを再インストールする必要があります深刻な問題が発生する可能性があります。 問題が発生する可能性のあることを十分に認識したうえで利用してください。  
  
 次の手順の詳細レベルを指定する方法を説明する[!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)]現在のユーザーのログ ファイル。 詳細出力レベルを減らすためには、このレジストリ値を削除します。  
  
### <a name="to-specify-verbose-log-files"></a>詳細なログ ファイルを指定するには  
  
1. 開いている**Regedit.exe**します。  
  
2. ノードに移動`HKEY_CURRENT_USER\Software\Classes\Software\Microsoft\Windows\CurrentVersion\Deployment`します。  
  
3. 必要に応じて、という名前の新しい文字列値を作成`LogVerbosityLevel`です。  
  
4. 設定、`LogVerbosityLevel`値を`1`します。  
  
## <a name="see-also"></a>関連項目  
 [ClickOnce 配置のトラブルシューティング](../deployment/troubleshooting-clickonce-deployments.md)
