---
keywords: リダイレクトオファー；リダイレクトオファーの作成；HTML オファーの追加；リダイレクトですべての URL パラメーターを渡す
description: リダイレクトオファーを作成して、ブラウザーを新しいページにシームレスにガイドする方法を説明します。
title: リダイレクトオファーの作成方法
feature: Experiences and Offers
exl-id: b7b960cb-5057-455b-8fab-86dd37343a04
source-git-commit: e8201198dc6ac36e803153d5c6b345a30716204a
workflow-type: tm+mt
source-wordcount: '1016'
ht-degree: 25%

---

# リダイレクトオファーの作成

リダイレクトオファーを作成して、ブラウザーを新しいページにシームレスにガイドする方法を説明します。

ページ内でコンテンツの一部を変更するのではなく、まったく異なる 2 つのページをテストすることができます。この場合、A/B テストではページ A とページ B を比較します。デフォルトのページ A を指すエクスペリエンスと、ページ B にリダイレクトするエクスペリエンスの 2 つを使用して [!UICONTROL A/B Test] アクティビティを設定します。オファーは、訪問者を別のページにリダイレクトするように設定されます。

>[!NOTE]
>
> * リダイレクトオファーは、[!UICONTROL Offers]/[!UICONTROL Code Offers] ページまたは [Forms ベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md) で作成できます。 [!UICONTROL Visual Experience Composer] （VEC）では、リダイレクトオファーの作成または適用はできません。 コンテンツは [!DNL Target] リクエストの場所に挿入されるので、これらの場所は、グローバル [!DNL Target] リクエストには適していない可能性が高くなります。
>
>* AJAX mbox では、リダイレクトオファーを使用できません（`mboxUpdate`）。
>
>* [[!UICONTROL Analytics as the reporting source]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) （A4T）を使用するアクティビティでリダイレクトオファーを使用する場合、実装が特定の最小要件を満たす必要があります。 また、知っておくべき重要な情報があります。[ リダイレクトオファー – A4T FAQ](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905) を参照してください。
>
>* リダイレクトするエクスペリエンスの設定については、[URL にリダイレクト](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA)を参照してください。

リダイレクトオファーでは、JavaScript コードを実行してブラウザーをリダイレクトします。このオファーでは `window.location.replace();` メソッドを使用するので、訪問者のリダイレクト元のページはブラウザー履歴に保存されません。このプロセスにより、訪問者はブラウザーで「戻る」ボタンを使用できます。

>[!NOTE]
>
>ランディングページのリファラー値を渡す場合は、リダイレクトオファーではなく、HTMLオファーを使用します。

## [!UICONTROL Code Offers] ページからのリダイレクトオファーの作成

1. 「**[!UICONTROL Offers]**」をクリックして、「**[!UICONTROL Code Offers]**」タブを選択します。
1. **[!UICONTROL Create Offer]**／**[!UICONTROL Redirect Offer]**&#x200B;をクリックします。
1. オファーのわかりやすい名前を入力します。

   わかりやすい名前を指定すると、作成者や他のユーザーが [!UICONTROL Assets] ライブラリでオファーをすばやく見つけやすくなります。

