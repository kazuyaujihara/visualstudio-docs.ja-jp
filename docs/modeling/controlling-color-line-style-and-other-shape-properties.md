---
title: 色、線のスタイル、およびその他のシェイプのプロパティの管理
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d1783ecf3b30207838d93fdb9cda93e3ed7e232c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62422928"
---
# <a name="controlling-color-line-style-and-other-shape-properties"></a>色、線のスタイル、およびその他のシェイプのプロパティの管理

いくつかの色などのシェイプのプロパティ ' を公開できます '。 つまり、プロパティは、図形のドメイン プロパティにリンクできます。 他のユーザーは、直接制御する必要があります。

## <a name="exposing-a-property"></a>プロパティを公開します。
 いくつかの色などのシェイプのプロパティは、ドメイン プロパティの値にリンクできます。

 DSL 定義では、図形、コネクタ、または図クラスを選択します。 その右クリック メニューで、**公開されている追加**、塗りつぶしの色など、目的のプロパティを選択し、します。

 図形は、ドメイン プロパティまたはユーザーとしてプログラム コードで設定できるようになりました。

## <a name="dynamically-updating-an-exposed-property"></a>公開されたプロパティを動的に更新
 一般公開されているプロパティを別のプロパティに依存しないようにします。 たとえば、特定のドメイン プロパティが赤色にするための図形が 0 未満たい場合があります。 この依存関係を作成、[ルール](../modeling/rules-propagate-changes-within-the-model.md)します。 例:

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using Microsoft.VisualStudio.Modeling;
using Microsoft.VisualStudio.Modeling.Diagrams;
namespace ExampleNamespace
{
 // Attribute associates the rule with class:
 [RuleOn(typeof(CarShape), FireTime = TimeToFire.TopLevelCommit)]
 // The rule is a class derived from one of the abstract rules:
 class CarShapeAddRule : AddRule
 {
 // Override the abstract method:
 public override void ElementAdded(ElementAddedEventArgs e)
 {
 base.ElementAdded(e);
 CarShape shape = e.ModelElement as CarShape;
 Store store = shape.Store;
 // Ignore this call if we're currently loading a model:
 if (store.TransactionManager.CurrentTransaction.IsSerializing)
  return;
 Car car = shape.ModelElement as Car;
 // Code here propagates change as required - for example:
 shape.FillColor = car.Somebool ? System.Drawing.Color.Red : System.Drawing.Color.Green;
 }
}
 // The rule must be registered:
 public partial class ExampleDomainModel
 {
 protected override Type[] GetCustomDomainModelTypes()
 {
  List<Type> types = new List<Type>(base.GetCustomDomainModelTypes());
  types.Add(typeof(CarShapeAddRule));
  // If you add more rules, list them here.
  return types.ToArray();
 }
 }
}
```