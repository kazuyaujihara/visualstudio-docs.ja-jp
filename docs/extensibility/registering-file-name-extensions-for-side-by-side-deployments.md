---
title: サイド バイ サイドで配置のファイル名拡張子を登録する |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- file extensions, registering for side-by-side
ms.assetid: 9ab046a2-147d-4167-aa14-7d661b1eaaa5
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 996f911f37b8226065feb4da311f736dd910550b
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/22/2019
ms.locfileid: "56709968"
---
# <a name="register-file-name-extensions-for-side-by-side-deployments"></a>サイド バイ サイドで配置のファイル名拡張子を登録します。
サイド バイ サイドで環境にデプロイされている Vspackage に、ファイルを関連付ける適切なバージョンのファイル名拡張子を登録する必要があります[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]します。 登録により、ユーザーが、プロジェクトを開き、プロジェクト項目ファイルの適切なバージョンをバージョン固有のファイル名拡張子を使用する場合を除き、[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]します。

## <a name="in-this-section"></a>このセクションの内容
- [ファイル名拡張子について](../extensibility/about-file-name-extensions.md)ファイル名拡張子を登録する方法について説明します。

- [ファイル名拡張子のファイル ハンドラーを指定](../extensibility/specifying-file-handlers-for-file-name-extensions.md)を開くことができるアプリケーション、編集、およびに、特定のファイル名拡張子を登録する方法について説明します。

- [ファイル名拡張子の動詞を登録](../extensibility/registering-verbs-for-file-name-extensions.md)動詞を登録する方法について説明します。

- [サイド バイ サイドでのファイルの関連付けを管理する](../extensibility/managing-side-by-side-file-associations.md)をサイド バイ サイドでインストールを処理する方法について説明します、特定のバージョンの[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]ファイルを呼び出す必要があります。

## <a name="related-sections"></a>関連項目
- [Visual Studio の複数のバージョンをサポートして](../extensibility/supporting-multiple-versions-of-visual-studio.md)の複数のバージョンに関連する問題について説明します[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]や VSPackage に開発およびエンドユーザーへのデプロイ中にします。