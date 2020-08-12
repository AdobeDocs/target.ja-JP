---
keywords: analytics tracking server;A4T;Adobe Experience Cloud debugger;reporting source
description: 古いバージョンの at.js または mbox.js を使用している場合は、Analytics for Target（A4T）を使用するアクティビティ用に Analytics トラッキングサーバーを指定する必要があります。
title: Analytics トラッキングサーバーの使用
feature: null
uuid: ad700b90-f409-496a-bc26-0f0367410a85
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '363'
ht-degree: 53%

---


# Analytics トラッキングサーバーの使用{#use-an-analytics-tracking-server}

If you are using an older version of at.js or mbox.js, you must specify an analytics tracking server for activities that use [!DNL Analytics] for [!DNL Target] (A4T).

>[!NOTE]
>
>If you use [!DNL Analytics] as your activity&#39;s reporting source, you do not need to specify a tracking server during activity creation if you are using mbox.js version 61 (or later) or at.js version 0.9.1 (or later). mbox.js または at.js ライブラリは、トラッキングサーバーの値を自動的に [!DNL Target] へ送信します。アクティビティの作成時には、[!UICONTROL 目標および設定]ページの「[!UICONTROL トラッキングサーバー]」フィールドを空白にできます。

To ensure that data from [!DNL Target] goes to the correct location in [!DNL Analytics], A4T requires an analytics tracking server to be sent in all calls to Modstats from [!DNL Target]. For implementations using multiple tracking servers you can use the [!DNL Adobe Experience Cloud Debugger] to determine the correct tracking server for your activity.

アクティビティが提供されるページでデバッガーを表示して、適切なトラッキングサーバーが選択されていることを確認します。アカウントごとにデフォルトのトラッキングサーバーを指定することもできます。デフォルトを指定または変更するには、カスタマーケアにお問い合わせください。

1. アクティビティを作成しているページから、を開き [!DNL Adobe Experience Cloud Debugger]ます。

   デバッガをインストールしていない場合は、 [Experience Cloud Debuggerのインストールを参照してください](https://docs.adobe.com/content/help/en/debugger/using/install-debugger.html)。

   ![](assets/Screen_DebuggerTrackServ.png)

   The analytics tracking server is found in the [!UICONTROL SiteCatalyst Image] section of the debugger. 実装環境に応じて、このフィールドは&#x200B;*ファーストパーティの Cookie* または&#x200B;*サードパーティの Cookie* と呼ばれます。 トラッキングサーバーの値は次のいずれかの形式になります。[!DNL Analytics]

   * （CNAME 実装の場合）
   * （RDC 以外の実装の場合）
   * （RDC 実装の場合）

   *Company*[!DNL Analytics] は、 企業名を指し、*metrics* は CNAME 値の例、*d1* は データセンターの例を指します。[!DNL Analytics]
1. フィールドの内容すべてをコピーします。
1. アクティビティの「[!UICONTROL 目標および設定][!UICONTROL 」画面の「]レポート設定&#x200B;**[!UICONTROL 」セクションで、「トラッキングサーバー]**」フィールドにトラッキングサーバーの情報を貼り付けます。

   >[!NOTE]
   >
   >You must select [!UICONTROL Analytics as the Reporting Source] for your activity for the [!UICONTROL Tracking Server] field to be available.

