---
keywords: リダイレクトオファー;リダイレクトオファーの作成;HTML オファーの追加;リダイレクト時にすべての URL パラメーターを渡す;リダイレクト時に mboxSessionId を渡す (リダイレクト先が別のドメインの場合にのみ必要)
description: 'リダイレクトオファーの作成方法については、Adobe [!DNL Target] をクリックすると、ブラウザーが新しいページにリダイレクトされます。 '
title: リダイレクトオファーの作成方法
feature: Experiences and Offers
exl-id: b7b960cb-5057-455b-8fab-86dd37343a04
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1189'
ht-degree: 48%

---

# リダイレクトオファーの作成

でのリダイレクトオファー [!DNL Adobe Target] ブラウザーで新しいページにリダイレクトさせます。

ページ内でコンテンツの一部を変更するのではなく、まったく異なる 2 つのページをテストすることができます。この場合、A/B テストでは、ページ A とページ B を比較します。次の 2 つのエクスペリエンスを持つ A/B テストアクティビティを設定します。1 つはデフォルトのページ A を指し、もう 1 つはページ B にリダイレクトします。オファーは、訪問者を別のページにリダイレクトするように設定されます。

>[!NOTE]
>
> * リダイレクトオファーは [!UICONTROL オファー] > [!UICONTROL コードオファー] ページまたは [Formsベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md). Visual Experience Composer(VEC) では、リダイレクトオファーを作成または適用できません。 コンテンツが [!DNL Target] リクエストの場所を指定する場合は、多くの場合、グローバル [!DNL Target] リクエスト。
>
>* ajax mbox（`mboxUpdate`）では、リダイレクトオファーは使用できません。
>
>* A4T を使用してアクティビティでリダイレクトオファーを使用する場合、実装が特定の最小要件を満たす必要があります。また、知っておくべき重要な情報があります。詳しくは、[リダイレクトオファー - A4T に関する FAQ](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905) を参照してください。
>
>* リダイレクトするエクスペリエンスの設定については、[URL にリダイレクト](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA)を参照してください。


リダイレクトオファーでは、JavaScript コードを実行してブラウザーをリダイレクトします。このオファーでは `window.location.replace();` メソッドを使用するので、訪問者のリダイレクト元のページはブラウザー履歴に保存されません。そのため、訪問者はブラウザーの「戻る」ボタンを引き続き使用できます。

>[!NOTE]
>
>ランディングページのリファラー値を渡す場合、リダイレクトオファーではなく HTML オファーを使用することをお勧めします。

## コードオファーページからのリダイレクトオファーの作成

1. 「**[!UICONTROL オファー]**」をクリックしてから、「**[!UICONTROL コードオファー]**」タブを選択します。

   ![「コードオファー」タブ](/help/main/c-experiences/c-manage-content/assets/offers-code-offers.png)

1. **[!UICONTROL 作成]**／**[!UICONTROL リダイレクトオファー]**&#x200B;をクリックします。

   ![リダイレクトオファーを作成ダイアログボックス](/help/main/c-experiences/c-manage-content/assets/create-redirect-offer.png)

1. オファーのわかりやすい名前を入力します。

   わかりやすい名前を付けると、後で アセット ライブラリからオファーをすばやく見つけることができます。

1. 一意のコンテンツまたはリダイレクト先の URL を入力します。この URL は絶対 URL にする必要があります。

   >[!NOTE]
   >
   >リダイレクト URL で、ユーザーが同一のアクティビティの条件も満たしていると見なされる場合、リダイレクトオファーが無限ループに陥るという情報を追加しました。リダイレクト後は、ユーザーがアクティビティの条件を再度満たすことがないようにする必要があります。

1. 目的のオプションを選択してリダイレクトオファーをカスタマイズします。

   * **すべての URL パラメーターを含める：** 切り替えボタンをスライドさせて、前のページに存在するすべての URL パラメーターをリダイレクト先のページに渡す場合に、このオプションを有効にします。

      例えば、男性向け商品のページから男性向けシャツカテゴリのページにユーザーを直接リダイレクトする場合などです。また、URL で動的なパラメーターを渡して、ユーザーが電子メール、バナー広告、検索広告経由でサイトに到達したか、または別の経路でサイトに到達したかを追跡する必要もあります。このオプションを有効にすると、ページ上のリダイレクトオファーが表示されます `https://www.mycompany.com/mens.html?emailId=123` は、自動的に `https://www.mycompany.com/mensShirts.html?emailId=123` 「URL」ボックスに入力したすべての項目が `https://www.mycompany.com/mensShirts.html`.

   * **mbox セッション ID を渡す：** 別のドメインにリダイレクトするために必要です。 必要に応じて、切り替えボタンをスライドさせて、このオプションを有効にします。 `sessionId` を自動的にリダイレクトに含める。 これは、電子メールからのクリックまたはドメイン間のクリックをテストする場合にのみ必要です。 この `sessionId` を使用して訪問者の Cookie を照合し、訪問者を引き続き追跡して適切なコンテンツが表示されるようにします。

      ファーストパーティおよびサードパーティ Cookie の設定を使用する場合、異なるドメインにアクセスする際に mbox セッション ID を渡す必要はありません。 この値はサードパーティ Cookie に保持されているため、URL に含める必要がないからです。

1. 「**[!UICONTROL 保存]**」をクリックします。

>[!NOTE]
>
>このようなテストを開始する場合は、導入コンサルタントにお問い合わせください。

