---
keywords: faq;frequently asked questions;analytics for target;a4T;classifications;classification;classifications importer;post-tnt-action
description: このトピックには、分類と、Analytics を Target のレポートソースとして使用すること（A4T）に関するよくある質問に対する回答が含まれています。
title: 分類 - A4T FAQ
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: cf47b7f3625bb1c3430b9fba00c573f489efc448
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 65%

---


# 分類 - A4T FAQ{#classifications-a-t-faq}

このトピックでは、分類に関してよくある質問と、[!DNL Analytics]を[!DNL Target]のレポートソースとして使用する(A4T)質問に対する回答を記載します。

## 分類インポーターを使用して分類をダウンロードした後、post-tnt-action 値をアクティビティ名と合致させるには、どうしたらよいですか。{#section_6045DAC488B248418F430E663C38D001}

管理ツールの[分類インポーター](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/c-working-with-saint.html)から A4T／TNT 文字列用の分類をダウンロードできます。値は、書き出しリストの「TNT」と呼ばれます。ダウンロードしたデータには、アクティビティ、エクスペリエンスなどのわかりやすい名前が含まれています。

このルックアップファイルは、アドビのクリックストリームデータフィードを受信する顧客にとって便利です。ファイルは、`post_tnt` および `post_tnt_action` 列のわかりやすい名前を提供します。

TNT 変数の文字列形式は、`activityID:experienceID:targettype|event` です。

* targettype = 0 (control/random)または1 (targeted) for [!UICONTROL 自動配分]と[!UICONTROL 自動ターゲット]のアクティビティ。
* event = 0 は、エクスペリエンスの開始を表します。
* event = 1 は、エクスペリエンスの訪問を表します。
* event = 2 は、アクティビティのインプレッションを表します。
* イベント= 3-32766は、Analytics成功指標IDを表します。
* event = 32767 は、アクティビティのコンバージョンを表します。

[ブラウザーインポート](https://docs.adobe.com/help/en/analytics/components/classifications/classifications-importer/browser-import.html)または[FTPインポート](https://docs.adobe.com/help/en/analytics/components/classifications/classifications-importer/import-file.html)を使用して、UIから分類ファイルを頻繁にインポートできます。 また、エンジニアリングサービスと連携して、クリックストリームデータフィードと同時にルックアップテーブルとしてファイルを取得できます。
