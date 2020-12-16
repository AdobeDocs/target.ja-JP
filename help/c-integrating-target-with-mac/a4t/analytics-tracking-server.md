---
keywords: analytics tracking server;A4T;Adobe Experience Cloud debugger;Adobe Experience Platform debugger;reporting source;developer tools
description: 古いバージョンの at.js または mbox.js を使用している場合は、Analytics for Target（A4T）を使用するアクティビティ用に Analytics トラッキングサーバーを指定する必要があります。
title: Analytics トラッキングサーバーの使用
feature: a4t general
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '696'
ht-degree: 27%

---


# Analytics トラッキングサーバーの使用

古いバージョンのat.jsまたはmbox.jsを使用している場合は、[!DNL Target]に[!DNL Analytics](A4T)を使用するアクティビティ用にAnalyticsトラッキングサーバーを指定する必要があります。

>[!NOTE]
>
>アクティビティのレポートソースとして[!DNL Analytics]を使用する場合、mbox.jsバージョン61（以降）またはat.jsバージョン0.9.1（以降）を使用している場合は、アクティビティの作成時にトラッキングサーバーを指定する必要はありません。 mbox.js または at.js ライブラリは、トラッキングサーバーの値を自動的に [!DNL Target] へ送信します。アクティビティの作成時には、[!UICONTROL 目標および設定]ページの「[!UICONTROL トラッキングサーバー]」フィールドを空白にできます。
>
>[!DNL Target]チームは、at.js 1の両方をサポートしています。*x* と at.js 2.*x* 間のマッピングについて説明します。サポートされているバージョンを実行していることを確認するには、at.jsのメジャーバージョンのいずれかを最新のアップデートにアップグレードしてください。 詳しくは、[at.jsバージョンの詳細](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)を参照してください。

[!DNL Target]のデータが[!DNL Analytics]の正しい場所に送信されるようにするため、A4Tでは、すべての呼び出しで[!DNL Target]からModstatsにAnalyticsトラッキングサーバーを送信する必要があります。 複数のトラッキングサーバーを使用する導入では、[!DNL Adobe Experience Platform Debugger]またはブラウザーの開発者ツールを使用して、お使いのアクティビティに適したトラッキングサーバーを判断できます。

## Adobe Experience Platformデバッガーを使用したAnalyticsトラッキングサーバーの取得

アクティビティが提供されるページでデバッガーを表示して、適切なトラッキングサーバーが選択されていることを確認します。アカウントごとにデフォルトのトラッキングサーバーを指定することもできます。デフォルトを指定または変更するには、カスタマーケアにお問い合わせください。

1. アクティビティを作成しているページで、[!DNL Adobe Experience Platform Debugger]を開きます。

   デバッガをインストールしていない場合は、[Adobe Experience Platformデバッガの紹介](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/web-sdk/introduction-to-the-experience-platform-debugger.html)を参照してください。

   ![](assets/Screen_DebuggerTrackServ.png)

1. 左側のナビゲーションメニューで「**[!UICONTROL Analytics]**」をクリックします。

   Analyticsトラッキングサーバーは、デバッガーの[!UICONTROL ホスト名]セクションにあります。

   * **ファーストパーティトラッキングサーバー**:リクエストのホスト名が、現在使用しているドメインと一致する場合、そのホスト名はファーストパーティのトラッキングサーバーです。例えば、`adobe.com`を使用している場合、`adobe.com`はファーストパーティのトラッキングサーバーです。
   * **サードパーティのトラッキングサーバー**:通常、サードパーティのトラッキングサーバー `[company].sc.omtrdc.net` では、会社が会社の名前ですが、常にで終わり `sc.omtrdc.net`ます。
   * **CNAMEの導入**: `sstats.adobe.com` は、https（セキュア）リクエスト用のCNAMEファーストパーティトラッキングサーバーの例です。`stats.adobe.com` は、http（非セキュア）ページに対するCNAMEファーストパーティリクエストの例です。

1. フィールドの内容すべてをコピーします。

1. アクティビティの「**[!UICONTROL 目標および設定]****[!UICONTROL 」画面の「]**&#x200B;レポート設定&#x200B;**[!UICONTROL 」セクションで、「トラッキングサーバー]**」フィールドにトラッキングサーバーの情報を貼り付けます。

   >[!NOTE]
   >
   >[!UICONTROL トラッキングサーバー]フィールドを使用できるようにするには、アクティビティのレポートソース]として「Analytics」を選択する必要があります。[!UICONTROL 

## ブラウザーの開発者ツールを使用してAnalyticsトラッキングサーバーを取得する

正しいトラッキングサーバーを選択できるように、アクティビティが配信されるページで開発者ツールを表示する必要があります。 アカウントごとにデフォルトのトラッキングサーバーを指定することもできます。デフォルトを指定または変更するには、カスタマーケアにお問い合わせください。

1. アクティビティを作成しているページから、ブラウザーの開発者ツールを開きます（Google Chromeで、右上隅の3つの縦長の楕円をクリックし、その他のツール/開発者ツールを選択します）。

   ![Chrome開発者ツール](/help/c-integrating-target-with-mac/a4t/assets/chrome-dev-tools.png)

1. 「**[!UICONTROL ネットワーク]**」タブをクリックします。

1. `/ss,`をフィルターして、Analyticsリクエストを表示します。

   ![/ss検索機能を備えたChrome開発者ツール](/help/c-integrating-target-with-mac/a4t/assets/chrome-search.png)

   トラッキングサーバーは、リクエストのホスト名です。

   * **ファーストパーティトラッキングサーバー**:リクエストのホスト名が、現在使用しているドメインと一致する場合、そのホスト名はファーストパーティのトラッキングサーバーです。例えば、`adobe.com`を使用している場合、`adobe.com`はファーストパーティのトラッキングサーバーです。
   * **サードパーティのトラッキングサーバー**:通常、サードパーティのトラッキングサーバー `[company].sc.omtrdc.net` では、会社が会社の名前ですが、常にで終わり `sc.omtrdc.net`ます。
   * **CNAMEの導入**: `sstats.adobe.com` は、https（セキュア）リクエスト用のCNAMEファーストパーティトラッキングサーバーの例です。`stats.adobe.com` は、http（非セキュア）ページに対するCNAMEファーストパーティリクエストの例です。

1. フィールドの内容すべてをコピーします。

1. アクティビティの「**[!UICONTROL 目標および設定]****[!UICONTROL 」画面の「]**&#x200B;レポート設定&#x200B;**[!UICONTROL 」セクションで、「トラッキングサーバー]**」フィールドにトラッキングサーバーの情報を貼り付けます。

   >[!NOTE]
   >
   >[!UICONTROL トラッキングサーバー]フィールドを使用できるようにするには、アクティビティのレポートソース]として「Analytics」を選択する必要があります。[!UICONTROL 

