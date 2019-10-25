---
title: 1つのファイルジェネレーターの登録 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- registration, custom tools
- custom tools, defining registry settings
ms.assetid: db7592c0-1273-4843-9617-6e2ddabb6ca8
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e9026da08272d69bac246f98ae741a47527d627f
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72724562"
---
# <a name="registering-single-file-generators"></a>単一ファイル ジェネレーターの登録
カスタムツールを [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] で使用できるようにするには、そのツールをインスタンス化して特定のプロジェクトの種類に関連付ける [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] に登録する必要があります。

### <a name="to-register-a-custom-tool"></a>カスタムツールを登録するには

1. カスタムツール DLL を [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ローカルレジストリまたはシステムレジストリの [HKEY_CLASSES_ROOT] の下に登録します。

    たとえば、[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] に付属しているマネージ MSDataSetGenerator カスタムツールの登録情報を次に示します。

   ```
   [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\14.0\CLSID\{E76D53CC-3D4F-40A2-BD4D-4F3419755476}]
   @="COM+ class: Microsoft.VSDesigner.CodeGenerator.TypedDataSourceGenerator.DataSourceGeneratorWrapper"
   "InprocServer32"="C:\\WINDOWS\\system32\\mscoree.dll"
   "ThreadingModel"="Both"
   "Class"="Microsoft.VSDesigner.CodeGenerator.TypedDataSourceGenerator.DataSourceGeneratorWrapper"
   "Assembly"="Microsoft.VSDesigner, Version=14.0.0.0, Culture=Neutral, PublicKeyToken=b03f5f7f11d50a3a"
   ```

2. [ジェネレーター \\*guid* ] の下にある目的の [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] hive で、レジストリキーを作成します。 *guid*は、特定の言語のプロジェクトシステムまたはサービスによって定義された guid です。 キーの名前は、カスタムツールのプログラム名になります。 カスタムツールキーの値は次のとおりです。

   - (既定)

        省略可能です。 カスタムツールについてのわかりやすい説明を提供します。 このパラメーターは省略可能ですが、推奨されます。

   - CLSID

        必須です。 @No__t_0 を実装する COM コンポーネントのクラスライブラリの識別子を指定します。

   - GeneratesDesignTimeSource

        必須です。 このカスタムツールによって生成されたファイルの型をビジュアルデザイナーで使用できるようにするかどうかを示します。 このパラメーターの値は、ビジュアルデザイナーで使用できない型の場合は (0) 0、ビジュアルデザイナーで使用できる型の場合は (1) 0 である必要があります。

   > [!NOTE]
   > カスタムツールを使用する言語ごとに、カスタムツールを個別に登録する必要があります。

    たとえば、MSDataSetGenerator は、言語ごとに1回登録します。

   ```
   [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\14.0\Generators\{164b10b9-b200-11d0-8c61-00a0c91e29d5}\MSDataSetGenerator]
   @="Microsoft VB Code Generator for XSD"
   "CLSID"="{E76D53CC-3D4F-40a2-BD4D-4F3419755476}"
   "GeneratesDesignTimeSource"=dword:00000001

   [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\14.0\Generators\{fae04ec1-301f-11d3-bf4b-00c04f79efbc}\MSDataSetGenerator]
   @="Microsoft C# Code Generator for XSD"
   "CLSID"="{E76D53CC-3D4F-40a2-BD4D-4F3419755476}"
   "GeneratesDesignTimeSource"=dword:00000001
   ```

## <a name="see-also"></a>関連項目
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator>
- [単一ファイル ジェネレーターの実装](../../extensibility/internals/implementing-single-file-generators.md)
- [ビジュアル デザイナーへのタイプの公開](../../extensibility/internals/exposing-types-to-visual-designers.md)
- [BuildManager オブジェクトの概要](https://msdn.microsoft.com/library/50080ec2-c1c9-412c-98ef-18d7f895e7fa)