---
keywords: analytics トラッキングサーバー；A4T;Adobe Experience Cloud debugger;Adobe Experience Platform debugger；レポートソース；デベロッパーツール
description: 旧バージョンの at.js を使用している場合に、Analytics for [!DNL Target]  （A4T）を使用するアクティビティ用に Analytics トラッキングサーバーを指定する方法を説明します。
title: Analytics トラッキングサーバーの使用方法
feature: Analytics for Target (A4T)
exl-id: 8066d6a6-661e-428b-9d5c-18537a80fb43
source-git-commit: 2fc704a1779414a370ffd00ef5442fce36e7a5dd
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 15%

---

# [!DNL Analytics] トラッキングサーバーの使用

古いバージョンの at.js を使用している場合は、[!DNL Analytics] for [!DNL Adobe Analytics] （A4T）を使用するアクティビティの [!DNL Adobe Target] トラッキングサーバーを指定する必要があります。

>[!NOTE]
>
>at.js バージョン 0.9.1 （またはそれ以降）を使用している場合は、アクティビティの作成中にトラッキングサーバーを指定する必要はありません。at.js ライブラリは、トラッキングサーバーの値を自動的に [!DNL Target] へ送信します。アクティビティの作成時には、[!UICONTROL Tracking Server] のページの「[!UICONTROL Goals & Settings]」フィールドを空白にできます。
>
>[!DNL Target] チームは、両方の at.js 1.*x* と at.js 2 の両方について示しています。*x* を通じてクロスドメイントラッキングを使用している場合です。サポート対象のバージョンを使用するには、at.js のいずれかのメジャーバージョンの最新アップデートにアップグレードしてください。 詳しくは、[at.js のバージョンの詳細](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=ja){target=_blank}を参照してください。

[!DNL Target] からのデータが [!DNL Analytics] の正しい場所に送信されるようにするために、A4T では、[!DNL Analytics] からの Modstats へのすべての呼び出しで [!DNL Target] トラッキングサーバーを送信する必要があります。 複数のトラッキングサーバーを使用する実装の場合は、[!DNL Adobe Experience Platform Debugger] またはブラウザーの開発者ツールを使用して、アクティビティに適したトラッキングサーバーを決定します。

## [!DNL Analytics] を使用した [!DNL Adobe Experience Platform Debugger] トラッキングサーバーの取得

アクティビティが配信されるページでデバッガーを表示して、正しいトラッキングサーバーを選択していることを確認してください。 アカウントごとにデフォルトのトラッキングサーバーを指定することもできます。デフォルトを指定または変更するには、カスタマーケアへのお問い合わせ。

1. アクティビティを作成するページから [!DNL Adobe Experience Platform Debugger] を開きます。

   デバッガーをまだインストールしていない場合は、[Adobe Experience Platform Debugger overview](https://experienceleague.adobe.com/docs/platform-learn/data-collection/debugger/overview.html?lang=ja) を参照してください。

1. 左側のナビゲーションメニューの「**[!UICONTROL Analytics]**」をクリックします。

   ![Screen_DebuggerTrackServ 画像 &#x200B;](assets/Screen_DebuggerTrackServ.png)

   [!DNL Analytics] トラッキングサーバーは、デバッガーの [!UICONTROL Hostname] セクションにあります。

   * **ファーストパーティトラッキングサーバー**：リクエストのホスト名が使用中のドメインと一致する場合、それはファーストパーティトラッキングサーバーです。 例えば、`adobe.com` を使用している場合、`adobe.com` はファーストパーティトラッキングサーバーです。
   * **サードパーティトラッキングサーバー**：通常、サードパーティトラッキングサーバーは `[company].sc.omtrdc.net` です。会社は会社の名前ですが、常に `sc.omtrdc.net` で終わります。
   * **CNAME 実装**:`sstats.adobe.com` は、https （セキュア）リクエスト用の CNAME ファーストパーティトラッキングサーバーの例です。 `stats.adobe.com` は、http （非セキュア）ページに対する CNAME ファーストパーティリクエストの例です。

1. フィールドの内容すべてをコピーします。

1. アクティビティの **[!UICONTROL Reporting Settings]** 画面の「**[!UICONTROL Goal & Settings]**」セクションで、トラッキングサーバー情報を **[!UICONTROL Tracking Server]** フィールドに貼り付けます。

   >[!NOTE]
   >
   >[!UICONTROL Analytics as the Reporting Source] フィールドを使用できるようにするには、アクティビティの「[!UICONTROL Tracking Server]」を選択します。

## ブラウザーの開発者ツールを使用して [!DNL Analytics] トラッキングサーバーを取得する

正しいトラッキングサーバーを確実に選択するために、アクティビティが配信されるページで開発者ツールを表示する必要があります。 アカウントごとにデフォルトのトラッキングサーバーを指定することもできます。デフォルトを指定または変更するには、カスタマーケアへのお問い合わせ。

1. アクティビティを作成するページから、ブラウザーのデベロッパーツールを開きます（Google Chromeで、右上隅にある 3 つの縦並びの省略記号（その他のツール/デベロッパーツール）をクリックします）。

   ![Chrome デベロッパーツール &#x200B;](/help/main/c-integrating-target-with-mac/a4t/assets/chrome-dev-tools.png)

1. 「**[!UICONTROL Network]**」タブをクリックします。

1. `/ss,` リクエストを表示する [!DNL Analytics] をフィルタリングします。

   ![/ss 検索を使用したChrome デベロッパーツール &#x200B;](/help/main/c-integrating-target-with-mac/a4t/assets/chrome-search.png)

   トラッキングサーバーはリクエストのホスト名です。

   * **ファーストパーティトラッキングサーバー**：リクエストのホスト名が使用中のドメインと一致する場合、それはファーストパーティトラッキングサーバーです。 例えば、`adobe.com` を使用している場合、`adobe.com` はファーストパーティトラッキングサーバーです。
   * **サードパーティトラッキングサーバー**：通常、サードパーティトラッキングサーバーは `[company].sc.omtrdc.net` です。会社は会社の名前ですが、常に `sc.omtrdc.net` で終わります。
   * **CNAME 実装**:`sstats.adobe.com` は、https （セキュア）リクエスト用の CNAME ファーストパーティトラッキングサーバーの例です。 `stats.adobe.com` は、http （非セキュア）ページに対する CNAME ファーストパーティリクエストの例です。

1. フィールドの内容すべてをコピーします。

1. アクティビティの **[!UICONTROL Reporting Settings]** 画面の「**[!UICONTROL Goal & Settings]**」セクションで、トラッキングサーバー情報を **[!UICONTROL Tracking Server]** フィールドに貼り付けます。

   >[!NOTE]
   >
   >[!UICONTROL Analytics as the Reporting Source] フィールドを使用できるようにするには、アクティビティの「[!UICONTROL Tracking Server]」を選択します。
