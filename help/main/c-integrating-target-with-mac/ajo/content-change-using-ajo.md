---
keywords: 最適化；パーソナライゼーション；adobe journey optimizer;ajo；ユースケース；シナリオ；コンテンツ変更/ab テスト；プロファイル属性；画像の変更；画像の置き換え
description: 秘密鍵のロックを解除して、Adobe Journey Optimizerでのコンテンツ変更の A/B テストを効果的に行う
title: ' [!DNL Adobe Journey Optimizer] の A/B テストによるコンテンツの変更'
badgeBeta: label="ベータ" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#beta newtab=true" tooltip=" [!DNL Adobe Target] のベータ版機能とは"
feature: Integrations
hide: true
hidefromtoc: true
exl-id: e5aed7cd-7701-4133-ac7c-98e528c8a763
source-git-commit: b66abe9649f8c257891c1cd8e5736b7f91501c13
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 1%

---

# [!DNL Adobe Journey Optimizer] の A/B テストによるコンテンツの変更

このユースケースは、[!DNL Adobe Journey Optimizer] でコンテンツの変更を効果的に A/B テストするための秘密鍵のロックを解除するのに役立ちます。

このユースケースでは、[ の代わりに ](/help/main/c-activities/t-test-ab/test-ab.md) を使用して、[!DNL Adobe Target] で [!DNL Journey Optimizer]A/B テスト アクティビティを使用した A/B テストなど [!DNL Adobe Target] 使い慣れたタスクを実行する方法を示します。

## メリットと価値

* **コンテンツの効果の最適化**：顧客の共感を最も呼ぶコンテンツバリエーションと要素を見つけ、エンゲージメントとコンバージョンの向上につなげます。
* **データに基づく意思決定**: データを活用して、コンテンツ戦略全体で十分な情報に基づいた意思決定を行い、最大限の影響を与えます。
* **パーソナライズされたユーザーエクスペリエンス**：すべてのオーディエンスセグメントに固有の好みやニーズに合わせてコンテンツをカスタマイズします。

## 考えられるシナリオ

* あるアパレル会社は、様々な画像をテストし、call-to-actionのテキストでユーザーの名を使用して campaign ランディングページをパーソナライズすることで、コンバージョンを向上させました。

* ある e コマース企業は、キャンペーンランディングページで様々な製品の説明と画像をテストすることで、ゴールドロイヤルティメンバーのコンバージョン率が高く、売上の増加につながることがわかりました。

## 手順

>[!NOTE]
>
>この節の手順では、画像を変更し、プロファイル属性を使用してテキストメッセージをパーソナライズするために必要な手順を重点的に説明します。 [!DNL Journey Optimizer] Web Designer で使用可能なオプションについて詳しくは、[Journey Optimizer ドキュメント ](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/web/author-web-pages/web-visual-editor){target=_blank}Web Designer の操作 *を参照してください*。
>
>ページ下部のビデオは特に役立ちます。

様々な画像をテストし、プロファイルスクリプトを使用してユーザーの名を使用したメッセージをパーソナライズすることで、web ページを最適化します。

1. [!DNL Journey Optimizer] で、左側のパネルから **キャンペーン** をクリックして、[!UICONTROL Campaigns] のページを表示します。

1. **[!UICONTROL Create Campaign]** ページの右上隅にある「[!UICONTROL Campaigns]」をクリックします。

1. 「**[!UICONTROL Scheduled - Marketing]**」（デフォルト）を選択し、「**作成** をクリックして、[!UICONTROL Campaign] の詳細ページを表示します。

1. 「**[!UICONTROL Properties]**」セクションでは、キャンペーンのわかりやすい名前と説明（オプション）を入力します。

1. （条件付き） **[!UICONTROL Audience]** のセクションで、「**[!UICONTROL Select Audience]**」をクリックして目的のオーディエンスを選択します。

   この使用例では、[!UICONTROL All Visitors] のキャンペーン（デフォルト）をアクティブ化できます。

