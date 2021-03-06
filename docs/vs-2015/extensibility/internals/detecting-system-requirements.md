---
title: システム要件の検出 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- setup, VSPackages
- launch conditions
ms.assetid: 0ba94acf-bf0b-4bb3-8cca-aaac1b5d6737
caps.latest.revision: 51
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7d92d895b0986a8a6df888d4bea258f9dab067e8
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2018
ms.locfileid: "49880560"
---
# <a name="detecting-system-requirements"></a>システム要件の検出
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Visual Studio がインストールされていない場合、VSPackage は機能できません。 Microsoft Windows インストーラーを使用して、VSPackage のインストールを管理する場合は、Visual Studio がインストールされているかどうかを検出するインストーラーを構成できます。 など、システムの他の要件を確認して、特定のバージョンの Windows または特定の容量の RAM を構成することもできます。  
  
## <a name="detecting-visual-studio-editions"></a>Visual Studio のエディションを検出します。  
 Visual Studio のエディションがインストールされているかどうかを判断するには、ことを確認インストールのレジストリ キーの値 (REG_DWORD) で、適切なフォルダーでは、1 次の表に記載されています。 Visual Studio のエディションの階層があることに注意してください。  
  
1. エンタープライズ  
  
2. 2 次元形式  
  
3. コミュニティ  
  
   「高」のエディションがインストールされている場合、そのエディションを"lower"エディションの場合と同様のレジストリ キーが追加されます。 つまり、Enterprise edition がインストールされている場合は、インストール キーが 1 の Enterprise、および Professional および Community エディションに設定されます。 そのために、必要があります「最高」エディションのみを確認する必要があります。  
  
> [!NOTE]
>  レジストリ エディターの 64 ビット バージョンで 32 ビットのキーは hkey_local_machine \software\wow6432node 下に表示されて\\します。 Visual Studio のキーは HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\DevDiv\vs\Servicing\\します。  
  
|製品|キー|  
|-------------|---------|  
|Visual Studio Enterprise 2015|HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\DevDiv\vs\Servicing\14.0\enterprise|  
|Visual Studio Professional 2015|HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\DevDiv\vs\Servicing\14.0\professional|  
|Visual Studio Community 2015|HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\DevDiv\vs\Servicing\14.0\community|  
|Visual Studio 2015 Shell (統合シェルと分離)|HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\DevDiv\vs\Servicing\14.0\isoshell|  
  
## <a name="detecting-when-visual-studio-is-running"></a>Visual Studio が実行中の検出  
 VSPackage は、VSPackage のインストール時に Visual Studio が実行されている場合、正しく登録できません。 インストーラーは、Visual Studio が実行されているときに検出され、プログラムのインストールを拒否しする必要があります。 Windows インストーラーではテーブルのエントリを使用して、このような検出を有効にできます。 代わりに、カスタムの動作を次のように作成する必要があります使用して、`EnumProcesses`関数を、devenv.exe プロセスを検出し、起動条件または条件付きで使用されるインストーラー プロパティを設定するかを、ユーザーを閉じるを求めるダイアログ ボックスを表示します。Visual Studio。  
  
## <a name="see-also"></a>関連項目  
 [Windows インストーラーによる VSPackage のインストール](../../extensibility/internals/installing-vspackages-with-windows-installer.md)

