---
keywords: リダイレクトオファー；リダイレクトオファーの作成；html オファーの追加；リダイレクトですべてのURL パラメーターを渡す
description: ブラウザーを新しいページにシームレスに誘導するリダイレクトオファーを作成する方法について説明します。
title: リダイレクトオファーを作成するにはどうすればよいですか？
feature: Experiences and Offers
exl-id: b7b960cb-5057-455b-8fab-86dd37343a04
TQID: https://experienceleague.adobe.com/-kFkgCCbzb34aNAxW-Q1CqmyK9rETL0qVMQeEP9JtrY
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: c93393a4-e558-47e1-992e-c91ed4d480ce
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 16fb7a1902ea76cab56a93fa141a32a3c6bc4467
workflow-type: tm+mt
source-wordcount: 1094
ht-degree: 23%

---

# リダイレクトオファーの作成

ブラウザーを新しいページにシームレスに誘導するリダイレクトオファーを作成する方法について説明します。

ページ内でコンテンツの一部を変更するのではなく、まったく異なる 2 つのページをテストすることができます。 この場合、A/B テストはページ Aとページ Bを比較します。[!UICONTROL A/B Test] アクティビティを2つのエクスペリエンスで設定します。1つはデフォルトのページ Aを指し、もう1つはページ Bにリダイレクトします。このオファーは、訪問者を別のページにリダイレクトするように設定されています。

>[!NOTE]
>
> * リダイレクトオファーは、[!UICONTROL Offers] > [!UICONTROL Code Offers] ページまたは[Forms ベースのExperience Composer](/help/main/c-experiences/form-experience-composer.md)で作成できます。 [!UICONTROL Visual Experience Composer] （VEC）でリダイレクト オファーを作成または適用することはできません。 コンテンツは[!DNL Target] リクエストの場所に挿入されるので、これらの場所はグローバル [!DNL Target] リクエストには適していない可能性が高くなります。
>
>* AJAX mbox （`mboxUpdate`）では、リダイレクトオファーを使用できません。
>
>* [[!UICONTROL Analytics as the reporting source]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) （A4T）を使用するアクティビティでのリダイレクト オファーの場合、実装は特定の最小要件を満たす必要があります。 また、知っておくべき重要な情報があります。 [ リダイレクトオファー – A4T FAQ](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905)を参照してください。
>
>* リダイレクトするエクスペリエンスの設定については、[URL にリダイレクト](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA)を参照してください。

リダイレクトオファーでは、JavaScript コードを実行してブラウザーをリダイレクトします。 このオファーでは `window.location.replace();` メソッドを使用するので、訪問者のリダイレクト元のページはブラウザー履歴に保存されません。 このプロセスにより、訪問者はブラウザーで「戻る」ボタンを使用できます。

>[!NOTE]
>
>ランディングページのリファラー値を渡す場合は、リダイレクトオファーではなくHTML オファーを使用します。

## [!UICONTROL Code Offers] ページからリダイレクト オファーを作成します

1. 「**[!UICONTROL Offers]**」をクリックし、「**[!UICONTROL Code Offers]**」タブを選択します。
1. **[!UICONTROL Create Offer]**／**[!UICONTROL Redirect Offer]**&#x200B;をクリックします。
1. オファーのわかりやすい名前を入力します。

   わかりやすい名前を付けると、[!UICONTROL Assets] ライブラリでオファーをすばやく見つけることができます。

