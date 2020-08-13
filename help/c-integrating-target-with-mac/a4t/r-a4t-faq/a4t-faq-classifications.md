---
keywords: faq;frequently asked questions;analytics for target;a4T;classifications;classification;classifications importer;post-tnt-action
description: このトピックには、分類と、Analytics を Target のレポートソースとして使用すること（A4T）に関するよくある質問に対する回答が含まれています。
title: 分類 - A4T FAQ
feature: a4t troubleshooting
topic: Standard
uuid: 4b42adbc-4fa8-4b62-86c8-bb8f8bec7e54
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 66%

---


# 分類 - A4T FAQ{#classifications-a-t-faq}

This topic contains answers to questions that are frequently asked about classifications and using [!DNL Analytics] as the reporting source for [!DNL Target] (A4T).

## 分類インポーターを使用して分類をダウンロードした後、post-tnt-action 値をアクティビティ名と合致させるには、どうしたらよいですか。{#section_6045DAC488B248418F430E663C38D001}

管理ツールの[分類インポーター](https://docs.adobe.com/content/help/en/analytics/components/classifications/classifications-importer/c-working-with-saint.html)から A4T／TNT 文字列用の分類をダウンロードできます。値は、書き出しリストの「TNT」と呼ばれます。ダウンロードしたデータには、アクティビティ、エクスペリエンスなどのわかりやすい名前が含まれています。

このルックアップファイルは、アドビのクリックストリームデータフィードを受信する顧客にとって便利です。ファイルは、`post_tnt` および `post_tnt_action` 列のわかりやすい名前を提供します。

TNT 変数の文字列形式は、`activityID:experienceID:targettype|event` です。

* targettype = 0（制御/ランダム）または1（ターゲット）( [!UICONTROL 自動配分] / [!UICONTROL 自動ターゲット] アクティビティの場合)
* event = 0 は、エクスペリエンスの開始を表します。
* event = 1 は、エクスペリエンスの訪問を表します。
* event = 2 は、アクティビティのインプレッションを表します。
* event = 32767 は、アクティビティのコンバージョンを表します。

You can import the classification file on a frequent basis from the UI using a [browser import](https://docs.adobe.com/help/en/analytics/components/classifications/classifications-importer/browser-import.html) or an [FTP import](https://docs.adobe.com/help/en/analytics/components/classifications/classifications-importer/import-file.html). また、エンジニアリングサービスと連携して、クリックストリームデータフィードと同時にルックアップテーブルとしてファイルを取得できます。
