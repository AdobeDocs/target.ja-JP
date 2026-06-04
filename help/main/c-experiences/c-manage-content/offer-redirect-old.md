---
keywords: リダイレクトオファー;リダイレクトオファーの作成;HTML オファーの追加;リダイレクト時にすべての URL パラメーターを渡す;リダイレクト時に mboxSessionId を渡す (リダイレクト先が別のドメインの場合にのみ必要)
description: ブラウザーが新しいページにリダイレクトするように、Adobe [!DNL Target] でリダイレクトオファーを作成する方法を説明します。
title: リダイレクトオファーを作成するにはどうすればよいですか？
feature: Experiences and Offers
exl-id: b7b960cb-5057-455b-8fab-86dd37343a04
source-git-commit: e8201198dc6ac36e803153d5c6b345a30716204a
workflow-type: tm+mt
source-wordcount: '1210'
ht-degree: 44%

---

# リダイレクトオファーの作成

[!DNL Adobe Target]のオファーをリダイレクトすると、ブラウザーは新しいページにリダイレクトされます。

ページ内でコンテンツの一部を変更するのではなく、まったく異なる 2 つのページをテストすることができます。 この場合、A/B テストはページ Aとページ Bを比較します。A/B テスト アクティビティを2つのエクスペリエンスで設定します。1つはデフォルトのページ Aを指し、もう1つはページ Bにリダイレクトします。このオファーは、訪問者を別のページにリダイレクトするように設定されています。

