---
title: Excel 拡張機能のサンプル:ActionFilter クラス |Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-test
ms.topic: conceptual
ms.assetid: c69fe3c7-f797-4e90-b21c-f2cc4dddf152
caps.latest.revision: 13
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 26eb001de3a8fed7c6bb1d9d1a547aa618e745e8
ms.sourcegitcommit: 2da366ba9ad124366f6502927ecc720985fc2f9e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2019
ms.locfileid: "68871601"
---
# <a name="sample-excel-extension-actionfilter-class"></a>Excel 拡張機能のサンプル:ActionFilter クラス
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

この内部クラスは、 [uitestactionfilter](/previous-versions/visualstudio/visual-studio-2012/dd985757(v=vs.110))クラスを拡張し、 [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)]要素に対するテストアクションのフィルターを表します。

## <a name="simple-properties"></a>単純なプロパティ
 開発者は、これらの読み取り専用プロパティを使用して、コード化された UI テスト フレームワークでこのテスト アクション フィルターをどのように実行するかを指定できます。 たとえば、`UITestActionFilter.Name` プロパティには、アクション フィルター名が設定されています。 他のプロパティには、アクション フィルターの `UITestActionFilter.Category`、`UITestActionFilter.FilterType`、このテスト アクション フィルターでフィルター処理されるテスト アクションの `UITestActionFilter.Group` の名前が設定されています。 また、`UITestActionFilter.ApplyTimeout` を適用するかどうか、テスト アクションが `UITestActionFilter.Enabled` かどうかを示すプロパティもあります。

## <a name="processrule-method"></a>ProcessRule メソッド
 このメソッドは、コード化された UI テスト フレームワークによって呼び出され、指定された `IUITestActionStack` に対してフィルターを実行します。 このオーバーライドによって、スタックの次のアクションがセルに対してキーストロークを送る場合はマウスを選択するセルのアクションを削除します。 その後で `false` が返されます。

## <a name="private-methods"></a>プライベート メソッド
 `IsLeftClick` メソッドは、指定されたアクションがマウスの左クリックを表すかどうかを判断します。 `AreActionsOnSameExcelCell` メソッドは、2 つの指定されたアクションが Excel の同じセルに対して実行されるかどうかを判断します。

## <a name="see-also"></a>関連項目

- [コード化された UI テストと操作の記録を拡張して Microsoft Excel をサポート](../test/extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel.md)
