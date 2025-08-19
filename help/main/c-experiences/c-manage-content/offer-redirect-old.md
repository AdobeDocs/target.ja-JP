---
keywords: リダイレクトオファー;リダイレクトオファーの作成;HTML オファーの追加;リダイレクト時にすべての URL パラメーターを渡す;リダイレクト時に mboxSessionId を渡す (リダイレクト先が別のドメインの場合にのみ必要)
description: ブラウザーが新しいページにリダイレクトするように  [!DNL Target] Adobeでリダイレクトオファーを作成する方法を説明します。
title: リダイレクトオファーの作成方法
feature: Experiences and Offers
exl-id: b7b960cb-5057-455b-8fab-86dd37343a04
source-git-commit: e8201198dc6ac36e803153d5c6b345a30716204a
workflow-type: tm+mt
source-wordcount: '1139'
ht-degree: 45%

---

# リダイレクトオファーの作成

[!DNL Adobe Target] のリダイレクトオファーは、ブラウザーが新しいページにリダイレクトする原因になります。

ページ内でコンテンツの一部を変更するのではなく、まったく異なる 2 つのページをテストすることができます。この場合、A/B テストではページ A とページ B を比較します。デフォルトのページ A を指すエクスペリエンスと、ページ B にリダイレクトするエクスペリエンスの 2 つを使用して A/B テスト アクティビティを設定します。オファーは、訪問者を別のページにリダイレクトするように設定されます。

>[!NOTE]
>
> * リダイレクトオファーは、[!UICONTROL Offers]/[!UICONTROL Code Offers] ページまたは [Forms ベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md) で作成できます。 Visual Experience Composer （VEC）では、リダイレクトオファーの作成または適用はできません。 コンテンツは [!DNL Target] リクエストの場所に挿入されるので、グローバル [!DNL Target] リクエストには適していない可能性が高くなります。
>
>* Ajax mbox （`mboxUpdate`）では、リダイレクトオファーを使用できません。
>
>* A4T を使用してアクティビティでリダイレクトオファーを使用する場合、実装が特定の最小要件を満たす必要があります。また、知っておくべき重要な情報があります。詳しくは、[リダイレクトオファー - A4T に関する FAQ](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905) を参照してください。
>
>* リダイレクトするエクスペリエンスの設定については、[URL にリダイレクト](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA)を参照してください。

リダイレクトオファーでは、JavaScript コードを実行してブラウザーをリダイレクトします。このオファーでは `window.location.replace();` メソッドを使用するので、訪問者のリダイレクト元のページはブラウザー履歴に保存されません。そのため、訪問者はブラウザーの「戻る」ボタンを引き続き使用できます。

>[!NOTE]
>
>ランディングページのリファラー値を渡す場合、リダイレクトオファーではなく HTML オファーを使用することをお勧めします。

## コードオファーページからのリダイレクトオファーの作成

1. 「**[!UICONTROL Offers]**」をクリックして、「**[!UICONTROL Code Offers]**」タブを選択します。

   ![ 「コードオファー」タブ ](/help/main/c-experiences/c-manage-content/assets/offers-code-offers.png)

1. **[!UICONTROL Create]**／**[!UICONTROL Redirect Offer]**&#x200B;をクリックします。

   ![ リダイレクトオファーを作成ダイアログボックス ](/help/main/c-experiences/c-manage-content/assets/create-redirect-offer.png)

1. オファーのわかりやすい名前を入力します。

   わかりやすい名前を付けると、作成者や他のユーザーがAssets ライブラリでオファーをすばやく見つけるのに役立ちます。

1. 一意のコンテンツまたはリダイレクト先の URL を入力します。この URL は絶対 URL にする必要があります。

   >[!NOTE]
   >
   >リダイレクト URL で、ユーザーが同一のアクティビティの条件も満たしていると見なされる場合、リダイレクトオファーが無限ループに陥るという情報を追加しました。リダイレクト後は、ユーザーがアクティビティの条件を再度満たすことがないようにする必要があります。

1. 目的のオプションを選択してリダイレクトオファーをカスタマイズします。

   * **すべての URL パラメーターを含める：** 前のページに存在するすべての URL パラメーターをリダイレクトされたページに反映する場合は、切り替えスイッチをスライドしてこのオプションを有効にします。

     例えば、男性向け商品のページから男性向けシャツカテゴリのページにユーザーを直接リダイレクトする場合などです。また、URL で動的なパラメーターを渡して、ユーザーが電子メール、バナー広告、検索広告経由でサイトに到達したか、または別の経路でサイトに到達したかを追跡する必要もあります。このオプションを有効にすると、URL ボックスに入力したすべてのものがリク `https://www.mycompany.com/mens.html?emailId=123` ストされた時点で、ページ `https://www.mycompany.com/mensShirts.html?emailId=123` のリダイレクトオファーが自動的に `https://www.mycompany.com/mensShirts.html` になります。

   * **mbox セッション ID を渡す：** 別のドメインにリダイレクトするには必須です。 `sessionId` をリダイレクトに自動的に含める場合は、切り替えスイッチをスライドしてこのオプションを有効にします。 これは、メールからのクリック数、またはドメイン間のクリック数をテストする場合にのみ必要です。 この `sessionId` を使用して訪問者の Cookie を照合し、訪問者を引き続き追跡して適切なコンテンツが表示されるようにします。

     ファーストパーティおよびサードパーティの Cookie 設定を使用する場合、ドメインを横断する際に mbox セッション ID を渡す必要はありません。 この値はサードパーティ Cookie に保持されているため、URL に含める必要がないからです。

