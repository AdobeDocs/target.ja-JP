---
keywords: 最適化；パーソナライゼーション；adobe journey optimizer;ajo；ユースケース；シナリオ；コンテンツの追加；コンテンツの非表示；コンポーネントの追加；コンポーネントの非表示
description: ' [!DNL Adobe Journey Optimizer]を使用してweb ページでコンポーネントを追加または非表示にする方法について説明します。'
title: Web ページへのコンポーネントの追加または非表示 [!DNL Adobe Journey Optimizer]
badgeBeta: label="Beta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#beta newtab=true" tooltip=" [!DNL Adobe Target] のベータ版機能とは"
feature: Integrations
hide: true
hidefromtoc: true
exl-id: 8c4fba88-908e-4742-ac4b-bdf7f4c882db
TQID: https://experienceleague.adobe.com/sTvR771HCE-lkk9Fg7wXkP2p2ORPYehO23d76hVCOZU
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: f7c7de77-382f-4f48-8b36-61a170f06d3d
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 16fb7a1902ea76cab56a93fa141a32a3c6bc4467
workflow-type: tm+mt
source-wordcount: 659
ht-degree: 2%

---

# Web ページへのコンポーネントの追加または非表示

このユースケースは、[!DNL Adobe Journey Optimizer]で効果的なA/B テスト コンテンツの変更を行うための秘密を解き放つのに役立ちます。

この使用例では、[!DNL Adobe Target]ではなく[!DNL Journey Optimizer]を使用して、[A/B テストアクティビティ ](/help/main/c-activities/t-test-ab/test-ab.md)を使用したA/B テストなどの使い慣れたタスクを実行する方法を示します。

このユースケースは、[!DNL Adobe Target]、[A/B テストアクティビティ ](/help/main/c-activities/t-test-ab/test-ab.md)を使用したA/B テスト、[!DNL Journey Optimizer]を使用したA/B テストを使用して実行した可能性のある、使い慣れたタスクを実行する方法を示すように設計されています。

## 利点と価値

* **ユーザーエンゲージメントの強化**：最適化されたページデザインで、プロモーションなどの関連情報を強調して、ユーザーの注目を集めます。
* **見つけやすさの向上**:webまたはモバイルアプリに新しいコンポーネントまたはコンテンツを戦略的に配置して、アクションを合理化し、ナビゲーションを強化します。
* **顧客接点を増やす**: ユーザーをコンバージョンイベントと目標に効果的に導き、ビジネスへの影響を加速させます。

## 考えられるシナリオ

* ある金融サービス企業は、ホームページに新しいタイルを追加し、ローン計算機にすばやくアクセスできるようにして、検索時間を短縮し、ローンの申し込みを増やす予定です。

* あるアパレル企業は、web ページに新しい「call-to-action」ボタンを追加することで、コンバージョン率を向上させました。

## 手順

>[!NOTE]
>
>この節の手順では、画像を変更し、プロファイル属性を使用してテキストメッセージをパーソナライズするために必要な手順を強調表示します。 [!DNL Journey Optimizer] web デザイナーで利用できるオプションについて詳しくは、*Journey Optimizer ドキュメント*&#x200B;の[web デザイナーの操作](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/web/author-web-pages/web-visual-editor){target=_blank}を参照してください。
>
>特にページ下部の動画が役立ちます。

Web ページでコンポーネントを追加または非表示にするには、次の手順を実行します。

1. [!DNL Adobe Journey Optimizer]で、左側のパネルの&#x200B;**キャンペーン**&#x200B;をクリックして、[!UICONTROL Campaigns] ページを表示します。

   「キャンペーン」タブが強調表示された![Adobe Journey Optimizer ランディングページ。](/help/main/c-integrating-target-with-mac/ajo/assets/ajo-landing-page.png)

1. [!UICONTROL Campaigns] ページの右上隅にある「**[!UICONTROL Create Campaign]**」をクリックします。

1. **[!UICONTROL Scheduled - Marketing]** （デフォルト）を選択し、**作成**&#x200B;をクリックして、[!UICONTROL Campaign]の詳細ページを表示します。

   Adobe Journey Optimizerの![ キャンペーンの詳細ページ ](/help/main/c-integrating-target-with-mac/ajo/assets/campaign-details.png)

1. 「**[!UICONTROL Properties]**」セクションで、キャンペーンの説明的な名前とオプションの説明を入力します。

1. （条件付き） **[!UICONTROL Audience]** セクションで、**[!UICONTROL Select Audience]**&#x200B;をクリックし、目的のオーディエンスを選択します。

   このユースケースでは、[!UICONTROL All Visitors]のキャンペーンをアクティブ化できます（デフォルト）。

1. **[!UICONTROL Action]** セクションで、**[!UICONTROL Action]** ドロップダウンリストから&#x200B;**[!UICONTROL Web]**&#x200B;を選択し、新しいweb設定を選択または作成します。

   web設定（チャネルサーフェス）は、システム管理者が定義する設定です。 Web設定には、ヘッダーパラメーター、サブドメイン、モバイルアプリなど、メッセージを送信するためのすべての技術的なパラメーターが含まれます。

   詳しくは、*Journey Optimizer ドキュメント*&#x200B;の「[ チャネルサーフェスの設定](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/configuration/channel-surfaces#set-up-channel-surfaces){target=_blank}」を参照してください。

1. **[!UICONTROL Action]** セクションで、**[!UICONTROL Edit Content]**&#x200B;をクリックして、[!DNL Journey Optimizer] web デザイナーでweb サイトを開きます。

   LUMA web サイトの![ ヨガランディングページ ](/help/main/c-integrating-target-with-mac/ajo/assets/luma-yoga-landing.png)

1. 要素を非表示にするには、右側のパネルで「**[!UICONTROL Edit Web Page]**」をクリックします。

1. 非表示にする要素をクリックし、右側のパネルの[!UICONTROL Hide] ボタンをクリックします。

   右側のパネルには、選択した要素に対して実行できるオプションが表示されます。 これらのオプションは、選択した要素によって異なります。

   ![要素ボタンを非表示](/help/main/c-integrating-target-with-mac/ajo/assets/hide-element.png)

1. 左上隅の後向き矢印をクリックして、web デザイナーに戻ります。

   ![戻る矢印](/help/main/c-integrating-target-with-mac/ajo/assets/back-arrow.png)

1. **[!UICONTROL Review to Activate]**&#x200B;をクリックし、すべてが期待どおりに表示されることを確認してから、**アクティブ化**&#x200B;をクリックします。

## レポートを表示

「[!UICONTROL Reports]」ボタンをクリックし、目的のレポート期間をクリックします。

* [!UICONTROL View all time report]
* [!UICONTROL View last 24hrs report]

詳しくは、*Journey Optimizer ドキュメント*&#x200B;の「[新しいレポートインターフェイスの基本を学ぶ](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channel-report/report-gs-cja){target=_blank}」を参照してください。

>[!MORELIKETHIS]
>
>[Web デザイナーの操作](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/web/author-web-pages/web-visual-editor){target=_blank} （*Journey Optimizer ドキュメント）*
>[*Journey Optimizer チュートリアル*&#x200B;でキャンペーン ](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/create-campaigns/create-a-campaign){target=_blank}を作成
