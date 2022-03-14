---
keywords: FAQ；よくある質問；analytics for target;A4T；分類；分類；分類インポーター；post-tnt-action；イベントコード
description: 分類と使用に関する質問に対する回答を見つけます。 [!UICONTROL Analytics for Target] (A4T)。
title: A4T を使用した分類に関する情報はどこで確認できますか？
feature: Analytics for Target (A4T)
exl-id: 875f6c1c-1bda-40a9-96f2-d58c00d91d20
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 29%

---

# 分類 - A4T FAQ

このトピックには、分類と [!DNL Analytics] レポートソースとして [!DNL Target] (A4T)。

## 使用後 [!UICONTROL 分類インポーター] 分類をダウンロードするには、post-tnt-action 値をアクティビティ名と照合する方法を教えてください。 {#section_6045DAC488B248418F430E663C38D001}

管理ツールの[分類インポーター](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/c-working-with-saint.html)から A4T／TNT 文字列用の分類をダウンロードできます。値は、書き出しリストの「TNT」と呼ばれます。ダウンロードしたデータには、アクティビティ、エクスペリエンスなどのわかりやすい名前が含まれています。

この参照ファイルは、 [!DNL Adobe]のクリックストリームデータフィード。 ファイルは、`post_tnt` および `post_tnt_action` 列のわかりやすい名前を提供します。

標準の場合 [!UICONTROL A/B テスト] および [!UICONTROL エクスペリエンスのターゲット設定] (XT) アクティビティの場合、TNT 文字列の形式は次のとおりです。

```
activityID:experienceID:targettype|event
```

の場合 [!UICONTROL 自動配分] および [!UICONTROL 自動ターゲット] アクティビティの場合、TNT 文字列の形式は次のとおりです。

```
activityId:experienceId:targettype:algorithmId|event
```

* `targettype` = `targettype` および `algorithmId` は、が使用する内部識別子です [!UICONTROL 自動配分] および [!UICONTROL 自動ターゲット] アクティビティ。
* event = 0 は、エクスペリエンスの開始を表します。
* event = 1 は、エクスペリエンスの訪問を表します。
* event = 2 は、アクティビティのインプレッションを表します。
* Event = 3-32766は、Analytics の成功指標 ID を表します。
* event = 32767 は、アクティビティのコンバージョンを表します。
* Event -1 または65535は、ユーザーがアクティビティまたはエクスペリエンスから削除されたことを表します。 この状況は、多くの場合、訪問者がコンバージョンしたときに発生します。 訪問者はエクスペリエンスからリリースされ、他のエクスペリエンスの資格を得ることができるようになりました。

UI から分類ファイルを頻繁にインポートするには、 [ブラウザーインポート](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/browser-import.html?lang=en) または [FTP インポート](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/import-file.html?lang=en). また、エンジニアリングサービスと連携して、クリックストリームデータフィードと同時にルックアップテーブルとしてファイルを取得できます。
