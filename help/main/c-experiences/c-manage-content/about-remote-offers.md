---
keywords: リモートオファー；リモートオファー選択マトリックス；キャッシュコンテンツ；動的コンテンツ；url タイプ
description: Adobeでのリモートオファーの使用方法を説明します [!DNL Target] 外部のコンテンツ（CMS または他のシステム内のコンテンツ）をホストする。 リモートオファーを使用する理由を見つけます。
title: リモートオファーを作成する方法を教えてください。
feature: Experiences and Offers
exl-id: 6a5283ee-c1fb-49f7-8e7f-c23ccde26ade
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1081'
ht-degree: 47%

---

# リモートオファーを作成

リモートオファーを使用すると、[!DNL Adobe Target] 外にあり、[!DNL Target] が参照してユーザーのウェブサイトに提供するコンテンツをホスティングすることができます。このコンテンツは、使いやすさのため、またはセキュリティ上の理由から、コンテンツ管理 (CMS) や他のシステムに存在する場合があります。

>[!NOTE]
>
>リモートオファーは [!UICONTROL オファー] > [!UICONTROL コードオファー] ページまたは [Formsベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md). Visual Experience Composer(VEC) でリモートオファーを作成または適用することはできません。 コンテンツが [!DNL Target] リクエストの場所を指定する場合は、多くの場合、グローバル [!DNL Target] リクエスト。
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

## リモートオファーを使用する際のベストプラクティス {#section_7718512D08E14121B6F6B8C38134F4BC}

アクティビティでリモートオファーを使用する際のベストプラクティス：

* オファーが [!DNL Target] リクエスト、使用 [!UICONTROL キャッシュ] 「 」オプションを使用すると、相対 URL を使用してオファーの場所を記述できます。

   つまり、ステージングサーバーから実稼動サーバーにアクティビティを移動する際、URL を手動で変更しなくても、そのコンテンツに自動的にアクセスできるようになります。

