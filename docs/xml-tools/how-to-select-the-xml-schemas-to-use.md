---
title: '方法: 使用する XML スキーマを選択する'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: d6fda3ef-d465-4788-8514-2f2d528d658c
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 41f830214b20df24587cf902e6b180e8a43a8cd3
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63007401"
---
# <a name="how-to-select-the-xml-schemas-to-use"></a>方法: 使用する XML スキーマを選択する

XML エディターでスキーマ キャッシュを提供する、 *%VSInstallDir%\xml\Schemas*ディレクトリ。 スキーマ キャッシュには、IntelliSense と XML ドキュメントの検証に使用される既知の XML スキーマが格納されています。

使用して、**スキーマ**ドキュメント プロパティを 1 つまたは複数の XML スキーマ定義言語 (XSD) スキーマを選択します。 スキーマのスキーマ キャッシュから、または別の場所を選択できます。

指定したスキーマは (非表示) のソリューション ユーザー オプション ファイルに保存されます (.*suo*)、およびその他のすべての XML ドキュメントのプロパティ。 その結果、次回ソリューションを開き、これらの値を再入力する必要はありません。

> [!NOTE]
> エディターは、インライン スキーマまたはによって参照されるスキーマを使用して検証できます、`xsd:schemaLocation`属性。 詳細については、次を参照してください。 [XML ドキュメントの検証](../xml-tools/xml-document-validation.md)です。

## <a name="to-select-an-xml-schema-from-the-schema-cache"></a>スキーマ キャッシュから XML スキーマを選択するには

1. XML エディターでファイルを開きます。

2. ドキュメントのプロパティ ウィンドウでクリックして、**スキーマ**フィールド。 ときに、参照ボタン (...) が表示されたら、それをクリックします。

   ![XML ファイルのスキーマ プロパティ](media/properties-schemas.png)

   [XML スキーマ ダイアログ ボックス](xml-schemas-dialog-box.md)が開きます。 ダイアログ ボックスですべてのスキーマを一覧表示します。*xsd*スキーマ キャッシュ内の拡張機能 (で参照されているスキーマを含む、 *catalog.xml*ファイル)、および Visual Studio で開いている現在のソリューションで参照されるスキーマも、 `xsd:schemaLocation`属性で参照したり、**スキーマ**プロパティ。

3. 次のいずれかを実行し、検証に使用するスキーマを選択します。

   - 表示されているスキーマを選択、 **XML スキーマ**ダイアログ ボックスで、をクリックして、**使用**列、および選択し**このスキーマを使用して、** します。

     - または -

   - 一覧表示される複数のスキーマを選択して、 **XML スキーマ**ダイアログ ボックスを右クリックして選択**このスキーマを使用して、** します。

4. **[OK]** をクリックします。

   選択したスキーマの一覧は、元にコピーされる、**スキーマ**ドキュメントのプロパティ。

## <a name="to-add-an-xml-schema-to-the-schema-cache"></a>XML スキーマをスキーマ キャッシュに追加するには

1. ドキュメントのプロパティ ウィンドウでのボタンをクリックします。、**スキーマ**フィールド。

2. **[追加]** をクリックします。

   **XSD スキーマを開く**ダイアログ ボックスが開きます。

3. スキーマ キャッシュに追加するスキーマを参照し、選択します。

4. **[開く]** をクリックします。

   スキーマはスキーマ キャッシュに追加されます、**使用**列の値に設定されて**このスキーマを使用して、**。

## <a name="to-delete-an-xml-schema-from-the-schema-cache"></a>スキーマ キャッシュから XML スキーマを削除するには

1. ドキュメントのプロパティ ウィンドウでのボタンをクリックします。、**スキーマ**フィールド。

2. クリックして削除するスキーマを選択**削除**します。

   スキーマは、メモリ内のスキーマ キャッシュから削除されますが、ファイル システムからは削除されません。

   > [!NOTE]
   > 使用してスキーマへの参照があるかどうか、`schemaLocation`属性、または、一致する`targetNamespace`し**削除**自動的な関連付けによりこのような状況では機能しません。 ここでお勧めときにスキーマをマークする**選択されているスキーマを使用しないでください**で、**使用**列。

## <a name="see-also"></a>関連項目

- [スキーマ キャッシュ](../xml-tools/schema-cache.md)
- [XML スキーマ ダイアログ ボックス](../xml-tools/xml-schemas-dialog-box.md)
- [XML エディター](../xml-tools/xml-editor.md)