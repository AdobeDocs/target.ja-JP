---
keywords: redirect offer;create redirect offer;add html offer;Pass all URL parameters in redirect;Pass mboxSessionId in redirect (only needed when the redirect is going to a different domain)
description: ブラウザーが新しいページにリダイレクトされる Adobe Target のリダイレクトオファーについて説明します。
title: リダイレクトオファーの作成
topic: Standard
uuid: 54336965-a26e-47c3-b3bc-079d3573502a
translation-type: tm+mt
source-git-commit: 65a4fd0d05ad065c9291a83dc0b3066451f7373e

---


# リダイレクトオファーの作成{#create-redirect-offers}

リダイレクトオファーを使用すると、ブラウザーで新しいページへのリダイレクトがおこなわれます。

ページ内でコンテンツの一部を変更するのではなく、まったく異なる 2 つのページをテストすることができます。この場合、A/B テストではページ A とページ B を比較します。A/B テストキャンペーンを 2 つのエクスペリエンスで設定します。1 つはデフォルトのページ A をポイントするエクスペリエンス、もう 1 つはページ B にリダイレクトするエクスペリエンスです。訪問者を別のページにリダイレクトするオファーが設定されます。

>[!NOTE] {class=&quot;- topic/note &quot;}
>
>ajax mbox（`mboxUpdate`）では、リダイレクトオファーは使用できません。
>
>A4T を使用してアクティビティでリダイレクトオファーを使用する場合、実装が特定の最小要件を満たす必要があります。また、知っておくべき重要な情報があります。詳しくは、[リダイレクトオファー - A4T に関する FAQ](../../c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905) を参照してください。

リダイレクトするエクスペリエンスの設定については、[URL にリダイレクト](../../c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA)を参照してください。

リダイレクトオファーでは、JavaScript コードを実行してブラウザーをリダイレクトします。このオファーでは `window.location.replace();` メソッドを使用するので、訪問者のリダイレクト元のページはブラウザー履歴に保存されません。そのため、訪問者はブラウザーの「戻る」ボタンを引き続き使用できます。

>[!NOTE] {class=&quot;- topic/note &quot;}
>
>ランディングページのリファラー値を渡す場合、リダイレクトオファーではなく HTML オファーを使用することをお勧めします。

**リダイレクトオファーを作成する手順は次のとおりです。**

1. 「**[!UICONTROL オファー]**」をクリックしてから、「**[!UICONTROL コードオファー]**」タブを選択します。
1. **[!UICONTROL 作成]**／**[!UICONTROL リダイレクトオファー]**&#x200B;をクリックします。
1. オファー名を入力します。
1. 一意のコンテンツまたはリダイレクト先の URL を入力します。この URL は絶対 URL にする必要があります。

   >[!NOTE]
   >
   >リダイレクト URL で、ユーザーが同一のアクティビティの条件も満たしていると見なされる場合、リダイレクトオファーが無限ループに陥るという情報を追加しました。リダイレクト後は、ユーザーがアクティビティの条件を再度満たすことがないようにする必要があります。

1. 目的のオプションを選択してリダイレクトオファーをカスタマイズします。

* **すべての URL パラメーターを含める：**&#x200B;リダイレクト前のページにあるすべての URL パラメーターをリダイレクト先のページに渡す場合は、このチェックボックスを選択します。

   例えば、男性向け商品のページから男性向けシャツカテゴリのページにユーザーを直接リダイレクトする場合などです。また、URL で動的なパラメーターを渡して、ユーザーが電子メール、バナー広告、検索広告経由でサイトに到達したか、または別の経路でサイトに到達したかを追跡する必要もあります。URL ボックスに [!DNL `https://www.mycompany.com/mens.html?emailId=123`] だけを入力した場合、このチェックボックスをオンにすると、[!DNL `https://www.mycompany.com/mensShirts.html?emailId=123`] のページのリダイレクトオファーが自動的に [!DNL `https://www.mycompany.com/mensShirts.html`] になります。

* **リダイレクト時に mbox セッション ID を渡す (別のドメインにリダイレクトするときに必要)：**&#x200B;リダイレクトに `sessionId` を自動的に含める場合にこのボックスをオンにします。これが必要なのは、電子メールからのクリックまたはドメイン間のクリックをテストする場合のみです。この `sessionId` を使用して訪問者の Cookie を照合し、訪問者を引き続き追跡して適切なコンテンツが表示されるようにします。

   ファーストパーティおよびサードパーティ Cookie の設定を使用する場合は、異なるドメインにアクセスするときに mbox セッション ID を渡す必要はありません。この値はサードパーティ Cookie に保持されているため、URL に含める必要がないからです。

>[!NOTE] {class=&quot;- topic/note &quot;}
>
>このようなテストを開始する場合は、導入コンサルタントにお問い合わせください。

## トレーニングビデオ：コンテンツリポジトリ（4:56） 概 ![要バッジ](/help/assets/overview.png)

このビデオでは、コンテンツの管理について説明します。

* [Experience Cloud アセットライブラリ](https://docs.adobe.com/content/help/en/core-services/interface/assets/creative-cloud.html)と Target コンテンツライブラリの間の接続
* カスタム HTML オファー
* Visual Experience Composer のカスタム HTML オファー

>[!VIDEO](https://video.tv.adobe.com/v/17387)