* サーバーが動的に生成するデータでテストをおこなう場合は、「[!UICONTROL 動的]」オプションを選択することをお勧めします。
* 既存のリモートオファーコンテンツの外見のテストをおこなう予定であれば、[!UICONTROL Visual Experience Composer] を使用し、コンテンツ管理システムから戻されるコンテンツの外観と操作性を変更します。
* 以下を使用： [リモートオファー選択のマトリックス](#reference_B23BEDD29DDD47709A7651AFD27E776B) （以下）を参照して、特定のケースに最適なオファーを選択します。 ご質問がある場合は、アカウント担当者にお問い合わせください。

## コードオファーページからのリモートオファーの作成

1. 「**[!UICONTROL オファー]**」をクリックしてから、「**[!UICONTROL コードオファー]**」タブを選択します。

   ![オファー/コードオファー](/help/main/c-experiences/c-manage-content/assets/offers-code-offers.png)

1. **[!UICONTROL 作成]**／**[!UICONTROL リモートオファー]**&#x200B;をクリックします。

   ![リモートオファーを作成ダイアログボックス](/help/main/c-experiences/c-manage-content/assets/remote_offer_ui.png)

1. オファーのわかりやすい名前を入力します。

   わかりやすい名前を付けると、後で [!UICONTROL アセット] ライブラリからオファーをすばやく見つけることができます。

1. リダイレクト URL のタイプを指定します。

   詳しくは、 [リダイレクト URL のタイプ：キャッシュ済みまたは動的](#url-type) 詳しくは、以下を参照してください。

1. リモートオファーのリモート URL を指定します。

1. 「**[!UICONTROL 保存]**」をクリックします。

## フォームベースの Experience Composer を使用したリモートオファーの作成

1. を使用してアクティビティを作成する場合、 [フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md)を選択し、 **[!UICONTROL コンテンツ]** 」セクションに入力します。

   ![フォームベースの Experience Composer のコンテンツセクション](/help/main/c-experiences/c-manage-content/assets/form-based-content.png)

1. 次をクリック： **[!UICONTROL デフォルトコンテンツ]** ドロップダウンリストから、 **[!UICONTROL リモートオファーを変更]**.

   ![リモートオファーオプションを変更](/help/main/c-experiences/c-manage-content/assets/change-remote-offer.png)

1. **[!UICONTROL 作成]**／**[!UICONTROL リモートオファー]**&#x200B;をクリックします。

   ![リモートオファーを作成ダイアログボックス](/help/main/c-experiences/c-manage-content/assets/remote_offer_ui.png)

1. オファーのわかりやすい名前を入力します。

   わかりやすい名前を付けると、後で [!UICONTROL アセット] ライブラリからオファーをすばやく見つけることができます。

1. リダイレクト URL のタイプを指定します。

   詳しくは、 [リダイレクト URL のタイプ：キャッシュ済みまたは動的](#url-type) 詳しくは、以下を参照してください。

1. リモートオファーのリモート URL を指定します。

1. 「**[!UICONTROL 保存]**」をクリックします。

## リダイレクト URL のタイプ：キャッシュ済みまたは動的 {#url-type}

次の情報は、2 つのオプションの違いを理解するのに役立ちます。

### キャッシュされた URL

キャッシュされたリモートオファーが [!DNL Target] から提供されます。

[!DNL Target] は 2 時間ごとにリモート URL にあるコンテンツを取得し、コンテンツを [!DNL Target] 内に保存します。リモートオファーを含むエクスペリエンスで訪問者がサイトを読み込むと、[!DNL Target] がオファーを提供します。

キャッシュされたリモートオファーは、誰かが次の場所にログインしたため、セキュリティを強化します。 [!DNL Target] コンテンツを変更できません。 コンテンツを変更するには、コンテンツ管理または他のシステムにログインしてそこでコンテンツを変更する必要があります。

キャッシュされたリモートオファーには、絶対または相対 URL を指定することができます。

### 動的 URL

動的リモートオファーは、[!DNL Target] から提供されるのではなく、コンテンツ管理または他のシステムから提供されます。

リモートオファーを含むエクスペリエンスで訪問者がサイトを読み込むたびに、[!DNL Target] が定期的にコンテンツをキャッシュし、その後配信するようにするのではなく、代わりに、コンテンツをホストしているシステムを呼び出し、場合によっては特定の情報を渡して、返されるオファーをユーザーごとに動的（または異なる）にする必要があります。 例えば、あるユーザーが、動的リモートオファーのエクスペリエンスを含むクレジットカード用ウェブサイトにログインしたら、そのユーザーのアカウント情報をパラメーターとして URL に渡すことができます。そうすると、ウェブサイトは、アカウントの残高など、ユーザーに特化した情報を提供することができます。

次をクリックできます。 **[!UICONTROL パラメータを追加]** 1 つ以上を追加 [!DNL Target] リクエストまたはリクエストパラメーター。

## アクティビティでリモートオファーを使用

リモートオファーを適用するには、 [!UICONTROL フォームベースの Experience Composer]. 現在、VEC を使用してリモートオファーを適用することはできません。

この [!DNL Adobe Target] [!UICONTROL フォームベースの Experience Composer] は、非視覚的なエクスペリエンスおよびオファー作成インターフェイスで、で使用するエクスペリエンスを作成するのに役立ちます。 [!UICONTROL A/B テスト], [!UICONTROL エクスペリエンスのターゲット設定] (XT), [!UICONTROL Automated Personalization] (AP) および [!UICONTROL Recommendations] Visual Experience Composer を使用できない場合や実用的な場合にアクティビティを使用します。 例えば、 [!UICONTROL フォームベースの Experience Composer] リモートオファーを使用するエクスペリエンスを作成する場合。

1. でアクティビティを作成または編集 [!UICONTROL フォームベースの Experience Composer].

   詳しくは、 [フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md) を参照してください。

1. 目的の場所を指定し、必要に応じてオーディエンスの絞り込みを追加します。

1. 次に示す **[!UICONTROL コンテンツ]** 「 」セクションで、「 **[!UICONTROL リモートオファーを変更]**.

   ![リモートオファーオプションを変更](/help/main/c-experiences/c-manage-content/assets/change-remote-offer.png)

1. 目的のリモートオファーを [!UICONTROL リモートオファーを選択] ダイアログボックスを開き、 **[!UICONTROL 完了]**.

1. アクティビティの設定を終了します。

## 動的なリモートオファーの仕組み {#concept_CC2A969420B34364A9FA78C1CE251818}

動的なオファーでは、動的なページテクノロジーを使用してオファーに値を渡します。

オファーはページのレンダリング後に実行されます。非表示の iframe でデータを収集し、フレームからコピーして、ページに挿入し、渡された値を読み込みます。

![](assets/remote_offer_howitworks_2.jpeg)

## リモートオファー選択のマトリックス {#reference_B23BEDD29DDD47709A7651AFD27E776B}

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

## トレーニングビデオ：フォームベースのコンポーザー ![チュートリアルバッジ](/help/main/assets/tutorial.png)

このビデオでは、リモートオファーの作成に使用できるフォームベースのコンポーザーのデモを提供します。

* フォームベースの Experience Composer を使用したアクティビティの作成
* フォームベースの Experience Composer と Visual Experience Composer のどちらを使用するかの理解
* 場所のターゲット設定の調整

>[!VIDEO](https://video.tv.adobe.com/v/17390)
