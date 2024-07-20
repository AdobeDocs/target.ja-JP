---
keywords: リモートオファー；キャッシュされたコンテンツ；動的コンテンツ；URL タイプ
description: リモートオファーを使用して外部のコンテンツ  [!DNL Target] CMS または他のシステムのコンテンツ）をホストする方法を説明します。
title: リモートオファーを作成するにはどうすればよいですか？
feature: Experiences and Offers
badgeBeta: label="ベータ" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#beta newtab=true" tooltip=" [!DNL Adobe Target] のベータ版機能とは"
hide: true
hidefromtoc: true
exl-id: e83ad57e-716d-4595-b5cf-3a882fcb9e37
source-git-commit: dedef7763a1d69f80c569a0e7edaadfb310b1a15
workflow-type: tm+mt
source-wordcount: '1087'
ht-degree: 21%

---

# リモートオファーを作成

リモートオファーを使用すると、[!DNL Adobe Target] 外にあり、[!DNL Target] が参照してユーザーのウェブサイトに提供するコンテンツをホスティングすることができます。このコンテンツは、使いやすさやセキュリティ上の理由から、コンテンツ管理（CMS）やその他のシステムに存在する場合があります。

>[!NOTE]
>
>この記事では、現在Beta プログラムの一部である [!DNL Target] ユーザーインターフェイスのアップデートについて説明します。 [!DNL Adobe Target] チームは、多くの場合、テストやフィードバックの目的で、一部のお客様に対して新機能を有効にします。 テスト期間が完了すると、これらの機能は今後の [!DNL Target Standard/Premium] リリースですべてのお客様に対して有効になり、リリースノートで発表されます。

リモートオファーは、[!UICONTROL Offers]/[!UICONTROL Code Offers] ページ、または [Forms ベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md) で作成できます。 [!UICONTROL Visual Experience Composer] （VEC）内でリモートオファーを作成または適用することはできません。 コンテンツは [!DNL Target] リクエストの場所に挿入されるので、これらの場所は、グローバル [!DNL Target] リクエストには適していない可能性が高くなります。

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

  つまり、アクティビティをステージングサーバーから実稼動環境に移動すると、URL を手動で変更しなくても、コンテンツに自動的にアクセスできます。

