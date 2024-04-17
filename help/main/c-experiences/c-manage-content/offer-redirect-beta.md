---
keywords: リダイレクトオファー;リダイレクトオファーの作成;HTML オファーの追加;リダイレクト時にすべての URL パラメーターを渡す;リダイレクト時に mboxSessionId を渡す (リダイレクト先が別のドメインの場合にのみ必要)
description: でリダイレクトオファーを作成する方法を説明します [!DNL Target] これにより、ブラウザーが新しいページにリダイレクトされます。
title: リダイレクトオファーの作成方法
feature: Experiences and Offers
badgeBeta: label="ベータ" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#beta newtab=true" tooltip=" [!DNL Adobe Target] のベータ版機能とは"
hide: true
hidefromtoc: true
source-git-commit: bd19686d2aa716af64f520fb0be798a300ed9fa3
workflow-type: tm+mt
source-wordcount: '1189'
ht-degree: 31%

---

# リダイレクトオファーの作成

でのリダイレクトオファーの作成 [!DNL Adobe Target] これにより、ブラウザーが新しいページにリダイレクトされます。

>[!NOTE]
>
>この記事には、の更新に関する情報が含まれています [!DNL Target] 現在ベータ版プログラムに含まれているユーザーインターフェイス。 この [!DNL Adobe Target] チームは、多くの場合、一部のお客様に対して、テストやフィードバックの目的で新機能を有効にします。 テスト期間が完了すると、今後、これらの機能はすべての顧客に対して有効になります [!DNL Target Standard/Premium] のリリースとリリースは、リリースノートで発表されました。

ページ内でコンテンツの一部を変更するのではなく、まったく異なる 2 つのページをテストすることができます。A/B テストではページ A とページ B を比較します。 [!UICONTROL A/B Test] 2 つのエクスペリエンスを持つアクティビティ。1 つはデフォルトページ A を指し、もう 1 つはページ B にリダイレクトします。オファーは、訪問者を別のページにリダイレクトするように設定されます。

>[!NOTE]
>
> * リダイレクトオファーは次の場所で作成できます [!UICONTROL Offers] > [!UICONTROL Code Offers] ページまたは [Forms ベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md). では、リダイレクトオファーの作成または適用はできません [!UICONTROL Visual Experience Composer] （VEC）。 コンテンツは次に挿入されます [!DNL Target] 場所をリクエストするので、これらの場所は、グローバルな場合には適していない可能性が高くなります [!DNL Target] リクエスト。
>
>* AJAX mbox では、リダイレクトオファーを使用できません（`mboxUpdate`）に設定します。
>
>* Analytics をレポートソースとして使用（A4T）するアクティビティでリダイレクトオファーを使用する場合は、実装が特定の最小要件を満たす必要があります。 また、知っておくべき重要な情報があります。詳しくは、[リダイレクトオファー - A4T に関する FAQ](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905) を参照してください。
>
>* リダイレクトするエクスペリエンスの設定については、[URL にリダイレクト](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA)を参照してください。

リダイレクトオファーでは、JavaScript コードを実行してブラウザーをリダイレクトします。このオファーでは `window.location.replace();` メソッドを使用するので、訪問者のリダイレクト元のページはブラウザー履歴に保存されません。このプロセスにより、訪問者はブラウザーで「戻る」ボタンを使用できます。

>[!NOTE]
>
>ランディングページのリファラー値を渡す場合は、リダイレクトオファーではなく、HTMLオファーを使用します。

## からのリダイレクトオファーの作成 [!UICONTROL Code Offers] ページ

1. クリック **[!UICONTROL Offers]**&#x200B;を選択してから、 **[!UICONTROL Code Offers]** タブ。

   ![「コードオファー」タブ](/help/main/c-experiences/c-manage-content/assets/offers-code-offers-new.png)

1. クリック **[!UICONTROL Create Offer]** > **[!UICONTROL Redirect Offer]**.

   ![リダイレクトオファーを作成ダイアログボックス](/help/main/c-experiences/c-manage-content/assets/create-redirect-offer-new.png)