>[!NOTE]
>
> * リダイレクトオファーは、[!UICONTROL &#x200B; オファー]/[!UICONTROL &#x200B; コードオファー] ページまたは[Forms ベースのExperience Composer](/help/main/c-experiences/form-experience-composer.md)で作成できます。 Visual Experience Composer （VEC）では、リダイレクトオファーを作成または適用できません。 コンテンツは[!DNL Target] リクエストの場所に挿入されるため、これらはグローバル [!DNL Target] リクエストには適していない可能性が高くなります。
>
>* ajax mbox （`mboxUpdate`）ではリダイレクト オファーを使用できません。
>
>* A4T を使用してアクティビティでリダイレクトオファーを使用する場合、実装が特定の最小要件を満たす必要があります。 また、知っておくべき重要な情報があります。 詳しくは、[リダイレクトオファー - A4T に関する FAQ](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905) を参照してください。
>
>* リダイレクトするエクスペリエンスの設定については、[URL にリダイレクト](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA)を参照してください。

リダイレクトオファーでは、JavaScript コードを実行してブラウザーをリダイレクトします。 このオファーでは `window.location.replace();` メソッドを使用するので、訪問者のリダイレクト元のページはブラウザー履歴に保存されません。 そのため、訪問者はブラウザーの「戻る」ボタンを引き続き使用できます。

>[!NOTE]
>
>ランディングページのリファラー値を渡す場合、リダイレクトオファーではなく HTML オファーを使用することをお勧めします。

## コードオファーページからリダイレクトオファーを作成します

1. 「**[!UICONTROL オファー]**」をクリックしてから、「**[!UICONTROL コードオファー]**」タブを選択します。

   ![&#x200B; コードオファータブ &#x200B;](/help/main/c-experiences/c-manage-content/assets/offers-code-offers.png)

1. **[!UICONTROL Create]** > **[!UICONTROL Redirect Offer]**&#x200B;をクリックします。

   ![&#x200B; リダイレクトオファーダイアログボックスを作成](/help/main/c-experiences/c-manage-content/assets/create-redirect-offer.png)

1. オファーのわかりやすい名前を入力します。

   わかりやすい名前を付けると、Assets ライブラリでオファーをすばやく見つけることができます。

1. 一意のコンテンツまたはリダイレクト先の URL を入力します。 この URL は絶対 URL にする必要があります。

   >[!NOTE]
   >
   >リダイレクト URL で、ユーザーが同一のアクティビティの条件も満たしていると見なされる場合、リダイレクトオファーが無限ループに陥るという情報を追加しました。 リダイレクト後は、ユーザーがアクティビティの条件を再度満たすことがないようにする必要があります。

1. 目的のオプションを選択してリダイレクトオファーをカスタマイズします。

   * **すべてのURL パラメーターを含める：**&#x200B;前のページに存在するすべてのURL パラメーターをリダイレクトされたページに反映する場合は、切り替えをスライドさせて、このオプションを有効にします。

     例えば、男性向け商品のページから男性向けシャツカテゴリのページにユーザーを直接リダイレクトする場合などです。 また、URL で動的なパラメーターを渡して、ユーザーが電子メール、バナー広告、検索広告経由でサイトに到達したか、または別の経路でサイトに到達したかを追跡する必要もあります。 このオプションを有効にすると、ページ `https://www.mycompany.com/mens.html?emailId=123`のリダイレクト オファーは、URL ボックスに入力したすべての項目が`https://www.mycompany.com/mensShirts.html`の場合、自動的に`https://www.mycompany.com/mensShirts.html?emailId=123`になります。

   * **別のドメインにリダイレクトするには、mbox セッション ID:**&#x200B;を渡す必要があります。 `sessionId`をリダイレクトに自動的に含める場合は、切り替えスイッチをスライドしてこのオプションを有効にします。 これは、電子メールのクリック数またはドメイン間のクリック数をテストする場合にのみ必要です。 この `sessionId` を使用して訪問者の Cookie を照合し、訪問者を引き続き追跡して適切なコンテンツが表示されるようにします。

     1st パーティおよび3rd パーティのCookie設定を使用する場合、ドメインを渡す際にmbox セッション IDを渡す必要はありません。 この値はサードパーティ Cookie に保持されているため、URL に含める必要がないからです。

1. 「**[!UICONTROL 保存]**」をクリックします。

>[!NOTE]
>
>このようなテストを開始する場合は、導入コンサルタントにお問い合わせください。

## フォームベースのExperience Composerを使用したリダイレクトオファーの作成

1. [&#x200B; フォームベースのExperience Composer](/help/main/c-experiences/form-experience-composer.md)を使用してアクティビティを作成する際に、**[!UICONTROL コンテンツ]** セクションを表示する場所を選択します。

   フォームベースのExperience Composerの![&#x200B; コンテンツセクション &#x200B;](/help/main/c-experiences/c-manage-content/assets/form-based-content.png)

1. 「**[!UICONTROL デフォルトコンテンツ]**」ドロップダウンリストをクリックし、**[!UICONTROL リダイレクトオファーの変更]**&#x200B;をクリックします。

   ![&#x200B; リダイレクトオファーオプションの変更](/help/main/c-experiences/c-manage-content/assets/change-redirect-offer-option.png)

1. **[!UICONTROL Create]** > **[!UICONTROL Redirect Offer]**&#x200B;をクリックします。

   ![&#x200B; リダイレクトオファーダイアログボックスを作成](/help/main/c-experiences/c-manage-content/assets/create-redirect-offer.png)

1. オファーのわかりやすい名前を入力します。

   わかりやすい名前を付けると、Assets ライブラリでオファーをすばやく見つけることができます。

1. 一意のコンテンツまたはリダイレクト先の URL を入力します。 この URL は絶対 URL にする必要があります。

   >[!NOTE]
   >
   >リダイレクト URL で、ユーザーが同一のアクティビティの条件も満たしていると見なされる場合、リダイレクトオファーが無限ループに陥るという情報を追加しました。 リダイレクト後は、ユーザーがアクティビティの条件を再度満たすことがないようにする必要があります。

1. 目的のオプションを選択してリダイレクトオファーをカスタマイズします。

   * **すべてのURL パラメーターを含める：**&#x200B;前のページに存在するすべてのURL パラメーターをリダイレクトされたページに反映する場合は、切り替えをスライドさせて、このオプションを有効にします。

     例えば、男性向け商品のページから男性向けシャツカテゴリのページにユーザーを直接リダイレクトする場合などです。 また、URL で動的なパラメーターを渡して、ユーザーが電子メール、バナー広告、検索広告経由でサイトに到達したか、または別の経路でサイトに到達したかを追跡する必要もあります。 このオプションを有効にすると、ページ `https://www.mycompany.com/mens.html?emailId=123`のリダイレクト オファーは、URL ボックスに入力したすべての項目が`https://www.mycompany.com/mensShirts.html`の場合、自動的に`https://www.mycompany.com/mensShirts.html?emailId=123`になります。

   * **別のドメインにリダイレクトするには、mbox セッション ID:**&#x200B;を渡す必要があります。 `sessionId`をリダイレクトに自動的に含める場合は、切り替えスイッチをスライドしてこのオプションを有効にします。 これは、電子メールのクリック数またはドメイン間のクリック数をテストする場合にのみ必要です。 この `sessionId` を使用して訪問者の Cookie を照合し、訪問者を引き続き追跡して適切なコンテンツが表示されるようにします。

     1st パーティおよび3rd パーティのCookie設定を使用する場合、ドメインを渡す際にmbox セッション IDを渡す必要はありません。 この値はサードパーティ Cookie に保持されているため、URL に含める必要がないからです。

1. 「**[!UICONTROL 保存]**」をクリックします。

>[!NOTE]
>
>このようなテストを開始する場合は、導入コンサルタントにお問い合わせください。

## アクティビティでのリダイレクトオファーの使用

[!UICONTROL &#x200B; フォームベースのExperience Composer]を使用してリダイレクト オファーを適用する必要があります。 現在、VECを使用してリダイレクトオファーを適用することはできません。

[!DNL Adobe Target] [!UICONTROL &#x200B; フォームベースのExperience Composer]は、[!UICONTROL A/B テスト &#x200B;]、[!UICONTROL &#x200B; エクスペリエンスのターゲット設定] （XT）、[!UICONTROL Automated Personalization] （AP）、[!UICONTROL Recommendations]のアクティビティで、Visual Experience Composerが使用できない、または使用できない場合に使用するエクスペリエンスの作成に役立つ、非ビジュアルなエクスペリエンスおよびオファー作成インターフェイスです。 例えば、[!UICONTROL &#x200B; フォームベースのExperience Composer]を使用して、リダイレクトオファーを使用するエクスペリエンスを作成できます。

1. [!UICONTROL &#x200B; フォームベースのExperience Composer]でアクティビティを作成または編集します。

   詳細な手順については、[&#x200B; フォームベースのExperience Composer](/help/main/c-experiences/form-experience-composer.md)を参照してください。

1. 必要に応じて、目的の場所を指定し、オーディエンスの絞り込みを追加します。

1. 「**[!UICONTROL コンテンツ]**」セクションのドロップダウンリストをクリックし、**[!UICONTROL リダイレクトオファーの変更]**&#x200B;をクリックします。

   ![&#x200B; リダイレクトオファーオプションの変更](/help/main/c-experiences/c-manage-content/assets/change-redirect-offer-option2.png)

1. 「[!UICONTROL &#x200B; リモートオファーを選択]」ダイアログボックスから目的のリダイレクトオファーを選択し、「**[!UICONTROL 完了]**」をクリックします。

1. アクティビティの設定を終了します。

## トレーニングビデオ：フォームベースのコンポーザー![&#x200B; チュートリアルバッジ &#x200B;](/help/main/assets/tutorial.png)

このビデオでは、リダイレクトオファーの作成に使用できるフォームベースのコンポーザーのデモを紹介します。

* フォームベースの Experience Composer を使用したアクティビティの作成
* フォームベースの Experience Composer と Visual Experience Composer のどちらを使用するかの理解
* 場所のターゲット設定の調整

>[!VIDEO](https://video.tv.adobe.com/v/17390)
