---
title: エディターでの Managed Extensibility Framework |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], new - using MEF for extensions
ms.assetid: 3f59a285-6c33-4ae3-a4fb-ec1f5aa21bd1
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: f376a43b6d59ba494db2ad4e5ef26b260d91f6ad
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "72632604"
---
# <a name="managed-extensibility-framework-in-the-editor"></a>エディターでの Managed Extensibility Framework
エディターは、Managed Extensibility Framework (MEF) コンポーネントを使用して作成されます。 独自の MEF コンポーネントをビルドしてエディターを拡張することができます。また、コードでエディターコンポーネントを使用することもできます。

## <a name="overview-of-the-managed-extensibility-framework"></a>Managed Extensibility Framework の概要
 MEF は、MEF プログラミングモデルに準拠するアプリケーションまたはコンポーネントの機能を追加および変更できる .NET ライブラリです。 Visual Studio エディターでは、MEF コンポーネントパーツを提供および使用することができます。

 MEF は、.NET Framework version 4 *system.componentmodel*アセンブリに含まれています。

 MEF の詳細については、「 [Managed Extensibility Framework (mef)](/dotnet/framework/mef/index)」を参照してください。

### <a name="component-parts-and-composition-containers"></a>コンポーネントパーツと合成コンテナー
 コンポーネントパーツは、次のいずれかまたは両方の操作を実行できるクラスまたはクラスのメンバーです。

- 別のコンポーネントを使用する

- 別のコンポーネントによって使用される

  たとえば、倉庫の在庫コンポーネントによって提供される製品の可用性データに依存する注文エントリコンポーネントを持つショッピングアプリケーションを考えてみます。 MEF 用語では、在庫部分は製品の可用性データを*エクスポート*でき、注文エントリパーツはデータを*インポート*できます。 注文エントリパーツと在庫部分は、互いについて知る必要はありません。(ホストアプリケーションによって提供される)*合成コンテナー*は、エクスポートのセットを維持し、エクスポートとインポートを解決します。

  合成コンテナー (<xref:System.ComponentModel.Composition.Hosting.CompositionContainer>) は、通常、ホストによって所有されます。 合成コンテナーは、エクスポートされたコンポーネントパーツの*カタログ*を保持します。

### <a name="export-and-import-component-parts"></a>コンポーネントパーツのエクスポートとインポート
 パブリッククラスまたはクラスのパブリックメンバー (プロパティまたはメソッド) として実装されている限り、任意の機能をエクスポートできます。 @No__t_0 からコンポーネント部分を派生させる必要はありません。 代わりに、エクスポートするクラスまたはクラスメンバーに <xref:System.ComponentModel.Composition.ExportAttribute> 属性を追加する必要があります。 この属性は、別のコンポーネントパーツが機能をインポートする際に使用する*コントラクト*を指定します。

### <a name="the-export-contract"></a>エクスポートコントラクト
 @No__t_0 は、エクスポートされるエンティティ (クラス、インターフェイス、または構造体) を定義します。 通常、export 属性は、エクスポートの種類を指定するパラメーターを受け取ります。

```
[Export(typeof(ContentTypeDefinition))]
class TestContentTypeDefinition : ContentTypeDefinition {   }
```

 既定では、<xref:System.ComponentModel.Composition.ExportAttribute> 属性は、エクスポートするクラスの型であるコントラクトを定義します。

```
[Export]
[Name("Structure")]
[Order(After = "Selection", Before = "Text")]
class TestAdornmentLayerDefinition : AdornmentLayerDefinition {   }
```

 この例では、既定の `[Export]` 属性は `[Export(typeof(TestAdornmentLayerDefinition))]` と同じです。

 次の例に示すように、プロパティまたはメソッドをエクスポートすることもできます。

```
[Export]
[Name("Scarlet")]
[Order(After = "Selection", Before = "Text")]
public AdornmentLayerDefinition scarletLayerDefinition;
```

### <a name="import-a-mef-export"></a>MEF エクスポートをインポートする
 MEF エクスポートを使用する場合は、エクスポートされたコントラクト (通常は型) を把握し、その値を持つ <xref:System.ComponentModel.Composition.ImportAttribute> 属性を追加する必要があります。 既定では、import 属性は、変更するクラスの型であるパラメーターを1つ受け取ります。 次のコード行では、<xref:Microsoft.VisualStudio.Text.Classification.IClassificationTypeRegistryService> 型がインポートされます。

```
[Import]
internal IClassificationTypeRegistryService ClassificationRegistry;
```

## <a name="get-editor-functionality-from-a-mef-component-part"></a>MEF コンポーネントパーツからエディター機能を取得する
 既存のコードが MEF コンポーネントのパーツである場合、MEF メタデータを使用してエディターコンポーネントのパーツを使用できます。

#### <a name="to-consume-editor-functionality-from-a-mef-component-part"></a>MEF コンポーネントパーツからエディター機能を使用するには

1. グローバルアセンブリキャッシュ (GAC) にある*system.componentmodel*への参照、およびエディターアセンブリへの参照を追加します。

2. 関連する using ディレクティブを追加します。

    ```
    using System.ComponentModel.Composition;
    using Microsoft.VisualStudio.Text;
    ```

3. 次のように、`[Import]` 属性をサービスインターフェイスに追加します。

    ```
    [Import]
    ITextBufferFactoryService textBufferService;
    ```

4. サービスを取得したら、そのコンポーネントのいずれかを使用できます。

5. アセンブリをコンパイルしたら、*.. に配置します。Visual Studio インストールの \Common7\IDE\Components \* フォルダー。

## <a name="see-also"></a>関連項目
- [言語サービスとエディターの拡張点](../extensibility/language-service-and-editor-extension-points.md)
