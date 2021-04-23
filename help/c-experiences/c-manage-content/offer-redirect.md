---
keywords: リダイレクトオファー;リダイレクトオファーの作成;HTML オファーの追加;リダイレクト時にすべての URL パラメーターを渡す;リダイレクト時に mboxSessionId を渡す (リダイレクト先が別のドメインの場合にのみ必要)
description: 'Adobe [!DNL Target] でリダイレクトオファーを作成して、ブラウザーを新しいページにリダイレクトさせる方法を説明します。 '
title: リダイレクトオファーの作成方法
feature: エクスペリエンスとオファー
exl-id: b7b960cb-5057-455b-8fab-86dd37343a04
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '1192'
ht-degree: 48%

---

# リダイレクトオファーの作成

[!DNL Adobe Target]のリダイレクトオファーは、ブラウザーが新しいページにリダイレクトする原因となります。

ページ内でコンテンツの一部を変更するのではなく、まったく異なる 2 つのページをテストすることができます。この場合、A/Bテストでは、ページAとページBを比較します。A/Bテストアクティビティを2つのエクスペリエンスと共に設定します。1つはデフォルトのページAを指し、もう1つはページBにリダイレクトします。オファーは、訪問者を別のページにリダイレクトするように構成されます。

>[!NOTE]
>
> * リダイレクトオファーは、[!UICONTROL オファー] > [!UICONTROL コードオファー]ページまたは[FormsベースのExperience Composer](/help/c-experiences/form-experience-composer.md)で作成できます。 Visual Experience Composer(VEC)でリダイレクトオファーを作成または適用することはできません。 コンテンツは[!DNL Target]リクエストの場所に挿入されるので、グローバル[!DNL Target]リクエストには適していない可能性が高くなります。
   >
   >
* ajax mbox（`mboxUpdate`）では、リダイレクトオファーは使用できません。
   >
   >
* A4T を使用してアクティビティでリダイレクトオファーを使用する場合、実装が特定の最小要件を満たす必要があります。また、知っておくべき重要な情報があります。詳しくは、[リダイレクトオファー - A4T に関する FAQ](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905) を参照してください。
   >
   >
* リダイレクトするエクスペリエンスの設定については、[URL にリダイレクト](/help/c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA)を参照してください。


リダイレクトオファーでは、JavaScript コードを実行してブラウザーをリダイレクトします。このオファーでは `window.location.replace();` メソッドを使用するので、訪問者のリダイレクト元のページはブラウザー履歴に保存されません。そのため、訪問者はブラウザーの「戻る」ボタンを引き続き使用できます。

>[!NOTE]
>
>ランディングページのリファラー値を渡す場合、リダイレクトオファーではなく HTML オファーを使用することをお勧めします。

## コードオファーページからのリダイレクトオファーの作成

1. 「**[!UICONTROL オファー]**」をクリックしてから、「**[!UICONTROL コードオファー]**」タブを選択します。

   ![「コードオファー」タブ](/help/c-experiences/c-manage-content/assets/offers-code-offers.png)

1. **[!UICONTROL 作成]**／**[!UICONTROL リダイレクトオファー]**&#x200B;をクリックします。

   ![リダイレクトオファーの作成ダイアログボックス](/help/c-experiences/c-manage-content/assets/create-redirect-offer.png)

1. オファーのわかりやすい名前を入力します。

   わかりやすい名前を付けると、後で アセット ライブラリからオファーをすばやく見つけることができます。

1. 一意のコンテンツまたはリダイレクト先の URL を入力します。この URL は絶対 URL にする必要があります。

   >[!NOTE]
   >
   >リダイレクト URL で、ユーザーが同一のアクティビティの条件も満たしていると見なされる場合、リダイレクトオファーが無限ループに陥るという情報を追加しました。リダイレクト後は、ユーザーがアクティビティの条件を再度満たすことがないようにする必要があります。

1. 目的のオプションを選択してリダイレクトオファーをカスタマイズします。

   * **すべてのURLパラメーターを含める：リダイレク** トされるページに前のページにあるすべてのURLパラメーターを渡す場合は、切り替えボタンをスライドして、このオプションを有効にします。

      例えば、男性向け商品のページから男性向けシャツカテゴリのページにユーザーを直接リダイレクトする場合などです。また、URL で動的なパラメーターを渡して、ユーザーが電子メール、バナー広告、検索広告経由でサイトに到達したか、または別の経路でサイトに到達したかを追跡する必要もあります。このオプションを有効にすると、「URL」ボックスに入力したオファーのみが`https://www.mycompany.com/mensShirts.html`の場合に、`https://www.mycompany.com/mens.html?emailId=123`ページのリダイレクト操作は自動的に`https://www.mycompany.com/mensShirts.html?emailId=123`になります。

   * **mboxセッションIDを渡す：別のドメインにリダイレクトする** 場合に必須です。`sessionId`を自動的にリダイレクトに含める場合は、トグルをスライドさせてこのオプションを有効にします。 これは、電子メールからのクリックまたはドメイン間のクリックをテストする場合にのみ必要です。 この `sessionId` を使用して訪問者の Cookie を照合し、訪問者を引き続き追跡して適切なコンテンツが表示されるようにします。

      ファーストパーティおよびサードパーティCookieの設定を使用する場合は、異なるドメインにアクセスするときにmboxセッションIDを渡す必要はありません。 この値はサードパーティ Cookie に保持されているため、URL に含める必要がないからです。

1. 「**[!UICONTROL 保存]**」をクリックします。

>[!NOTE]
>
>このようなテストを開始する場合は、導入コンサルタントにお問い合わせください。

