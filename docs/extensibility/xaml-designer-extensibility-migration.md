---
title: XAML デザイナー機能拡張の移行
ms.date: 07/09/2019
ms.topic: conceptual
author: lutzroeder
ms.author: lutzr
manager: jillfra
dev_langs:
- csharp
- vb
monikerRange: vs-2019
ms.openlocfilehash: 4485e9a11cb4770477374deed651fbff2df6df52
ms.sourcegitcommit: 748d9cd7328a30f8c80ce42198a94a4b5e869f26
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2019
ms.locfileid: "67890324"
---
# <a name="xaml-designer-extensibility-migration"></a>XAML デザイナー機能拡張の移行

Visual Studio 2019 では、XAML デザイナーは、2 つの異なるアーキテクチャをサポートしています。 デザイナーの分離アーキテクチャと最近のサーフェス分離アーキテクチャ。 このアーキテクチャの遷移が .NET Framework のプロセスでホストできないターゲット ランタイムをサポートするために必要です。 画面の分離アーキテクチャへの移行、サード パーティ製の機能拡張モデルに重大な変更が導入されています。 この記事では、Visual Studio 2019 16.2 プレビュー チャネルで使用可能なこれらの変更について説明します。

**デザイナーの分離**を .NET Framework を対象とするプロジェクトの WPF デザイナーによって使用され、サポート *. design.dll*拡張機能。 ユーザー コード、コントロールのライブラリおよびサード パーティの拡張機能は、外部プロセスに読み込まれる (*XDesProc.exe*) と共に、実際のデザイナー コードとデザイナー パネル。

**分離のサーフェス**UWP デザイナーによって使用されます。 WPF デザイナーで .NET Core を対象とするプロジェクトにも使用されます。 サーフェスの分離の唯一のユーザー コードとコントロールのライブラリが読み込まれる別のプロセスで、デザイナーとそのパネルは、Visual Studio のプロセスに読み込まれるときに (*DevEnv.exe*)。 ユーザー コードとコントロール ライブラリを実行するために使用されるランタイムは、実際のデザイナーおよびサード パーティ製の機能拡張コードの .NET Framework で使用されるものは異なります。

![機能拡張-移行-アーキテクチャ](media/xaml-designer-extensibility-migration-architecture.png)

このアーキテクチャの移行のためのサード パーティ製のコントロール ライブラリと同じプロセスにサード パーティの拡張機能は不要になった読み込まれます。 拡張機能が不要になったコントロール ライブラリの直接的な依存関係があるまたはランタイム オブジェクトに直接アクセスできます。 デザイナーの分離のアーキテクチャを使用するために以前記述された拡張機能、 *Microsoft.Windows.Extensibility.dll* API サーフェスの分離アーキテクチャを使用する新しいアプローチに移行する必要があります。 実際には、既存の拡張機能は、新しい機能拡張 API アセンブリに対してコンパイルする必要があります。 実行時のコントロールへのアクセスの種類を使用して[typeof](/dotnet/csharp/language-reference/keywords/typeof)またはランタイム インスタンスを置換またはコントロール ライブラリが、別のプロセスに読み込まれるようになりましたので、削除する必要があります。

## <a name="new-extensibility-api-assemblies"></a>新しい拡張性 API アセンブリ

新しい拡張性 API アセンブリが既存の機能拡張 API アセンブリと同じですが、それらを区別するためのさまざまな名前付けスキームに従います。 同様に、名前空間の名前は、新しいアセンブリ名を反映するように変更があります。

| デザイナーの分離 API アセンブリ            | アセンブリの API サーフェスの分離                       |
|:------------------------------------------ |:---------------------------------------------------- |
| Microsoft.Windows.Design.Extensibility.dll | Microsoft.VisualStudio.DesignTools.Extensibility.dll |
| Microsoft.Windows.Design.Interaction.dll   | Microsoft.VisualStudio.DesignTools.Interaction.dll   |

## <a name="new-file-extension-and-discovery"></a>新しいファイル拡張子と探索

使用する代わりに、 *. design.dll*ファイル拡張子が拡張機能の検出を使用して新しい画面を *. designtools.dll*ファイル拡張子。 *。 design.dll*と *。 designtools.dll*で同じ拡張機能が存在できる*デザイン*サブフォルダーです。

実際のターゲット ランタイム (.NET Core または UWP) 向けのサードパーティ コントロール ライブラリにコンパイルされたときに、 *. designtools.dll*拡張機能は、.NET Framework アセンブリとして常にコンパイルする必要があります。

## <a name="decouple-attribute-tables-from-runtime-types"></a>ランタイム型の属性テーブルを分離します。

画面の分離の機能拡張モデルでは、実際のコントロールのライブラリに依存する拡張機能が許可されていませんし、そのため、拡張機能は、コントロール ライブラリからの型を参照できません。 たとえば、 *MyLibrary.designtools.dll*依存関係のない*MyLibrary.dll*します。

