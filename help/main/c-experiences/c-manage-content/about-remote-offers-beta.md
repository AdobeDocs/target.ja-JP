---
keywords: リモートオファー；キャッシュされたコンテンツ；動的コンテンツ；URL タイプ
description: でリモートオファーを使用する方法を説明します [!DNL Target] 外部のコンテンツ（CMS または他のシステム内のコンテンツ）をホストします。
title: リモートオファーを作成するにはどうすればよいですか？
feature: Experiences and Offers
badgeBeta: label="ベータ" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#beta newtab=true" tooltip=" [!DNL Adobe Target] のベータ版機能とは"
hide: true
hidefromtoc: true
source-git-commit: 26cb9d6a2359714f41acaf91c6e26a7e0ac93238
workflow-type: tm+mt
source-wordcount: '1087'
ht-degree: 21%

---

# リモートオファーを作成

リモートオファーを使用すると、[!DNL Adobe Target] 外にあり、[!DNL Target] が参照してユーザーのウェブサイトに提供するコンテンツをホスティングすることができます。このコンテンツは、使いやすさやセキュリティ上の理由から、コンテンツ管理（CMS）やその他のシステムに存在する場合があります。

>[!NOTE]
>
>この記事には、の更新に関する情報が含まれています [!DNL Target] 現在ベータ版プログラムに含まれているユーザーインターフェイス。 この [!DNL Adobe Target] チームは、多くの場合、一部のお客様に対して、テストやフィードバックの目的で新機能を有効にします。 テスト期間が完了すると、今後、これらの機能はすべての顧客に対して有効になります [!DNL Target Standard/Premium] のリリースとリリースは、リリースノートで発表されました。

リモートオファーは次で作成できます [!UICONTROL Offers] > [!UICONTROL Code Offers] ページまたは [Forms ベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md). では、リモートオファーを作成または適用できません [!UICONTROL Visual Experience Composer] （VEC）。 コンテンツは次に挿入されます [!DNL Target] 場所をリクエストするので、これらの場所は、グローバルな場合には適していない可能性が高くなります [!DNL Target] リクエスト。

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

* オファーがと同じドメインに存在する場合 [!DNL Target] リクエスト、使用する [!UICONTROL Cached] オプションでは、オファーの場所を説明する際に相対 URL を使用できます。

  つまり、アクティビティをステージングサーバーから実稼動環境に移動すると、URL を手動で変更しなくても、コンテンツに自動的にアクセスできます。

