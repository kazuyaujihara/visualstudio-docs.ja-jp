---
title: Vspackage | のリソースMicrosoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- managed VSPackages, resources in
- resources, managed VSPackages
- VSPackages, managed resources
ms.assetid: cc8c17a6-b190-4856-b001-0c1104f104b2
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 07e1e19f802203b9770764330ea894b7d0eb98b8
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72724155"
---
# <a name="resources-in-vspackages"></a>VSPackage のリソース
ローカライズされたリソースは、ネイティブサテライト UI Dll、マネージサテライト Dll、またはマネージ VSPackage 自体に埋め込むことができます。

 一部のリソースは Vspackage に埋め込むことができません。 次のマネージ型を埋め込むことができます。

- 文字列

- パッケージ読み込みキー (文字列でもあります)

- ツールウィンドウのアイコン

- コンパイルされたコマンドテーブル出力 (CTO) ファイル

- CTO ビットマップ

- コマンドラインヘルプ

- ダイアログボックスのデータについて

  マネージパッケージ内のリソースは、リソース ID によって選択されます。 例外は、CTO ファイルです。このファイルには、CTMENU という名前を付ける必要があります。 CTO ファイルは、リソーステーブルに `byte[]` として表示される必要があります。 他のすべてのリソース項目は、型によって識別されます。

  @No__t_0 属性を使用して、マネージリソースが使用可能であることを [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] を示すことができます。

  [!code-csharp[VSSDKResources#1](../../extensibility/internals/codesnippet/CSharp/resources-in-vspackages_1.cs)]
  [!code-vb[VSSDKResources#1](../../extensibility/internals/codesnippet/VisualBasic/resources-in-vspackages_1.vb)]

  この方法で <xref:Microsoft.VisualStudio.Shell.PackageRegistrationAttribute> を設定すると、<xref:Microsoft.VisualStudio.Shell.Interop.IVsShell.LoadPackageString%2A> などを使用してリソースを検索するときに、[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] がアンマネージサテライト Dll を無視するように指定します。 同じリソース ID を持つ2つ以上のリソースが検出された [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 場合は、検出された最初のリソースが使用されます。

## <a name="example"></a>例
 次の例は、ツールウィンドウアイコンのマネージ表現です。

```
<data name="1001"
type="System.Resources.ResXFileRef,System.Windows.Forms">
     <value>
     MyToolWinIcon.bmp;
     System.Drawing.Bitmap,
     System.Drawing,
     Version=1.0.0.0,
     Culture=neutral,
     PublicKeyToken=b03f5f7f11d50a3a
     </value>
</data>
```

 次の例は、CTO のバイト配列を埋め込む方法を示しています。この配列には、CTMENU という名前を付ける必要があります。

```
<data name="CTMENU"
type="System.Resources.ResXFileRef,System.Windows.Forms">
     <value>
     MyPackage.cto;
     System.Byte[],
     mscorlib,
     Version=1.0.0.0,
     Culture=neutral,
     PublicKeyToken=b03f5f7f11d50a3a
     </value>
</data>
```

## <a name="implementation-notes"></a>実装に関する注意事項
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] は、可能な限り Vspackage の読み込みを遅延します。 VSPackage に CTO ファイルを埋め込むと、セットアップ中に、マージされたコマンドテーブルを作成するときに、このようなすべての Vspackage をメモリに読み込む必要 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] があります。 リソースを VSPackage から抽出するには、VSPackage でコードを実行せずにメタデータを調べます。 VSPackage は現時点で初期化されていないため、パフォーマンスが低下することは少なくありません。

 セットアップ後に VSPackage からリソースを要求する [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] と、そのパッケージは既に読み込まれて初期化される可能性があるため、パフォーマンスが低下することは少なくありません。

## <a name="see-also"></a>関連項目
- [VSPackage の管理](../../extensibility/managing-vspackages.md)
- [MFC アプリケーションのローカライズされたリソース: サテライト DLL](/cpp/build/localized-resources-in-mfc-applications-satellite-dlls)