1. （条件付き）Target Premium アカウント [をお持ちの場合は、目的の[ ワークスペース ](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md##section_B82EB409B67C4D9D9D20CE30E48DB1DC)を選択します。](/help/main/c-intro/intro.md#premium)

1. リダイレクト先の一意のコンテンツまたは宛先のURLを指定します。 このURLは絶対URLでなければなりません。

   >[!NOTE]
   >
   >リダイレクト URL で、ユーザーが同一のアクティビティの条件も満たしていると見なされる場合、リダイレクトオファーが無限ループに陥るという情報を追加しました。 これを防ぐには、リダイレクト URLにクエリパラメーターを追加します（例：`?redirect=true`）。 次に、アクティビティオーディエンスまたはテンプレートルールで、このクエリパラメーターが存在しないことを確認します。 これにより、ユーザーはリダイレクト後にアクティビティの再選定を行わなくなります。

1. 目的のオプションを選択してリダイレクトオファーをカスタマイズします。

   * **[!UICONTROL Include all URL parameters]:**&#x200B;前のページに存在するすべてのURL パラメーターをリダイレクトされたページに反映する場合は、このオプションを有効にします。

     例えば、男性向け商品のページから男性向けシャツカテゴリのページにユーザーを直接リダイレクトする場合などです。 また、この方法は、電子メール、バナー広告、検索広告、またはオーガニックを介してサイトに到達したかどうかを追跡する方法であるため、URL内の動的パラメーターを渡す必要があります。 このオプションを有効にすると、URL ボックスに入力したすべての項目が`https://www.mycompany.com/mensShirts.html`の場合、ページ `https://www.mycompany.com/mens.html?emailId=123`上のリダイレクト オファーは自動的に`https://www.mycompany.com/mensShirts.html?emailId=123`になります。

   * **[!UICONTROL Pass mbox session ID]:**&#x200B;別のドメインにリダイレクトする必要があります。 `sessionId`をリダイレクトに自動的に含める場合は、切り替えスイッチをスライドしてこのオプションを有効にします。 このオプションは、電子メールのクリック数またはドメイン間のクリック数をテストする場合にのみ必要です。 この `sessionId` を使用して訪問者の Cookie を照合し、訪問者を引き続き追跡して適切なコンテンツが表示されるようにします。

     1st パーティおよび3rd パーティのCookie設定を使用する場合、ドメインを渡す際にmbox セッション IDを渡す必要はありません。 この値はサードパーティ Cookie に保持されているため、URL に含める必要がないからです。

1. **[!UICONTROL Create]** をクリックします。

>[!IMPORTANT]
>
>テストを開始する前に、実装コンサルタントに依頼してください。

## [!UICONTROL Form-Based Experience Composer]を使用したリダイレクト オファーの作成

1. [ フォームベースのExperience Composer](/help/main/c-experiences/form-experience-composer.md)を使用してアクティビティを作成する際に、**[!UICONTROL Content]** セクションを表示する場所を選択します。
1. **[!UICONTROL Content]** ドロップダウンリストをクリックし、**[!UICONTROL List]** アイコン （![ リスト ](/help/main/assets/icons/MoreSmallList.svg)）をクリックしてから、**[!UICONTROL Change Redirect Offer]**&#x200B;をクリックします。
1. **[!UICONTROL Create Offer]**／**[!UICONTROL Redirect Offer]**&#x200B;をクリックします。
1. オファーのわかりやすい名前を入力します。

   わかりやすい名前を付けると、[!UICONTROL Assets] ライブラリでオファーをすばやく見つけることができます。

1. リダイレクト先の一意のコンテンツまたは宛先のURLを指定します。 このURLは絶対URLでなければなりません。

   >[!NOTE]
   >
   >リダイレクト URL で、ユーザーが同一のアクティビティの条件も満たしていると見なされる場合、リダイレクトオファーが無限ループに陥るという情報を追加しました。 これを防ぐには、リダイレクト URLにクエリパラメーターを追加します（例：`?redirect=true`）。 次に、アクティビティオーディエンスまたはテンプレートルールで、このクエリパラメーターが存在しないことを確認します。 これにより、ユーザーはリダイレクト後にアクティビティの再選定を行わなくなります。

1. 目的のオプションを選択してリダイレクトオファーをカスタマイズします。

   * **[!UICONTROL Include all URL parameters]:**&#x200B;前のページに存在するすべてのURL パラメーターをリダイレクトされたページに反映する場合は、切り替えスイッチをスライドしてこのオプションを有効にします。

     例えば、男性向け商品のページから男性向けシャツカテゴリのページにユーザーを直接リダイレクトする場合などです。 また、この方法は、電子メール、バナー広告、検索広告、またはオーガニックを介してサイトに到達したかどうかを追跡する方法であるため、URL内の動的パラメーターを渡す必要があります。 このオプションを有効にすると、URL ボックスに入力したすべての項目が`https://www.mycompany.com/mensShirts.html`の場合、ページ `https://www.mycompany.com/mens.html?emailId=123`上のリダイレクト オファーは自動的に`https://www.mycompany.com/mensShirts.html?emailId=123`になります。

   * **[!UICONTROL Pass mbox session ID]:**&#x200B;別のドメインにリダイレクトする必要があります。 `sessionId`をリダイレクトに自動的に含める場合は、切り替えスイッチをスライドしてこのオプションを有効にします。 このオプションは、電子メールのクリック数またはドメイン間のクリック数をテストする場合にのみ必要です。 この `sessionId` を使用して訪問者の Cookie を照合し、訪問者を引き続き追跡して適切なコンテンツが表示されるようにします。

     1st パーティおよび3rd パーティのCookie設定を使用する場合、ドメインを渡す際にmbox セッション IDを渡す必要はありません。 この値はサードパーティ Cookie に保持されているため、URL に含める必要がないからです。

1. **[!UICONTROL Create]** をクリックします。

>[!IMPORTANT]
>
>テストを開始する前に、実装コンサルタントに依頼してください。

## アクティビティでのリダイレクトオファーの使用

[[!UICONTROL Form-Based Experience Composer]](/help/main/c-experiences/form-experience-composer.md)を使用してリダイレクト オファーを適用します。 現在、[!UICONTROL Visual Experience Composer] （VEC）を使用してリダイレクト オファーを適用することはできません。

[!DNL Adobe Target] [!UICONTROL Form-Based Experience Composer]は、[!UICONTROL Visual Experience Composer]が使用できない場合や使用できない場合に、[!UICONTROL A/B Tests]、[!UICONTROL Experience Targeting] （XT）、[!UICONTROL Automated Personalization] （AP）、[!UICONTROL Recommendations] アクティビティで使用するエクスペリエンスの作成に役立つ、視覚的でないエクスペリエンスおよびオファー作成インターフェイスです。 例えば、[!UICONTROL Form-Based Experience Composer]を使用して、リダイレクト オファーを使用するエクスペリエンスを作成できます。

1. [!UICONTROL Form-Based Experience Composer]でアクティビティを作成または編集します。

   詳細な手順については、[ フォームベースのExperience Composer](/help/main/c-experiences/form-experience-composer.md)を参照してください。

1. 必要に応じて、目的の場所を指定し、オーディエンスの絞り込みを追加します。

1. **[!UICONTROL Content]** ドロップダウンリストをクリックし、**[!UICONTROL List]** アイコン （![ リスト ](/help/main/assets/icons/MoreSmallList.svg)）をクリックしてから、**[!UICONTROL Change Redirect Offer]**&#x200B;をクリックします。
1. [!UICONTROL Select Redirect Offer] ダイアログボックスから目的のリダイレクトオファーを選択し、**[!UICONTROL Add]**&#x200B;をクリックします。
1. アクティビティの設定を終了します。
