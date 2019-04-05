---
title: プロジェクトの種類の展開 |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- projects [Visual Studio SDK], managed-code
- projects [Visual Studio SDK], aggregator
ms.assetid: 7f132f67-8589-464c-90dc-0d57ae02aa8f
caps.latest.revision: 13
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 6f168656950c65ce133a8e808a0fa1232726e1b5
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2019
ms.locfileid: "58963704"
---
# <a name="deploying-project-types"></a>プロジェクト タイプの配置
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

[!INCLUDE[vsipsdk](../../includes/vsipsdk-md.md)] 新しいプロジェクトの種類アグリゲーター (ProjectAggregator2.dll) とも再配布 (ProjectAggregator2.msi) 用の Windows インストーラー パッケージをインストールします。 マネージ コード プロジェクトの種類の新しいアグリゲーターを使用する必要があります。 ProjectAggregator2 で策の制限の動作、[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]マネージ コード プロジェクトの種類が正しく動作するを防ぐアグリゲーターのプロジェクトします。 次の手順では、新しいアグリゲーターを使用するように VSPackage を変更する方法について説明します。  
  
1.  NativeHierarchyWrapper プロジェクトをソリューションから削除します。  
  
2.  セットアップから NativeHierarchyWrapper バイナリを削除します。  
  
3.  セットアップに ProjectAggregator2.msi を追加します。
