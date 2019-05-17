---
description: 古いバージョンの at.js または mbox.js を使用している場合は、Analytics for Target（A4T）を使用するアクティビティ用に Analytics トラッキングサーバーを指定する必要があります。
keywords: analytics トラッキングサーバー;A4T;Adobe Experience Cloud デバッガー;レポートソース
seo-description: 古いバージョンの at.js または mbox.js を使用している場合は、Analytics for Target（A4T）を使用するアクティビティ用に Analytics トラッキングサーバーを指定する必要があります。
seo-title: Analytics トラッキングサーバーの使用
title: Analytics トラッキングサーバーの使用
uuid: ad700b90-f409-496a-bc26-0f0367410a85
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Analytics トラッキングサーバーの使用{#use-an-analytics-tracking-server}

古いバージョンの at.js または mbox.js を使用している場合は、Analytics for Target（A4T）を使用するアクティビティ用に Analytics トラッキングサーバーを指定する必要があります。

>[!NOTE]
>
>Adobe Analytics をアクティビティのレポートソースとして使用する場合、 mbox.js バージョン 61 （またはそれ以降）または at.js バージョン 0.9.1 （またはそれ以降）を使用しているのであれば、アクティビティを作成する際にトラッキングサーバーを指定する必要はありません。mbox.js または at.js ライブラリは、トラッキングサーバーの値を自動的に [!DNL Target] へ送信します。アクティビティの作成時には、[!UICONTROL 目標および設定]ページの「[!UICONTROL トラッキングサーバー]」フィールドを空白にできます。

Target のデータが Analytics の適切な場所に送信されるようにするため、A4T ではすべての呼び出しで Modstats から Target に Analytics トラッキングサーバーを送信する必要があります。複数のトラッキングサーバーを使用した実装では、Adobe Experience Cloud デバッガーを使用して、アクティビティに適したトラッキングサーバーを判断します。

アクティビティが提供されるページでデバッガーを表示して、適切なトラッキングサーバーが選択されていることを確認します。アカウントごとにデフォルトのトラッキングサーバーを指定することもできます。デフォルトを指定または変更するには、カスタマーケアにお問い合わせください。

1. アクティビティを作成しているページから、Adobe Experience Cloud デバッガーを起動します。

   デバッガーがまだインストールされていない場合は、[Adobe デバッガーのインストール手順](https://marketing.adobe.com/resources/help/en_US/sc/implement/debugger_install.html)を参照してください。

   ![](assets/Screen_DebuggerTrackServ.png)

   Analytics トラッキングサーバーは、デバッガーの SiteCatalyst Image セクションに表示されます。実装環境に応じて、このフィールドは*ファーストパーティの Cookie* または*サードパーティの Cookie* と呼ばれます。Analytics トラッキングサーバーの値は次のいずれかの形式になります。

   * （CNAME 実装の場合）
   * （RDC 以外の実装の場合）
   * （RDC 実装の場合）
   *Company* は、Analytics 企業名を指し、*metrics* は CNAME 値の例、*d1* は Analytics データセンターの例を指します。
1. フィールドの内容すべてをコピーします。
1. アクティビティの「[!UICONTROL 目標および設定][!UICONTROL 」画面の「]レポート設定**」セクションで、「[!UICONTROL トラッキングサーバー]**」フィールドにトラッキングサーバーの情報を貼り付けます。

   >[!NOTE]
   >
   >「トラッキングサーバー」フィールドを利用できるようにするには、アクティビティのレポートソースとして Adobe Analytics を選択する必要があります。