属性テーブルを使用して型のメタデータを登録するときに、このような依存関係が最も一般的なでした。 コントロール ライブラリを参照する拡張機能コードの種類が経由で直接[typeof](/dotnet/csharp/language-reference/keywords/typeof)または[GetType](/dotnet/visual-basic/language-reference/operators/gettype-operator)文字列ベースの型名を使用して、新しい Api で置き換えられます。

```csharp
using Microsoft.VisualStudio.DesignTools.Extensibility.Metadata;
using Microsoft.VisualStudio.DesignTools.Extensibility.Features;
using Microsoft.VisualStudio.DesignTools.Extensibility.Model;

[assembly: ProvideMetadata(typeof(AttributeTableProvider))]

public class AttributeTableProvider : IProvideAttributeTable
{
  public AttributeTable AttributeTable
  {
    get
    {
      var builder = new AttributeTableBuilder();
      builder.AddCustomAttributes("MyLibrary.MyControl", new DescriptionAttribute(Strings.MyControlDescription);
      builder.AddCustomAttributes("MyLibrary.MyControl", new FeatureAttribute(typeof(MyControlDefaultInitializer));
      return builder.CreateTable();
    }
  }
}
```

```vb
Imports Microsoft.VisualStudio.DesignTools.Extensibility.Metadata
Imports Microsoft.VisualStudio.DesignTools.Extensibility.Features
Imports Microsoft.VisualStudio.DesignTools.Extensibility.Model

<Assembly: ProvideMetadata(GetType(AttributeTableProvider))>

Public Class AttributeTableProvider
    Implements IProvideAttributeTable

    Public ReadOnly Property AttributeTable As AttributeTable Implements IProvideAttributeTable.AttributeTable
        Get
            Dim builder As New AttributeTableBuilder
            builder.AddCustomAttributes("MyLibrary.MyControl", New DescriptionAttribute(Strings.MyControlDescription))
            builder.AddCustomAttributes("MyLibrary.MyControl", New FeatureAttribute(GetType(MyControlDefaultInitializer)))
            Return builder.CreateTable()
        End Get
    End Property
End Class
```

## <a name="feature-providers-and-model-api"></a>機能プロバイダーとモデルの API

機能プロバイダーは拡張機能アセンブリで実装され、Visual Studio のプロセスに読み込まれます。 `FeatureAttribute` 機能プロバイダーの種類を使用して直接の参照は引き続き[typeof](/dotnet/csharp/language-reference/keywords/typeof)します。

現時点では、次の機能のプロバイダーがサポートされています。

* `DefaultInitializer`
* `AdornerProvider`
* `ContextMenuProvider`
* `ParentAdapter`
* `PlacementAdapter`

機能プロバイダーは、実際の実行時のコードとコントロールのライブラリから別のプロセスに読み込まれるようになりました、ためランタイム オブジェクトに直接アクセスすることはなくなりました。 代わりに、このようなすべての対話は、対応するモデルに基づく Api を使用して変換する必要があります。 モデルの API が更新されたら、およびへのアクセス<xref:System.Type>または<xref:System.Object>いずれかが使用できなくに置き換えられましたまたは`TypeIdentifier`と`TypeDefinition`。

`TypeIdentifier` アセンブリ名、種類を識別することがなく、文字列を表します。 A`TypeIdenfifier`に解決できる、`TypeDefinition`型に関する追加情報をクエリします。 `TypeDefinition` 拡張機能のコードでは、インスタンスをキャッシュできません。

```csharp
TypeDefinition type = ModelFactory.ResolveType(
    item.Context, new TypeIdentifier("MyLibrary.MyControl"));
TypeDefinition buttonType = ModelFactory.ResolveType(
    item.Context, new TypeIdentifier("System.Windows.Controls.Button"));
if (type?.IsSubclassOf(buttonType) == true)
{
}
```

```vb
Dim type As TypeDefinition = ModelFactory.ResolveType(
    item.Context, New TypeIdentifier("MyLibrary.MyControl"))
Dim buttonType As TypeDefinition = ModelFactory.ResolveType(
    item.Context, New TypeIdentifier("System.Windows.Controls.Button"))
If type?.IsSubclassOf(buttonType) Then

End If
```

Api は、画面の分離機能拡張 API のセットから削除されます。

* `ModelFactory.CreateItem(EditingContext context, object item)`
* `ViewItem.PlatformObject`
* `ModelProperty.DefaultValue`

Api を使用する`TypeIdentifier`の代わりに<xref:System.Type>:

* `ModelFactory.CreateItem(EditingContext context, Type itemType, params object[] arguments)`
* `ModelFactory.CreateItem(EditingContext context, Type itemType, CreateOptions options, params object[] arguments)`
* `ModelFactory.CreateStaticMemberItem(EditingContext context, Type type, string memberName)`
* `ViewItem.ItemType`
* `ModelEvent.EventType`
* `ModelEvent.IsEventOfType(Type type)`
* `ModeItem.IsItemOfType(Type type)`
* `ModelParent.CanParent(EditingContext context, ModelItem parent, Type childType)`
* `ModelParent.FindParent(EditingContext context, Type childType, ModelItem startingItem)`
* `ModelParent.FindParent(Type childType, GestureData gestureData)`
* `ModelProperty.IsPropertyOfType(Type type)`
* `ParentAdpater.CanParent(ModelItem parent, Type childType)`
* `ParentAdapter.RedirectParent(ModelItem parent, Type childType)`

Api を使用する`TypeIdentifier`の代わりに<xref:System.Type>コンス トラクターの引数はサポートされなくと。

* `ModelFactory.CreateItem(EditingContext context, TypeIdentifier typeIdentifier, params object[] arguments)`
* `ModelFactory.CreateItem(EditingContext context, TypeIdentifier typeIdentifier, CreateOptions options, params object[] arguments)`

Api を使用する`TypeDefinition`の代わりに<xref:System.Type>:

* `ModelFactory.ResolveType(EditingContext context, TypeIdentifier typeIdentifier)`
* `ValueTranslationService.GetProperties(Type itemType)`
* `ValueTranslationService.HasValueTranslation(Type itemType, PropertyIdentifier identifier)`
* `ValueTranslationService.TranslatePropertyValue(Type itemType, ModelItem item, PropertyIdentifier identifier, object value)`
* `ModelService.Find(ModelItem startingItem, Type type)`
* `ModelService.Find(ModelItem startingItem, Predicate<Type> match)`
* `ModelItem.ItemType`
* `ModelProperty.AttachedOwnerType`
* `ModelProperty.PropertyType`
* `FeatureManager.CreateFeatureProviders(Type featureProviderType, Type type)`
* `FeatureManager.CreateFeatureProviders(Type featureProviderType, Type type, Predicate<Type> match)`
* `FeatureManager.InitializeFeatures(Type type)`
* `FeatureManager.GetCustomAttributes(Type type, Type attributeType)`
* `AdapterService.GetAdapter<TAdapterType>(Type itemType)`
* `AdapterService.GetAdapter(Type adapterType, Type itemType)`

Api を使用する`ModelItem`の代わりに<xref:System.Object>:

* `ModelItemCollection.Insert(int index, object value)`
* `ModelItemCollection.Remove(object value)`
* `ModelItemDictionary.Add(object key, object value)`
* `ModelItemDictionary.ContainsKey(object key)`
* `ModelItemDictionary.Remove(object key)`
* `ModelItemDictionary.TryGetValue(object key, out ModelItem value)`

既知のなどのプリミティブ型`Int32`、 `String`、または`Thickness`.NET Framework のインスタンスとしてモデル API に渡すことが、ターゲットのランタイム プロセスに対応するオブジェクトに変換されます。 例えば:

```csharp
using Microsoft.VisualStudio.DesignTools.Extensibility.Features;
using Microsoft.VisualStudio.DesignTools.Extensibility.Model;

public class MyControlDefaultInitializer : DefaultInitializer
{
  public override void InitializeDefaults(ModelItem item)
  {
    item.Properties["Width"].SetValue(800d);
    base.InitializeDefaults(item);
  }
}
```

```vb
Imports Microsoft.VisualStudio.DesignTools.Extensibility.Features
Imports Microsoft.VisualStudio.DesignTools.Extensibility.Model

Public Class MyControlDefaultInitializer
    Inherits DefaultInitializer

    Public Overrides Sub InitializeDefaults(item As ModelItem)
        item.Properties!Width.SetValue(800.0)
        MyBase.InitializeDefaults(item)
    End Sub
End Class
```

複数のコード サンプルは、 [xaml デザイナー機能拡張サンプル](https://github.com/microsoft/xaml-designer-extensibility-samples)リポジトリ。

## <a name="limited-support-for-designdll-extensions"></a>制限付きサポート design.dll 拡張機能。

存在する場合 *. designtools.dll*コントロール ライブラリの拡張機能が検出された、最初との検出が読み込まれる *. design.dll*拡張機能はスキップされます。

ない場合は *. designtools.dll*拡張機能が存在するが、 *. design.dll*拡張機能が見つかると、XAML 言語サービスをサポートする属性の表の情報を抽出するには、このアセンブリをロードしようとしました。基本的なエディター、プロパティ インスペクターのシナリオの場合は。 このメカニズムは、スコープに制限されます。 機能プロバイダーを実行するデザイナーの分離の拡張機能の読み込みを許可しませんが、既存の WPF コントロール ライブラリの基本的なサポートを提供する可能性があります。
