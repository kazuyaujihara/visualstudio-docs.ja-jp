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
ms.openlocfilehash: 6ffa8888529586e23d6f9762c3ec5b724c708ca5
ms.sourcegitcommit: ab2c49ce72ccf44b27b5c8852466d15a910453a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2019
ms.locfileid: "69024558"
---
# <a name="xaml-designer-extensibility-migration"></a>XAML デザイナーの機能拡張の移行

Visual Studio 2019 では、XAML デザイナーが2つの異なるアーキテクチャ (デザイナー分離アーキテクチャと、より新しい surface 分離アーキテクチャ) をサポートしています。 このアーキテクチャ遷移は、.NET Framework プロセスでホストできないターゲットランタイムをサポートするために必要です。 Surface 分離アーキテクチャに移行すると、サードパーティの拡張モデルに重大な変更が加えられます。 この記事では、これらの変更について説明します。これらの変更は、バージョン16.3 以降の Visual Studio 2019 で使用できます。

**デザイナーの分離**は、.NET Framework を対象とし、 *.dll*拡張子をサポートするプロジェクトの WPF デザイナーによって使用されます。 ユーザーコード、コントロールライブラリ、およびサードパーティの拡張機能は、実際のデザイナーコードおよびデザイナーパネルと共に外部プロセス (*Xdesproc .exe*) に読み込まれます。

**サーフェイスの分離**は、UWP デザイナーによって使用されます。 また、.NET Core を対象とするプロジェクトの WPF デザイナーによっても使用されます。 サーフェイスの分離では、ユーザーコードとコントロールのライブラリだけが別のプロセスに読み込まれ、デザイナーとそのパネルは Visual Studio プロセス (*devenv.exe*) に読み込まれます。 ユーザーコードとコントロールライブラリの実行に使用されるランタイムは、実際のデザイナーおよびサードパーティの拡張コードの .NET Framework によって使用されるランタイムとは異なります。

![拡張性-移行-アーキテクチャ](media/xaml-designer-extensibility-migration-architecture.png)

このアーキテクチャの移行により、サードパーティ製の拡張機能は、サードパーティ製のコントロールライブラリと同じプロセスに読み込まれなくなりました。 拡張機能は、コントロールライブラリに直接依存したり、ランタイムオブジェクトに直接アクセスしたりすることができなくなりました。 以前にデザイナー分離アーキテクチャ用に作成された拡張機能は、surface 分離アーキテクチャを使用するための新しいアプローチに移行する必要があります。 実際には、既存の拡張機能を新しい機能拡張 API アセンブリに対してコンパイルする必要があります。 コントロールライブラリが別のプロセスに読み込まれるようになったため、 [typeof](/dotnet/csharp/language-reference/keywords/typeof)またはランタイムインスタンスを介したランタイムコントロール型へのアクセスは、置換または削除する必要があります。

## <a name="new-extensibility-api-assemblies"></a>新しい機能拡張 API アセンブリ

新しい機能拡張 API アセンブリは、既存の機能拡張 API アセンブリに似ていますが、区別するために別の名前付けスキームに従います。 同様に、名前空間の名前は新しいアセンブリ名を反映するように変更されています。

| デザイナー分離 API アセンブリ            | Surface 分離 API アセンブリ                       |
|:------------------------------------------ |:---------------------------------------------------- |
| Microsoft. Windows. 拡張機能 .dll | VisualStudio. 拡張機能の .dll |
| Microsoft.........   | VisualStudio......................   |

## <a name="new-file-extension-and-discovery"></a>新しいファイル拡張子と検出

*デザインの .dll*ファイル拡張子を使用する代わりに、 *designtools .dll*ファイル拡張子を使用して新しい surface 拡張機能が検出されます。 *. design*および*designtools .dll*拡張子は、同じ*design*サブフォルダーに存在できます。

サードパーティ製のコントロールライブラリは、実際のターゲットランタイム (.NET Core または UWP) 用にコンパイルされますが、 *designtools .dll*拡張子は常に .NET Framework アセンブリとしてコンパイルする必要があります。

## <a name="decouple-attribute-tables-from-runtime-types"></a>ランタイム型から属性テーブルを分離する

Surface 分離機能拡張モデルでは、拡張機能が実際のコントロールライブラリに依存することは許可されていないため、拡張機能はコントロールライブラリから型を参照できません。 たとえば、mylibrary. *designtools .dll*は、 *mylibrary .dll*に依存していてはなりません。

このような依存関係は、属性テーブルを介して型のメタデータを登録するときに最もよく使用されます。 [Typeof](/dotnet/csharp/language-reference/keywords/typeof)または[GetType](/dotnet/visual-basic/language-reference/operators/gettype-operator)経由で直接コントロールライブラリ型を参照する拡張コードは、文字列ベースの型名を使用して新しい api で置き換えられます。

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