1. （条件付き） [Target Premium アカウント ](/help/main/c-intro/intro.md#premium) をお持ちの場合は、目的の [ ワークスペース ](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md##section_B82EB409B67C4D9D9D20CE30E48DB1DC) を選択します。

1. リダイレクト先となる一意のコンテンツまたは宛先の URL を指定します。 この URL は絶対 URL である必要があります。

   >[!NOTE]
   >
   >リダイレクト URL で、ユーザーが同一のアクティビティの条件も満たしていると見なされる場合、リダイレクトオファーが無限ループに陥るという情報を追加しました。ユーザーがリダイレクトされた後にアクティビティに再適合しないことを確認します。

1. 目的のオプションを選択してリダイレクトオファーをカスタマイズします。

   * **[!UICONTROL Include all URL parameters]:** 前のページに存在するすべての URL パラメーターを、リダイレクトされたページに反映する場合は、このオプションを有効にします。

     例えば、男性向け商品のページから男性向けシャツカテゴリのページにユーザーを直接リダイレクトする場合などです。また、URL の動的パラメーターを渡す必要もあります。この方法は、ユーザーがメール、バナー広告、検索広告またはオーガニックを介してサイトに到達したかどうかを追跡する方法であるからです。 このオプションを有効にすると、URL ボックスに入力したすべてのものがリク `https://www.mycompany.com/mensShirts.html` ストされたときに、ページ `https://www.mycompany.com/mens.html?emailId=123` のリダイレクトオファーが自動的に `https://www.mycompany.com/mensShirts.html?emailId=123` になります。

   * **[!UICONTROL Pass mbox session ID]:** 別のドメインにリダイレクトする必要があります。 `sessionId` をリダイレクトに自動的に含める場合は、切り替えスイッチをスライドしてこのオプションを有効にします。 このオプションは、メールまたはドメイン間のクリックをテストする場合にのみ必要です。 この `sessionId` を使用して訪問者の Cookie を照合し、訪問者を引き続き追跡して適切なコンテンツが表示されるようにします。

     ファーストパーティおよびサードパーティの Cookie 設定を使用する場合、ドメインを横断する際に mbox セッション ID を渡す必要はありません。 この値はサードパーティ Cookie に保持されているため、URL に含める必要がないからです。

1. **[!UICONTROL Create]** をクリックします。

>[!IMPORTANT]
>
>これらのテストを開始する前に、実装コンサルタントに問い合わせてください。

## [!UICONTROL Form-Based Experience Composer] を使用したリダイレクトオファーの作成

1. [ フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md) を使用してアクティビティを作成する際に、「**[!UICONTROL Content]**」セクションを表示する場所を選択します。
1. 「**[!UICONTROL Content]**」ドロップダウンリストをクリックし、**[!UICONTROL List]** アイコン（![ リスト ](/help/main/assets/icons/MoreSmallList.svg)）をクリックしてから「**[!UICONTROL Change Redirect Offer]**」をクリックします。
1. **[!UICONTROL Create Offer]**／**[!UICONTROL Redirect Offer]**&#x200B;をクリックします。
1. オファーのわかりやすい名前を入力します。

   わかりやすい名前を指定すると、作成者や他のユーザーが [!UICONTROL Assets] ライブラリでオファーをすばやく見つけやすくなります。

1. リダイレクト先となる一意のコンテンツまたは宛先の URL を指定します。 この URL は絶対 URL である必要があります。

   >[!NOTE]
   >
   >リダイレクト URL で、ユーザーが同一のアクティビティの条件も満たしていると見なされる場合、リダイレクトオファーが無限ループに陥るという情報を追加しました。ユーザーがリダイレクトされた後にアクティビティに再適合しないことを確認します。

1. 目的のオプションを選択してリダイレクトオファーをカスタマイズします。

   * **[!UICONTROL Include all URL parameters]:** 前のページに存在するすべての URL パラメーターをリダイレクトされたページに反映する場合は、切り替えスイッチをスライドしてこのオプションを有効にします。

     例えば、男性向け商品のページから男性向けシャツカテゴリのページにユーザーを直接リダイレクトする場合などです。また、URL の動的パラメーターを渡す必要もあります。この方法は、ユーザーがメール、バナー広告、検索広告またはオーガニックを介してサイトに到達したかどうかを追跡する方法であるからです。 このオプションを有効にすると、URL ボックスに入力したすべてのものがリク `https://www.mycompany.com/mensShirts.html` ストされたときに、ページ `https://www.mycompany.com/mens.html?emailId=123` のリダイレクトオファーが自動的に `https://www.mycompany.com/mensShirts.html?emailId=123` になります。

   * **[!UICONTROL Pass mbox session ID]:** 別のドメインにリダイレクトする必要があります。 `sessionId` をリダイレクトに自動的に含める場合は、切り替えスイッチをスライドしてこのオプションを有効にします。 このオプションは、メールまたはドメイン間のクリックをテストする場合にのみ必要です。 この `sessionId` を使用して訪問者の Cookie を照合し、訪問者を引き続き追跡して適切なコンテンツが表示されるようにします。

     ファーストパーティおよびサードパーティの Cookie 設定を使用する場合、ドメインを横断する際に mbox セッション ID を渡す必要はありません。 この値はサードパーティ Cookie に保持されているため、URL に含める必要がないからです。

1. **[!UICONTROL Create]** をクリックします。

>[!IMPORTANT]
>
>これらのテストを開始する前に、実装コンサルタントに問い合わせてください。

## アクティビティでのリダイレクトオファーの使用

[[!UICONTROL Form-Based Experience Composer]](/help/main/c-experiences/form-experience-composer.md) を使用してリダイレクトオファーを適用します。 現在、[!UICONTROL Visual Experience Composer] （VEC）を使用してリダイレクトオファーを適用することはできません。

[!DNL Adobe Target] [!UICONTROL Form-Based Experience Composer] は、[!UICONTROL A/B Tests]、[!UICONTROL Experience Targeting] （XT）、[!UICONTROL Automated Personalization] （AP）、[!UICONTROL Recommendations] の各アクティビティで使用するエクスペリエンスを作成する際に、そのエクスペリエンスが使用できない、または実用的でない場合に役立つ、非視覚的なエクスペリ [!UICONTROL Visual Experience Composer] ンスおよびオファー作成インターフェイスです。 例えば、[!UICONTROL Form-Based Experience Composer] を使用して、リダイレクトオファーを使用するエクスペリエンスを作成できます。

1. [!UICONTROL Form-Based Experience Composer] でアクティビティを作成または編集します。

   詳しい手順については、[ フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md) を参照してください。

1. 目的の場所を指定し、必要に応じてオーディエンスの絞り込みを追加します。

1. 「**[!UICONTROL Content]**」ドロップダウンリストをクリックし、**[!UICONTROL List]** アイコン（![ リスト ](/help/main/assets/icons/MoreSmallList.svg)）をクリックしてから「**[!UICONTROL Change Redirect Offer]**」をクリックします。
1. [!UICONTROL Select Redirect Offer] ダイアログボックスで目的のリダイレクトオファーを選択し、「**[!UICONTROL Add]**」をクリックします。
1. アクティビティの設定を終了します。