## フォームベースの Experience Composer を使用したリダイレクトオファーの作成

1. を使用してアクティビティを作成する場合、 [フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md)を選択し、 **[!UICONTROL コンテンツ]** 」セクションに入力します。

   ![フォームベースの Experience Composer のコンテンツセクション](/help/main/c-experiences/c-manage-content/assets/form-based-content.png)

1. 次をクリック： **[!UICONTROL デフォルトコンテンツ]** ドロップダウンリストから、 **[!UICONTROL リダイレクトオファーの変更]**.

   ![リダイレクトオファーオプションの変更](/help/main/c-experiences/c-manage-content/assets/change-redirect-offer-option.png)

1. **[!UICONTROL 作成]**／**[!UICONTROL リダイレクトオファー]**&#x200B;をクリックします。

   ![リダイレクトオファーを作成ダイアログボックス](/help/main/c-experiences/c-manage-content/assets/create-redirect-offer.png)

1. オファーのわかりやすい名前を入力します。

   わかりやすい名前を付けると、後で アセット ライブラリからオファーをすばやく見つけることができます。

1. 一意のコンテンツまたはリダイレクト先の URL を入力します。この URL は絶対 URL にする必要があります。

   >[!NOTE]
   >
   >リダイレクト URL で、ユーザーが同一のアクティビティの条件も満たしていると見なされる場合、リダイレクトオファーが無限ループに陥るという情報を追加しました。リダイレクト後は、ユーザーがアクティビティの条件を再度満たすことがないようにする必要があります。

1. 目的のオプションを選択してリダイレクトオファーをカスタマイズします。

   * **すべての URL パラメーターを含める：** 切り替えボタンをスライドさせて、前のページに存在するすべての URL パラメーターをリダイレクト先のページに渡す場合に、このオプションを有効にします。

      例えば、男性向け商品のページから男性向けシャツカテゴリのページにユーザーを直接リダイレクトする場合などです。また、URL で動的なパラメーターを渡して、ユーザーが電子メール、バナー広告、検索広告経由でサイトに到達したか、または別の経路でサイトに到達したかを追跡する必要もあります。このオプションを有効にすると、ページ上のリダイレクトオファーが表示されます `https://www.mycompany.com/mens.html?emailId=123` は、自動的に `https://www.mycompany.com/mensShirts.html?emailId=123` 「URL」ボックスに入力したすべての項目が `https://www.mycompany.com/mensShirts.html`.

   * **mbox セッション ID を渡す：** 別のドメインにリダイレクトするために必要です。 必要に応じて、切り替えボタンをスライドさせて、このオプションを有効にします。 `sessionId` を自動的にリダイレクトに含める。 これは、電子メールからのクリックまたはドメイン間のクリックをテストする場合にのみ必要です。 この `sessionId` を使用して訪問者の Cookie を照合し、訪問者を引き続き追跡して適切なコンテンツが表示されるようにします。

      ファーストパーティおよびサードパーティ Cookie の設定を使用する場合、異なるドメインにアクセスする際に mbox セッション ID を渡す必要はありません。 この値はサードパーティ Cookie に保持されているため、URL に含める必要がないからです。

1. 「**[!UICONTROL 保存]**」をクリックします。

>[!NOTE]
>
>このようなテストを開始する場合は、導入コンサルタントにお問い合わせください。

## アクティビティでのリダイレクトオファーの使用

リダイレクトオファーを適用するには、 [!UICONTROL フォームベースの Experience Composer]. 現在、VEC を使用してリダイレクトオファーを適用することはできません。

この [!DNL Adobe Target] [!UICONTROL フォームベースの Experience Composer] は、非視覚的なエクスペリエンスおよびオファー作成インターフェイスで、で使用するエクスペリエンスを作成するのに役立ちます。 [!UICONTROL A/B テスト], [!UICONTROL エクスペリエンスのターゲット設定] (XT), [!UICONTROL Automated Personalization] (AP) および [!UICONTROL Recommendations] Visual Experience Composer を使用できない場合や実用的な場合にアクティビティを使用します。 例えば、 [!UICONTROL フォームベースの Experience Composer] リダイレクトオファーを使用するエクスペリエンスを作成する場合。

1. でアクティビティを作成または編集 [!UICONTROL フォームベースの Experience Composer].

   詳しくは、 [フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md) を参照してください。

1. 目的の場所を指定し、必要に応じてオーディエンスの絞り込みを追加します。

1. 次に示す **[!UICONTROL コンテンツ]** 「 」セクションで、「 **[!UICONTROL リダイレクトオファーの変更]**.

   ![リダイレクトオファーオプションの変更](/help/main/c-experiences/c-manage-content/assets/change-redirect-offer-option2.png)

1. 目的のリダイレクトオファーを [!UICONTROL リモートオファーを選択] ダイアログボックスを開き、 **[!UICONTROL 完了]**.

1. アクティビティの設定を終了します。

## トレーニングビデオ：フォームベースのコンポーザー ![チュートリアルバッジ](/help/main/assets/tutorial.png)

このビデオでは、リダイレクトオファーの作成に使用できるフォームベースのコンポーザーのデモを提供します。

* フォームベースの Experience Composer を使用したアクティビティの作成
* フォームベースの Experience Composer と Visual Experience Composer のどちらを使用するかの理解
* 場所のターゲット設定の調整

>[!VIDEO](https://video.tv.adobe.com/v/17390)
