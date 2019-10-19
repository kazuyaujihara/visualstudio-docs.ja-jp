---
title: Entity Framework のツール
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 1b06b573-84aa-4458-b3f5-e238df47bf45
author: jillre
ms.author: jillfra
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: 53b87ce39f0eb5b1455f0a38b2aea7cc6b604342
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72648529"
---
# <a name="entity-framework-tools-in-visual-studio"></a>Visual Studio での Entity Framework Tools

Entity Framework は、.NET 開発者がドメイン固有のオブジェクトを使用してリレーショナルデータを操作できるようにするオブジェクトリレーショナルマッピングテクノロジです。 開発者が通常記述しなければならないデータアクセス コードの多くが不要になります。 Entity Framework は、新しい .NET アプリケーションに推奨されるオブジェクトリレーショナルマッピング (ORM) モデリングテクノロジです。

Entity Framework Tools は、Entity Framework (EF) アプリケーションの構築を支援するように設計されています。 Entity Framework の完全なドキュメントについては、 [「概要-EF 6」](/ef/ef6/)を参照してください。

  > [!NOTE]
  > このページで説明されている Entity Framework Tools は、EF Core ではサポートされていない *.edmx*ファイルを生成するために使用されます。 既存のデータベースから EF Core モデルを生成するには、「[リバースエンジニアリング-EF Core](/ef/core/managing-schemas/scaffolding)」を参照してください。 EF 6 と EF Core の相違点の詳細については、「 [ef 6 と EF Core の比較](/ef/efcore-and-ef6/)」を参照してください。

Entity Framework Tools を使用すると、既存のデータベースから*概念モデル*を作成し、その概念モデルをグラフィカルに視覚化して編集できます。 また、グラフィカルな概念モデルを作成し、そのモデルをサポートするデータベースを生成することもできます。 いずれの場合も、基になるデータベースの変更時には、モデルを自動的に更新できるだけではなく、アプリケーションのオブジェクトレイヤー コードも自動生成できます。 データベースの生成とオブジェクトレイヤー コードの生成はカスタマイズ可能です。

Entity Framework ツールは、Visual Studio インストーラーの**データストレージと処理**ワークロードの一部としてインストールされます。 また、 **sdk、ライブラリ、およびフレームワーク**のカテゴリの下に個々のコンポーネントとしてインストールすることもできます。

これらは、Visual Studio の Entity Framework ツールを構成する特定のツールです。

- @No__t_0 **[!INCLUDE[adonet_edm](../data-tools/includes/adonet_edm_md.md)] デザイナー** (**Entity Designer**) を使用して、エンティティ、アソシエーション、マッピング、および継承関係を視覚的に作成および変更できます。 また、 **Entity Designer**は、オブジェクトレイヤーコード [!INCLUDE[TLA#tla_cshrp](../data-tools/includes/tlasharptla_cshrp_md.md)] または [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 生成します。

- **@No__t_1 ウィザード**を使用して、既存のデータベースから概念モデルを生成し、データベース接続情報をアプリケーションに追加できます。

- **データベースの作成ウィザード**を使用すると、最初に概念モデルを作成し、そのモデルをサポートするデータベースを作成できます。

- 基になるデータベースに変更が加えられた場合は、**モデルの更新ウィザード**を使用して、概念モデル、ストレージモデル、およびマッピングを更新できます。

  > [!NOTE]
  > Visual Studio 2010 以降では、Entity Framework ツールは [!INCLUDE[ss2k](../data-tools/includes/ss2k_md.md)] をサポートしていません。

これらのツールは *.edmx*ファイルを生成または変更します。 この *.edmx*ファイルには、概念モデル、ストレージモデル、およびそれらの間のマッピングについて説明する情報が含まれています。 詳細については、「 [EDMX](https://docs.microsoft.com/ef/ef6/)」を参照してください。

[Entity Framework パワーツール](https://marketplace.visualstudio.com/items?itemName=EntityFrameworkTeam.EntityFrameworkPowerToolsBeta4)は、Entity Data Model を使用するアプリケーションを構築するのに役立ちます。 パワーツールは、概念モデルの生成、既存のモデルの検証、概念モデルに基づくオブジェクトクラスを含むソースコードファイルの生成、およびモデルによって生成されるビューを含むソースコードファイルの生成を行うことができます。 詳細については、「[事前に生成されたマッピングビュー](https://docs.microsoft.com/ef/ef6/fundamentals/performance/pre-generated-views)」を参照してください。

## <a name="related-topics"></a>関連トピック

| Title | 説明 |
| - | - |
| [ADO.NET Entity Framework](/dotnet/framework/data/adonet/ef/index) | アプリケーションを作成するために [!INCLUDE[adonet_ef](../data-tools/includes/adonet_ef_md.md)] 提供する [!INCLUDE[adonet_edm](../data-tools/includes/adonet_edm_md.md)] ツールを使用する方法について説明します。 |
| [Entity Data Model](/dotnet/framework/data/adonet/entity-data-model) | @No__t_0 上に構築されたアプリケーションで使用されるデータを操作するためのリンクと情報を提供します。 |
| [Entity Framework (EF) のドキュメント)](https://docs.microsoft.com/ef/ef6/get-started) | Entity Framework を最大限に活用するのに役立つビデオ、チュートリアル、および高度なドキュメントのインデックスを提供します。 |
| [ASP.NET 5 アプリケーションを新しいデータベースに](https://docs.efproject.net/en/latest/platforms/aspnetcore/new-db.html) | Entity Framework 7 を使用して新しい ASP.NET 5 アプリケーションを作成する方法について説明します。 |

## <a name="see-also"></a>関連項目

- [.NET 用の Visual Studio データ ツール](../data-tools/visual-studio-data-tools-for-dotnet.md)