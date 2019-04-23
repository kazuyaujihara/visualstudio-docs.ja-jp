---
title: '方法: XML ファイルを編集 |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: 07fa3ecf-6345-4d30-9d85-d5ef5b083319
caps.latest.revision: 7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 92f233a036c3c0b40cbd53a298154919861b58b8
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/17/2019
ms.locfileid: "59663662"
---
# <a name="how-to-edit-xml-files"></a>方法: XML ファイルを編集する
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

XML エディターは、XML ファイル用の新しいエディターです。 スタンドアロンの XML ファイル、または Visual Studio プロジェクトと関連付けられたファイルに対して使用できます。 XML エディターと関連付けられるファイル拡張子は、.config、.dtd、.xml、.xsd、.xdr、.xsl、.xslt、および .vssettings です。 XML エディターは、特定のエディターが登録されておらず、XML や DTD のコンテンツを含む他のファイルの種類にも関連付けられます。  
  
> [!NOTE]
>  XHTML ドキュメントは HTML エディターによって処理されます。  
  
### <a name="to-edit-an-xml-file"></a>XML ファイルを編集するには  
  
1.  編集するファイルをダブルクリックします。  
  
### <a name="to-add-a-new-xml-file-to-a-project"></a>新しい XML ファイルをプロジェクトに追加するには  
  
1.  **プロジェクト**メニューの **新しい項目の追加**します。  
  
2.  選択**XML ファイル**から、**テンプレート**ウィンドウ。  
  
3.  内のファイル名を入力、**名前**フィールドとキーを押して**追加**します。  
  
     XML ファイルがプロジェクトに追加され、XML エディターによって開かれます。 ファイルには既定の XML 宣言 `<?xml version="1.0" encoding="utf-8" ?>` が含まれています。  
  
### <a name="to-add-an-existing-xml-file-to-a-project"></a>既存の XML ファイルをプロジェクトに追加するには  
  
1.  **プロジェクト**メニューの **既存項目の追加**します。  
  
     **既存項目の追加** ダイアログ ボックスが表示されます。  
  
2.  XML ファイルとキーを押して選択**追加**します。  
  
### <a name="to-create-a-new-xml-or-xslt-file"></a>新しい XML ファイルまたは XSLT ファイルを作成するには  
  
1.  **ファイル**メニューの **新規**します。  
  
     **新しいファイル** ダイアログ ボックスが表示されます。  
  
2.  選択**XML ファイル**; 新しい XML ファイルを作成するか、選択する**XSLT ファイル**新しい XSLT スタイル シートを作成します。  
  
3.  **[開く]** をクリックします。  
  
### <a name="to-create-a-project-for-xml-files"></a>XML ファイル用のプロジェクトを作成するには  
  
1.  **ファイル**メニューの **新規**、し、**プロジェクト**します。  
  
     **[新しいプロジェクト]** ダイアログ ボックスが表示されます。  
  
2.  任意のコード言語の選択**空のプロジェクト**、 をクリック**OK**します。  
  
3.  プロジェクトに XML ファイルを追加します。  
  
     このプロジェクトに追加したスキーマは XML エディターによって検出され、このプロジェクトが開かれている間に編集する XML、スキーマ、または XSLT ファイルにおいて、検証と IntelliSense のために使用されます。  
  
## <a name="see-also"></a>関連項目  
 [XML エディター](../xml-tools/xml-editor.md)   
 [XML ドキュメントのプロパティと [プロパティ] ウィンドウ](../xml-tools/xml-document-properties-properties-window.md)   
 [方法: XML ドキュメントから XML スキーマを作成する](../xml-tools/how-to-create-an-xml-schema-from-an-xml-document.md)
