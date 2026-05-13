---
keywords: リモートオファー；キャッシュされたコンテンツ；動的コンテンツ；url タイプ
description: ' [!DNL Target] のリモートオファーを活用して、CMSまたはその他のシステムから外部コンテンツをホストする方法について説明します。'
title: リモートオファーの作成方法
feature: Experiences and Offers
exl-id: 6a5283ee-c1fb-49f7-8e7f-c23ccde26ade
TQID: https://experienceleague.adobe.com/maKcis5ROOKMcc3-axxGv1qJIQzC6o-Qc-Cjl8clQ1I
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 1040
ht-degree: 19%

---

# リモートオファーを作成

[!DNL Adobe Target]以外のコンテンツをホストするためにリモートオファーを使用し、[!DNL Target]がこのコンテンツを参照してユーザーのWeb サイトに配信できるようにします。 このコンテンツは、使いやすさやセキュリティ上の理由から、CMS （コンテンツ管理システム）や他のシステムに格納できます。

リモートオファーは、[!UICONTROL Offers] > [!UICONTROL Code Offers] ページまたは[Forms ベースのExperience Composer](/help/main/c-experiences/form-experience-composer.md)で作成できます。 [!UICONTROL Visual Experience Composer] （VEC）でリモート オファーを作成または適用することはできません。 コンテンツは[!DNL Target] リクエストの場所に挿入されるので、これらの場所はグローバル [!DNL Target] リクエストには適していない可能性が高くなります。

リモートオファーの例をいくつか挙げます。

* 様々なバージョンのクロス販売
* 動的な買い物かごのメッセージ
* フォーム
* カルキュレーター
* 金利の更新
* 電子メール
* キオスク
* 音声アシスタント

## リモートオファーのベストプラクティス {#section_7718512D08E14121B6F6B8C38134F4BC}

アクティビティでリモートオファーを使用する際のベストプラクティス：

* リモートオファーは、次の場所でサポートされています。

   * A/B アクティビティ
   * エクスペリエンスのターゲット設定（XT）アクティビティ
   * フォームベースワークフロー

