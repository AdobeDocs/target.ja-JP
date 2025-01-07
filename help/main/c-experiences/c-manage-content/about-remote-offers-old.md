---
keywords: リモートオファー；リモートオファー選択マトリックス；キャッシュされたコンテンツ；動的コンテンツ；URL タイプ
description: Adobeでリモートオファーを使用して、外部のコンテンツ  [!DNL Target] CMSやその他のシステムのコンテンツ）をホストする方法を説明します。 リモートオファーを使用する理由を見つけます。
title: リモートオファーを作成するにはどうすればよいですか？
feature: Experiences and Offers
exl-id: 6a5283ee-c1fb-49f7-8e7f-c23ccde26ade
source-git-commit: e8201198dc6ac36e803153d5c6b345a30716204a
workflow-type: tm+mt
source-wordcount: '1017'
ht-degree: 29%

---

# リモートオファーを作成

リモートオファーを使用すると、[!DNL Adobe Target] 外にあり、[!DNL Target] が参照してユーザーのウェブサイトに提供するコンテンツをホスティングすることができます。このコンテンツは、使いやすさやセキュリティ上の理由から、コンテンツ管理（CMS）やその他のシステムに格納されている場合があります。

>[!NOTE]
>
>リモートオファーは、[!UICONTROL Offers]/[!UICONTROL Code Offers] ページ、または [Forms ベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md) で作成できます。 Visual Experience Composer （VEC）では、リモートオファーを作成または適用できません。 コンテンツは [!DNL Target] リクエストの場所に挿入されるので、グローバル [!DNL Target] リクエストには適していない可能性が高くなります。
>
>[!DNL Target Classic] には、[!UICONTROL Offer on Your Site] と [!UICONTROL Offer Outside Test&Target] という類似の機能が含まれています。

リモートオファーの例をいくつか挙げます。

* 様々なバージョンのクロス販売
* 動的な買い物かごのメッセージ
* フォーム
* カルキュレーター
* 金利の更新
* 電子メール
* キオスク
* 音声アシスタント

## リモートオファーを使用するためのベストプラクティス {#section_7718512D08E14121B6F6B8C38134F4BC}

アクティビティでリモートオファーを使用する際のベストプラクティス：

* オファーが [!DNL Target] リクエストと同じドメインに存在する場合、「[!UICONTROL Cached]」オプションを使用すると、オファーの場所を説明する際に相対 URL を使用できます。

  つまり、ステージングサーバーから実稼動サーバーにアクティビティを移動する際、URL を手動で変更しなくても、そのコンテンツに自動的にアクセスできるようになります。

