---
keywords: 最適化；パーソナライゼーション；adobe journey optimizer;ajo；ユースケース；シナリオ；コンテンツ変更/ab テスト；プロファイル属性；画像の変更；画像の入れ替え
description: Adobe Journey Optimizerで効果的なA/B テストを実施するための秘訣
title: ' [!DNL Adobe Journey Optimizer]でのA/B テストによるコンテンツの変更'
badgeBeta: label="Beta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#beta newtab=true" tooltip=" [!DNL Adobe Target] のベータ版機能とは"
feature: Integrations
hide: true
hidefromtoc: true
exl-id: e5aed7cd-7701-4133-ac7c-98e528c8a763
source-git-commit: f6034e83564a9a386e21e4e57279c66cc3c94537
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 1%

---

# [!DNL Adobe Journey Optimizer]でのA/B テストによるコンテンツの変更

このユースケースは、[!DNL Adobe Journey Optimizer]で効果的なA/B テスト コンテンツの変更を行うための秘密を解き放つのに役立ちます。

この使用例では、[ではなく](/help/main/c-activities/t-test-ab/test-ab.md)を使用して、[!DNL Adobe Target]の[!DNL Journey Optimizer]A/B テストアクティビティ [!DNL Adobe Target]でA/B テストを行うなど、使い慣れたタスクを実行する方法を示します。

## 利点と価値

* **コンテンツの効果を最適化**：どのコンテンツバリエーションや要素が顧客の共感を最も呼ぶかを明らかにし、エンゲージメントやコンバージョンを向上させます。
* **データ主導の意思決定**: データを活用して、コンテンツ戦略全体で情報に基づいた意思決定を行い、最大の効果を実現します。
* **パーソナライズされたユーザーエクスペリエンス**：すべてのオーディエンスセグメントの独自の環境設定とニーズに合わせてコンテンツをカスタマイズします。

## 考えられるシナリオ

* アパレル企業は、さまざまな画像をテストし、call-to-actionのテキストに表示されているユーザーの名前を使ってキャンペーンのランディングページをパーソナライズすることで、コンバージョン率を向上させました。

* あるコマース企業では、キャンペーンのランディングページで様々な商品説明や画像をテストした結果、ゴールドロイヤルティの会員のコンバージョン率が高く、売上が増加したことがわかりました。

## 手順

