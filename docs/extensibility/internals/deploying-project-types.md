---
title: プロジェクトの種類の展開 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- projects [Visual Studio SDK], managed-code
- projects [Visual Studio SDK], aggregator
ms.assetid: 7f132f67-8589-464c-90dc-0d57ae02aa8f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 958628194e4ea768de5a47dc66476345bff6c4f3
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56625336"
---
# <a name="deploy-project-types"></a>プロジェクトの種類をデプロイします。
[!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] 新しいプロジェクトの種類のアグリゲーターをインストール (*ProjectAggregator2.dll*) と再頒布用の Windows インストーラー パッケージも (*ProjectAggregator2.msi*)。 マネージ コード プロジェクトの種類の新しいアグリゲーターを使用する必要があります。 ProjectAggregator2 の機能の制限を回避、[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]マネージ コード プロジェクトの種類が正しく動作するを防ぎますアグリゲーターのプロジェクトします。 次の手順では、新しいアグリゲーターを使用するように VSPackage を変更する方法について説明します。

1.  NativeHierarchyWrapper プロジェクトをソリューションから削除します。

2.  セットアップから NativeHierarchyWrapper バイナリを削除します。

3.  追加*ProjectAggregator2.msi*のセットアップにします。