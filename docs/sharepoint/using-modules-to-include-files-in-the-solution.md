---
title: モジュールを使用したソリューションへのファイルの追加 |Microsoft Docs
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, deployment modules
- SharePoint development in Visual Studio, modules
- modules [SharePoint development in Visual Studio]
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 4f8f2aa6c5d86af2424a811b6167829cefdb6fb5
ms.sourcegitcommit: dcbb876a5dd598f2538e62e1eabd4dc98595b53a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2019
ms.locfileid: "72985301"
---
# <a name="use-modules-to-include-files-in-the-solution"></a>モジュールを使用してソリューションにファイルを含める
  ファイルの種類 (新しいマスターページなど) に関係なく、SharePoint サーバーにファイルを配置することが必要になる場合があります。 これを行うには、*モジュール*を使用できます ([!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)] コードモジュールと混同しないでください)。 モジュールは、SharePoint ソリューション内のファイルのコンテナーです。 ソリューションを配置すると、モジュール内のファイルが SharePoint サーバー上の指定されたフォルダーにコピーされます。

## <a name="module-items-and-elements"></a>モジュールの項目と要素
 モジュールを作成するには、 **[新しい項目の追加]** ダイアログボックスでモジュールを選択して、プロジェクトに追加します。 次に、*要素 .xml*ファイルを変更して、配置するファイルの名前、システム上の場所、および SharePoint サーバー上でのコピー先ファイルの名前を含めます。

 モジュールの*Elements .xml*ファイルの例を次に示します。

```xml
<?xml version="1.0" encoding="utf-8"?>
<Elements xmlns="http://schemas.microsoft.com/sharepoint/">
    <Module Name="Module1">
        <File Path="Module1\Sample.txt" Url="Module1/Sample.txt" />
    </Module>
</Elements>

```

 新しく作成されたモジュールには、次の既定のファイルが含まれています。

|ファイル名|説明|
|---------------|-----------------|
|*Elements .xml*|モジュールの定義ファイルです。|
|*サンプル .txt*|モジュール内のファイルの例として機能するプレースホルダーファイル。|

 *Elements .xml*ファイルには、次の要素が含まれています。

|要素名|説明|
|------------------|-----------------|
|Elements|モジュールで定義されているすべての要素が含まれます。|
|Module|Module 要素には、`<Module Name="Module1">`の形式でモジュールの名前を指定する単一の属性*name*があります。<br /><br /> モジュール (またはその*フォルダー名*プロパティ) の名前を変更する場合は、モジュール要素内の名前を手動で更新する必要があることに注意してください。<br /><br /> Module 要素内のファイルのサブディレクトリを指定すると、[!INCLUDE[sharepointShort](../sharepoint/includes/sharepointshort-md.md)] (WSS) によって、対応するディレクトリ構造が自動的に作成されます。|
|ファイル|File 要素には、*パス*と*Url*という2つのパラメーターがあります。<br /><br /> -Path: SharePoint ソリューション内のファイルの名前と場所。 形式は、`Path="Module1\Sample.txt"`です。<br /><br /> -Url: SharePoint サーバー上でファイルが配置される場所。 形式は、`Url="Module1/Sample.txt"`です。<br /><br /> -Type: *GhostableInLibrary*と*Ghostable*の2つの設定を持つ省略可能な属性です。 形式は、`Type="GhostableInLibrary"`です。 *GhostableInLibrary*を指定すると、ファイルがライブラリに追加されたときにファイルに付随するリスト項目と共に、SharePoint のドキュメントライブラリに追加されます。 *Ghostable*を指定すると、ファイルがドキュメントライブラリの外部の SharePoint に追加されます。|

 配置する各ファイルには、 *Elements .xml*に個別の `<File>` 要素エントリが必要です。

## <a name="see-also"></a>関連項目
- [方法: モジュールを使用してファイルを含める](../sharepoint/how-to-include-files-by-using-a-module.md)
- [方法: ファイルを準備する](/previous-versions/office/developer/sharepoint-2010/ms441170(v=office.14))
- [SharePoint ソリューションの開発](../sharepoint/developing-sharepoint-solutions.md)
- [SharePoint の web パーツの作成](../sharepoint/creating-web-parts-for-sharepoint.md)
- [SharePoint ソリューションのパッケージ化と配置](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)
