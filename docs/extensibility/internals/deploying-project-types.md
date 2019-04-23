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
ms.openlocfilehash: 1e89f74d940182cd92fd15f726676f0979d21186
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "60047216"
---
# <a name="deploy-project-types"></a>プロジェクトの種類をデプロイします。
[!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] 新しいプロジェクトの種類のアグリゲーターをインストール (*ProjectAggregator2.dll*) と再頒布用の Windows インストーラー パッケージも (*ProjectAggregator2.msi*)。 マネージ コード プロジェクトの種類の新しいアグリゲーターを使用する必要があります。 ProjectAggregator2 の機能の制限を回避、[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]マネージ コード プロジェクトの種類が正しく動作するを防ぎますアグリゲーターのプロジェクトします。 次の手順では、新しいアグリゲーターを使用するように VSPackage を変更する方法について説明します。

1. NativeHierarchyWrapper プロジェクトをソリューションから削除します。

2. セットアップから NativeHierarchyWrapper バイナリを削除します。

3. 追加*ProjectAggregator2.msi*のセットアップにします。