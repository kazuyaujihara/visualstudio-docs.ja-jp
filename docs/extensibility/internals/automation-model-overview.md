---
title: オートメーションモデルの概要 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- automation [Visual Studio SDK], about automation
- extensibility
ms.assetid: 12b6d6db-0d22-4aaa-aa7d-1365f759b7b0
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 6ea38dc79bd557f17bbae8276dd112304c9a40fa
ms.sourcegitcommit: 40bd5b27f247a07c2e2514acb293b23d6ce03c29
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2019
ms.locfileid: "73186735"
---
# <a name="automation-model-overview"></a>オートメーションモデルの概要
オートメーションモデルは、Visual Studio アドインまたは拡張機能を記述できるオブジェクトのセットで構成されます。 アドインは、Visual Studio 環境を操作したり、一般的なタスクを自動化したりできるアプリケーションです。 Visual Studio 拡張機能では、Visual Studio のカスタムコンポーネントを作成したり、テキストエディターなどの標準コンポーネントの機能を追加したりできます。

## <a name="objects-in-the-automation-model"></a>オートメーションモデル内のオブジェクト
 オートメーションモデルは、共通環境の主要なファセットを制御するオブジェクトの関連グループで構成されます。 次の図は、オートメーションモデルを構成する Visual Studio オブジェクトの広範なセットを示しています。

 ![Visual Studio オートメーションオブジェクトグラフ](../../extensibility/internals/media/vsvisualstudioautomationobjectchart.gif "vsVisualStudioAutomationObjectChart")

 詳細については、「 [Visual Studio 環境の拡張](https://msdn.microsoft.com/Library/4173a963-7ac7-4966-9bb7-e28a9d9f6792)」を参照してください。

 環境によって、さまざまな機能領域のモデルが提供されます。 たとえば、コードで見つかる可能性のあるさまざまな要素のコードモデルがあります。 さまざまなドキュメント要素のドキュメントモデルがあります。 プロジェクト領域の1つの領域は、VSPackage プロバイダーにとって特に重要です。 多くの場合、新しいプロジェクトの種類は、[!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] と同様の方法でオートメーションモデルに寄与し、[!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] オートメーションモデルに寄与します。 このプロセスについては、「 [vspackage の自動化を提供](../../extensibility/internals/providing-automation-for-vspackages.md)する」で説明しています。

 環境のオートメーションモデルの拡張を検討できる場所は次のとおりです。

- [プロジェクト]

- ドキュメント

- コード

- Build

オートメーションの詳細については、「 [Visual Studio のオートメーションと拡張機能](/visualstudio/extensibility/extensibility-in-visual-studio?view=vs-2015)」を参照してください。 このドキュメントとそのドキュメントには、VSPackage の自動化を提供する方法についての意思決定に役立つリンクが記載されています。

## <a name="see-also"></a>関連項目
- [方法: アドインを作成する](https://msdn.microsoft.com/Library/50be56d2-e3a5-4cd2-8569-2a0666b268ce)