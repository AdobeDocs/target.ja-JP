---
keywords: FAQ；よくある質問；analytics for target;A4T；分類；分類インポーター；post-tnt-action；イベントコード
description: 分類と[!UICONTROL Analytics for Target](A4T)の使用に関する質問に対する回答を見つけます。
title: A4Tを使用した分類に関する情報はどこで確認できますか？
feature: Analytics for Target (A4T)
exl-id: 875f6c1c-1bda-40a9-96f2-d58c00d91d20
source-git-commit: e81a27bc321fa83cc1b2449e5df32edfa37d5198
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 29%

---

# 分類 - A4T FAQ

このトピックには、分類と、[!DNL Target]のレポートソースとして[!DNL Analytics]を使用する(A4T)ことに関するよくある質問に対する回答が含まれています。

## [!UICONTROL 分類インポーター]を使用して分類をダウンロードした後、post-tnt-action値をアクティビティ名と照合するには、どうすればよいですか。 {#section_6045DAC488B248418F430E663C38D001}

管理ツールの[分類インポーター](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/c-working-with-saint.html)から A4T／TNT 文字列用の分類をダウンロードできます。値は、書き出しリストの「TNT」と呼ばれます。ダウンロードしたデータには、アクティビティ、エクスペリエンスなどのわかりやすい名前が含まれています。

このルックアップファイルは、[!DNL Adobe]のクリックストリームデータフィードを受け取るお客様に役立ちます。 ファイルは、`post_tnt` および `post_tnt_action` 列のわかりやすい名前を提供します。

標準の[!UICONTROL A/Bテスト]および[!UICONTROL エクスペリエンスのターゲット設定](XT)アクティビティの場合、TNT文字列の形式は次のようになります。

```
activityID:experienceID:targettype|event
```

[!UICONTROL 自動配分]および[!UICONTROL 自動ターゲット]アクティビティの場合、TNT文字列の形式は次のようになります。

```
activityId:experienceId:targettype:algorithmId|event
```

* `targettype` =および `targettype` は、自動配 `algorithmId` 分および自動ターゲットアクティビティで [!UICONTROL 使用さ] れる内 [!UICONTROL 部識] 別子です。
* event = 0 は、エクスペリエンスの開始を表します。
* event = 1 は、エクスペリエンスの訪問を表します。
* event = 2 は、アクティビティのインプレッションを表します。
* event = 3-32766は、Analyticsの成功指標IDを表します。
* event = 32767 は、アクティビティのコンバージョンを表します。
* イベント —1または65535は、ユーザーがアクティビティまたはエクスペリエンスから削除されたことを表します。 この状況は、多くの場合、訪問者がコンバージョンする際に発生します。 訪問者はエクスペリエンスからリリースされ、他のエクスペリエンスの資格を得られるようになりました。

[ブラウザーインポート](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/browser-import.html?lang=en)または[FTPインポート](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/import-file.html?lang=en)を使用して、UIから分類ファイルを頻繁にインポートできます。 また、エンジニアリングサービスと連携して、クリックストリームデータフィードと同時にルックアップテーブルとしてファイルを取得できます。
