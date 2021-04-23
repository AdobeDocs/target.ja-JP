---
keywords: リモートオファー；リモートオファー選択マトリックス；キャッシュコンテンツ；動的コンテンツ；URLタイプ
description: Adobe [!DNL Target] でリモートオファーを使用して外部コンテンツ（CMSや他のシステムのコンテンツ）をホストする方法を学びます。 リモートオファーを使用する理由を特定します。
title: リモートオファーの作成方法
feature: エクスペリエンスとオファー
exl-id: 6a5283ee-c1fb-49f7-8e7f-c23ccde26ade
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '1084'
ht-degree: 47%

---

# リモートオファーを作成

リモートオファーを使用すると、[!DNL Adobe Target] 外にあり、[!DNL Target] が参照してユーザーのウェブサイトに提供するコンテンツをホスティングすることができます。このコンテンツは、使いやすさ、セキュリティ上の理由から、コンテンツ管理(CMS)や他のシステムにある場合があります。

>[!NOTE]
>
>リモートオファーは、[!UICONTROL オファー] > [!UICONTROL コードオファー]ページまたは[FormsベースのExperience Composer](/help/c-experiences/form-experience-composer.md)に作成できます。 Visual Experience Composer(VEC)でリモートオファーを作成または適用することはできません。 コンテンツは[!DNL Target]リクエストの場所に挿入されるので、グローバル[!DNL Target]リクエストには適していない可能性が高くなります。
>
>[!DNL Target Classic]に同様の機能がありました。[!UICONTROL Offer on Your Site] と [!UICONTROL Offer Outside Test&amp;Target] です。

リモートオファーの例をいくつか挙げます。

* 様々なバージョンのクロス販売
* 動的な買い物かごのメッセージ
* フォーム
* カルキュレーター
* 金利の更新
* 電子メール
* キオスク
* 音声アシスタント

## リモートオファー{#section_7718512D08E14121B6F6B8C38134F4BC}の使用に関するベストプラクティス

アクティビティでリモートオファーを使用する際のベストプラクティス：

* オファーが[!DNL Target]リクエストと同じドメインに存在する場合は、[!UICONTROL 「キャッシュ」]オプションを使用すると、オファーの場所の指定に相対URLを使用できます。

   つまり、ステージングサーバーから実稼動サーバーにアクティビティを移動する際、URL を手動で変更しなくても、そのコンテンツに自動的にアクセスできるようになります。

