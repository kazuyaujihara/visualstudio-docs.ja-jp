---
title: 別名を使用した Visual Studio サブスクリプションへのサインインが失敗する場合がある | Microsoft Docs
author: evanwindom
ms.author: lank
manager: lank
ms.date: 07/19/2019
ms.topic: conceptual
description: 別名またはフレンドリ名の使用でサインインに失敗する場合がある
ms.openlocfilehash: 392b86699b1116f45ca75df3b611fff6a2aebc62
ms.sourcegitcommit: 485881e6ba872c7b28a7b17ceaede845e5bea4fe
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/22/2019
ms.locfileid: "68378026"
---
# <a name="signing-in-to-visual-studio-subscriptions-may-fail-when-using-aliases"></a>別名を使用した Visual Studio サブスクリプションへのサインインが失敗する場合がある
サインインに使用されるアカウントの種類によっては、[https://my.visualstudio.com](https://my.visualstudio.com?wt.mc_id=o~msft~docs) にサインインするときに利用可能なサブスクリプションが正しく表示されない場合があります。 考えられる原因の 1 つは、サブスクリプションが割り当てられているサインイン ID の代わりに "別名" または "表示名" を使用していることです。 これは "別名定義" と呼ばれます。

## <a name="what-is-aliasing"></a>別名定義とは
"別名定義" という用語は、Windows (または Active Directory) へのサインインと電子メールへのアクセスに別々の ID を持っているユーザーを指します。

別名定義は、"JohnD@contoso.com" のように、会社が自社のディレクトリのサインイン用に Microsoft オンライン サービスを持っているが、ユーザーは "John.Doe@contoso.com" などの別名や表示名を使用して自分の電子メール アカウントにアクセスしている場合に発生する場合があります。 ボリューム ライセンス サービス センター (VLSC) を介してサブスクリプションを管理している多くのユーザーにとって、これがサインインが失敗する原因となる場合があります。指定したメール アドレス ("John.Doe@contoso.com") が、"職場または学校アカウント" オプションを通じて正常に認証するために必要なディレクトリ アドレス ("JohnD@contoso.com") と一致していないからです。

## <a name="as-an-administrator-what-options-do-i-have"></a>管理者として選択できるオプションとは
管理者には、[https://my.visualstudio.com](https://my.visualstudio.com?wt.mc_id=o~msft~docs) でユーザーのサインインを確実に成功させるために、次の 2 つのオプションがあります。
- 1 番目のオプション (推奨) は、ディレクトリ アカウントをボリューム ライセンス サービス センター (VLSC) で割り当てられたアドレスとして利用することです。 詳細については、この記事の「[サブスクライバーをディレクトリ アカウントに割り当てる](#assigning-subscribers-to-a-directory-account)」セクションを参照してください。
- 2 番目のオプション (安全性で劣る) は、サブスクライバーに自身の "職場または学校" のメール アドレスを "個人用" アカウント (別名: Microsoft アカウント (MSA)) に関連付けることを許可することです。 詳細については、この記事の「[職場または学校アカウントを個人用アカウントとして定義する](#defining-a-work-or-school-account-as-a-personal-account)」セクションを参照してください。

> [!NOTE]
> 会社が新しい Visual Studio サブスクリプションの[管理ポータル](https://manage.visualstudio.com)に移行すると、ディレクトリとメール アドレスの両方をサブスクライバーのプロファイルの一部として指定できる、新しい管理エクスペリエンスが利用できるようになります。 移行の詳細については、[こちら](https://support.microsoft.com/help/4013930/visual-studio-subscriptions-administrator-migration-details)をご覧ください。

## <a name="assigning-subscribers-to-a-directory-account"></a>サブスクライバーをディレクトリ アカウントに割り当てる
いずれのケースでも、ボリューム ライセンス サービス センター (VLSC) 内のサブスクリプション マネージャーは、新しいサブスクライバーのディレクトリ アドレスを使用するか、"既存の" サブスクライバーの電子メール アドレスを更新する必要があります。 ディレクトリ アドレスを使用すると、新しいサブスクライバーがウェルカム メールを受信しないため、管理者がサブスクライバーにサブスクリプションが割り当てられたことを通知する必要があることに注意してください。 次の手順を実行してから、自由にメール [テンプレート](#notifying-your-subscribers-with-directory-addresses)を使ってサブスクライバーに通知し、サインイン プロセスを支援してください。

### <a name="adding-new-subscribers"></a>新しいサブスクライバーを追加する
次の手順に従って、ディレクトリ アカウントを使用して新しいサブスクライバーを追加します。

1. [ボリューム ライセンス サービス センター](https://www.microsoft.com/Licensing/servicecenter/default.aspx) (VLSC) にアクセスしてサインインします。
2. VLSC の管理ページから、 **[サブスクリプション]** 、 **[Visual Studio サブスクリプション]** の順にクリックします。

    > [!div class="mx-imgBorder"]
    > ![サブスクリプション メニュー](_img//vlsc/vlsc-subscriptions.png)

3. Visual Studio サブスクリプションに関連付けられている**契約番号**をクリックします。

    > [!div class="mx-imgBorder"]
    > ![契約の選択](_img/vlsc/vlsc-agreement.png)

4. **[サブスクリプションの割り当て]** をクリックします。
5. 目的の**サブスクリプション レベル**を選択します。
6. サブスクリプションが割り当て可能になっていることを確認し、 **[次へ]** をクリックします。
7. サブスクライバーの詳細と [電子メール アドレス] フィールドにディレクトリ アドレスを入力し、 **[次へ]** をクリックします。
8. サブスクライバー情報を確認し、 **[完了]** をクリックします。
9. 下記の[テンプレート](#notifying-your-subscribers-with-directory-addresses)を使用して、サブスクリプションがプロビジョニングされたことをサブスクライバーに通知します。

### <a name="updating-an-existing-subscriber"></a>既存のサブスクライバーを更新する
次の手順に従って、ディレクトリ アカウントを使用して既存のサブスクライバーを更新します。

1. [ボリューム ライセンス サービス センター](https://www.microsoft.com/Licensing/servicecenter/default.aspx) (VLSC) にアクセスしてサインインします。
2. VLSC の管理ページから、 **[サブスクリプション]** 、 **[Visual Studio サブスクリプション]** の順にクリックします。
3. Visual Studio サブスクリプションに関連付けられている**契約番号**をクリックします。
4. **検索**バーで下矢印をクリックします。
5. [電子メール アドレス] フィールドを使用してサブスクライバーを検索します。
6. 結果リストからサブスクライバーの**姓**をクリックします。
7. **[編集]** をクリックします。
8. [電子メール アドレス] フィールドを目的のディレクトリ アドレスに変更し、 **[保存]** をクリックします。
9. 下記のメール テンプレートを使用して、サブスクリプションがプロビジョニングされたことをサブスクライバーに通知します。

### <a name="notifying-your-subscribers-with-directory-addresses"></a>ディレクトリ アドレスを使用してサブスクライバーに通知する
ウェルカム メールがサブスクライバーに正常に送信されないため、次のメッセージをコピーして電子メールに貼り付け、サブスクライバーに送信します。 %用語% の部分を各サブスクライバーに適した情報に置き換えます。

```
----------- Copy Below (Ctrl+C) -----------

Hello %SUBSCRIBER NAME%

You have been assigned a Visual Studio subscription. Please visit https://my.visualstudio.com, and log in with your %DIRECTORY ADDRESS% address to activate and access your subscription.

If you’re having trouble, please contact the support team (https://visualstudio.microsoft.com/subscriptions/support/).

At the bottom of the page, select the following:
   - Accounts, Subscriptions, and Billing Support
   - From Issue, choose Subscription sign in support
   - Choose the appropriate Country
   - Select the desired Assisted Support option

----------- End Copy -----------
```

## <a name="defining-a-work-or-school-account-as-a-personal-account"></a>職場または学校アカウントを個人用アカウントとして定義する
「[サブスクライバーをディレクトリ アカウントに割り当てる](#assigning-subscribers-to-a-directory-account)」セクションに記載した指示に従って、新しいユーザーを追加するか、ボリューム ライセンス サービス センター (VLSC) 内でユーザーのメール アドレスを更新します。  メール アドレスがディレクトリで認識されない場合は、ユーザーがプロセスを実行して新しいアカウントを作成し、個人用アカウントとしてメール アドレスを定義する必要があります。  短期的には、Visual Studio サブスクリプション チームは、以下で定義されている ID ポリシーの免除を保証されていますが、マイクロソフトではこのポリシーを除去するために必要な機能に投資しています。

> [!WARNING]
> "職場または学校" の ID を "個人用" の ID と組み合わせることはお勧めできません。  これを行うと、組織がアカウントの所有権と制御を失い、従業員が退職後でも特定の製品やサービスに引き続きアクセスできてしまいます。  

### <a name="defining-an-email-address-as-a-personal-account"></a>メール アドレスを個人用アカウントとして定義する
サブスクリプションがサブスクライバーに割り当てられると、サブスクライバーは、[https://my.visualstudio.com](https://my.visualstudio.com?wt.mc_id=o~msft~docs) にアクセスしてサブスクリプションの特典を利用するように求めるメールを受信します。  サインインしようとすると、アカウントが認識されないことを示すエラーで Visual Studio サブスクリプションのサインインが失敗します。  [https://my.visualstudio.com](https://my.visualstudio.com?wt.mc_id=o~msft~docs) にログインする前に、サブスクライバーに次の手順を行うように求めます。  必要に応じて、サブスクリプションを割り当てた後、この[テンプレート](#notifying-your-subscribers-using-personal-accounts)を使用してサブスクライバーに通知できます。

1. [https://my.visualstudio.com](https://my.visualstudio.com ) にアクセスして、 **[新しい Microsoft アカウントを作成する]** をクリックします。

2. フィールドに入力します。
   - Someone@example.com ボックスにウェルカム メールを受信したメール アドレスを入力します。
   - パスワードを作成します。
   - キャンペーンの設定を選択します。
   - **[次へ]** をクリックします。

3. 検証手順を実行して、 **[次へ]** をクリックします。

4. 場合によっては、新しいユーザーは、Visual Studio のプロファイルを完成させる必要があります。

5. これでサブスクリプションと特典が表示されます。

### <a name="notifying-your-subscribers-using-personal-accounts"></a>個人用アカウントを使用してサブスクライバーに通知する
上記で説明したシナリオでは、サブスクライバーは "ウェルカム メール" を受信しますが、別名定義によりサブスクライバーがサインインできない場合があります。  次のテキストを使用して、サブスクライバーに上記の手順を通知し、必要に応じてサポート オプションを勧めることができます。  %用語% の部分を各サブスクライバーに適した情報に置き換えます。

```
----------- Copy Below (Ctrl+C) -----------

Hello %SUBSCRIBER NAME%

You have been assigned a Visual Studio subscription, and may have been directed to log into https://my.visualstudio.com based on your Welcome email.  While this is the correct website for consuming benefits, our organization requires you to take a few extra steps before you can access the site.  Please follow the below instructions to help you create a “Microsoft Account” that is tied to our corporate email address.  Once these steps are completed, you will use your email address to access the Subscription benefits.
1. Visit https://my.visualstudio.com

2. Click Create new Microsoft Account on the right hand side

3. Complete the Form:
   - Use your corporate email address in the someone@example.com box
   - Enter a password
   - Select your promotional preference
   - Click Next

4. Complete the account validation steps

5. If necessary, complete the Visual Studio profile

6. You should now see your benefits

Note:  When visiting https://my.visualstudio.com in the future, you may be prompted to select which account you’d like to use (e.g. “Work or School Account” or “Personal Account”).  After following the steps above, you will need to leverage the “Personal Account” option.

If you’re having trouble, please contact the support team (https://visualstudio.microsoft.com/subscriptions/support/).

At the bottom of the page, select the following:
   - Accounts, Subscriptions, and Billing Support
   - From Issue, choose Subscription sign in support
   - Choose the appropriate Country
   - Select the desired Assisted Support option

----------- End Copy -----------
```
