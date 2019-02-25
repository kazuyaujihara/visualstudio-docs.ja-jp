---
title: Vspackage の登録 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- managed VSPackages, registering
- registration, managed VSPackages
ms.assetid: 79b9424e-7e9b-4fc8-9b9f-00212674573c
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 426adc0cd150d5867760a8570df5777fec8260a2
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2019
ms.locfileid: "56601578"
---
# <a name="registering-vspackages"></a>VSPackage の登録
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] .pkgdef ファイルを記述し、VSPackage の検索に依存します。 .Pkgdef ファイルには、それ以外の場合は、システム レジストリに追加するすべての登録情報が含まれています。 マネージ Vspackage が、ソース コードに属性を追加して実行し、登録されている、 [CreatePkgDef ユーティリティ](../../extensibility/internals/createpkgdef-utility.md).pkgdef ファイルを生成する結果として得られるアセンブリ。

## <a name="in-this-section"></a>このセクションの内容
- [VSPackage ファイルの場所を VS Shell に指定する](../../extensibility/internals/specifying-vspackage-file-location-to-the-vs-shell.md)

 Vspackage、読み込みパスをについて説明します。

- [VSPackage の登録と登録解除](../../extensibility/registering-and-unregistering-vspackages.md)

 VSPackage を登録する方法について説明します。
