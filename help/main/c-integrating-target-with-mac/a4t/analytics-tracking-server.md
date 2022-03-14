---
keywords: analytics トラッキングサーバー；A4T;Adobe Experience Cloudデバッガー；Adobe Experience Platformデバッガー；レポートソース；開発者ツール
description: 'Analytics を使用するアクティビティ用に Analytics トラッキングサーバーを指定する方法を説明します。 [!DNL Target] (A4T) を使用します。 '
title: Analytics トラッキングサーバーの使用方法を教えてください。
feature: Analytics for Target (A4T)
exl-id: 8066d6a6-661e-428b-9d5c-18537a80fb43
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 19%

---

# Analytics トラッキングサーバーの使用

古いバージョンの at.js を使用している場合、 [!DNL Adobe Analytics] 対象 [!DNL Adobe Target] (A4T)。

>[!NOTE]
>
>at.js バージョン 0.9.1 以降を使用している場合は、アクティビティの作成中にトラッキングサーバーを指定する必要はありません。 at.js ライブラリは、トラッキングサーバーの値をに自動的に送信します。 [!DNL Target]. アクティビティの作成時には、[!UICONTROL 目標および設定]ページの「[!UICONTROL トラッキングサーバー]」フィールドを空白にできます。
>
>この [!DNL Target] チームは at.js 1.*x* と at.js 2.*x* 間のマッピングについて説明します。at.js のメジャーバージョンのいずれかの最新の更新にアップグレードして、サポート対象のバージョンを実行していることを確認してください。 詳しくは、[at.js のバージョンの詳細](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)を参照してください。

からのデータを確実に取得するには、以下を実行します。 [!DNL Target] は、 [!DNL Analytics]A4T では、Modstats へのすべての呼び出しで Analytics トラッキングサーバーを送信する必要があります。 [!DNL Target]. 複数のトラッキングサーバーを使用する実装の場合、 [!DNL Adobe Experience Platform Debugger] またはブラウザーの開発者ツールを使用して、アクティビティに適したトラッキングサーバーを判断します。

## Adobe Experience Platform Debugger を使用した Analytics トラッキングサーバーの取得

デバッガーは、正しいトラッキングサーバーが選択されていることを確認するために、アクティビティが配信されるページ上で表示される必要があります。 アカウントごとにデフォルトのトラッキングサーバーを指定することもできます。デフォルトを指定または変更するには、カスタマーケアにお問い合わせください。

1. アクティビティを作成しているページから、 [!DNL Adobe Experience Platform Debugger].

   デバッガーをまだインストールしていない場合は、 [Adobe Experience Platform Debugger の概要](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/web-sdk/introduction-to-the-experience-platform-debugger.html).

   ![](assets/Screen_DebuggerTrackServ.png)

1. クリック **[!UICONTROL Analytics]** をクリックします。

   Analytics トラッキングサーバーは、 [!UICONTROL ホスト名] デバッガーの「 」セクションに表示されます。

   * **ファーストパーティトラッキングサーバー**:リクエストのホスト名が現在のドメインと一致する場合、それはファーストパーティのトラッキングサーバーです。 例えば、 `adobe.com`, `adobe.com` はファーストパーティのトラッキングサーバーです。
   * **サードパーティトラッキングサーバー**:通常、サードパーティのトラッキングサーバーは `[company].sc.omtrdc.net` ここで、会社は会社の名前ですが、常に `sc.omtrdc.net`.
   * **CNAME 実装**: `sstats.adobe.com` は、https（セキュリティで保護された）リクエストに対する CNAME ファーストパーティトラッキングサーバーの例です。 `stats.adobe.com` は、http（非セキュア）ページに対する CNAME ファーストパーティリクエストの例です。

1. フィールドの内容すべてをコピーします。

1. アクティビティの「**[!UICONTROL 目標および設定]****[!UICONTROL 」画面の「]**&#x200B;レポート設定&#x200B;**[!UICONTROL 」セクションで、「トラッキングサーバー]**」フィールドにトラッキングサーバーの情報を貼り付けます。

   >[!NOTE]
   >
   >選択 [!UICONTROL レポートソースとしての Analytics] アクティビティの [!UICONTROL トラッキングサーバー] フィールドを使用できます。

## ブラウザーの開発者ツールを使用して、Analytics トラッキングサーバーを取得します

正しいトラッキングサーバーが選択されていることを確認するために、開発者ツールは、アクティビティが配信されるページ上に表示される必要があります。 アカウントごとにデフォルトのトラッキングサーバーを指定することもできます。デフォルトを指定または変更するには、カスタマーケアにお問い合わせください。

1. アクティビティを作成しているページで、ブラウザーの開発者ツールを開きます (Google Chrome で、右上隅の縦並びの省略記号/その他のツール/開発者ツールをクリックします )。

   ![Chrome 開発者ツール](/help/main/c-integrating-target-with-mac/a4t/assets/chrome-dev-tools.png)

1. 次をクリック： **[!UICONTROL ネットワーク]** タブをクリックします。

1. フィルター `/ss,` をクリックして、Analytics リクエストを表示します。

   ![/ss 検索を使用する Chrome 開発者ツール](/help/main/c-integrating-target-with-mac/a4t/assets/chrome-search.png)

   トラッキングサーバーは、リクエストのホスト名です。

   * **ファーストパーティトラッキングサーバー**:リクエストのホスト名が現在のドメインと一致する場合、それはファーストパーティのトラッキングサーバーです。 例えば、 `adobe.com`, `adobe.com` はファーストパーティのトラッキングサーバーです。
   * **サードパーティトラッキングサーバー**:通常、サードパーティのトラッキングサーバーは `[company].sc.omtrdc.net` ここで、会社は会社の名前ですが、常に `sc.omtrdc.net`.
   * **CNAME 実装**: `sstats.adobe.com` は、https（セキュリティで保護された）リクエストに対する CNAME ファーストパーティトラッキングサーバーの例です。 `stats.adobe.com` は、http（非セキュア）ページに対する CNAME ファーストパーティリクエストの例です。

1. フィールドの内容すべてをコピーします。

1. アクティビティの「**[!UICONTROL 目標および設定]****[!UICONTROL 」画面の「]**&#x200B;レポート設定&#x200B;**[!UICONTROL 」セクションで、「トラッキングサーバー]**」フィールドにトラッキングサーバーの情報を貼り付けます。

   >[!NOTE]
   >
   >選択 [!UICONTROL レポートソースとしての Analytics] アクティビティの [!UICONTROL トラッキングサーバー] フィールドを使用できます。