* サーバーで動的に生成されるデータがテストに含まれる場合、 [!UICONTROL Dynamic] オプションは適切な選択かもしれません。
* 既存のリモートオファーコンテンツの外観のみをテストする場合は、を使用します。 [!UICONTROL Visual Experience Composer] コンテンツ管理システムから返されるコンテンツのルックアンドフィールを変更する。
* の使用 [リモートオファー選択マトリックス](#reference_B23BEDD29DDD47709A7651AFD27E776B) （以下）特定のケースに最適なオファーを選択するのに役立ちます。 ご質問がある場合は、アカウント担当者にお問い合わせください。

## からのリモートオファーの作成 [!UICONTROL Code Offers] ページ

1. クリック **[!UICONTROL Offers]**&#x200B;を選択してから、 **[!UICONTROL Code Offers]** タブ。

   ![オファー/ コードオファー](/help/main/c-experiences/c-manage-content/assets/offers-code-offers-new.png)

1. クリック **[!UICONTROL Create Offer]** > **[!UICONTROL Remote Offer]**.

   ![リモートオファーを作成ダイアログボックス](/help/main/c-experiences/c-manage-content/assets/remote_offer_ui_new.png)

1. オファーのわかりやすい名前を入力します。

   わかりやすい名前を指定すると、自分や他のユーザーがでオファーをすばやく見つけやすくなります [!UICONTROL Assets] ライブラリ。

1. （条件付き）がある場合 [Target Premium アカウント](/help/main/c-intro/intro.md#premium)、目的のを選択します [workspace](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md##section_B82EB409B67C4D9D9D20CE30E48DB1DC).

1. リダイレクト URL のタイプを指定します。

   参照： [リダイレクト URL のタイプ：キャッシュまたは動的](#url-type) 詳しくは、を参照してください。

1. リモートオファーの絶対リモート URL を指定します。

1. **[!UICONTROL Create]** をクリックします。

## を使用したリモートオファーの作成 [!UICONTROL Form-Based Experience Composer]

1. を使用してアクティビティを作成するとき [フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md)を表示する場所を選択します。 **[!UICONTROL Content]** セクション。

   ![フォームベースの Experience Composer のコンテンツセクション](/help/main/c-experiences/c-manage-content/assets/form-based-content.png)

1. 「」をクリックします **[!UICONTROL Default Content]** ドロップダウンリストから、 **[!UICONTROL Change Remote Offer]**.

   ![リモートオファーオプションを変更](/help/main/c-experiences/c-manage-content/assets/change-remote-offer.png)

1. クリック **[!UICONTROL Create]** > **[!UICONTROL Remote Offer]**.

   ![リモートオファーを作成ダイアログボックス](/help/main/c-experiences/c-manage-content/assets/remote_offer_ui.png)

1. オファーのわかりやすい名前を入力します。

   わかりやすい名前を指定すると、自分や他のユーザーがでオファーをすばやく見つけやすくなります [!UICONTROL Assets] ライブラリ。

1. リダイレクト URL のタイプを指定します。

   参照： [リダイレクト URL のタイプ：キャッシュまたは動的](#url-type) 詳しくは、を参照してください。

1. リモートオファーのリモート URL を指定します。

1. **[!UICONTROL Save]** をクリックします。

## リダイレクト URL のタイプ：キャッシュまたは動的 {#url-type}

次の情報は、2 つのオプションの違いを理解するのに役立ちます。

### キャッシュされた URL

キャッシュされたリモートオファーのコンテンツの提供元 [!DNL Target].

2 時間ごと、 [!DNL Target] は、リモート URL のコンテンツを取得し、内に格納します [!DNL Target]. 訪問者がリモートオファーを含むエクスペリエンスでサイトを読み込んだ場合、 [!DNL Target] オファーを配信します。

キャッシュされたリモートオファーは、誰かがにログインしたためにセキュリティが強化された [!DNL Target] コンテンツを変更できません。 コンテンツを変更するには、誰かがまたは他のシステムをログに記録し、そこでコンテンツを変更する必要があります。

キャッシュされたリモートオファーには、絶対または相対 URL を指定することができます。

### 動的 URL

動的なリモートオファーは、からではなく、コンテンツ管理またはその他のシステムから提供されます [!DNL Target].

コンテンツを定期的にキャッシュした後、次のユーザーが配信したくない場合があります。 [!DNL Target] 訪問者がリモートオファーを含むエクスペリエンスをサイトに読み込むたびに。 代わりに、コンテンツをホストしているシステムを呼び出して、特定の情報を渡し、返されるオファーがユーザーごとに動的（または異なる）になるようにします。 例えば、あるユーザーが、動的リモートオファーのエクスペリエンスを含むクレジットカード用ウェブサイトにログインしたら、そのユーザーのアカウント情報をパラメーターとして URL に渡すことができます。そうすると、ウェブサイトは、アカウントの残高など、ユーザーに特化した情報を提供することができます。

次のいずれかをクリックできます。 **[!UICONTROL Add Parameter]** 1 つ以上を追加するには [!DNL Target] リクエストまたはリクエストパラメーター。

## アクティビティでのリモートオファーの使用

リモートオファーを適用するには、 [!UICONTROL Form-Based Experience Composer]. 現在、を使用してリモートオファーを適用することはできません [!UICONTROL Visual Experience Composer] （VEC）。

この [!DNL Adobe Target] [!UICONTROL Form-Based Experience Composer] は、で使用するエクスペリエンスの作成に役立つ、視覚的でないエクスペリエンスおよびオファー作成インターフェイスです [!UICONTROL A/B Tests], [!UICONTROL Experience Targeting] （XT）、 [!UICONTROL Automated Personalization] （AP）および [!UICONTROL Recommendations] 次の場合にアクティビティ [!UICONTROL Visual Experience Composer] は使用できないか、実用的ではありません。 例えば、 [!UICONTROL Form-Based Experience Composer] リモートオファーを使用するエクスペリエンスを作成する場合

1. でのアクティビティの作成または編集 [!UICONTROL Form-Based Experience Composer].

   参照： [フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md) 詳細な手順については、を参照してください。

1. 目的の場所を指定し、必要に応じてオーディエンスの絞り込みを追加します。

1. のドロップダウンリストをクリックします。 **[!UICONTROL Content]** セクションで、 **[!UICONTROL Change Remote Offer]**.

   ![リモートオファーオプションを変更](/help/main/c-experiences/c-manage-content/assets/change-remote-offer.png)

1. から目的のリモートオファーを選択 [!UICONTROL Select Remote Offer] ダイアログボックスで、 **[!UICONTROL Done]**.

1. アクティビティの設定を終了します。

## 動的なリモートオファーの機能 {#concept_CC2A969420B34364A9FA78C1CE251818}

動的なオファーでは、動的なページテクノロジーを使用してオファーに値を渡します。

オファーはページのレンダリング後に実行されます。非表示の iFrame がデータを収集してフレームからコピーし、ページに挿入して、渡された値を読み込みます。

![remote_offer_howitworks_2 画像](assets/remote_offer_howitworks_2.jpeg)

1. 訪問者のブラウザーが、サーバーにページをリクエストします。

2. ブラウザーが mbox を含むページをレンダリングします。

3. `mboxCreate` 呼び出しには、動的コンテンツのレンダリングに必要なパラメーターが含まれます。

4. [!DNL Target] 動的コンテンツの場所とそのパラメーターを含む URL を返します。 mbox 領域に iFrame を設定します。

5. ブラウザーが URL をリクエストし、ページでレンダリングします。

## リモートオファー選択マトリックス {#reference_B23BEDD29DDD47709A7651AFD27E776B}

リモートオファー選択マトリックスを使用すると、選択するリモートオファーのタイプを決定できます。 [!UICONTROL Cached] または [!UICONTROL Dynamic].

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

このビデオでは、のデモを紹介します [!UICONTROL Form-Based Experience Composer]リモートオファーの作成に使用できます。

* を使用したアクティビティの作成 [!UICONTROL Form-Based Experience Composer]
* 使用するタイミングについて [!UICONTROL Form-Based Experience Composer] との比較 [!UICONTROL Visual Experience Composer]
* 場所のターゲット設定の調整

>[!VIDEO](https://video.tv.adobe.com/v/17390)