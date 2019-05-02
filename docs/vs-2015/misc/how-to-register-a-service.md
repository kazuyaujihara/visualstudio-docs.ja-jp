---
title: '方法: サービスの登録 |Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: devlang-csharp
ms.topic: conceptual
helpviewer_keywords:
- services, registering
ms.assetid: d086be78-ec3c-43cc-b799-5180a71e19f1
caps.latest.revision: 16
manager: jillfra
ms.openlocfilehash: f41578f2522487f746a469933a2269a621390f3c
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "63408423"
---
# <a name="how-to-register-a-service"></a>方法: サービスを登録します。
Managed Package Framework (MPF) は、管理するサービスの登録を制御する属性を提供します。 RegPkg ユーティリティでは、これらの属性を使用して、 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]にサービスを登録します。  
  
## <a name="example"></a>例  
 次のコードは[VSSDK のサンプル](../misc/vssdk-samples.md)します。  
  
 [!code-csharp[VSSDKRegisterService#1](../snippets/csharp/VS_Snippets_VSSDK/vssdkregisterservice/cs/vssdkregisterservicepackage.cs#1)]
 [!code-vb[VSSDKRegisterService#1](../snippets/visualbasic/VS_Snippets_VSSDK/vssdkregisterservice/vb/vssdkregisterservicepackage.vb#1)]  
  
 <xref:Microsoft.VisualStudio.Shell.ProvideServiceAttribute> によって、[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] に SMyGlobalService サービスが登録されます。 詳細については<xref:Microsoft.VisualStudio.Shell.DefaultRegistryRootAttribute>と<xref:Microsoft.VisualStudio.Shell.PackageRegistrationAttribute>を参照してください[の登録および登録を解除する Vspackage](../extensibility/registering-and-unregistering-vspackages.md)します。  
  
 名前が同じ別のサービスを置き換えるサービスを登録するには、<xref:Microsoft.VisualStudio.Shell.ProvideServiceAttribute> ではなく <xref:Microsoft.VisualStudio.Shell.ProvideServiceOverrideAttribute> を使用します。  
  
## <a name="robust-programming"></a>信頼性の高いプログラミング  
 サービス クライアントを変更せずに、サービス プロバイダーの再コンパイルを容易にできるようにするか、またはその逆を実行するには、別のアセンブリ モジュールでサービスとそのインターフェイスを定義することができます。 次のコードは Reference.Services (C#) サンプルの IMyGlobalService.cs ファイルのものです。  
  
 [!code-csharp[VSSDKRegisterService#2](../snippets/csharp/VS_Snippets_VSSDK/vssdkregisterservice/cs/vssdkregisterservicepackage.cs#2)]
 [!code-vb[VSSDKRegisterService#2](../snippets/visualbasic/VS_Snippets_VSSDK/vssdkregisterservice/vb/vssdkregisterservicepackage.vb#2)]  
  
 アンマネージ コードからインターフェイスを取得するには、<xref:System.Runtime.InteropServices.ComVisibleAttribute> が必要です。  
  
> [!NOTE]
> サービスとインターフェイスの両方に同じ型または GUID を使用できますが、サービスが異なるインターフェイスを公開できるようにするために、2 つを分離することをお勧めします。  
  
## <a name="see-also"></a>関連項目  
 [Vspackage の登録](../extensibility/internals/registering-vspackages.md)   
 [サービスの基本情報](../extensibility/internals/service-essentials.md)