## フォームベースのExperience Composerを使用したリダイレクトオファーの作成

1. [フォームベースのExperience Composer](/help/c-experiences/form-experience-composer.md)を使用してアクティビティを作成する際に、**[!UICONTROL コンテンツ]**&#x200B;セクションを表示する場所を選択します。

   ![フォームベースのExperience Composerの「コンテンツ」セクション](/help/c-experiences/c-manage-content/assets/form-based-content.png)

1. **[!UICONTROL デフォルトコンテンツ]**&#x200B;ドロップダウンリストをクリックし、**[!UICONTROL リダイレクトオファーを変更]**&#x200B;をクリックします。

   ![リダイレクトオファーの変更オプション](/help/c-experiences/c-manage-content/assets/change-redirect-offer-option.png)

1. **[!UICONTROL 作成]**／**[!UICONTROL リダイレクトオファー]**&#x200B;をクリックします。

   ![リダイレクトオファーの作成ダイアログボックス](/help/c-experiences/c-manage-content/assets/create-redirect-offer.png)

1. オファーのわかりやすい名前を入力します。

   わかりやすい名前を付けると、後で アセット ライブラリからオファーをすばやく見つけることができます。

1. 一意のコンテンツまたはリダイレクト先の URL を入力します。この URL は絶対 URL にする必要があります。

   >[!NOTE]
   >
   >リダイレクト URL で、ユーザーが同一のアクティビティの条件も満たしていると見なされる場合、リダイレクトオファーが無限ループに陥るという情報を追加しました。リダイレクト後は、ユーザーがアクティビティの条件を再度満たすことがないようにする必要があります。

1. 目的のオプションを選択してリダイレクトオファーをカスタマイズします。

   * **すべてのURLパラメーターを含める：リダイレク** トされるページに前のページにあるすべてのURLパラメーターを渡す場合は、切り替えボタンをスライドして、このオプションを有効にします。

      例えば、男性向け商品のページから男性向けシャツカテゴリのページにユーザーを直接リダイレクトする場合などです。また、URL で動的なパラメーターを渡して、ユーザーが電子メール、バナー広告、検索広告経由でサイトに到達したか、または別の経路でサイトに到達したかを追跡する必要もあります。このオプションを有効にすると、「URL」ボックスに入力したオファーのみが`https://www.mycompany.com/mensShirts.html`の場合に、`https://www.mycompany.com/mens.html?emailId=123`ページのリダイレクト操作は自動的に`https://www.mycompany.com/mensShirts.html?emailId=123`になります。

   * **mboxセッションIDを渡す：別のドメインにリダイレクトする** 場合に必須です。`sessionId`を自動的にリダイレクトに含める場合は、トグルをスライドさせてこのオプションを有効にします。 これは、電子メールからのクリックまたはドメイン間のクリックをテストする場合にのみ必要です。 この `sessionId` を使用して訪問者の Cookie を照合し、訪問者を引き続き追跡して適切なコンテンツが表示されるようにします。

      ファーストパーティおよびサードパーティCookieの設定を使用する場合は、異なるドメインにアクセスするときにmboxセッションIDを渡す必要はありません。 この値はサードパーティ Cookie に保持されているため、URL に含める必要がないからです。

1. 「**[!UICONTROL 保存]**」をクリックします。

>[!NOTE]
>
>このようなテストを開始する場合は、導入コンサルタントにお問い合わせください。

## アクティビティでリダイレクトオファーを使用する

[!UICONTROL フォームベースのExperience Composer]を使用して、リダイレクトオファーを適用する必要があります。 現在、VECを使用してリダイレクトオファーを適用することはできません。

[!DNL Adobe Target] [!UICONTROL フォームベースのExperience Composer]は、[!UICONTROL A/Bテスト]、[!UICONTROL エクスペリエンスのターゲット設定](XT)、[!UICONTROL Automated Personalization](AP)で使用するエクスペリエンスを作成するのに便利です)、および[!UICONTROL Recommendations]アクティビティ（visual experience composerが使用できない場合や実際に使用できない場合）に追加します。 例えば、[!UICONTROL フォームベースのExperience Composer]を使用して、リダイレクトオファーを使用するエクスペリエンスを作成できます。

1. [!UICONTROL フォームベースのExperience Composer]でアクティビティを作成または編集します。

   詳しい手順については、[フォームベースのExperience Composer](/help/c-experiences/form-experience-composer.md)を参照してください。

1. 必要な場所を指定し、必要に応じてオーディエンスの調整を追加します。

1. 「**[!UICONTROL コンテンツ]**」セクションのドロップダウンリストをクリックし、「**[!UICONTROL リダイレクトオファーを変更]**」をクリックします。

   ![リダイレクトオファーの変更オプション](/help/c-experiences/c-manage-content/assets/change-redirect-offer-option2.png)

1. [!UICONTROL リモートオファーを選択]ダイアログボックスから目的のリダイレクトオファーを選択し、**[!UICONTROL 完了]**&#x200B;をクリックします。

1. アクティビティの設定を終了します。

## トレーニングビデオ：フォームベースのコンポーザー![チュートリアルバッジ](/help/assets/tutorial.png)

このビデオは、リダイレクトオファーの作成に使用できるフォームベースのコンポーザーのデモを提供します。

* フォームベースの Experience Composer を使用したアクティビティの作成
* フォームベースの Experience Composer と Visual Experience Composer のどちらを使用するかの理解
* 場所のターゲット設定の調整

>[!VIDEO](https://video.tv.adobe.com/v/17390)
