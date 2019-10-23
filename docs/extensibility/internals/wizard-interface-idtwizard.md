---
title: Wizard インターフェイス (IDTWizard) |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- IDTWizard interface
- wizards, interface
ms.assetid: 09618d9d-d115-45b6-bccc-de328994b39c
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: f571fbd0a68ddbf56b637071ac250159461f61d1
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72721527"
---
# <a name="wizard-interface-idtwizard"></a>ウィザード インターフェイス (IDTWizard)
統合開発環境 (IDE: integrated development environment) は、<xref:EnvDTE.IDTWizard> インターフェイスを使用してウィザードと通信します。 ウィザードは、IDE にインストールするために、このインターフェイスを実装する必要があります。

 @No__t_0 メソッドは、<xref:EnvDTE.IDTWizard> インターフェイスに関連付けられている唯一のメソッドです。 ウィザードはこのメソッドを実装し、IDE はインターフェイスに対してメソッドを呼び出します。 次の例は、メソッドのシグネチャを示しています。

```
/* IDTWizard Method */
STDMETHOD(Execute)(THIS_
   /* [in] */ IDispatch *Application,
   /* [in] */ long hwndOwner,
   /* [in] */ SAFEARRAY * *ContextParams,
   /* [in] */ SAFEARRAY * *CustomParams,
   /* [out] [in] */ wizardResult *RetVal
   );
```

 開始メカニズムは、**新しいプロジェクト**と**新しい項目の追加**ウィザードの両方で似ています。 どちらかを開始するには、Dteinternal. h で定義されている <xref:EnvDTE.IDTWizard> インターフェイスを呼び出します。 唯一の違いは、インターフェイスが呼び出されたときにインターフェイスに渡されるコンテキストとカスタムパラメーターのセットです。

 ここでは、[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE で動作するためにウィザードで実装する必要がある <xref:EnvDTE.IDTWizard> インターフェイスについて説明します。 IDE は、ウィザードの <xref:EnvDTE.IDTWizard.Execute%2A> メソッドを呼び出し、次のように渡します。

- DTE オブジェクト

     DTE オブジェクトは、オートメーションモデルのルートです。

- コードセグメントに示されているように、ウィンドウのダイアログボックスを `hwndOwner ([in] long)` するハンドル。

     ウィザードでは、この `hwndOwner` をウィザードのダイアログボックスの親として使用します。

- コードセグメントに示されているように、SAFEARRAY のバリアントとしてインターフェイスに渡されるコンテキストパラメーター `[in] SAFEARRAY (VARIANT)* ContextParams`。

     コンテキストパラメーターには、開始するウィザードの種類とプロジェクトの現在の状態に固有の値の配列が含まれます。 IDE は、コンテキストパラメーターをウィザードに渡します。 詳細については、「[コンテキストパラメーター](../../extensibility/internals/context-parameters.md)」を参照してください。

- コードセグメントに示されているように、SAFEARRAY のバリアントとしてインターフェイスに渡されるカスタムパラメーター (`[in] SAFEARRAY (VARIANT)* CustomParams`)。

     カスタムパラメーターには、ユーザー定義パラメーターの配列が含まれています。 .Vsz ファイルは、IDE にカスタムパラメーターを渡します。 値は、`Param=` ステートメントによって決定されます。 詳細については、「[カスタムパラメーター](../../extensibility/internals/custom-parameters.md)」を参照してください。

- インターフェイスの戻り値は、

    ```
    wizardResultSuccess = -1,
    wizardResultFailure = 0
    wizardResultCancel = 1
    wizardResultBackout = 2
    ```

## <a name="see-also"></a>関連項目
- [コンテキスト パラメーター](../../extensibility/internals/context-parameters.md)
- [カスタム パラメーター](../../extensibility/internals/custom-parameters.md)
- [ウィザード](../../extensibility/internals/wizards.md)
- [ウィザード (.Vsz) ファイル](../../extensibility/internals/wizard-dot-vsz-file.md)