1. オファーのわかりやすい名前を入力します。

   わかりやすい名前を指定すると、自分や他のユーザーがでオファーをすばやく見つけやすくなります [!UICONTROL Assets] ライブラリ。

1. （条件付き）がある場合 [Target Premium アカウント](/help/main/c-intro/intro.md#premium)、目的のを選択します [workspace](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md##section_B82EB409B67C4D9D9D20CE30E48DB1DC).

1. リダイレクト先となる一意のコンテンツまたは宛先の URL を指定します。 この URL は絶対 URL である必要があります。

   >[!NOTE]
   >
   >リダイレクト URL で、ユーザーが同一のアクティビティの条件も満たしていると見なされる場合、リダイレクトオファーが無限ループに陥るという情報を追加しました。ユーザーがリダイレクトされた後にアクティビティに再適合しないことを確認します。

1. 目的のオプションを選択してリダイレクトオファーをカスタマイズします。

   * **すべての URL パラメーターを含める：** 前のページに存在するすべての URL パラメーターをリダイレクトされたページに反映する場合は、切り替えスイッチをスライドしてこのオプションを有効にします。

     例えば、男性向け商品のページから男性向けシャツカテゴリのページにユーザーを直接リダイレクトする場合などです。また、URL で動的なパラメーターを渡して、ユーザーが電子メール、バナー広告、検索広告経由でサイトに到達したか、または別の経路でサイトに到達したかを追跡する必要もあります。このオプションを有効にすると、ページ上でリダイレクトオファーが有効になります `https://www.mycompany.com/mens.html?emailId=123` 自動的にになる `https://www.mycompany.com/mensShirts.html?emailId=123` url ボックスに入力した内容が `https://www.mycompany.com/mensShirts.html`.

   * **mbox セッション ID を渡す：** 別のドメインにリダイレクトする場合に必要です。 切り替えスイッチをスライドしてこのオプションを有効にするには、 `sessionId` が自動的にリダイレクトに含まれる。 このオプションは、メールまたはドメイン間のクリックをテストする場合にのみ必要です。 この `sessionId` を使用して訪問者の Cookie を照合し、訪問者を引き続き追跡して適切なコンテンツが表示されるようにします。

     ファーストパーティおよびサードパーティの Cookie 設定を使用する場合、ドメインを横断する際に mbox セッション ID を渡す必要はありません。 この値はサードパーティ Cookie に保持されているため、URL に含める必要がないからです。

1. **[!UICONTROL Create]** をクリックします。

>[!NOTE]
>
>これらのテストを開始する前に、実装コンサルタントに問い合わせてください。

## を使用したリダイレクトオファーの作成 [!UICONTROL Form-Based Experience Composer]

1. を使用してアクティビティを作成するとき [フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md)を表示する場所を選択します。 **[!UICONTROL Content]** セクション。

   ![フォームベースの Experience Composer のコンテンツセクション](/help/main/c-experiences/c-manage-content/assets/form-based-content.png)

1. 「」をクリックします **[!UICONTROL Default Content]** ドロップダウンリストから、 **[!UICONTROL Change Redirect Offer]**.

   ![リダイレクトオファーオプションの変更](/help/main/c-experiences/c-manage-content/assets/change-redirect-offer-option.png)

1. クリック **[!UICONTROL Create]** > **[!UICONTROL Redirect Offer]**.

   ![リダイレクトオファーを作成ダイアログボックス](/help/main/c-experiences/c-manage-content/assets/create-redirect-offer.png)

1. オファーのわかりやすい名前を入力します。

   わかりやすい名前を指定すると、自分や他のユーザーがでオファーをすばやく見つけやすくなります [!UICONTROL Assets] ライブラリ。

1. リダイレクト先となる一意のコンテンツまたは宛先の URL を指定します。 この URL は絶対 URL である必要があります。

   >[!NOTE]
   >
   >リダイレクト URL で、ユーザーが同一のアクティビティの条件も満たしていると見なされる場合、リダイレクトオファーが無限ループに陥るという情報を追加しました。ユーザーがリダイレクトされた後にアクティビティに再適合しないことを確認します。

1. 目的のオプションを選択してリダイレクトオファーをカスタマイズします。

   * **すべての URL パラメーターを含める：** 前のページに存在するすべての URL パラメーターをリダイレクトされたページに反映する場合は、切り替えスイッチをスライドしてこのオプションを有効にします。

     例えば、男性向け商品のページから男性向けシャツカテゴリのページにユーザーを直接リダイレクトする場合などです。また、URL で動的なパラメーターを渡して、ユーザーが電子メール、バナー広告、検索広告経由でサイトに到達したか、または別の経路でサイトに到達したかを追跡する必要もあります。このオプションを有効にすると、ページ上でリダイレクトオファーが有効になります `https://www.mycompany.com/mens.html?emailId=123` 自動的にになる `https://www.mycompany.com/mensShirts.html?emailId=123` url ボックスに入力した内容が `https://www.mycompany.com/mensShirts.html`.

   * **mbox セッション ID を渡す：** 別のドメインにリダイレクトする場合に必要です。 切り替えスイッチをスライドしてこのオプションを有効にするには、 `sessionId` が自動的にリダイレクトに含まれる。 このオプションは、メールまたはドメイン間のクリックをテストする場合にのみ必要です。 この `sessionId` を使用して訪問者の Cookie を照合し、訪問者を引き続き追跡して適切なコンテンツが表示されるようにします。

     ファーストパーティおよびサードパーティの Cookie 設定を使用する場合、ドメインを横断する際に mbox セッション ID を渡す必要はありません。 この値はサードパーティ Cookie に保持されているため、URL に含める必要がないからです。

1. **[!UICONTROL Save]** をクリックします。

>[!NOTE]
>
>これらのテストを開始する前に、実装コンサルタントに問い合わせてください。

## アクティビティでのリダイレクトオファーの使用

次を使用して、リダイレクトオファーを適用する必要があります [[!UICONTROL Form-Based Experience Composer]](/help/main/c-experiences/form-experience-composer.md). 現在、を使用してリダイレクトオファーを適用することはできません [!UICONTROL Visual Experience Composer] （VEC）。

この [!DNL Adobe Target] [!UICONTROL Form-Based Experience Composer] は、で使用するエクスペリエンスの作成に役立つ、視覚的でないエクスペリエンスおよびオファー作成インターフェイスです [!UICONTROL A/B Tests], [!UICONTROL Experience Targeting] （XT）、 [!UICONTROL Automated Personalization] （AP）および [!UICONTROL Recommendations] visual experience composer が使用できない場合のアクティビティまたは使用が実用的なアクティビティ。 例えば、 [!UICONTROL Form-Based Experience Composer] リダイレクトオファーを使用するエクスペリエンスを作成する場合。

1. でのアクティビティの作成または編集 [!UICONTROL Form-Based Experience Composer].

   参照： [フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md) 詳細な手順については、を参照してください。

1. 目的の場所を指定し、必要に応じてオーディエンスの絞り込みを追加します。

1. のドロップダウンリストをクリックします。 **[!UICONTROL Content]** セクションで、 **[!UICONTROL Change Redirect Offer]**.

   ![リダイレクトオファーオプションの変更](/help/main/c-experiences/c-manage-content/assets/change-redirect-offer-option2.png)

1. から目的のリダイレクトオファーを選択 [!UICONTROL Select Remote Offer] ダイアログボックスで、 **[!UICONTROL Done]**.

1. アクティビティの設定を終了します。

## トレーニングビデオ：フォームベースのコンポーザー ![チュートリアルバッジ](/help/main/assets/tutorial.png)

このビデオでは、のデモを紹介します [!UICONTROL Form-Based Experience Composer]（リダイレクトオファーの作成に使用できます）。

* を使用したアクティビティの作成 [!UICONTROL Form-Based Experience Composer]
* を使用するタイミングについて [!UICONTROL Form-Based Experience Composer] との比較 [!UICONTROL Visual Experience Composer]
* 場所のターゲット設定の調整

>[!VIDEO](https://video.tv.adobe.com/v/17390)