1. **[!UICONTROL Save]** をクリックします。

>[!NOTE]
>
>このようなテストを開始する場合は、導入コンサルタントにお問い合わせください。

## フォームベースの Experience Composer を使用したリダイレクトオファーの作成

1. [ フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md) を使用してアクティビティを作成する際に、「**[!UICONTROL Content]**」セクションを表示する場所を選択します。

   ![ フォームベースの Experience Composer の「コンテンツ」セクション ](/help/main/c-experiences/c-manage-content/assets/form-based-content.png)

1. [**[!UICONTROL Default Content]**] ドロップダウンリストをクリックし、[**[!UICONTROL Change Redirect Offer]**] をクリックします。

   ![ リダイレクトオファーオプションの変更 ](/help/main/c-experiences/c-manage-content/assets/change-redirect-offer-option.png)

1. **[!UICONTROL Create]**／**[!UICONTROL Redirect Offer]**&#x200B;をクリックします。

   ![ リダイレクトオファーを作成ダイアログボックス ](/help/main/c-experiences/c-manage-content/assets/create-redirect-offer.png)

1. オファーのわかりやすい名前を入力します。

   わかりやすい名前を付けると、作成者や他のユーザーがAssets ライブラリでオファーをすばやく見つけるのに役立ちます。

1. 一意のコンテンツまたはリダイレクト先の URL を入力します。この URL は絶対 URL にする必要があります。

   >[!NOTE]
   >
   >リダイレクト URL で、ユーザーが同一のアクティビティの条件も満たしていると見なされる場合、リダイレクトオファーが無限ループに陥るという情報を追加しました。リダイレクト後は、ユーザーがアクティビティの条件を再度満たすことがないようにする必要があります。

1. 目的のオプションを選択してリダイレクトオファーをカスタマイズします。

   * **すべての URL パラメーターを含める：** 前のページに存在するすべての URL パラメーターをリダイレクトされたページに反映する場合は、切り替えスイッチをスライドしてこのオプションを有効にします。

     例えば、男性向け商品のページから男性向けシャツカテゴリのページにユーザーを直接リダイレクトする場合などです。また、URL で動的なパラメーターを渡して、ユーザーが電子メール、バナー広告、検索広告経由でサイトに到達したか、または別の経路でサイトに到達したかを追跡する必要もあります。このオプションを有効にすると、URL ボックスに入力したすべてのものがリク `https://www.mycompany.com/mens.html?emailId=123` ストされた時点で、ページ `https://www.mycompany.com/mensShirts.html?emailId=123` のリダイレクトオファーが自動的に `https://www.mycompany.com/mensShirts.html` になります。

   * **mbox セッション ID を渡す：** 別のドメインにリダイレクトするには必須です。 `sessionId` をリダイレクトに自動的に含める場合は、切り替えスイッチをスライドしてこのオプションを有効にします。 これは、メールからのクリック数、またはドメイン間のクリック数をテストする場合にのみ必要です。 この `sessionId` を使用して訪問者の Cookie を照合し、訪問者を引き続き追跡して適切なコンテンツが表示されるようにします。

     ファーストパーティおよびサードパーティの Cookie 設定を使用する場合、ドメインを横断する際に mbox セッション ID を渡す必要はありません。 この値はサードパーティ Cookie に保持されているため、URL に含める必要がないからです。

1. **[!UICONTROL Save]** をクリックします。

>[!NOTE]
>
>このようなテストを開始する場合は、導入コンサルタントにお問い合わせください。

## アクティビティでのリダイレクトオファーの使用

[!UICONTROL Form-Based Experience Composer] を使用してリダイレクトオファーを適用する必要があります。 現在、VEC を使用してリダイレクトオファーを適用することはできません。

[!DNL Adobe Target] [!UICONTROL Form-Based Experience Composer] は、Visual Experience Composer が使用できない、または使用が実用的でない場合に、[!UICONTROL A/B Tests]、[!UICONTROL Experience Targeting] （XT）、[!UICONTROL Automated Personalization] （AP）、および [!UICONTROL Recommendations] アクティビティで使用するエクスペリエンスを作成するのに便利な、非視覚的なエクスペリエンスおよびオファー作成インターフェイスです。 例えば、[!UICONTROL Form-Based Experience Composer] を使用して、リダイレクトオファーを使用するエクスペリエンスを作成できます。

1. [!UICONTROL Form-Based Experience Composer] でアクティビティを作成または編集します。

   詳しい手順については、[ フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md) を参照してください。

1. 目的の場所を指定し、必要に応じてオーディエンスの絞り込みを追加します。

1. 「**[!UICONTROL Content]**」セクションのドロップダウンリストをクリックして、「**[!UICONTROL Change Redirect Offer]**」をクリックします。

   ![ リダイレクトオファーオプションの変更 ](/help/main/c-experiences/c-manage-content/assets/change-redirect-offer-option2.png)

1. [!UICONTROL Select Remote Offer] ダイアログボックスで目的のリダイレクトオファーを選択し、「**[!UICONTROL Done]**」をクリックします。

1. アクティビティの設定を終了します。

## トレーニングビデオ：フォームベースの Composer![ チュートリアルバッジ ](/help/main/assets/tutorial.png)

このビデオでは、リダイレクトオファーの作成に使用できるフォームベースのコンポーザーのデモを紹介します。

* フォームベースの Experience Composer を使用したアクティビティの作成
* フォームベースの Experience Composer と Visual Experience Composer のどちらを使用するかの理解
* 場所のターゲット設定の調整

>[!VIDEO](https://video.tv.adobe.com/v/17390)