* サーバーが動的に生成するデータでテストをおこなう場合は、「[!UICONTROL 動的]」オプションを選択することをお勧めします。
* 既存のリモートオファーコンテンツの外見のテストをおこなう予定であれば、[!UICONTROL Visual Experience Composer] を使用し、コンテンツ管理システムから戻されるコンテンツの外観と操作性を変更します。
* [リモートオファー選択マトリックス](#reference_B23BEDD29DDD47709A7651AFD27E776B) （下記）を使用して、特定のケースに最も適したオファーを選択します。 ご質問がある場合は、アカウント担当者にお問い合わせください。

## コードオファーページからのリモートオファーの作成

1. 「**[!UICONTROL オファー]**」をクリックしてから、「**[!UICONTROL コードオファー]**」タブを選択します。

   ![オファー/コードオファー](/help/c-experiences/c-manage-content/assets/offers-code-offers.png)

1. **[!UICONTROL 作成]**／**[!UICONTROL リモートオファー]**&#x200B;をクリックします。

   ![[リモートオファーの作成]ダイアログボックス](/help/c-experiences/c-manage-content/assets/remote_offer_ui.png)

1. オファーのわかりやすい名前を入力します。

   わかりやすい名前を付けると、後で [!UICONTROL アセット] ライブラリからオファーをすばやく見つけることができます。

1. リダイレクトURLの種類を指定します。

   「[リダイレクトURLの種類：キャッシュ済みまたは動的](#url-type)を参照してください。

1. リモートオファーのリモートURLを指定します。

1. 「**[!UICONTROL 保存]**」をクリックします。

## フォームベースのExperience Composerを使用したリモートオファーの作成

1. [フォームベースのExperience Composer](/help/c-experiences/form-experience-composer.md)を使用してアクティビティを作成する際に、**[!UICONTROL コンテンツ]**&#x200B;セクションを表示する場所を選択します。

   ![フォームベースのExperience Composerの「コンテンツ」セクション](/help/c-experiences/c-manage-content/assets/form-based-content.png)

1. 「**[!UICONTROL デフォルトコンテンツ]**」ドロップダウンリストをクリックし、「**[!UICONTROL リモートオファーの変更]**」をクリックします。

   ![リモートオファーオプションの変更](/help/c-experiences/c-manage-content/assets/change-remote-offer.png)

1. **[!UICONTROL 作成]**／**[!UICONTROL リモートオファー]**&#x200B;をクリックします。

   ![[リモートオファーの作成]ダイアログボックス](/help/c-experiences/c-manage-content/assets/remote_offer_ui.png)

1. オファーのわかりやすい名前を入力します。

   わかりやすい名前を付けると、後で [!UICONTROL アセット] ライブラリからオファーをすばやく見つけることができます。

1. リダイレクトURLの種類を指定します。

   「[リダイレクトURLの種類：キャッシュ済みまたは動的](#url-type)を参照してください。

1. リモートオファーのリモートURLを指定します。

1. 「**[!UICONTROL 保存]**」をクリックします。

## リダイレクトURLの種類：キャッシュ済みまたは動的{#url-type}

次の情報は、2つのオプションの違いを理解するのに役立ちます。

### キャッシュURL

キャッシュされたリモートオファーが [!DNL Target] から提供されます。

[!DNL Target] は 2 時間ごとにリモート URL にあるコンテンツを取得し、コンテンツを [!DNL Target] 内に保存します。リモートオファーを含むエクスペリエンスで訪問者がサイトを読み込むと、[!DNL Target] がオファーを提供します。

キャッシュされたリモートオファーは、[!DNL Target]にログインしたユーザーがコンテンツを変更できないので、セキュリティを強化します。 コンテンツを変更するには、コンテンツ管理または他のシステムにログインしてそこでコンテンツを変更する必要があります。

キャッシュされたリモートオファーには、絶対または相対 URL を指定することができます。

### 動的URL

動的リモートオファーは、[!DNL Target] から提供されるのではなく、コンテンツ管理または他のシステムから提供されます。

リモートオファーを含むエクスペリエンスで訪問者がサイトを読み込むたびに、[!DNL Target] が定期的にコンテンツをキャッシュし、その後配信するようにするのではなく、代わりに、コンテンツをホストするシステムを呼び出し、場合によっては特定の情報を渡すことで、返されるオファーをユーザーごとに動的（または異なる）にできます。 例えば、あるユーザーが、動的リモートオファーのエクスペリエンスを含むクレジットカード用ウェブサイトにログインしたら、そのユーザーのアカウント情報をパラメーターとして URL に渡すことができます。そうすると、ウェブサイトは、アカウントの残高など、ユーザーに特化した情報を提供することができます。

「**[!UICONTROL パラメーター追加]**」をクリックして、1つ以上の[!DNL Target]リクエストまたはリクエストパラメーターを追加できます。

## アクティビティでリモートオファーを使用する

[!UICONTROL フォームベースのExperience Composer]を使用してリモートオファーを適用する必要があります。 現在、VECを使用してリモートオファーを適用することはできません。

[!DNL Adobe Target] [!UICONTROL フォームベースのExperience Composer]は、[!UICONTROL A/Bテスト]、[!UICONTROL エクスペリエンスのターゲット設定](XT)、[!UICONTROL Automated Personalization](AP)で使用するエクスペリエンスを作成するのに便利です)、および[!UICONTROL Recommendations]アクティビティ（visual experience composerが使用できない場合や実際に使用できない場合）に追加します。 例えば、[!UICONTROL フォームベースのExperience Composer]を使用して、リモートオファーを使用するエクスペリエンスを作成できます。

1. [!UICONTROL フォームベースのExperience Composer]でアクティビティを作成または編集します。

   詳しい手順については、[フォームベースのExperience Composer](/help/c-experiences/form-experience-composer.md)を参照してください。

1. 必要な場所を指定し、必要に応じてオーディエンスの調整を追加します。

1. 「**[!UICONTROL コンテンツ]**」セクションのドロップダウンリストをクリックし、「**[!UICONTROL リモートオファーの変更]**」をクリックします。

   ![リモートオファーオプションの変更](/help/c-experiences/c-manage-content/assets/change-remote-offer.png)

1. [!UICONTROL リモートオファーを選択]ダイアログボックスから目的のリモートオファーを選択し、**[!UICONTROL 完了]**&#x200B;をクリックします。

1. アクティビティの設定を終了します。

## 動的リモートオファーの動作{#concept_CC2A969420B34364A9FA78C1CE251818}

動的なオファーでは、動的なページテクノロジーを使用してオファーに値を渡します。

オファーはページのレンダリング後に実行されます。非表示のiframeでデータを収集し、フレーム外にコピーし、ページ上に挿入して、渡された値をロードします。

![](assets/remote_offer_howitworks_2.jpeg)

## リモートオファー選択マトリックス{#reference_B23BEDD29DDD47709A7651AFD27E776B}

リモートオファーには[!UICONTROL キャッシュ]と[!UICONTROL 動的]の 2 つのタイプがあり、リモートオファー選択のマトリックスは、どちらのタイプを選択するか判断するのに役立ちます。

| 機能 | キャッシュ | 動的 |
|--- |--- |--- |
| 訪問者がリクエストするたびに更新 | × | ○ |
| コンテンツの更新 | 2 時間ごとにキャッシュ | リクエストのたびにすぐに更新 |
| 読み込み時間 | 高速 | リクエスト処理が原因となり低速 |
| ページ上での JavaScript の確認 | ○ | 不可（URL 経由で渡すことは可能） |
| オファーへの JavaScript の追加 | ○ | ○ |
| オファーの URL | 絶対または相対 | 相対 |
| リクエストするコンピューター | Adobe サーバー | 訪問者の Cookie を処理する訪問者のコンピューター |

## トレーニングビデオ：フォームベースのコンポーザー![チュートリアルバッジ](/help/assets/tutorial.png)

このビデオは、リモートオファーの作成に使用できるフォームベースのコンポーザーのデモを提供します。

* フォームベースの Experience Composer を使用したアクティビティの作成
* フォームベースの Experience Composer と Visual Experience Composer のどちらを使用するかの理解
* 場所のターゲット設定の調整

>[!VIDEO](https://video.tv.adobe.com/v/17390)