## <a name="feature-providers-and-model-api"></a>機能プロバイダーとモデル API

機能プロバイダーは拡張機能アセンブリに実装され、Visual Studio プロセスに読み込まれます。 `FeatureAttribute`は、 [typeof](/dotnet/csharp/language-reference/keywords/typeof)を直接使用して機能プロバイダーの型を直接参照します。

現時点では、次の機能プロバイダーがサポートされています。

* `DefaultInitializer`
* `AdornerProvider`
* `ContextMenuProvider`
* `ParentAdapter`
* `PlacementAdapter`

機能プロバイダーは、実際のランタイムコードとコントロールライブラリとは異なるプロセスに読み込まれるため、ランタイムオブジェクトに直接アクセスできなくなります。 代わりに、対応するモデルベースの Api を使用するように、このようなすべての対話を変換する必要があります。 モデル API が更新さ<xref:System.Type>れ、または<xref:System.Object>へのアクセスが使用できなくなったか、また`TypeIdentifier`は`TypeDefinition`とに置き換えられました。

`TypeIdentifier`型を識別するアセンブリ名のない文字列を表します。 をに解決して、型に関する追加情報`TypeIdenfifier` を`TypeDefinition`照会できます。 `TypeDefinition`インスタンスを拡張コードにキャッシュすることはできません。

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

Surface 分離機能拡張 API セットから削除された Api:

* `ModelFactory.CreateItem(EditingContext context, object item)`
* `ViewItem.PlatformObject`
* `ModelProperty.DefaultValue`

`TypeIdentifier` の<xref:System.Type>代わりにを使用する api:

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

`TypeIdentifier` の<xref:System.Type>代わりにを使用する api では、コンストラクター引数をサポートしていません。

* `ModelFactory.CreateItem(EditingContext context, TypeIdentifier typeIdentifier, params object[] arguments)`
* `ModelFactory.CreateItem(EditingContext context, TypeIdentifier typeIdentifier, CreateOptions options, params object[] arguments)`

`TypeDefinition` の<xref:System.Type>代わりにを使用する api:

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

`ModelItem` の<xref:System.Object>代わりにを使用する api:

* `ModelItemCollection.Insert(int index, object value)`
* `ModelItemCollection.Remove(object value)`
* `ModelItemDictionary.Add(object key, object value)`
* `ModelItemDictionary.ContainsKey(object key)`
* `ModelItemDictionary.Remove(object key)`
* `ModelItemDictionary.TryGetValue(object key, out ModelItem value)`

さらに`ModelItem` 、の`SetValue`ような api では、プリミティブ型または組み込みの .NET Framework 型のインスタンスのみがサポートされます。これは、ターゲットランタイム用に変換できます。 現在、次の種類がサポートされています。

* プリミティブ .NET Framework 型: `Boolean` `Byte` 、、`Nullable`、 `DateTime`、 `Double` `Enum` 、、`SByte` 、、、、、 `Guid` `Char` `Int16` `Int32` `Int64`, `Single`, `String`, `Type`, `UInt16`, `UInt32`, `UInt64`,`Uri`
* `Brush`既知`EasingFunctionBase` `Duration` `CornerRadius` `EasingMode`のWPF`FontFamily`.NET Framework 型 (および派生型): `Color`、、 、`EllipseGeometry`、 、、、、、、`GeneralTransform` `CompositeTransform` `Geometry`, `GradientStopCollection`, `GradientStop`, `GridLength`, `ImageSource`, `InlineCollection`, `Inline`, `KeySpline`, `Material`, `Matrix`, `PathFigureCollection`, `PathFigure`, `PathSegmentCollection`, `PathSegment`, `Path`, `PointCollection`, `Point`, `PropertyPath`, `Rect`, `RepeatBehavior`, `Setter`, `Size`, `StaticResource`, `TextAlignment`, `TextDecorationCollection`, `ThemeResourceExtension`, `Thickness`, `TimeSpan`, `Transform3D`,`TransformCollection`

例えば:

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

コードサンプルの詳細については、「 [xaml デザイナーの機能拡張-サンプル](https://github.com/microsoft/xaml-designer-extensibility-samples)リポジトリ」を参照してください。

## <a name="limited-support-for-designdll-extensions"></a>. Design 拡張子のサポートの制限

コントロールライブラリに対して*designtools .dll*拡張子が検出された場合は、最初に読み込まれ、の検出はスキップされます。

*Designtools .dll*拡張子が存在しないが、拡張子 *.dll*が見つかると、XAML 言語サービスは、基本エディターとプロパティインスペクターのシナリオをサポートするために、このアセンブリを読み込んで属性テーブル情報を抽出しようとします。 このメカニズムは、スコープに限定されています。 機能プロバイダーを実行するためにデザイナー分離拡張機能を読み込むことはできませんが、既存の WPF コントロールライブラリの基本的なサポートを提供する場合があります。
