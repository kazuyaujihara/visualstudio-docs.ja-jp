---
title: プロジェクトの種類を作成する場合 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- project types, conditions for creating
ms.assetid: 26adc860-ee4a-4f5c-95e1-e41b207dd7e6
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ff29843965c220c505266a9cd973e5695c0b9dab
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72721562"
---
# <a name="when-to-create-project-types"></a>プロジェクト タイプを作成する状況
新しいプロジェクトの種類を作成すると、ユーザーの [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] をカスタマイズするための基礎となります。 ただし、[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] のすべてのカスタマイズでは、新しいプロジェクトの種類を作成する必要はありません。 次のガイドラインは、シナリオに新しいプロジェクトの種類が必要かどうかを判断するのに役立ちます。

## <a name="create-a-new-project-type"></a>新しいプロジェクトの種類を作成する
 次の1つまたは複数の方法で動作するように [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] をカスタマイズする場合は、プロジェクトの種類を作成する必要があります。

- ビルド、配置、構成、ソース管理に参加します。

- デバッグサポートを提供します。

- **ソリューションエクスプローラー**にプロジェクト項目を表示します。

- **[プロジェクトを開く]** または **[新しいプロジェクト]** ダイアログボックスを使用します。

- プロジェクトの入れ子をサポートします。

## <a name="extend-an-existing-project-type"></a>既存のプロジェクトの種類を拡張する
 既存のプロジェクトの種類の動作を変更または拡張するために、次の方法で [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] を使用できる新しいプロジェクトの種類を作成することもできます。たとえば、[!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] プロジェクトのビルドプロセスを変更できます。

- 複数のファイルを1つの単位として操作します。

- サブ項目の階層として1つのファイルを表示します。

- エディターの周囲にコマンドコンテキストを表示します。

- エディターのサービスコンテキストを表示します。

## <a name="use-an-existing-project-type"></a>既存のプロジェクトの種類を使用する
 新しいプロジェクトを作成する必要はない場合があります。 次の表に、プロジェクトの種類を作成する必要がないタスクを示します。

|タスク|説明|
|----------|-----------------|
|コマンドの処理|VSPackage は、コマンドを処理できます。|
|エディターのビルド|カスタムエディターを登録できます。 詳細については、「[ドキュメントウィンドウとエディター](https://msdn.microsoft.com/library/603625e1-62b6-413a-bc44-089346e166bc)」を参照してください。|
|所有しているウィンドウ|新しいプロジェクトの種類を追加せずに、ツールウィンドウとドキュメントウィンドウの両方を作成できます。|
|プロパティウィンドウでのプロパティの公開|すべてのオブジェクトがプロパティを公開できます。|

## <a name="create-a-project-subtype"></a>プロジェクトのサブタイプを作成する
 プロジェクトのサブタイプを使用して、新しいプロジェクトの種類を作成することなく、マネージプロジェクトの種類を拡張することができます。 プロジェクトのサブタイプは、COM 集計を使用して、Microsoft [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] または [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] で記述されたマネージプロジェクトを拡張します。 COM 集計を使用すると、マネージプロジェクトシステムの実装の大部分を再利用しながら、集計やサポートインターフェイスを使用して特定のシナリオに合わせてカスタマイズできます。 プロジェクトのサブタイプの詳細については、「[プロジェクトのサブタイプ](../../extensibility/internals/project-subtypes.md)」を参照してください。

## <a name="see-also"></a>関連項目
- [ドキュメントウィンドウとエディター](https://msdn.microsoft.com/library/603625e1-62b6-413a-bc44-089346e166bc)
- [チェック リスト: 新しいプロジェクト タイプの作成](../../extensibility/internals/checklist-creating-new-project-types.md)
- [Visual Studio での階層](../../extensibility/internals/hierarchies-in-visual-studio.md)