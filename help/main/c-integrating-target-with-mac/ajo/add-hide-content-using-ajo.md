---
keywords: 最適化；パーソナライゼーション；adobe journey optimizer;ajo；ユースケース；シナリオ；コンテンツを追加；コンテンツを非表示；コンポーネントを追加；コンポーネントを非表示
description: ' [!DNL Adobe Journey Optimizer] を使用して、web ページ上のコンポーネントを追加または非表示にする方法を説明します。'
title: ' [!DNL Adobe Journey Optimizer] の場所で Web ページにコンポーネントを追加または非表示にします。'
badgeBeta: label="ベータ" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#beta newtab=true" tooltip=" [!DNL Adobe Target] のベータ版機能とは"
feature: Integrations
hide: true
hidefromtoc: true
exl-id: 8c4fba88-908e-4742-ac4b-bdf7f4c882db
source-git-commit: 52f11998149cddeb4245a0f07280562d79332a04
workflow-type: tm+mt
source-wordcount: '584'
ht-degree: 2%

---

# Web ページへのコンポーネントの追加または非表示

このユースケースは、[!DNL Adobe Journey Optimizer] でコンテンツの変更を効果的に A/B テストするための秘密鍵のロックを解除するのに役立ちます。

このユースケースでは、[ の代わりに ](/help/main/c-activities/t-test-ab/test-ab.md) を使用して、[!DNL Journey Optimizer]A/B テスト アクティビティ [!DNL Adobe Target] による A/B テストなど、使い慣れたタスクを実行する方法を示します。

このユースケースは、[!DNL Adobe Target]、[A/B テスト アクティビティ ](/help/main/c-activities/t-test-ab/test-ab.md) を使用した A/B テストを使用し、[!DNL Journey Optimizer] を使用して、実行した可能性のある使い慣れたタスクを実行する方法を示すように設計されています。

## メリットと価値

* **ユーザーエンゲージメントの向上**：プロモーションなどの関連情報をハイライト表示する最適化されたページデザインでユーザーの注意を引きます。
* **検出性の向上**：新しいコンポーネントやコンテンツを web またはモバイルアプリに戦略的に配置して、アクションを合理化し、ナビゲーションを強化します。
* **追加のタッチポイントを増やす**：コンバージョンイベントと目標に向けてユーザーを効果的に導き、ビジネスに与える影響を加速します。

## 考えられるシナリオ

* ある金融サービス企業は、ホームページに新しいタイルを追加して、ローン計算ツールにすばやくアクセスし、検索時間を短縮し、ローン申し込みを強化する予定です。

* あるアパレル会社は、web ページに新しい「call-to-action」ボタンを追加し、コンバージョンを向上させました。

## 手順

>[!NOTE]
>
>この節の手順では、画像を変更し、プロファイル属性を使用してテキストメッセージをパーソナライズするために必要な手順を重点的に説明します。 [!DNL Journey Optimizer] Web Designer で使用可能なオプションについて詳しくは、[Journey Optimizer ドキュメント ](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/web/author-web-pages/web-visual-editor){target=_blank}Web Designer の操作 *を参照してください*。
>
>ページ下部のビデオは特に役立ちます。

次の手順を実行して、コンポーネントを追加するか、web ページ上のコンポーネントを非表示にします。

1. [!DNL Adobe Journey Optimizer] で、左側のパネルから **キャンペーン** をクリックして、[!UICONTROL Campaigns] のページを表示します。

   ![ 「キャンペーン」タブがハイライト表示されたAdobe Journey Optimizerランディングページ ](/help/main/c-integrating-target-with-mac/ajo/assets/ajo-landing-page.png)

1. **[!UICONTROL Create Campaign]** ページの右上隅にある「[!UICONTROL Campaigns]」をクリックします。

1. 「**[!UICONTROL Scheduled - Marketing]**」（デフォルト）を選択し、「**作成** をクリックして、[!UICONTROL Campaign] の詳細ページを表示します。

   ![Adobe Journey Optimizerのキャンペーン詳細ページ ](/help/main/c-integrating-target-with-mac/ajo/assets/campaign-details.png)

1. 「**[!UICONTROL Properties]**」セクションでは、キャンペーンのわかりやすい名前と説明（オプション）を入力します。

1. （条件付き） **[!UICONTROL Audience]** のセクションで、「**[!UICONTROL Select Audience]**」をクリックして目的のオーディエンスを選択します。

   この使用例では、[!UICONTROL All Visitors] のキャンペーン（デフォルト）をアクティブ化できます。

1. 「**[!UICONTROL Action]**」セクションで、「**[!UICONTROL Web]**」ドロップダウンリストから「**[!UICONTROL Action]**」を選択し、新しい web 設定を選択または作成します。

   Web 設定（チャネルサーフェス）は、システム管理者が定義する設定です。 Web 設定には、ヘッダーパラメーター、サブドメイン、モバイルアプリなど、メッセージを送信するためのすべての技術的なパラメーターが含まれています。

   詳しくは、[Journey Optimizer ドキュメント ](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/configuration/channel-surfaces#set-up-channel-surfaces){target=_blank} チャネルサーフェスの設定 *を参照してください*。

1. [**[!UICONTROL Action]**] セクションの [**[!UICONTROL Edit Content]**] をクリックして、[!DNL Journey Optimizer] Web Designer で Web サイトを開きます。

   ![LUMA web サイトの Yoga ランディングページ ](/help/main/c-integrating-target-with-mac/ajo/assets/luma-yoga-landing.png)

1. 要素の非表示を追加するには、右側のパネルで「**[!UICONTROL Edit Web Page]**」をクリックします。

1. 非表示にする要素をクリックし、右側のパネルの「[!UICONTROL Hide]」ボタンをクリックします。

   右側のパネルには、選択した要素に対して実行できるオプションが表示されます。 これらのオプションは、選択した要素によって異なります。

   ![ 要素を非表示ボタン ](/help/main/c-integrating-target-with-mac/ajo/assets/hide-element.png)

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
>&#x200B;>[キャンペーンの作成 ](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/tutorials/create-campaigns/create-a-campaign){target=_blank} *Journey Optimizer チュートリアル*