>[!NOTE]
>
>この節の手順では、画像を変更し、プロファイル属性を使用してテキストメッセージをパーソナライズするために必要な手順を強調表示します。 [!DNL Journey Optimizer] web デザイナーで利用できるオプションについて詳しくは、[Journey Optimizer ドキュメント &#x200B;](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/web/author-web-pages/web-visual-editor){target=_blank}の&#x200B;*web デザイナーの操作*&#x200B;を参照してください。
>
>特にページ下部の動画が役立ちます。

プロファイルスクリプトを使用して、様々な画像をテストし、ユーザーの名前でメッセージをパーソナライズして、web ページを最適化するには：

1. [!DNL Journey Optimizer]で、左側のパネルの&#x200B;**キャンペーン**&#x200B;をクリックして、[!UICONTROL Campaigns] ページを表示します。

1. **[!UICONTROL Create Campaign]** ページの右上隅にある「[!UICONTROL Campaigns]」をクリックします。

1. **[!UICONTROL Scheduled - Marketing]** （デフォルト）を選択し、**作成**&#x200B;をクリックして、[!UICONTROL Campaign]の詳細ページを表示します。

1. 「**[!UICONTROL Properties]**」セクションで、キャンペーンの説明的な名前とオプションの説明を入力します。

1. （条件付き） **[!UICONTROL Audience]** セクションで、**[!UICONTROL Select Audience]**&#x200B;をクリックし、目的のオーディエンスを選択します。

   このユースケースでは、[!UICONTROL All Visitors]のキャンペーンをアクティブ化できます（デフォルト）。

1. **[!UICONTROL Action]** セクションで、**[!UICONTROL Web]** ドロップダウンリストから&#x200B;**[!UICONTROL Action]**&#x200B;を選択し、新しいweb設定を選択または作成します。

   web設定（チャネルサーフェス）は、システム管理者が定義する設定です。 Web設定には、ヘッダーパラメーター、サブドメイン、モバイルアプリなど、メッセージを送信するためのすべての技術的なパラメーターが含まれます。

   詳しくは、[Journey Optimizer ドキュメント &#x200B;](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/configuration/channel-surfaces#set-up-channel-surfaces){target=_blank}の「*チャネルサーフェスの設定*」を参照してください。

1. **[!UICONTROL Action]** セクションで、**[!UICONTROL Edit Content]**&#x200B;をクリックして、[!DNL Journey Optimizer] web デザイナーでweb サイトを開きます。

   A/B テストには、2つ以上の実験が必要です。 既存のホームページを最初の実験として使用できます。 以降の手順では、2回目の実験を設定する方法を説明します。

   LUMA web サイトの![&#x200B; ヨガランディングページ &#x200B;](/help/main/c-integrating-target-with-mac/ajo/assets/luma-yoga-landing.png)

1. どのコンテンツがより効果的かを判断するための実験を作成するには、**[!UICONTROL Create Experiment]**&#x200B;をクリックします。

   コンテンツの検証により、メッセージのコンテンツ、件名、送信者を変更して、複数の処理を定義し、オーディエンスに最適な組み合わせを決定できます。 詳しくは、[Journey Optimizer ドキュメント &#x200B;](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/content-management/content-experiment/content-experiment){target=_blank}の「*コンテンツ実験の作成*」を参照してください。

1. 成功指標を選択し、「アクション」をクリックします。

   詳細と関連記事へのリンクについては、ヘルプアイコンをクリックしてください。

1. **[!UICONTROL Add Treatment]**&#x200B;をクリックしてから、**[!UICONTROL Create]**&#x200B;をクリックします。

   このユースケースでは、各実験に対して分布を50%のままにすることができます。

1. [!UICONTROL Campaign]の詳細ページの&#x200B;**[!UICONTROL Action]**&#x200B;の下にある「**[!UICONTROL Edit Content]**」をクリックします。

1. 「処理」 Bの下の「Web」をクリックします。

   このユースケースでは、[!UICONTROL Treatment A]を変更せず、A/B テストの最初のエクスペリエンスとして元のエクスペリエンスを使用します。

1. 右側のパネルで「**[!UICONTROL Edit Web Page]**」をクリックします。

   ![&#x200B; ヨガランディングページのコンテンツページを編集](/help/main/c-integrating-target-with-mac/ajo/assets/edit-yoga-page.png)

1. ヒーロー画像を変更するには、変更する画像をクリックし、**[!UICONTROL Choose Image]** ボタンをクリックします。

   ![画像を選択ボタン &#x200B;](/help/main/c-integrating-target-with-mac/ajo/assets/choose-image.png)

1. 目的の画像を参照して選択し、**[!UICONTROL Use This Image]**&#x200B;をクリックします。

   ![&#x200B; ヨガページに新しいヒーロー画像](/help/main/c-integrating-target-with-mac/ajo/assets/new-hero-image.png)

1. プロファイル属性を使用してユーザーのファーストネームでメッセージをパーソナライズするには、パーソナライズするテキストをクリックし、**[!UICONTROL Add Personalization]**&#x200B;をクリックして[!UICONTROL Add Personalization] ページを表示します。

   ![Personalization ボタンを追加します。](/help/main/c-integrating-target-with-mac/ajo/assets/add-personalization-button.png)

   プロファイル属性について詳しくは、[Journey Optimizer ドキュメント &#x200B;](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/content-management/personalization/expression-editor/personalization-build-expressions){target=_blank}の「*パーソナライゼーションエディターの基本を学ぶ*」を参照してください。

1. 「+」記号を検索してクリックし、「名」プロファイル属性を追加し、必要に応じてテキストを調整してから「**[!UICONTROL Save]**」をクリックします。

   ![名前](/help/main/c-integrating-target-with-mac/ajo/assets/add-profile-attribute-for-name.png)のプロファイル属性を追加

   詳しくは、[Journey Optimizer ドキュメント &#x200B;](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/content-management/personalization/expression-editor/personalization-build-expressions){target=_blank}の「*パーソナライゼーションエディターの基本を学ぶ*」を参照してください。

1. 左上隅の後向き矢印をクリックして、web デザイナーに戻ります。

   ![戻る矢印](/help/main/c-integrating-target-with-mac/ajo/assets/back-arrow.png)

1. **[!UICONTROL Review to Activate]**&#x200B;をクリックし、すべてが期待どおりに表示されることを確認してから、**アクティブ化**&#x200B;をクリックします。

## レポートを表示

「[!UICONTROL Reports]」ボタンをクリックし、目的のレポート期間をクリックします。

* [!UICONTROL View all time report]
* [!UICONTROL View last 24hrs report]

詳しくは、[Journey Optimizer ドキュメント &#x200B;](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channel-report/report-gs-cja){target=_blank}の「*新しいレポートインターフェイスの基本を学ぶ*」を参照してください。

>[!MORELIKETHIS]
>
>[Journey Optimizer ドキュメント &#x200B;](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/web/author-web-pages/web-visual-editor){target=_blank}のweb デザイナー&#x200B;*の操作*
>[&#128279;](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/create-campaigns/create-a-campaign){target=_blank}Journey Optimizer チュートリアル *でキャンペーン*&#x200B;を作成