* テストにサーバーで動的に生成されるデータが含まれる場合は、[!UICONTROL Dynamic] のオプションが適切な選択肢となる可能性があります。
* 既存のリモートオファーコンテンツの外観のみをテストする場合は、[!UICONTROL Visual Experience Composer] を使用して、コンテンツ管理システムから返されるコンテンツのルックアンドフィールを変更します。
* （以下の [ リモートオファー選択マトリックス ](#reference_B23BEDD29DDD47709A7651AFD27E776B) を使用すると、特定のケースに最適なオファーを選択できます。 ご質問がある場合は、アカウント担当者にお問い合わせください。

## [!UICONTROL Code Offers] ページからのリモートオファーの作成

1. 「**[!UICONTROL Offers]**」をクリックして、「**[!UICONTROL Code Offers]**」タブを選択します。

   ![ オファー/コードオファー ](/help/main/c-experiences/c-manage-content/assets/offers-code-offers-new.png)

1. **[!UICONTROL Create Offer]**／**[!UICONTROL Remote Offer]**&#x200B;をクリックします。

   ![ リモートオファーを作成ダイアログボックス ](/help/main/c-experiences/c-manage-content/assets/remote_offer_ui_new.png)

1. オファーのわかりやすい名前を入力します。

   わかりやすい名前を指定すると、作成者や他のユーザーが [!UICONTROL Assets] ライブラリでオファーをすばやく見つけやすくなります。

1. （条件付き） [Target Premium アカウント ](/help/main/c-intro/intro.md#premium) をお持ちの場合は、目的の [ ワークスペース ](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md##section_B82EB409B67C4D9D9D20CE30E48DB1DC) を選択します。

1. リダイレクト URL のタイプを指定します。

   詳しくは、以下の [ リダイレクト URL タイプ：キャッシュまたは動的 ](#url-type) を参照してください。

1. リモートオファーの絶対リモート URL を指定します。

1. **[!UICONTROL Create]** をクリックします。

## [!UICONTROL Form-Based Experience Composer] を使用したリモートオファーの作成

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

2 時間ごとに、[!DNL Target] はリモート URL からコンテンツを取得し、そのコンテンツを [!DNL Target] 内に保存します。 訪問者がリモートオファーを含むエクスペリエンスをサイトに読み込むと、[!DNL Target] はオファーを配信します。

キャッシュされたリモートオファーは、[!DNL Target] にログインしたユーザーがコンテンツを変更できないので、セキュリティが強化されます。 コンテンツを変更するには、誰かがまたは他のシステムをログに記録し、そこでコンテンツを変更する必要があります。

キャッシュされたリモートオファーには、絶対または相対 URL を指定することができます。

### 動的 URL

動的なリモートオファーは、[!DNL Target] ージからではなく、コンテンツ管理またはその他のシステムから提供されます。

リモートオファーを含むエクスペリエンスで訪問者がサイトを読み込むたびに、コンテンツを定期的にキャッシュして、[!DNL Target] で配信したくない場合があります。 代わりに、コンテンツをホストしているシステムを呼び出して、特定の情報を渡し、返されるオファーがユーザーごとに動的（または異なる）になるようにします。 例えば、あるユーザーが、動的リモートオファーのエクスペリエンスを含むクレジットカード用ウェブサイトにログインしたら、そのユーザーのアカウント情報をパラメーターとして URL に渡すことができます。そうすると、ウェブサイトは、アカウントの残高など、ユーザーに特化した情報を提供することができます。

「**[!UICONTROL Add Parameter]**」をクリックして、1 つ以上の [!DNL Target] リクエストまたはリクエストパラメーターを追加できます。

## アクティビティでのリモートオファーの使用

[!UICONTROL Form-Based Experience Composer] を使用してリモートオファーを適用する必要があります。 現在、[!UICONTROL Visual Experience Composer] （VEC）を使用してリモートオファーを適用することはできません。

[!DNL Adobe Target] [!UICONTROL Form-Based Experience Composer] は、[!UICONTROL A/B Tests]、[!UICONTROL Experience Targeting] （XT）、[!UICONTROL Automated Personalization] （AP）、[!UICONTROL Recommendations] の各アクティビティで使用するエクスペリエンスを作成する際に、そのエクスペリエンスが使用できない、または実用的でない場合に役立つ、非視覚的なエクスペリ [!UICONTROL Visual Experience Composer] ンスおよびオファー作成インターフェイスです。 例えば、[!UICONTROL Form-Based Experience Composer] を使用して、リモートオファーを使用するエクスペリエンスを作成できます。

1. [!UICONTROL Form-Based Experience Composer] でアクティビティを作成または編集します。

   詳しい手順については、[ フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md) を参照してください。

1. 目的の場所を指定し、必要に応じてオーディエンスの絞り込みを追加します。

1. 「**[!UICONTROL Content]**」セクションのドロップダウンリストをクリックして、「**[!UICONTROL Change Remote Offer]**」をクリックします。

   ![ リモートオファーオプションを変更 ](/help/main/c-experiences/c-manage-content/assets/change-remote-offer.png)

1. [!UICONTROL Select Remote Offer] ダイアログボックスで目的のリモートオファーを選択し、「**[!UICONTROL Done]**」をクリックします。

1. アクティビティの設定を終了します。

## 動的なリモートオファーの機能 {#concept_CC2A969420B34364A9FA78C1CE251818}

動的なオファーでは、動的なページテクノロジーを使用してオファーに値を渡します。

オファーはページのレンダリング後に実行されます。非表示の iFrame がデータを収集してフレームからコピーし、ページに挿入して、渡された値を読み込みます。

![remote_offer_howitworks_2 画像 ](assets/remote_offer_howitworks_2.jpeg)

1. 訪問者のブラウザーが、サーバーにページをリクエストします。

2. ブラウザーが mbox を含むページをレンダリングします。

3. 呼び出 `mboxCreate` には、動的コンテンツのレンダリングに必要なパラメーターが含まれます。

4. [!DNL Target] は、動的コンテンツの場所とそのパラメーターを含む URL を返します。 mbox 領域に iFrame を設定します。

5. ブラウザーが URL をリクエストし、ページでレンダリングします。

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

このビデオでは、リモートオファーの作成に使用できる [!UICONTROL Form-Based Experience Composer] のデモを紹介します。

* [!UICONTROL Form-Based Experience Composer] を使用したアクティビティの作成
* [!UICONTROL Form-Based Experience Composer] と [!UICONTROL Visual Experience Composer] を使用するタイミングについて
* 場所のターゲット設定の調整

>[!VIDEO](https://video.tv.adobe.com/v/17390)