* 次の場所では、リモートオファーはサポートされていません。

   * [&#x200B; プレミアム機能](/help/main/c-intro/intro.md#premium) （Automated Personalization （AP）、自動ターゲット、およびレコメンデーション）
   * Multivariate Testing（MVT）は、リモートオファーをサポートしていないVECに依存しているため、

* オファーが[!DNL Target] リクエストと同じドメインに存在する場合、[!UICONTROL Cached] オプションを使用すると、オファーの場所を説明する際に相対URLを使用できます。

  つまり、アクティビティをステージングサーバーから実稼動環境に移動すると、URLを手動で変更することなく、コンテンツに自動的にアクセスできるようになります。

* テストでサーバーによって動的に生成されたデータが含まれる場合は、[!UICONTROL Dynamic] オプションが適切な選択肢になる可能性があります。
* 既存のリモート オファーコンテンツの外観のみをテストする場合は、[!UICONTROL Visual Experience Composer]を使用して、コンテンツ管理システムから返されるコンテンツの外観を変更します。
* 特定のケースに最適なオファーを選択するには、[Remote Offer Selection Matrix](#reference_B23BEDD29DDD47709A7651AFD27E776B) （以下）を使用してください。 ご質問がある場合は、アカウント担当者にお問い合わせください。

## [!UICONTROL Code Offers] ページからリモート オファーを作成

1. 「**[!UICONTROL Offers]**」をクリックし、「**[!UICONTROL Code Offers]**」タブを選択します。

1. **[!UICONTROL Create Offer]**／**[!UICONTROL Remote Offer]**&#x200B;をクリックします。

1. [!UICONTROL Create Remote Offer] ダイアログで、オファーのわかりやすい名前を入力します。

   わかりやすい名前を付けると、[!UICONTROL Offers] ライブラリでオファーをすばやく見つけることができます。

1. （条件付き）Target Premium アカウント [&#128279;](/help/main/c-intro/intro.md#premium)をお持ちの場合は、目的の[&#x200B; ワークスペース &#x200B;](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md##section_B82EB409B67C4D9D9D20CE30E48DB1DC)を選択します。

1. リダイレクト URL タイプを指定します。

   詳しくは、以下の「[&#x200B; リダイレクト URL タイプ：[!UICONTROL Onsite Cached]または[!UICONTROL Onsite Dynamic]](#url-type)」を参照してください。

1. リモートオファーの絶対リモート URLを指定します。

1. **[!UICONTROL Create]** をクリックします。

## [!UICONTROL Form-Based Experience Composer]を使用したリモート オファーの作成

1. [&#x200B; フォームベースのExperience Composer](/help/main/c-experiences/form-experience-composer.md)を使用してアクティビティを作成する際に、**[!UICONTROL Content]** セクションを表示する場所を選択します。
1. **[!UICONTROL Content]** ドロップダウンリストをクリックし、**[!UICONTROL List]** アイコン （![&#x200B; リスト &#x200B;](/help/main/assets/icons/MoreSmallList.svg)）をクリックしてから、**[!UICONTROL Change Remote Offer]**&#x200B;をクリックします。

1. **[!UICONTROL Create Offer]**／**[!UICONTROL Remote Offer]**&#x200B;をクリックします。

1. オファーのわかりやすい名前を入力します。

   わかりやすい名前を付けると、[!UICONTROL Assets] ライブラリでオファーをすばやく見つけることができます。

1. （条件付き）Target Premium アカウント [&#128279;](/help/main/c-intro/intro.md#premium)をお持ちの場合は、目的の[&#x200B; ワークスペース &#x200B;](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md##section_B82EB409B67C4D9D9D20CE30E48DB1DC)を選択します。

1. リダイレクト URL タイプを指定します。

   詳しくは、以下の「[&#x200B; リダイレクト URL タイプ：[!UICONTROL Onsite Cached]または[!UICONTROL Onsite Dynamic]](#url-type)」を参照してください。

1. リモートオファーのリモート URLを指定します。

1. **[!UICONTROL Create]** をクリックします。

## リダイレクト URLの種類：[!UICONTROL Onsite Cached]または[!UICONTROL Onsite Dynamic] {#url-type}

次の情報は、2つのオプションの違いを理解するのに役立ちます。

### [!UICONTROL Onsite Cached] URL

キャッシュされたリモート オファーのコンテンツは[!DNL Target]から提供されます。

2時間ごとに、[!DNL Target]はリモート URLでコンテンツを取得し、そのコンテンツを[!DNL Target]内に保存します。 訪問者がリモート オファーを含むエクスペリエンスを持つサイトを読み込むと、[!DNL Target]がオファーを配信します。

[!DNL Target]にログインしたユーザーがコンテンツを変更できないため、キャッシュされたリモート オファーはセキュリティを強化します。 コンテンツを変更するには、コンテンツ管理システムやその他のシステムにログインし、そこでコンテンツを変更する必要がありました。

キャッシュされたリモートオファーには、絶対または相対 URL を指定することができます。

### [!UICONTROL Onsite Dynamic] URL

動的なリモート オファーは、[!DNL Target]からではなく、コンテンツ管理またはその他のシステムから提供されます。

訪問者がリモートオファーを含むエクスペリエンスを含むサイトを読み込むたびに、コンテンツを定期的にキャッシュしてから[!DNL Target]によって配信することは望ましくないかもしれません。 代わりに、コンテンツをホストしているシステムを呼び出し、返されるオファーがユーザーごとに動的（または異なる）ように、特定の情報を渡す可能性があります。 例えば、あるユーザーが、動的リモートオファーのエクスペリエンスを含むクレジットカード用ウェブサイトにログインしたら、そのユーザーのアカウント情報をパラメーターとして URL に渡すことができます。 そうすると、ウェブサイトは、アカウントの残高など、ユーザーに特化した情報を提供することができます。

**[!UICONTROL Add Parameter]**&#x200B;をクリックして、1つ以上の[!DNL Target]要求または要求パラメーターを追加できます。

## アクティビティでのリモートオファーの使用

[!UICONTROL Form-Based Experience Composer]を使用してリモート オファーを適用します。 現在、[!UICONTROL Visual Experience Composer] （VEC）を使用してリモート オファーを適用することはできません。

[!DNL Adobe Target] [!UICONTROL Form-Based Experience Composer]は、[!UICONTROL Visual Experience Composer]が使用できない場合や使用できない場合に、[!UICONTROL A/B Tests]、[!UICONTROL Experience Targeting] （XT）、[!UICONTROL Automated Personalization] （AP）、[!UICONTROL Recommendations] アクティビティで使用するエクスペリエンスの作成に役立つ、視覚的でないエクスペリエンスおよびオファー作成インターフェイスです。 例えば、[!UICONTROL Form-Based Experience Composer]を使用して、リモート オファーを使用するエクスペリエンスを作成できます。

1. [!UICONTROL Form-Based Experience Composer]でアクティビティを作成または編集します。

   詳細な手順については、[&#x200B; フォームベースのExperience Composer](/help/main/c-experiences/form-experience-composer.md)を参照してください。

1. 必要に応じて、目的の場所を指定し、オーディエンスの絞り込みを追加します。

1. **[!UICONTROL Content]** ドロップダウンリストをクリックし、**[!UICONTROL List]** アイコン （![&#x200B; リスト &#x200B;](/help/main/assets/icons/MoreSmallList.svg)）をクリックしてから、**[!UICONTROL Change Remote Offer]**&#x200B;をクリックします。

1. [!UICONTROL Change Remote Offer] ダイアログボックスから目的のリモートオファーを選択し、**[!UICONTROL Create Offer]** > **[!UICONTROL Remote Offer]**&#x200B;をクリックします。

1. アクティビティの設定を終了します。

## ダイナミックリモートオファーの仕組み {#concept_CC2A969420B34364A9FA78C1CE251818}

動的なオファーでは、動的なページテクノロジーを使用してオファーに値を渡します。

オファーはページのレンダリング後に実行されます。 非表示のiFrameがデータを収集し、フレームからコピーしてページに挿入し、渡された値を読み込みます。

![remote_offer_howitworks_2 image](assets/remote_offer_howitworks_2.jpeg)

1. 訪問者のブラウザーは、サーバーからページをリクエストします。

2. ブラウザーは、mboxを含むページをレンダリングします。

3. `mboxCreate`呼び出しには、動的コンテンツのレンダリングに必要なパラメーターが含まれています。

4. [!DNL Target]は、動的コンテンツの場所とそのパラメーターを含むURLを返します。 mbox領域にiFrameを設定します。

5. ブラウザーはURLをリクエストし、ページ内でレンダリングします。

## リモートオファーの選択指標 {#reference_B23BEDD29DDD47709A7651AFD27E776B}

リモート オファー選択マトリックスは、選択するリモート オファーの種類（[!UICONTROL Onsite Cached]または[!UICONTROL Onsite Dynamic]）を決定するのに役立ちます。

| 機能 | オンサイトのキャッシュ | オンサイトの動的 |
|--- |--- |--- |
| 訪問者がリクエストするたびに更新 | × | ○ |
| コンテンツの更新 | 2時間ごとにキャッシュ | リクエストのたびにすぐに更新 |
| 読み込み時間 | 高速 | リクエスト処理が原因となり低速 |
| ページ上での JavaScript の確認 | ○ | 不可（URL 経由で渡すことは可能） |
| オファーへの JavaScript の追加 | ○ | ○ |
| オファーの URL | 絶対的または相対的 | 相対 |
| リクエストするコンピューター | Adobe サーバー | 訪問者の Cookie を処理する訪問者のコンピューター |
