---
keywords: 最適化；パーソナライゼーション；adobe journey optimizer;ajo；ユースケース；シナリオ；コンテンツ変更/ab テスト；プロファイル属性；画像の変更；画像の置き換え
description: 秘密鍵のロックを解除して、Adobe Journey Optimizerでのコンテンツ変更の A/B テストを効果的に行う
title: ' [!DNL Adobe Journey Optimizer] の A/B テストによるコンテンツの変更'
badgeBeta: label="ベータ" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#beta newtab=true" tooltip=" [!DNL Adobe Target] のベータ版機能とは"
feature: Integrations
hide: true
hidefromtoc: true
source-git-commit: bbf56b2d041ea6537116d900278242a7a679dedd
workflow-type: tm+mt
source-wordcount: '500'
ht-degree: 2%

---

# [!DNL Adobe Journey Optimizer] の A/B テストによるコンテンツの変更

このユースケースは、[!DNL Adobe Journey Optimizer] でコンテンツの変更を効果的に A/B テストするための秘密鍵のロックを解除するのに役立ちます。

## シナリオ

あるアパレル会社は、様々な画像をテストし、プロファイル属性からユーザーの名を使用してキャンペーンランディングページをパーソナライズすることで、コンバージョンを向上させました。

## メリットと価値

* **コンテンツの効果の最適化**：顧客の共感を最も呼ぶコンテンツバリエーションと要素を見つけ、エンゲージメントとコンバージョンの向上につなげます。
* **データに基づく意思決定**: データを活用して、コンテンツ戦略全体で十分な情報に基づいた意思決定を行い、最大限の影響を与えます。
* **パーソナライズされたユーザーエクスペリエンス**：すべてのオーディエンスセグメントに固有の好みやニーズに合わせてコンテンツをカスタマイズします。

## 詳しい手順

様々な画像をテストし、ユーザーの名を使用してメッセージをパーソナライズすることで、web ページを最適化するには、次の手順を実行します。

1. [!DNL Adobe Journey Optimizer] で、左側のパネルから **キャンペーン** をクリックして、[!UICONTROL Campaigns] のページを表示します。

   ![ 「キャンペーン」タブがハイライト表示されたAdobe Journey Optimizerランディングページ ](/help/main/c-integrating-target-with-mac/ajo/assets/ajo-landing-page.png)

1. [!UICONTROL Campaigns] ページの右上隅にある「**[!UICONTROL Create Campaign]**」をクリックします。

1. 「**[!UICONTROL Scheduled - Marketing]**」（デフォルト）を選択し、「**作成** をクリックして、[!UICONTROL Campaign] の詳細ページを表示します。

   ![Adobe Journey Optimizerのキャンペーン詳細ページ ](/help/main/c-integrating-target-with-mac/ajo/assets/campaign-details.png)

1. キャンペーンのわかりやすい名前と説明（オプション）を入力します。

1. （条件付き）「**[!UICONTROL Select Audience]**」をクリックして、目的のオーディエンスを選択します。

   このユースケースでは、すべての訪問者に対してキャンペーンをアクティブ化することを選択しました（デフォルト）。

1. **[!UICONTROL Action]** ドロップダウンリストから「**[!UICONTROL Web]**」を選択し、Web 設定を選択または新規作成します。

   Web 設定（チャネルサーフェス）は、システム管理者によって定義された設定です。 Web 設定には、ヘッダーパラメーター、サブドメイン、モバイルアプリなど、メッセージを送信するためのすべての技術的なパラメーターが含まれています。

   詳しくは、*Journey Optimizer ドキュメント [ チャネルサーフェスの設定 ](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/configuration/channel-surfaces#set-up-channel-surfaces){target=_blank} を参照してください*。

1. 「**[!UICONTROL Edit Content]**」をクリックして、[!DNL Journey Optimizer] web デザイナーで web サイトを開きます。

   ![LUMA web サイトの Yoga ランディングページ ](/help/main/c-integrating-target-with-mac/ajo/assets/luma-yoga-landing.png)

1. 右側のパネルで「**[!UICONTROL Edit Web Page]**」をクリックします。

   ![Yoga ランディングページのコンテンツを編集ページ ](/help/main/c-integrating-target-with-mac/ajo/assets/edit-yoga-page.png)

1. ヒーロー画像を変更するには、変更する画像をクリックし、「**[!UICONTROL Choose Image]**」ボタンをクリックします。

   ![ 画像を選択ボタン ](/help/main/c-integrating-target-with-mac/ajo/assets/choose-image.png)

1. 目的の画像を参照して選択し、「**[!UICONTROL Use This Image]**」をクリックします。

   ![ ヨガページの新しいヒーロー画像 ](/help/main/c-integrating-target-with-mac/ajo/assets/new-hero-image.png)

1. プロファイル属性を使用してユーザーの名前（名）でメッセージをパーソナライズするには、パーソナライズするテキストをクリックし、「**[!UICONTROL Add Personalization]**」をクリックしてパーソナライ [!UICONTROL Add Personalization] ーションページを表示します。

   ![ 「Personalizationを追加」ボタン ](/help/main/c-integrating-target-with-mac/ajo/assets/add-personalization-button.png)

1. 「名」プロファイル属性を検索して選択し、必要に応じてテキストを調整して、「**[!UICONTROL Save]**」をクリックします。

   ![ 名前のプロファイル属性を追加 ](/help/main/c-integrating-target-with-mac/ajo/assets/add-profile-attribute-for-name.png)

   詳しくは、*Journey Optimizer ドキュメント [ パーソナライゼーションエディターの基本を学ぶ ](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/content-management/personalization/expression-editor/personalization-build-expressions){target=_blank} を参照してください*。

1. 左上隅の戻る矢印をクリックして、web デザイナーに戻ります。

   ![ 左向き矢印 ](/help/main/c-integrating-target-with-mac/ajo/assets/back-arrow.png)

1. 「**[!UICONTROL Review to Activate]**」をクリックして、すべてが期待どおりに表示されることを確認してから、「**アクティブ化**」をクリックします。

>[!MORELIKETHIS]
>
>[3}Journey Optimizer ドキュメントの ](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/web/author-web-pages/edit-web-content){target=_blank}Web コンテンツを編集 **
>[](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/web/author-web-pages/web-spa#video){target=_blank}2}Journey Optimizer ドキュメント } のチュートリアルビデオ **
>[キャンペーン ](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/create-campaigns/create-a-campaign){target=_blank} を *Journey Optimizer Tutorialsに作成*

