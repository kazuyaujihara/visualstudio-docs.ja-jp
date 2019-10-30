---
title: ワークフローでのフォームのサポート |Microsoft Docs
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, workflows
- workflows [SharePoint development in Visual Studio]
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: b064df6729b914af7758cde86b03b886fd0e5d26
ms.sourcegitcommit: dcbb876a5dd598f2538e62e1eabd4dc98595b53a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2019
ms.locfileid: "72986259"
---
# <a name="form-support-in-workflows"></a>ワークフローでのフォームのサポート
  ワークフローでは、アソシエーション、開始、タスク、および変更の4種類のフォームを使用できます。 これらのフォーム型は、ASPX フォームまたは InfoPath フォームに基づいて作成できます。 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] が特定のフォームに提供するサポートレベルは、次の表で説明されているいくつかの要因によって異なります。 ワークフローフォームの種類の詳細については、「[ワークフローフォームの概要](/previous-versions/office/developer/sharepoint-2010/ms457061(v=office.14))」を参照してください。

## <a name="xml-refactoring"></a>XML リファクタリング
 ASPX の関連付けまたは開始フォームを [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] ワークフロープロジェクト項目に追加すると [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] は、同期のアソシエーションまたは開始フォームを参照する属性を保持するために、ワークフローのリファクタファイルの XML を自動的に作成し*ます。* フォーム名または配置パスが更新されるか、フォームが削除されるたびに。 ただし、タスクや変更フォームなどの他のフォームの種類をワークフローで使用する場合、*要素 .xml*ファイルはリファクタリングされません。

## <a name="form-support-in-new-visual-studio-workflows"></a>新しい Visual Studio ワークフローでのフォームのサポート
 次の表に、[!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]で作成されるワークフローにおける、ASPX または InfoPath フォームでのさまざまなフォーム型のサポート [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 一覧を示します。

|フォームの種類|ASPX フォームを使用して Visual Studio で作成されたワークフロー|InfoPath フォームを使用して Visual Studio で作成されたワークフロー|
|---------------|---------------------------------------------------------|-----------------------------------------------------------------|
|関連付け|-ワークフロー**関連付け**フォーム項目テンプレートを使用して、ASPX 関連付けフォームをワークフローに追加できます。<br />-ワークフローの*要素 .xml*ファイルは、フォームが追加、名前変更、または削除されたとき、または配置パスが変更されたときにリファクタリングされます。<br />-詳細については、「[チュートリアル: 関連付けフォームと開始フォームを使用したワークフローの作成](../sharepoint/walkthrough-creating-a-workflow-with-association-and-initiation-forms.md)」を参照してください。|-[!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]に InfoPath アソシエーションフォームテンプレートがありません。<br />-[!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] と InfoPath デザイナーの間には統合がありません。<br />-ワークフローの*要素 .xml*ファイルはリファクタリングされません。|
|確立|-**ワークフロー開始**フォーム項目テンプレートを使用して、ASPX 開始フォームをワークフローに追加できます。<br />-ワークフローの*要素 .xml*ファイルは、フォームが追加、名前変更、または削除されたとき、または配置パスが変更されたときにリファクタリングされます。<br />-詳細については、「[チュートリアル: 関連付けフォームと開始フォームを使用したワークフローの作成](../sharepoint/walkthrough-creating-a-workflow-with-association-and-initiation-forms.md)」を参照してください。|-[!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]に InfoPath アソシエーションフォームテンプレートがありません。<br />-[!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] と InfoPath デザイナーの間には統合がありません。<br />-ワークフローの*要素 .xml*ファイルはリファクタリングされません。|
|タスク|-[!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]で使用できる ASPX タスクフォームテンプレートがありません。 アプリケーションページを作成し、それにコードを追加する必要があります。<br />-ワークフローの*要素 .xml*ファイルはリファクタリングされません。<br />-詳細については、「[ワークフロータスクフォーム (SharePoint Foundation)](/previous-versions/office/developer/sharepoint-2010/ms438856(v=office.14)) 」を参照してください。|-[!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]に InfoPath タスクフォームテンプレートがありません。<br />-[!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] と InfoPath デザイナーの間には統合がありません。<br />-ワークフローの*要素 .xml*ファイルはリファクタリングされません。|
|変更|-[!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]では、ASPX 変更フォームテンプレートは使用できません。 変更フォームを追加するには、アプリケーションページを作成してコードを追加する必要があります。<br />-ワークフローの*要素 .xml*ファイルはリファクタリングされません。 必要に応じて手動で編集する必要があります。<br />-詳細については、「[ワークフロー変更フォーム (SharePoint Foundation)](/previous-versions/office/developer/sharepoint-2010/ms480794(v=office.14)) 」を参照してください。|-[!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]に InfoPath 変更フォームテンプレートがありません。<br />-[!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] と InfoPath デザイナーの間には統合がありません。<br />-ワークフローの*要素 .xml*ファイルはリファクタリングされません。|

## <a name="form-support-in-imported-sharepoint-reusable-workflows"></a>インポートされた SharePoint 再利用可能なワークフローでのフォームのサポート
 次の表は、[!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]にインポートされる SharePoint の再利用可能なワークフローにおける、ASPX または InfoPath フォームでのさまざまなフォーム型のサポート [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 一覧です。

|フォームの種類|SharePoint デザイナーから ASPX フォームがインポートされた再利用可能なワークフロー|SharePoint デザイナーから InfoPath フォームをインポートした再利用可能なワークフロー|
|---------------|-------------------------------------------------------------------------------| - |
|関連付け|-フォームは、ワークフローの*Elements .xml*ファイルで参照されます。<br />-ワークフローの*要素 .xml*ファイルは、フォームの名前が変更されたり削除されたりしたとき、または配置パスが変更されたときにリファクタリングされます。|-フォームはインポートされますが、ワークフローの*要素 .xml*では参照されません。<br />-ワークフローの*要素 .xml*ファイルはリファクタリングされません。|
|確立|-フォームは、ワークフローの*要素 .xml*ファイル内のワークフローによって参照されます。<br />-ワークフローの*要素 .xml*ファイルは、フォームの名前が変更されたり削除されたりしたとき、または配置パスが変更されたときにリファクタリングされます。|-フォームはインポートされますが、ワークフローの*要素 .xml*では参照されません。<br />-ワークフローの*要素 .xml*ファイルはリファクタリングされません。 **注:** このシナリオを機能させるには、ルールとプロパティを追加して変更する必要があります。|
|タスク|-フォームは、ワークフローの*Elements .xml*ファイルで参照されます。<br />-ワークフローの*要素 .xml*ファイルはリファクタリングされません。|-フォームはインポートされますが、ワークフローの*要素 .xml*では参照されません。<br />-ワークフローの*要素 .xml*ファイルはリファクタリングされません。 **注:** このシナリオを機能させるには、ルールとプロパティを追加して変更する必要があります。|
|変更|該当しない。 SharePoint Designer で ASPX 変更フォームを作成することはできません。|該当しない。 SharePoint デザイナーで InfoPath 変更フォームを作成することはできません。ただし、ワークフローをエクスポートするときに、.wsp ファイルには含まれていません。|

## <a name="see-also"></a>関連項目
- [チュートリアル: 関連付けフォームと開始フォームを使用したワークフローの作成](../sharepoint/walkthrough-creating-a-workflow-with-association-and-initiation-forms.md)
- [SharePoint ワークフローソリューションの作成](../sharepoint/creating-sharepoint-workflow-solutions.md)
- [既存の SharePoint サイトからのアイテムのインポート](../sharepoint/importing-items-from-an-existing-sharepoint-site.md)
