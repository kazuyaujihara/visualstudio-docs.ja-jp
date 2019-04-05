---
title: 提供されるサービス (ソース管理 VSPackage) |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- services, source control packages
- source control packages, services
ms.assetid: 9db07d70-87d2-4401-bc88-e3a49d81e9a2
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 4f9a4a873f2b6b3f41bd86d046bc187c17f063f1
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56601154"
---
# <a name="services-provided-source-control-vspackage"></a>提供されるサービス (ソース管理 VSPackage)
サービスは、Vspackage 間および Visual Studio 統合開発環境 (IDE) と、インストールされている Vspackage 間に共有する機能により、主要なメカニズムです。 サービスと、Visual Studio IDE で、重要度の詳細については、[を使用すると、サービスを提供する](../../extensibility/using-and-providing-services.md)を参照してください。

## <a name="the-source-control-service"></a>ソース管理サービス
 Visual Studio では、サービス、IDE レベルのサービスおよびパッケージ レベルのサービスの 2 つのレイヤーを提供します。 Visual Studio IDE は、ネイティブ IDE レベルのサービスを提供します。 ソース管理パッケージは、これらのサービスの一部を消費します。 VSPackage としてソース管理パッケージでは、独自の秘密のソース管理サービスを提供することで、ソース管理機能を共有します。 ソース管理パッケージは、Visual Studio IDE で使用できるコントラクトの形式でによって実装されるソース コントロールに関連するインターフェイスのセットをカプセル化します。

## <a name="see-also"></a>関連項目
- [デザイン要素](../../extensibility/internals/source-control-vspackage-design-elements.md)