1. 「**[!UICONTROL Action]**」セクションで、「**[!UICONTROL Web]**」ドロップダウンリストから「**[!UICONTROL Action]**」を選択し、新しい web 設定を選択または作成します。

   Web 設定（チャネルサーフェス）は、システム管理者が定義する設定です。 Web 設定には、ヘッダーパラメーター、サブドメイン、モバイルアプリなど、メッセージを送信するためのすべての技術的なパラメーターが含まれています。

   詳しくは、[Journey Optimizer ドキュメント ](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/configuration/channel-surfaces#set-up-channel-surfaces){target=_blank} チャネルサーフェスの設定 *を参照してください*。

1. [**[!UICONTROL Action]**] セクションの [**[!UICONTROL Edit Content]**] をクリックして、[!DNL Journey Optimizer] Web Designer で Web サイトを開きます。

   A/B テストには 2 つ以上の実験が必要です。 最初の実験として既存のホームページを使用できます。 次の手順では、2 番目の実験の設定方法を説明します。

   ![LUMA web サイトの Yoga ランディングページ ](/help/main/c-integrating-target-with-mac/ajo/assets/luma-yoga-landing.png)

1. パフォーマンスの高いコンテンツを判別するための実験を作成するには、「実 **[!UICONTROL Create Experiment]**」をクリックします。

   コンテンツ実験を使用すると、メッセージコンテンツ、件名、送信者を変更して、複数の処理を定義したり、オーディエンスに最適な組み合わせを決定したりできます。 詳しくは、[Journey Optimizer ドキュメント ](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/content-management/content-experiment/content-experiment){target=_blank} コンテンツ実験の作成 *を参照してください*。

1. 成功指標を選択し、「アクション」をクリックします。

   ヘルプ アイコンをクリックすると、詳細と関連記事へのリンクが表示されます。

1. 「**[!UICONTROL Add Treatment]**」をクリックし、「**[!UICONTROL Create]**」をクリックします。

   このユースケースでは、各実験の分布を 50% のままにすることができます。

1. [!UICONTROL Campaign] の詳細ページの [**[!UICONTROL Action]**] で、[**[!UICONTROL Edit Content]**] をクリックします。

1. 処理 B の下の「Web」をクリックします。

   このユースケースでは、元のエクスペリエンスを A/B テストの最初のエクスペリエンスとして使用する場合、[!UICONTROL Treatment A] を変更しません。

1. 右側のパネルで「**[!UICONTROL Edit Web Page]**」をクリックします。

   ![Yoga ランディングページのコンテンツを編集ページ ](/help/main/c-integrating-target-with-mac/ajo/assets/edit-yoga-page.png)

1. ヒーロー画像を変更するには、変更する画像をクリックし、「**[!UICONTROL Choose Image]**」ボタンをクリックします。

   ![ 画像を選択ボタン ](/help/main/c-integrating-target-with-mac/ajo/assets/choose-image.png)

1. 目的の画像を参照して選択し、「**[!UICONTROL Use This Image]**」をクリックします。

   ![ ヨガページの新しいヒーロー画像 ](/help/main/c-integrating-target-with-mac/ajo/assets/new-hero-image.png)

1. プロファイル属性を使用してユーザーの名前（名）でメッセージをパーソナライズするには、パーソナライズするテキストをクリックし、「**[!UICONTROL Add Personalization]**」をクリックしてパーソナライ [!UICONTROL Add Personalization] ーションページを表示します。

   ![ 「Personalizationを追加」ボタン ](/help/main/c-integrating-target-with-mac/ajo/assets/add-personalization-button.png)

   プロファイル属性について詳しくは、[Journey Optimizer ドキュメントの ](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/content-management/personalization/expression-editor/personalization-build-expressions){target=_blank} パーソナライゼーションエディターの基本を学ぶ *を参照してください*。

1. 「」を検索し、「+」記号をクリックして「名」プロファイル属性を追加し、必要に応じてテキストを調整して、「**[!UICONTROL Save]**」をクリックします。

   ![ 名前のプロファイル属性を追加 ](/help/main/c-integrating-target-with-mac/ajo/assets/add-profile-attribute-for-name.png)

   詳しくは、[Journey Optimizer ドキュメント ](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/content-management/personalization/expression-editor/personalization-build-expressions){target=_blank} パーソナライゼーションエディターの基本を学ぶ *を参照してください*。

1. 左上隅の戻る矢印をクリックして、web デザイナーに戻ります。

   ![ 左向き矢印 ](/help/main/c-integrating-target-with-mac/ajo/assets/back-arrow.png)

1. 「**[!UICONTROL Review to Activate]**」をクリックして、すべてが期待どおりに表示されることを確認してから、「**アクティブ化**」をクリックします。

## レポートを表示

「[!UICONTROL Reports]」ボタンをクリックしてから、目的のレポート期間をクリックします。

* [!UICONTROL View all time report]
* [!UICONTROL View last 24hrs report]

詳しくは、[Journey Optimizer ドキュメント ](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channel-report/report-gs-cja){target=_blank} 新しいレポートインターフェイスの概要 *を参照してください*。

>[!MORELIKETHIS]
>
>[Web デザイナーの操作 ](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/web/author-web-pages/web-visual-editor){target=_blank}、*Journey Optimizer ドキュメント*
>>[キャンペーンの作成 ](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/create-campaigns/create-a-campaign){target=_blank} *Journey Optimizer チュートリアル*
