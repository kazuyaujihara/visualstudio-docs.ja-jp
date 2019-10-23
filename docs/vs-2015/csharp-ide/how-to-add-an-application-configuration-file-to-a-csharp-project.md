---
title: '方法: アプリケーション構成ファイルをC#プロジェクトに追加する |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
dev_langs:
- CSharp
helpviewer_keywords:
- app.config files, adding to C# projects
ms.assetid: 9caf6bb0-c2fc-4ab6-ba69-bed3b880fbf8
caps.latest.revision: 20
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: f8417b5520dc9587fa3231a3bc459335d2a9896d
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72667528"
---
# <a name="how-to-add-an-application-configuration-file-to-a-c-project"></a>方法: C# プロジェクトにアプリケーション構成ファイルを追加する
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

アプリケーション構成ファイル (app.config ファイル) を C# プロジェクトに追加すると、共通言語ランタイムがアセンブリ ファイルを検索し読み込む方法をカスタマイズできます。 アプリケーション構成ファイルの詳細については、「[ランタイムがアセンブリを検索する方法](https://msdn.microsoft.com/library/772ac6f4-64d2-4cfb-92fd-58096dcd6c34)」を参照してください。

> [!NOTE]
> Windows ストアでは <xref:System.Configuration> がサポートされていません。 その結果、ストアアプリには app.config テンプレートが含まれていません。

 プロジェクトをビルドすると、開発環境によって app.config ファイルが自動的にコピーされ、実行可能ファイルと一致するようにコピーのファイル名が変更されます。その後、コピーを bin ディレクトリに移動します。

### <a name="to-add-an-application-configuration-file-to-your-c-project"></a>アプリケーション構成ファイルをC#プロジェクトに追加するには

1. メニューバーで、 **[プロジェクト]** 、 **[新しい項目の追加]** の順に選択します。

     **[新しい項目の追加]** ダイアログ ボックスが表示されます。

2. **[インストール済み]** 、 **[ビジュアルC#項目]** の順に展開し、 **[アプリケーション構成ファイル]** テンプレートを選択します。

3. **[名前]** ボックスに名前を入力し、 **[追加]** ボタンをクリックします。

     App.config という名前のファイルがプロジェクトに追加されます。

## <a name="see-also"></a>参照
 [アプリケーション設定の管理 (.net)](../ide/managing-application-settings-dotnet.md) [構成ファイルスキーマ](https://msdn.microsoft.com/library/69003d39-dc8a-460c-a6be-e6d93e690b38)[アプリ](https://msdn.microsoft.com/library/86bd26d3-737e-4484-9782-19b17f34cd1f)[のC#構成方法: Visual Studio 開発環境を使用して](../csharp-ide/using-the-visual-studio-development-environment-for-csharp.md) [.NET Framework バージョンを対象とするようにアプリを構成](https://msdn.microsoft.com/5247b307-89ca-417b-8dd0-e8f9bd2f4717)する