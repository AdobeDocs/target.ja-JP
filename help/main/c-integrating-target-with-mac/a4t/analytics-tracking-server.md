---
keywords: analytics トラッキングサーバー；A4T;Adobe Experience Cloud デバッガー；Adobe Experience Platform デバッガー；レポートソース；開発者ツール
description: 古いバージョンのat.jsを使用している場合に、 [!DNL Target]  （A4T）用にAnalyticsを使用するアクティビティにAnalytics トラッキングサーバーを指定する方法について説明します。
title: Analytics トラッキングサーバーの使用方法を教えてください。
feature: Analytics for Target (A4T)
exl-id: 8066d6a6-661e-428b-9d5c-18537a80fb43
TQID: https://experienceleague.adobe.com/mJM5kZPQfnWodzwQ3qDKxu1e1Oq2Y53fA2LpSB4SVSc
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: c93393a4-e558-47e1-992e-c91ed4d480ce
subfeature_v2: id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 675
ht-degree: 15%

---

# [!DNL Analytics] トラッキングサーバーの使用

古いバージョンのat.jsを使用している場合は、[!DNL Adobe Target] （A4T）に[!DNL Adobe Analytics]を使用するアクティビティに[!DNL Analytics] トラッキングサーバーを指定する必要があります。

>[!NOTE]
>
>at.js バージョン 0.9.1 （またはそれ以降）を使用している場合は、アクティビティの作成中にトラッキングサーバーを指定する必要はありません。 at.js ライブラリは、トラッキングサーバーの値を自動的に [!DNL Target] へ送信します。 アクティビティの作成中、[!UICONTROL Goals & Settings] ページで[!UICONTROL Tracking Server] フィールドを空のままにできます。
>
>[!DNL Target] チームは、at.js 1.*x*&#x200B;とat.js 2.*x*&#x200B;の両方をサポートしています。 いずれかのメジャーバージョンのat.jsの最新のアップデートにアップグレードして、サポートされているバージョンを実行していることを確認します。 詳しくは、[at.js のバージョンの詳細](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=ja){target=_blank}を参照してください。

[!DNL Target]からのデータが[!DNL Analytics]の正しい場所に確実に送信されるようにするには、A4Tでは、[!DNL Target]からのすべての呼び出しで[!DNL Analytics] トラッキングサーバーを送信する必要があります。 複数のトラッキングサーバーを使用する実装の場合は、[!DNL Adobe Experience Platform Debugger]またはブラウザーの開発者ツールを使用して、アクティビティに適したトラッキングサーバーを決定します。

## [!DNL Adobe Experience Platform Debugger]を使用して[!DNL Analytics] トラッキングサーバーを取得する

デバッガーは、アクティビティが配信されるページで表示され、正しいトラッキングサーバーを選択していることを確認する必要があります。 アカウントごとにデフォルトのトラッキングサーバーを指定することもできます。 デフォルトを指定または変更するには、カスタマーケアへのお問い合わせ。

1. アクティビティを作成しているページから、[!DNL Adobe Experience Platform Debugger]を開きます。

   デバッガーをインストールしていない場合は、[Adobe Experience Platform Debuggerの概要](https://experienceleague.adobe.com/docs/platform-learn/data-collection/debugger/overview.html)を参照してください。

1. 左側のナビゲーションメニューで「**[!UICONTROL Analytics]**」をクリックします。

   ![Screen_DebuggerTrackServ画像](assets/Screen_DebuggerTrackServ.png)

   [!DNL Analytics] トラッキングサーバーは、デバッガーの[!UICONTROL Hostname] セクションにあります。

   * **ファーストパーティ追跡サーバー**：要求のホスト名が使用中のドメインと一致する場合、それはファーストパーティ追跡サーバーです。 例えば、`adobe.com`を使用している場合、`adobe.com`は1st パーティトラッキングサーバーです。
   * **サードパーティ追跡サーバー**: サードパーティ追跡サーバーは通常`[company].sc.omtrdc.net`です。会社は会社名ですが、常に`sc.omtrdc.net`で終わります。
   * **CNAME実装**: `sstats.adobe.com`は、https （セキュア）リクエストのCNAME ファーストパーティ追跡サーバーの例です。 `stats.adobe.com`は、http （非セキュア）ページに対するCNAME ファーストパーティリクエストの例です。

1. フィールドの内容すべてをコピーします。

1. アクティビティの&#x200B;**[!UICONTROL Goal & Settings]**&#x200B;画面の&#x200B;**[!UICONTROL Reporting Settings]** セクションで、**[!UICONTROL Tracking Server]** フィールドにトラッキングサーバー情報を貼り付けます。

   >[!NOTE]
   >
   >「[!UICONTROL Tracking Server]」フィールドを使用できるようにするには、アクティビティの「[!UICONTROL Analytics as the Reporting Source]」を選択します。

## ブラウザーの開発者ツールを使用して[!DNL Analytics]追跡サーバーを取得します

開発者ツールは、アクティビティが配信されるページで表示され、適切なトラッキングサーバーを選択できることが確認されます。 アカウントごとにデフォルトのトラッキングサーバーを指定することもできます。 デフォルトを指定または変更するには、カスタマーケアへのお問い合わせ。

1. アクティビティを作成するページで、ブラウザーのデベロッパーツールを開きます（Google Chromeで、右上隅の3つの縦長の省略記号をクリックして、その他のツール/デベロッパーツール）。

   ![Chrome開発者向けツール ](/help/main/c-integrating-target-with-mac/a4t/assets/chrome-dev-tools.png)

1. 「**[!UICONTROL Network]**」タブをクリックします。

1. `/ss,`にフィルターを適用して、[!DNL Analytics]要求を表示します。

   ![Chrome開発者向けツールと/ss検索](/help/main/c-integrating-target-with-mac/a4t/assets/chrome-search.png)

   トラッキングサーバーは、リクエストのホスト名です。

   * **ファーストパーティ追跡サーバー**：要求のホスト名が使用中のドメインと一致する場合、それはファーストパーティ追跡サーバーです。 例えば、`adobe.com`を使用している場合、`adobe.com`は1st パーティトラッキングサーバーです。
   * **サードパーティ追跡サーバー**: サードパーティ追跡サーバーは通常`[company].sc.omtrdc.net`です。会社は会社名ですが、常に`sc.omtrdc.net`で終わります。
   * **CNAME実装**: `sstats.adobe.com`は、https （セキュア）リクエストのCNAME ファーストパーティ追跡サーバーの例です。 `stats.adobe.com`は、http （非セキュア）ページに対するCNAME ファーストパーティリクエストの例です。

1. フィールドの内容すべてをコピーします。

1. アクティビティの&#x200B;**[!UICONTROL Goal & Settings]**&#x200B;画面の&#x200B;**[!UICONTROL Reporting Settings]** セクションで、**[!UICONTROL Tracking Server]** フィールドにトラッキングサーバー情報を貼り付けます。

   >[!NOTE]
   >
   >「[!UICONTROL Tracking Server]」フィールドを使用できるようにするには、アクティビティの「[!UICONTROL Analytics as the Reporting Source]」を選択します。
