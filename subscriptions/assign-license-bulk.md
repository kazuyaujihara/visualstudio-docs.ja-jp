---
title: Visual Studio サブスクリプションのライセンスをユーザーのグループに割り当てる | Microsoft Docs
author: evanwindom
ms.author: lank
manager: lank
ms.date: 07/24/2019
ms.topic: conceptual
description: 管理者が複数のサブスクライバーにライセンスを割り当てる方法を説明します
ms.openlocfilehash: 7d54dcf3cf3e7fea7845a4e9a0053de4ba734ae9
ms.sourcegitcommit: ce1ab8a25c66a83e60eab80ed8e1596fe66dd85c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2019
ms.locfileid: "68610522"
---
# <a name="assign-subscriptions-to-multiple-users"></a>複数のユーザーにサブスクリプションを割り当てる
サブスクリプション管理ポータルでは、ユーザーを一度に 1 人ずつ追加することも、大きなグループ単位で追加することもできます。  ユーザーを個別に追加するには、[1 人のユーザーの追加](assign-license.md)に関する記事を参照してください。

## <a name="use-bulk-add-to-assign-subscriptions"></a>一括追加を使用してサブスクリプションを割り当てる
1. [https://manage.visualstudio.com](https://manage.visualstudio.com ) で Visual Studio サブスクリプション管理ポータルにサインインします。
2. 複数のサブスクライバーを一度に追加するには、 **[サブスクライバーの管理]** タブに移動します。上部リボンの **[一括追加]** をクリックします。
   > [!div class="mx-imgBorder"]
   > ![複数のサブスクライバーを追加する](media/add-multiple-subscribers.png)

2. 一括追加では、Microsoft Excel テンプレートを使用してサブスクライバー情報をアップロードします。 [Upload Multiple Subscribers]\(複数のサブスクライバーのアップロード\) ダイアログ ボックスで、 **[ダウンロード]** をクリックしてテンプレートをダウンロードします。
   > [!div class="mx-imgBorder"]
   > ![複数のサブスクライバーをアップロードするための Excel テンプレートをダウンロードする](media/download-template-upload-subscribers.png)
   >
   > [!NOTE]
   > 常にこのテンプレートの最新バージョンをダウンロードしてください。 古いバージョンを使うと、一括アップロードが失敗する可能性があります。

3. Excel スプレッドシートのフィールドに、サブスクリプションを割り当てるユーザーの情報を入力します。 *[Reference]* は省略可能なフィールドです。完成したらローカルにファイルを保存します。

   問題なくアップロードできるよう、次のベスト プラクティスに従ってください。

    - フォームのどのフィールドにもコンマが含まれていないことを確認します。
    - フォームのフィールドの前後のスペースを削除します。
    - ユーザーの名前の名または姓が 2 つの部分からなる場合、それらの間に余分なスペースがないようにします (たとえば、"Maggie May" のように 2 つの部分からなる名前は、"MaggieMay" と入力する必要があります。システムは余分なスペースを除去しません)。

4. Visual Studio サブスクリプション管理ポータルに戻ります。 **[Upload Multiple Subscribers]\(複数のサブスクライバーのアップロード\)** ダイアログ ボックスで、 **[参照]** をクリックします。
   > [!div class="mx-imgBorder"]
   > ![複数のサブスクライバーをアップロードするために保存したテンプレートを参照する](media/bulk-add-browse-saved-template.png)

5. 保存した Excel ファイルを選んで、 **[OK]** をクリックします。
   > [!div class="mx-imgBorder"]
   > ![複数のサブスクライバーをアップロードするための Excel テンプレートをアップロードする](media/bulk-upload-subscribers.png)

    アップロードの進行状況を示すダイアログが表示されます。

    テンプレートにエラーが含まれていると、アップロードは失敗してエラーが表示されるので、テンプレートを修正して一括アップロードを再試行します。
   > [!div class="mx-imgBorder"]
   > ![複数サブスクライバーのアップロードが失敗した場合のエラー メッセージ](media/bulk-add-template-failed.png)

    アップロードが成功すると、サブスクライバーの一覧と確認メッセージが表示されます。
   > [!div class="mx-imgBorder"]
   > ![複数サブスクライバーのアップロードが成功した場合の確認メッセージ](media/bulk-add-template-success.png)

## <a name="next-steps"></a>次の手順
- 追加するサブスクライバーは 1 人または 2 人だけですか?  [1 人のユーザーの追加](assign-license.md)に関する記事を参照してください。
- 既存のサブスクリプションの[編集](edit-license.md)方法をご確認ください。
- お困りの際は、 [Visual Studio の管理とサブスクリプションのサポート](https://visualstudio.microsoft.com/support/support-overview-vs)にお問い合わせください。
