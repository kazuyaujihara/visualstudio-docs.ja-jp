---
title: XML スキーマを作成します。
ms.date: 03/05/2019
ms.topic: conceptual
ms.assetid: 1d6700a9-fd67-4794-8997-399589e99bec
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0e93155f230ee4a564116f5d1357a97923706c36
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62783494"
---
# <a name="how-to-create-an-xml-schema-from-an-xml-document"></a>方法: XML ドキュメントから XML スキーマを作成する

XML エディターを使用して、XML ドキュメントから XML スキーマ定義言語 (XSD) スキーマを作成できます。 XML ファイルは、次のように、スキーマを生成する方法を決定します。

- XML ドキュメントにスキーマまたはドキュメント型定義 (DTD) が関連付けられていない場合は、新しい XML スキーマを推論するために XML ドキュメント内のデータが使用されます。

- 関連する DTD が XML ドキュメントに含まれている場合は、外部 DTD および内部サブセットが、対応する XML スキーマに変換されます。

- インラインの XDR (XML-Data Reduced) スキーマが XML ドキュメントに含まれている場合は、その XDR スキーマが、対応する XML スキーマに変換されます。

作成されるスキーマを使用し、XML ファイルに対して IntelliSense を提供します。

スキーマ推論エンジンの詳細については、次を参照してください。 [XML スキーマを推論](/dotnet/standard/data/xml/inferring-an-xml-schema)します。

## <a name="to-create-an-xml-schema"></a>XML スキーマを作成するには

1. Visual Studio で XML ファイルを開きます。

2. メニュー バーで、 **XML** > **Create Schema**します。

   XML スキーマ ドキュメントが作成され、XML ファイルで見つかった各名前空間用に開きます。 各スキーマは、一時的にその他のファイルとして開かれます。 スキーマは、ディスクに保存するか、プロジェクトに追加するか、破棄することができます。

## <a name="see-also"></a>関連項目

- [XML エディター](../xml-tools/xml-editor.md)