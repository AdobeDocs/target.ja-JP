---
keywords: リモートオファー；リモートオファー選択マトリックス；キャッシュされたコンテンツ；動的コンテンツ；url タイプ
description: Adobe [!DNL Target] でリモートオファーを使用して、外部コンテンツ（CMSまたはその他のシステムのコンテンツ）をホストする方法を説明します。 リモートオファーを利用する理由。
title: リモートオファーの作成方法
feature: Experiences and Offers
exl-id: 6a5283ee-c1fb-49f7-8e7f-c23ccde26ade
source-git-commit: e8201198dc6ac36e803153d5c6b345a30716204a
workflow-type: tm+mt
source-wordcount: '1034'
ht-degree: 29%

---

# リモートオファーを作成

リモートオファーを使用すると、[!DNL Adobe Target] 外にあり、[!DNL Target] が参照してユーザーのウェブサイトに提供するコンテンツをホスティングすることができます。 このコンテンツは、使いやすさやセキュリティ上の理由から、コンテンツ管理（CMS）システムやその他のシステムに保存されている場合があります。

>[!NOTE]
>
>リモートオファーは、[!UICONTROL Offers] > [!UICONTROL Code Offers] ページまたは[Forms ベースのExperience Composer](/help/main/c-experiences/form-experience-composer.md)で作成できます。 Visual Experience Composer （VEC）でリモート オファーを作成または適用することはできません。 コンテンツは[!DNL Target] リクエストの場所に挿入されるため、これらはグローバル [!DNL Target] リクエストには適していない可能性が高くなります。
>
>[!DNL Target Classic]には同様の機能が含まれています：[!UICONTROL Offer on Your Site]と[!UICONTROL Offer Outside Test&Target]。

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

* オファーが[!DNL Target] リクエストと同じドメインに存在する場合、[!UICONTROL Cached] オプションを使用すると、オファーの場所を説明する際に相対URLを使用できます。

  つまり、ステージングサーバーから実稼動サーバーにアクティビティを移動する際、URL を手動で変更しなくても、そのコンテンツに自動的にアクセスできるようになります。

