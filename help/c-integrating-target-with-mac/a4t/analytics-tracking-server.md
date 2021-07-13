---
keywords: analyticsトラッキングサーバー；A4T;Adobe Experience Cloudデバッガー；Adobe Experience Platformデバッガー；レポートソース；開発者ツール
description: '古いバージョンのat.jsを使用している場合に、Analytics for [!DNL Target] (A4T)を使用するアクティビティに対してAnalyticsトラッキングサーバーを指定する方法について説明します。 '
title: Analyticsトラッキングサーバーの使用方法を教えてください。
feature: Analytics for Target（A4T）
exl-id: 8066d6a6-661e-428b-9d5c-18537a80fb43
source-git-commit: 3c79b2ce70e456275ddf6774a35ae5c36f0ae99d
workflow-type: tm+mt
source-wordcount: '693'
ht-degree: 19%

---

# Analytics トラッキングサーバーの使用

古いバージョンのat.jsを使用している場合、[!DNL Adobe Analytics]を[!DNL Adobe Target](A4T)に使用するアクティビティ用にAnalyticsトラッキングサーバーを指定する必要があります。

>[!NOTE]
>
>at.jsバージョン0.9.1（またはそれ以降）を使用している場合、アクティビティ作成時にトラッキングサーバーを指定する必要はありません。 at.jsライブラリは、トラッキングサーバーの値を自動的に[!DNL Target]に送信します。 アクティビティの作成時には、[!UICONTROL 目標および設定]ページの「[!UICONTROL トラッキングサーバー]」フィールドを空白にできます。
>
>[!DNL Target]チームは、at.js 1.*x* と at.js 2.*x* 間のマッピングについて説明します。at.jsのメジャーバージョンを最新の更新にアップグレードして、サポート対象のバージョンを実行していることを確認してください。 詳しくは、[at.js のバージョンの詳細](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)を参照してください。

[!DNL Target]からのデータが[!DNL Analytics]の正しい場所に送信されるように、A4Tでは、[!DNL Target]からModstatsへのすべての呼び出しでAnalyticsトラッキングサーバーを送信する必要があります。 複数のトラッキングサーバーを使用する実装の場合は、[!DNL Adobe Experience Platform Debugger]またはブラウザーの開発者ツールを使用して、アクティビティに適したトラッキングサーバーを判断します。

## Adobe Experience Platform Debuggerを使用したAnalyticsトラッキングサーバーの取得

アクティビティが配信されるページにデバッガーを表示して、正しいトラッキングサーバーが選択されていることを確認する必要があります。 アカウントごとにデフォルトのトラッキングサーバーを指定することもできます。デフォルトを指定または変更するには、カスタマーケアにお問い合わせください。

1. アクティビティを作成するページから、[!DNL Adobe Experience Platform Debugger]を開きます。

   Debuggerをまだインストールしていない場合は、「[Adobe Experience Platform Debuggerの概要](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/web-sdk/introduction-to-the-experience-platform-debugger.html)」を参照してください。

   ![](assets/Screen_DebuggerTrackServ.png)

1. 左側のナビゲーションメニューで「**[!UICONTROL Analytics]**」をクリックします。

   Analyticsトラッキングサーバーは、デバッガーの[!UICONTROL Hostname]セクションにあります。

   * **ファーストパーティトラッキングサーバー**:リクエストのホスト名が現在のドメインと一致する場合、それはファーストパーティのトラッキングサーバーです。例えば、`adobe.com`を使用している場合、`adobe.com`はファーストパーティのトラッキングサーバーです。
   * **サードパーティトラッキングサーバー**:サードパーティのトラッキングサーバーで `[company].sc.omtrdc.net` は、通常、会社は会社の名前ですが、常にで終わりま `sc.omtrdc.net`す。
   * **CNAME実装**: `sstats.adobe.com` は、https（セキュア）リクエストのCNAMEファーストパーティトラッキングサーバーの例です。`stats.adobe.com` は、http（セキュアでない）ページに対するCNAMEファーストパーティリクエストの例です。

1. フィールドの内容すべてをコピーします。

1. アクティビティの「**[!UICONTROL 目標および設定]****[!UICONTROL 」画面の「]**&#x200B;レポート設定&#x200B;**[!UICONTROL 」セクションで、「トラッキングサーバー]**」フィールドにトラッキングサーバーの情報を貼り付けます。

   >[!NOTE]
   >
   >「[!UICONTROL トラッキングサーバー]」フィールドを使用可能にするアクティビティのレポートソースとして「[!UICONTROL Analytics]」を選択します。

## ブラウザーの開発者ツールを使用してAnalyticsトラッキングサーバーを取得する

正しいトラッキングサーバーが選択されていることを確認するために、開発者ツールは、アクティビティが配信されるページに表示される必要があります。 アカウントごとにデフォルトのトラッキングサーバーを指定することもできます。デフォルトを指定または変更するには、カスタマーケアにお問い合わせください。

1. アクティビティを作成するページで、ブラウザーの開発者ツールを開きます（Google Chromeで、右上隅にある縦並びの省略記号/その他のツール/開発者ツールをクリックします）。

   ![Chrome開発者ツール](/help/c-integrating-target-with-mac/a4t/assets/chrome-dev-tools.png)

1. 「**[!UICONTROL ネットワーク]**」タブをクリックします。

1. `/ss,`をフィルターして、Analytics要求を表示します。

   ![/ss検索を使用するChrome開発者ツール](/help/c-integrating-target-with-mac/a4t/assets/chrome-search.png)

   トラッキングサーバーは、リクエストのホスト名です。

   * **ファーストパーティトラッキングサーバー**:リクエストのホスト名が現在のドメインと一致する場合、それはファーストパーティのトラッキングサーバーです。例えば、`adobe.com`を使用している場合、`adobe.com`はファーストパーティのトラッキングサーバーです。
   * **サードパーティトラッキングサーバー**:サードパーティのトラッキングサーバーで `[company].sc.omtrdc.net` は、通常、会社は会社の名前ですが、常にで終わりま `sc.omtrdc.net`す。
   * **CNAME実装**: `sstats.adobe.com` は、https（セキュア）リクエストのCNAMEファーストパーティトラッキングサーバーの例です。`stats.adobe.com` は、http（セキュアでない）ページに対するCNAMEファーストパーティリクエストの例です。

1. フィールドの内容すべてをコピーします。

1. アクティビティの「**[!UICONTROL 目標および設定]****[!UICONTROL 」画面の「]**&#x200B;レポート設定&#x200B;**[!UICONTROL 」セクションで、「トラッキングサーバー]**」フィールドにトラッキングサーバーの情報を貼り付けます。

   >[!NOTE]
   >
   >「[!UICONTROL トラッキングサーバー]」フィールドを使用可能にするアクティビティのレポートソースとして「[!UICONTROL Analytics]」を選択します。
