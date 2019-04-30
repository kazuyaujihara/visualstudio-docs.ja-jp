---
title: '方法: XML ドキュメントから XML スキーマを作成する |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: 1d6700a9-fd67-4794-8997-399589e99bec
caps.latest.revision: 10
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 0f12436f9f129c6fb8a0fe3a4b6c853a9e58e650
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63438124"
---
# <a name="how-to-create-an-xml-schema-from-an-xml-document"></a>方法: XML ドキュメントから XML スキーマを作成する
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

XML エディターを使用することで、XML ドキュメントから XML スキーマ定義言語 (XSD) スキーマを作成することができます。 スキーマがどのように生成されるかは、XML インスタンス ドキュメントによって、次の方法で決定されます。  
  
- XML ドキュメントにスキーマまたはドキュメント型定義 (DTD) が関連付けられていない場合は、新しい XML スキーマを推論するために XML ドキュメント内のデータが使用されます。  
  
- 関連する DTD が XML ドキュメントに含まれている場合は、外部 DTD および内部サブセットが、対応する XML スキーマに変換されます。  
  
- インラインの XDR (XML-Data Reduced) スキーマが XML ドキュメントに含まれている場合は、その XDR スキーマが、対応する XML スキーマに変換されます。  
  
  作成されたスキーマは次に、XML ドキュメントで IntelliSense を利用できるようにするために使用されます。  
  
  スキーマ推論エンジンの詳細については、次を参照してください。 [XML スキーマの推論](http://msdn.microsoft.com/library/b18e7ffd-3c04-482d-9934-ba2f6a59b2c9)します。  
  
### <a name="to-create-an-xml-schema"></a>XML スキーマを作成するには  
  
1. XML インスタンス ドキュメントを XML エディターに読み込みます。  
  
2. をクリックして、 **Create Schema**からボタン、**ツールバー**します。  
  
     XML インスタンス ドキュメントで見つかった名前空間ごとに 1 つの XML スキーマ ドキュメントが作成され、開かれます。 各スキーマは、一時的にその他のファイルとして開かれます。  
  
     スキーマは、ディスクに保存するか、プロジェクトに追加するか、破棄することができます。  
  
    > [!NOTE]
    > **Create Schema**コマンドは、XML エディターのとでは、ショートカット メニューからも、 **XML**メニュー。  
  
## <a name="see-also"></a>関連項目  
 [XML エディター](../xml-tools/xml-editor.md)
