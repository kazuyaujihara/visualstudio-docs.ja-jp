---
title: Strings 要素 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Strings element (VSCT XML schema)
- VSCT XML schema elements, Strings
ms.assetid: 23a42074-a689-481d-824f-b43aa448f266
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 7c91a8ea07daee77855017d641a569a892612c3e
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72719444"
---
# <a name="strings-element"></a>文字列要素
Strings 要素には、少なくとも**Buttontext**子要素が含まれている必要があります。 その他のすべての子要素は省略可能です。 ' & ' や ' < ' などの無効な XML 文字は、エンティティとしてコーディングされている必要があります (' &amp; ' および ' &lt; ' など)。

 テキスト文字列内のアンパサンドは、コマンドのショートカットキーを指定します。

## <a name="syntax"></a>構文

```
<Strings>
  <ButtonText>... </ButtonText>
  <CommandName>... </CommandName>
</Strings>
```

## <a name="attributes-and-elements"></a>属性および要素
 以降のセクションでは、属性、子要素、および親要素について説明します。

### <a name="attributes"></a>属性

|属性|説明|
|---------------|-----------------|
|language|省略可能です。 Language = "."。|

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|ButtonText|このフィールドとコマンド定義内の5つの次のテキストフィールドを使用すると、さまざまなメニューに表示されるテキストを指定できます。 既定では、[`ButtonText`] フィールドはメニューコントローラーに表示されます。 他のテキストフィールドが空白の場合は、`ButtonText` フィールドも既定値になります。 他のテキストフィールドが指定されている場合でも、`ButtonText` フィールドを空白にすることはできません。|
|ToolTipText|@No__t_0 フィールドは、メニュー項目のツールヒントに表示されるテキストを指定します。<br /><br /> @No__t_0 フィールドが空白の場合は、[`ButtonText`] フィールドが使用されます。|
|MenuText|@No__t_0 フィールドは、コマンドがメインメニュー、ツールバー、ショートカットメニュー、またはサブメニュー上にある場合に、コマンドに対して表示されるテキストを指定します。 @No__t_0 フィールドが空白の場合、統合開発環境 (IDE) は `ButtonText` フィールドを使用します。 @No__t_0 フィールドはローカライズにも使用できます。<br /><br /> ショートカットメニューの場合、`MenuText` フィールドは、ショートカットメニューのツールバーに表示される名前です。これにより、IDE のショートカットメニューをカスタマイズできます。 そのため、ショートカットメニューの名前を指定してください。たとえば、"Shortcut" ではなく "ウィジェットパッケージのショートカットメニュー" を使用します。<br /><br /> @No__t_0 フィールドが指定されていない場合は、`ButtonText` フィールドが使用されます。|
|CommandName|@No__t_0 フィールドは、 **[カスタマイズ]** ダイアログボックスの **[コマンド]** タブの キーボード カテゴリに表示されるテキストを指定します ( **[ツール]** メニューの **[カスタマイズ]** をクリックして利用できます)。|
|CanonicalName|英語の `CanonicalName` フィールドでは、コマンドの名前を英語のテキストで指定します。これは、メニュー項目を実行するために**コマンド**ウィンドウに入力できます。 IDE では、文字、数字、アンダースコア、または埋め込み期間以外の文字は除去されます。 次に、このテキストを `ButtonText` フィールドに連結して、コマンドを定義します。 たとえば、 **[ファイル]** メニューの **[新しいプロジェクト]** がコマンド NewProject になります。<br /><br /> [英語 `CanonicalName`] フィールドが指定されていない場合、IDE は [`ButtonText`] フィールドを使用し、文字、数字、アンダースコア、および埋め込み期間以外のすべてを除去します。 たとえば、ボタンテキスト "& 定義コマンド..."は DefineCommands になり、アンパサンド、スペース、および省略記号が削除されます。<br /><br /> @No__t_0 フラグが指定されていて、コマンドのテキストが変更された場合、**コマンド**ウィンドウで認識される対応するコマンドは変更されません。これは、元の `ButtonText` または英語の `CanonicalName` フィールドの正規の形式にとどまります。|
|LocCanonicalName|@No__t_0 フィールドは、英語 `CanonicalName` フィールドと同じように動作しますが、ローカライズされたコマンドテキストを指定できます。 両方の正規フィールドを指定できます。 IDE では、**コマンド**ウィンドウに入力されたテキストを解析してコマンドに関連付けるだけなので、英語と英語以外のテキストの両方を同じコマンドに関連付けることができます。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[Button 要素](../extensibility/button-element.md)|ユーザーが操作できる要素を定義します。|
|[Menu 要素](../extensibility/menu-element.md)|1つのメニュー項目を定義します。|
|[Combo 要素](../extensibility/combo-element.md)|コンボボックスに表示されるコマンドを定義します。|

## <a name="see-also"></a>関連項目
- [Visual Studio Command Table (.Vsct) ファイル](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)