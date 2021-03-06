---
title: ファイル名拡張子について |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- file extensions
- file name extensions
ms.assetid: 99f4f9ff-fb84-4258-9787-6890f308a57f
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: fd181bb7daca21ff263dcb7989a0aecbef3ed278
ms.sourcegitcommit: 8ee7efb70a1bfebcb6dd9855b926a4ff043ecf35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/17/2018
ms.locfileid: "39081697"
---
# <a name="about-file-name-extensions"></a>ファイル名拡張子について
バージョンを関連付ける場合、VSPackage のファイル拡張子を登録するときに[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]します。 これは、1 つのバージョンではより重要な場合は[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]をコンピューターにインストールされます。  
  
 Vspackage のファイル拡張子が登録されている**HKEY_CLASSES_ROOT**キーに関連付けられているなプログラム識別子 (ProgID) を指す既定値。  
  
 次の例の登録情報を示しています、 *.vcproj*ファイル拡張子。  
  
```  
HKEY_CLASSES_ROOT\  
   .vcproj\  
      (default)=" VisualStudio.vcproj.8.0"   
```  
  
 ファイルに関連付けられている[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]バージョン管理された ProgID などがあります`VisualStudio.vcproj.8.0`します。 バージョン管理された ProgID は、製品のバージョン間でファイル拡張子の関連付けを維持するために、製品のサイド バイ サイドでインストールできます。 バージョン固有の ProgID では、オープン、編集などと、上書きやその他のアプリケーションまたはのバージョンで上書きされるの気にせず、標準の動詞を使用することもできます[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]します。  
  
 場合によっては、ファイル拡張子に関連付けられている ProgID を変更しない必要があります。 などの ProgID を *.htm*ファイル拡張子 (progid htmlfile =) は、さまざまなオペレーティング システムの場所でハード コーディングし、広く知られで使用される関連付けられている *.htm*と *.html*ファイル。  
  
## <a name="see-also"></a>関連項目  
 [サイド バイ サイドで配置のファイル名拡張子を登録します。](../extensibility/registering-file-name-extensions-for-side-by-side-deployments.md)   
 [ファイル名拡張子のファイル ハンドラーを指定します。](../extensibility/specifying-file-handlers-for-file-name-extensions.md)