---
description: このトピックには、分類と、Analytics を Target のレポートソースとして使用すること（A4T）に関するよくある質問に対する回答が含まれています。
keywords: FAQ;よくある質問;analytics for target;A4T;分類;分類;分類インポーター; post-tnt-action
seo-description: このトピックには、分類と、Analytics を Target のレポートソースとして使用すること（A4T）に関するよくある質問に対する回答が含まれています。
seo-title: 分類 - A4T FAQ
solution: 'Target '
title: 分類 - A4T FAQ
topic: Standard
uuid: 4b42adbc-4fa8-4b62-86c8-bb8f8bec7e54
translation-type: tm+mt
source-git-commit: 74a6f402bc0c9dae6f89cbdb632d7dbc53743593

---


# 分類 - A4T FAQ{#classifications-a-t-faq}

このトピックには、分類と、Analytics を Target のレポートソースとして使用すること（A4T）に関するよくある質問に対する回答が含まれています。

## 分類インポーターを使用して分類をダウンロードした後、post-tnt-action 値をアクティビティ名と合致させるには、どうしたらよいですか。{#section_6045DAC488B248418F430E663C38D001}

管理ツールの[分類インポーター](https://marketing.adobe.com/resources/help/en_US/reference/c_working_with_saint.html)から A4T／TNT 文字列用の分類をダウンロードできます。値は、書き出しリストの「TNT」と呼ばれます。ダウンロードしたデータには、アクティビティ、エクスペリエンスなどのわかりやすい名前が含まれています。

このルックアップファイルは、アドビのクリックストリームデータフィードを受信する顧客にとって便利です。ファイルは、`post_tnt` および `post_tnt_action` 列のわかりやすい名前を提供します。

TNT 変数の文字列形式は、`activityID:experienceID:targettype|event` です。

* targettype は、A4T の場合、常に 0 になります。
* event = 0 は、エクスペリエンスの開始を表します。
* event = 1 は、エクスペリエンスの訪問を表します。
* event = 2 は、アクティビティのインプレッションを表します。
* event = 32767 は、アクティビティのコンバージョンを表します。

[ブラウザーエクスポート](https://marketing.adobe.com/resources/help/en_US/reference/browser_export.html)または [FTP エクスポート](https://marketing.adobe.com/resources/help/en_US/reference/ftp_export.html)を使用して、UI から分類ファイルを何度もダウンロードできます。また、エンジニアリングサービスと連携して、クリックストリームデータフィードと同時にルックアップテーブルとしてファイルを取得できます。