* テストでサーバーによって動的に生成されたデータが含まれる場合は、[!UICONTROL Dynamic] オプションが適切な選択肢になる可能性があります。
* 既存のリモート オファーコンテンツの外観のみをテストする場合は、[!UICONTROL Visual Experience Composer]を使用して、コンテンツ管理システムから返されるコンテンツの外観を変更します。
* 特定のケースに最適なオファーを選択するには、[Remote Offer Selection Matrix](#reference_B23BEDD29DDD47709A7651AFD27E776B) （以下）を使用してください。 ご質問がある場合は、アカウント担当者にお問い合わせください。

## コードオファーページからリモートオファーを作成する

1. 「**[!UICONTROL Offers]**」をクリックし、「**[!UICONTROL Code Offers]**」タブを選択します。

   ![ オファー/ コードオファー](/help/main/c-experiences/c-manage-content/assets/offers-code-offers.png)

1. **[!UICONTROL Create]**／**[!UICONTROL Remote Offer]**&#x200B;をクリックします。

   ![ リモートオファーダイアログボックスを作成](/help/main/c-experiences/c-manage-content/assets/remote_offer_ui.png)

1. オファーのわかりやすい名前を入力します。

   わかりやすい名前を付けると、[!UICONTROL Assets] ライブラリでオファーをすばやく見つけることができます。

1. リダイレクト URL タイプを指定します。

   詳しくは、以下の「[ リダイレクト URL タイプ：キャッシュ済み」または「動的](#url-type)」を参照してください。

1. リモートオファーのリモート URLを指定します。

1. **[!UICONTROL Save]** をクリックします。

## フォームベースのExperience Composerを使用したリモートオファーの作成

1. [ フォームベースのExperience Composer](/help/main/c-experiences/form-experience-composer.md)を使用してアクティビティを作成する際に、**[!UICONTROL Content]** セクションを表示する場所を選択します。

   フォームベースのExperience Composerの![ コンテンツセクション ](/help/main/c-experiences/c-manage-content/assets/form-based-content.png)

1. **[!UICONTROL Default Content]** ドロップダウンリストをクリックし、**[!UICONTROL Change Remote Offer]**&#x200B;をクリックします。

   ![ リモートオファーオプションの変更](/help/main/c-experiences/c-manage-content/assets/change-remote-offer.png)

1. **[!UICONTROL Create]**／**[!UICONTROL Remote Offer]**&#x200B;をクリックします。

   ![ リモートオファーダイアログボックスを作成](/help/main/c-experiences/c-manage-content/assets/remote_offer_ui.png)

1. オファーのわかりやすい名前を入力します。

   わかりやすい名前を付けると、[!UICONTROL Assets] ライブラリでオファーをすばやく見つけることができます。

1. リダイレクト URL タイプを指定します。

   詳しくは、以下の「[ リダイレクト URL タイプ：キャッシュ済み」または「動的](#url-type)」を参照してください。

1. リモートオファーのリモート URLを指定します。

1. **[!UICONTROL Save]** をクリックします。

## リダイレクト URL タイプ：キャッシュまたは動的 {#url-type}

次の情報は、2つのオプションの違いを理解するのに役立ちます。

### キャッシュ URL

キャッシュされたリモート オファーのコンテンツは[!DNL Target]から提供されます。

2時間ごとに、[!DNL Target]はリモート URLでコンテンツを取得し、そのコンテンツを[!DNL Target]内に保存します。 訪問者がリモート オファーを含むエクスペリエンスを含むサイトを読み込むと、そのオファーは[!DNL Target]様によって配信されます。

[!DNL Target]にログインしたユーザーがコンテンツを変更できないため、キャッシュされたリモート オファーはセキュリティを強化します。 コンテンツを変更するには、コンテンツ管理または他のシステムにログインしてそこでコンテンツを変更する必要があります。

キャッシュされたリモートオファーには、絶対または相対 URL を指定することができます。

### 動的URL

動的なリモート オファーは、[!DNL Target]からではなく、コンテンツ管理またはその他のシステムから提供されます。

訪問者がリモートオファーを含むエクスペリエンスを含むサイトを読み込むたびに、コンテンツを定期的にキャッシュしてから[!DNL Target]によって配信することは望ましくないかもしれません。 代わりに、コンテンツをホストしているシステムを呼び出し、返されるオファーがユーザーごとに動的（または異なる）ように、特定の情報を渡す可能性があります。 例えば、あるユーザーが、動的リモートオファーのエクスペリエンスを含むクレジットカード用ウェブサイトにログインしたら、そのユーザーのアカウント情報をパラメーターとして URL に渡すことができます。 そうすると、ウェブサイトは、アカウントの残高など、ユーザーに特化した情報を提供することができます。

**[!UICONTROL Add Parameter]**&#x200B;をクリックして、1つ以上の[!DNL Target]要求または要求パラメーターを追加できます。

## アクティビティでのリモートオファーの使用

[!UICONTROL Form-Based Experience Composer]を使用してリモート オファーを適用する必要があります。 現在、VECを使用してリモート オファーを適用することはできません。

[!DNL Adobe Target] [!UICONTROL Form-Based Experience Composer]は、[!UICONTROL A/B Tests]、[!UICONTROL Experience Targeting] （XT）、[!UICONTROL Automated Personalization] （AP）、[!UICONTROL Recommendations]のアクティビティで使用するエクスペリエンスの作成に役立つ、非ビジュアルエクスペリエンスおよびオファー作成インターフェイスです。ビジュアルエクスペリエンスコンポーザーが使用できないか、使用に実用的でない場合に使用できます。 例えば、[!UICONTROL Form-Based Experience Composer]を使用して、リモート オファーを使用するエクスペリエンスを作成できます。

1. [!UICONTROL Form-Based Experience Composer]でアクティビティを作成または編集します。

   詳細な手順については、[ フォームベースのExperience Composer](/help/main/c-experiences/form-experience-composer.md)を参照してください。

1. 必要に応じて、目的の場所を指定し、オーディエンスの絞り込みを追加します。

1. **[!UICONTROL Content]** セクションのドロップダウンリストをクリックし、**[!UICONTROL Change Remote Offer]**&#x200B;をクリックします。

   ![ リモートオファーオプションの変更](/help/main/c-experiences/c-manage-content/assets/change-remote-offer.png)

1. [!UICONTROL Select Remote Offer] ダイアログボックスから目的のリモートオファーを選択し、**[!UICONTROL Done]**&#x200B;をクリックします。

1. アクティビティの設定を終了します。

## ダイナミックリモートオファーの仕組み {#concept_CC2A969420B34364A9FA78C1CE251818}

動的なオファーでは、動的なページテクノロジーを使用してオファーに値を渡します。

オファーはページのレンダリング後に実行されます。 非表示のiframeがデータを収集し、それをフレームからコピーして、ページに挿入し、渡された値を読み込みます。

![remote_offer_howitworks_2 image](assets/remote_offer_howitworks_2.jpeg)

## リモートオファーの選択指標 {#reference_B23BEDD29DDD47709A7651AFD27E776B}

Remote Offer Selection Matrixでは、選択するリモート オファーの種類を[!UICONTROL Cached]または[!UICONTROL Dynamic]に決定できます。

| 機能 | キャッシュ | 動的 |
|--- |--- |--- |
| 訪問者がリクエストするたびに更新 | × | ○ |
| コンテンツの更新 | 2 時間ごとにキャッシュ | リクエストのたびにすぐに更新 |
| 読み込み時間 | 高速 | リクエスト処理が原因となり低速 |
| ページ上での JavaScript の確認 | ○ | 不可（URL 経由で渡すことは可能） |
| オファーへの JavaScript の追加 | ○ | ○ |
| オファーの URL | 絶対的または相対的 | 相対 |
| リクエストするコンピューター | Adobe サーバー | 訪問者の Cookie を処理する訪問者のコンピューター |

## トレーニングビデオ：フォームベースのコンポーザー![ チュートリアルバッジ ](/help/main/assets/tutorial.png)

このビデオでは、リモートオファーの作成に使用できるフォームベースのコンポーザーのデモを紹介します。

* フォームベースの Experience Composer を使用したアクティビティの作成
* フォームベースの Experience Composer と Visual Experience Composer のどちらを使用するかの理解
* 場所のターゲット設定の調整

>[!VIDEO](https://video.tv.adobe.com/v/17390)
