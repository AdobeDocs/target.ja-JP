---
keywords: analytics tracking server;A4T;Adobe Experience Cloud debugger;Adobe Experience Cloud debugger;reporting source
description: 古いバージョンの at.js または mbox.js を使用している場合は、Analytics for Target（A4T）を使用するアクティビティ用に Analytics トラッキングサーバーを指定する必要があります。
title: Analytics トラッキングサーバーの使用
feature: a4t general
uuid: ad700b90-f409-496a-bc26-0f0367410a85
translation-type: tm+mt
source-git-commit: 2f437e4cf33e4facba60d53ba545beb95c16f191
workflow-type: tm+mt
source-wordcount: '647'
ht-degree: 24%

---


# Analytics トラッキングサーバーの使用{#use-an-analytics-tracking-server}

If you are using an older version of at.js or mbox.js, you must specify an analytics tracking server for activities that use [!DNL Analytics] for [!DNL Target] (A4T).

>[!NOTE]
>
>If you use [!DNL Analytics] as your activity&#39;s reporting source, you do not need to specify a tracking server during activity creation if you are using mbox.js version 61 (or later) or at.js version 0.9.1 (or later). mbox.js または at.js ライブラリは、トラッキングサーバーの値を自動的に [!DNL Target] へ送信します。アクティビティの作成時には、[!UICONTROL 目標および設定]ページの「[!UICONTROL トラッキングサーバー]」フィールドを空白にできます。
>
>チ [!DNL Target] ームはat.js 1の両方をサポートしています。*x* と at.js 2.*x* 間のマッピングについて説明します。サポートされているバージョンを実行していることを確認するには、at.jsのメジャーバージョンのいずれかを最新のアップデートにアップグレードしてください。 For more information, see [at.js version details](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md).

To ensure that data from [!DNL Target] goes to the correct location in [!DNL Analytics], A4T requires an analytics tracking server to be sent in all calls to Modstats from [!DNL Target]. For implementations using multiple tracking servers you can use the [!DNL Adobe Experience Platform Debugger] or your browser&#39;s Developer Tools to determine the correct tracking server for your activity.

## Adobe Experience Platformデバッガーを使用したAnalyticsトラッキングサーバーの取得

アクティビティが提供されるページでデバッガーを表示して、適切なトラッキングサーバーが選択されていることを確認します。アカウントごとにデフォルトのトラッキングサーバーを指定することもできます。デフォルトを指定または変更するには、カスタマーケアにお問い合わせください。

1. アクティビティを作成しているページから、を開き [!DNL Adobe Experience Platform Debugger]ます。

   デバッガをインストールしていない場合は、「 [Adobe Experience Platformデバッガの概要](https://docs.adobe.com/content/help/en/platform-learn/tutorials/data-ingestion/web-sdk/introduction-to-the-experience-platform-debugger.html)」を参照してください。

   ![](assets/Screen_DebuggerTrackServ.png)

1. 左側のナビゲーションメニューで **[!UICONTROL 「解析]** 」をクリックします。

   The analytics tracking server is found in the [!UICONTROL Hostname] section of the debugger.

   * **ファーストパーティトラッキングサーバー**:リクエストのホスト名が、現在使用しているドメインと一致する場合、そのホスト名はファーストパーティのトラッキングサーバーです。 例えば、を使用している場合、 `adobe.com`はファーストパーティ `adobe.com` のトラッキングサーバーです。
   * **サードパーティのトラッキングサーバー**:通常、サードパーティのトラッキングサーバー `[company].sc.omtrdc.net` では、会社が会社の名前ですが、常にで終わり `sc.omtrdc.net`ます。
   * **CNAMEの導入**: `sstats.adobe.com` は、https（セキュア）リクエスト用のCNAMEファーストパーティトラッキングサーバーの例です。 `stats.adobe.com` は、http（非セキュア）ページに対するCNAMEファーストパーティリクエストの例です。

1. フィールドの内容すべてをコピーします。
1. アクティビティの「**[!UICONTROL 目標および設定]****[!UICONTROL 」画面の「]**&#x200B;レポート設定&#x200B;**[!UICONTROL 」セクションで、「トラッキングサーバー]**」フィールドにトラッキングサーバーの情報を貼り付けます。

   >[!NOTE]
   >
   >You must select [!UICONTROL Analytics as the Reporting Source] for your activity for the [!UICONTROL Tracking Server] field to be available.

## ブラウザーの開発者ツールを使用してAnalyticsトラッキングサーバーを取得する

正しいトラッキングサーバーを選択できるように、アクティビティが配信されるページで開発者ツールを表示する必要があります。 アカウントごとにデフォルトのトラッキングサーバーを指定することもできます。デフォルトを指定または変更するには、カスタマーケアにお問い合わせください。

1. アクティビティを作成しているページから、ブラウザーの開発者ツールを開きます（Google Chromeで、右上隅の3つの縦長の楕円をクリックし、その他のツール/開発者ツールを選択します）。

   ![Chrome開発者ツール](/help/c-integrating-target-with-mac/a4t/assets/chrome-dev-tools.png)

1. Click the **[!UICONTROL Network]** tab.

1. 「/ss」でフィルターし、解析リクエストを表示します。

   ![Chrome開発者ツール](/help/c-integrating-target-with-mac/a4t/assets/chrome-dev-tools.png)

   トラッキングサーバーは、リクエストのホスト名です。

   * **ファーストパーティトラッキングサーバー**:リクエストのホスト名が、現在使用しているドメインと一致する場合、そのホスト名はファーストパーティのトラッキングサーバーです。 例えば、を使用している場合、 `adobe.com`はファーストパーティ `adobe.com` のトラッキングサーバーです。
   * **サードパーティのトラッキングサーバー**:通常、サードパーティのトラッキングサーバー `[company].sc.omtrdc.net` では、会社が会社の名前ですが、常にで終わり `sc.omtrdc.net`ます。
   * **CNAMEの導入**: `sstats.adobe.com` は、https（セキュア）リクエスト用のCNAMEファーストパーティトラッキングサーバーの例です。 `stats.adobe.com` は、http（非セキュア）ページに対するCNAMEファーストパーティリクエストの例です。