* テストにサーバーで動的に生成されるデータが含まれる場合は、[!UICONTROL Dynamic] のオプションが適切な選択肢となる可能性があります。
* 既存のリモートオファーコンテンツの外観のみをテストする場合は、[!UICONTROL Visual Experience Composer] を使用して、コンテンツ管理システムから返されるコンテンツのルックアンドフィールを変更します。
* （以下の [ リモートオファー選択マトリックス ](#reference_B23BEDD29DDD47709A7651AFD27E776B) を使用すると、特定のケースに最適なオファーを選択できます。 ご質問がある場合は、アカウント担当者にお問い合わせください。

## コードオファーページからのリモートオファーの作成

1. 「**[!UICONTROL Offers]**」をクリックして、「**[!UICONTROL Code Offers]**」タブを選択します。

   ![ オファー/コードオファー ](/help/main/c-experiences/c-manage-content/assets/offers-code-offers.png)

1. **[!UICONTROL Create]**／**[!UICONTROL Remote Offer]**&#x200B;をクリックします。

   ![ リモートオファーを作成ダイアログボックス ](/help/main/c-experiences/c-manage-content/assets/remote_offer_ui.png)

1. オファーのわかりやすい名前を入力します。

   わかりやすい名前を指定すると、作成者や他のユーザーが [!UICONTROL Assets] ライブラリでオファーをすばやく見つけやすくなります。

1. リダイレクト URL のタイプを指定します。

   詳しくは、以下の [ リダイレクト URL タイプ：キャッシュまたは動的 ](#url-type) を参照してください。

1. リモートオファーのリモート URL を指定します。

1. **[!UICONTROL Save]** をクリックします。

## フォームベースの Experience Composer を使用したリモートオファーの作成

1. [ フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md) を使用してアクティビティを作成する際に、「**[!UICONTROL Content]**」セクションを表示する場所を選択します。

   ![ フォームベースの Experience Composer の「コンテンツ」セクション ](/help/main/c-experiences/c-manage-content/assets/form-based-content.png)

1. [**[!UICONTROL Default Content]**] ドロップダウンリストをクリックし、[**[!UICONTROL Change Remote Offer]**] をクリックします。

   ![ リモートオファーオプションを変更 ](/help/main/c-experiences/c-manage-content/assets/change-remote-offer.png)

1. **[!UICONTROL Create]**／**[!UICONTROL Remote Offer]**&#x200B;をクリックします。

   ![ リモートオファーを作成ダイアログボックス ](/help/main/c-experiences/c-manage-content/assets/remote_offer_ui.png)

1. オファーのわかりやすい名前を入力します。

   わかりやすい名前を指定すると、作成者や他のユーザーが [!UICONTROL Assets] ライブラリでオファーをすばやく見つけやすくなります。

1. リダイレクト URL のタイプを指定します。

   詳しくは、以下の [ リダイレクト URL タイプ：キャッシュまたは動的 ](#url-type) を参照してください。

1. リモートオファーのリモート URL を指定します。

1. **[!UICONTROL Save]** をクリックします。

## リダイレクト URL のタイプ：キャッシュまたは動的 {#url-type}

次の情報は、2 つのオプションの違いを理解するのに役立ちます。

### キャッシュされた URL

キャッシュされたリモートオファーのコンテンツは、[!DNL Target] から提供されます。

2 時間ごとに、[!DNL Target] はリモート URL からコンテンツを取得し、そのコンテンツを [!DNL Target] 内に保存します。 訪問者がリモートオファーを含むエクスペリエンスでサイトを読み込むと、オファーは [!DNL Target] によって配信されます。

キャッシュされたリモートオファーは、[!DNL Target] にログインしたユーザーがコンテンツを変更できないので、セキュリティが強化されます。 コンテンツを変更するには、コンテンツ管理または他のシステムにログインしてそこでコンテンツを変更する必要があります。

キャッシュされたリモートオファーには、絶対または相対 URL を指定することができます。

### 動的 URL

動的なリモートオファーは、[!DNL Target] ージからではなく、コンテンツ管理またはその他のシステムから提供されます。

リモートオファーを含むエクスペリエンスで訪問者がサイトを読み込むたびに、コンテンツを定期的にキャッシュして、[!DNL Target] で配信したくない場合があります。 代わりに、コンテンツをホストしているシステムを呼び出して、特定の情報を渡し、返されるオファーがユーザーごとに動的（または異なる）になるようにします。 例えば、あるユーザーが、動的リモートオファーのエクスペリエンスを含むクレジットカード用ウェブサイトにログインしたら、そのユーザーのアカウント情報をパラメーターとして URL に渡すことができます。そうすると、ウェブサイトは、アカウントの残高など、ユーザーに特化した情報を提供することができます。

「**[!UICONTROL Add Parameter]**」をクリックして、1 つ以上の [!DNL Target] リクエストまたはリクエストパラメーターを追加できます。

## アクティビティでのリモートオファーの使用

[!UICONTROL Form-Based Experience Composer] を使用してリモートオファーを適用する必要があります。 現在、VEC を使用してリモートオファーを適用することはできません。

[!DNL Adobe Target] [!UICONTROL Form-Based Experience Composer] は、Visual Experience Composer が使用できない、または使用が実用的でない場合に、[!UICONTROL A/B Tests]、[!UICONTROL Experience Targeting] （XT）、[!UICONTROL Automated Personalization] （AP）、および [!UICONTROL Recommendations] アクティビティで使用するエクスペリエンスを作成するのに便利な、非視覚的なエクスペリエンスおよびオファー作成インターフェイスです。 例えば、[!UICONTROL Form-Based Experience Composer] を使用して、リモートオファーを使用するエクスペリエンスを作成できます。

1. [!UICONTROL Form-Based Experience Composer] でアクティビティを作成または編集します。

   詳しい手順については、[ フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md) を参照してください。

1. 目的の場所を指定し、必要に応じてオーディエンスの絞り込みを追加します。

1. 「**[!UICONTROL Content]**」セクションのドロップダウンリストをクリックして、「**[!UICONTROL Change Remote Offer]**」をクリックします。

   ![ リモートオファーオプションを変更 ](/help/main/c-experiences/c-manage-content/assets/change-remote-offer.png)

1. [!UICONTROL Select Remote Offer] ダイアログボックスで目的のリモートオファーを選択し、「**[!UICONTROL Done]**」をクリックします。

1. アクティビティの設定を終了します。

## 動的なリモートオファーの機能 {#concept_CC2A969420B34364A9FA78C1CE251818}

動的なオファーでは、動的なページテクノロジーを使用してオファーに値を渡します。

オファーはページのレンダリング後に実行されます。非表示の iframe は、データを収集してフレームからコピーし、ページに挿入して、渡された値を読み込みます。

![remote_offer_howitworks_2 画像 ](assets/remote_offer_howitworks_2.jpeg)

## リモートオファー選択マトリックス {#reference_B23BEDD29DDD47709A7651AFD27E776B}

リモートオファー選択マトリックスを使用すると、選択するリモートオファーのタイプ（[!UICONTROL Cached] または [!UICONTROL Dynamic]）を決定できます。

| 機能 | キャッシュ | 動的 |
|--- |--- |--- |
| 訪問者がリクエストするたびに更新 | × | ○ |
| コンテンツの更新 | 2 時間ごとにキャッシュ | リクエストのたびにすぐに更新 |
| 読み込み時間 | 高速 | リクエスト処理が原因となり低速 |
| ページ上での JavaScript の確認 | ○ | 不可（URL 経由で渡すことは可能） |
| オファーへの JavaScript の追加 | ○ | ○ |
| オファーの URL | 絶対または相対 | 相対 |
| リクエストするコンピューター | Adobe サーバー | 訪問者の Cookie を処理する訪問者のコンピューター |

## トレーニングビデオ：フォームベースの Composer![ チュートリアルバッジ ](/help/main/assets/tutorial.png)

このビデオでは、リモートオファーを作成する際に使用できる、フォームベースのコンポーザーのデモを紹介します。

* フォームベースの Experience Composer を使用したアクティビティの作成
* フォームベースの Experience Composer と Visual Experience Composer のどちらを使用するかの理解
* 場所のターゲット設定の調整

>[!VIDEO](https://video.tv.adobe.com/v/17390)
