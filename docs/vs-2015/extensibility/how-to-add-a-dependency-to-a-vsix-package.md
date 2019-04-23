---
title: '方法: VSIX パッケージへの依存関係の追加 |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- package reference
- package assembly
- package dll
- vsix reference
ms.assetid: 8f20177b-dab9-43a3-b959-81a591b451d6
caps.latest.revision: 13
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: cbd9426b7a9190872a2b04246d7f051b480a188d
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "60066885"
---
# <a name="how-to-add-a-dependency-to-a-vsix-package"></a>方法: VSIX パッケージへの依存関係の追加
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

ターゲット コンピューターに含まれていないすべての依存関係をインストールする VSIX パッケージの配置を設定することができます。 これを実現するには、source.extension.vsixmanifest ファイルを VSIX の依存関係を含めます。  
  
#### <a name="to-add-a-dependency"></a>依存関係を追加するには  
  
1. Source.extension.vsixmanifest ファイルを開き、**デザイン**ビュー。 移動して、**依存関係** タブでをクリックし、**新規**します。  
  
2. インストールされている拡張機能を追加する: で、**新しい依存関係の追加**ダイアログ ボックスで、**拡張機能がインストールされている**し、**名前**リストの拡張機能を選択します。  
  
3. インストールされていない別の VSIX を追加する:: で、**新しい依存関係の追加**ダイアログ ボックスで、**ファイル システム上のファイル**しを使用して、**参照**VSIX を選択するボタンをクリックします。  
  
## <a name="see-also"></a>関連項目  
 [VSIX 拡張機能スキーマ 1.0 リファレンス](http://msdn.microsoft.com/76e410ec-b1fb-4652-ac98-4a4c52e09a2b)   
 [VSIX パッケージの構造](../extensibility/anatomy-of-a-vsix-package.md)   
 [Windows インストーラーの配置に関する拡張機能を準備する](../extensibility/preparing-extensions-for-windows-installer-deployment.md)
