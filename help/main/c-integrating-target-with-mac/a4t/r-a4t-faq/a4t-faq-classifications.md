---
keywords: faq；よくある質問；analytics for target;a4T；分類；分類；分類インポーター；tnt アクション後；イベントコード
description: 分類と [!UICONTROL Analytics for Target] （A4T）の使用に関する質問への回答を示します。
title: A4T での分類に関する情報はどこで入手できますか？
feature: Analytics for Target (A4T)
exl-id: 875f6c1c-1bda-40a9-96f2-d58c00d91d20
source-git-commit: aff96eca1380f4274dba0c1567f6e41d42f4b5ab
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 24%

---

# 分類 - A4T FAQ

このトピックには、分類と、[!DNL Analytics] を [!DNL Target] （A4T）のレポートソースとして使用する方法に関するよくある質問に対する回答が含まれています。

## [!UICONTROL Classifications Importer] を使用して分類をダウンロードした後、tnt-action 後の値をアクティビティ名と照合するにはどうすればよいですか？ {#section_6045DAC488B248418F430E663C38D001}

+++回答
A4T/TNT 文字列の分類は、管理ツール [ 分類インポーター ](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/c-working-with-saint.html) からダウンロードできます。 エクスポートリストでは、変数は「TNT」と呼ばれます。 ダウンロードしたデータには、アクティビティ、エクスペリエンスなどのわかりやすい名前が含まれています。

このルックアップファイルは、[!DNL Adobe] のクリックストリームデータフィードを受け取るお客様に役立ちます。 ファイルは、`post_tnt` および `post_tnt_action` 列のわかりやすい名前を提供します。

標準の [!UICONTROL A/B Test] および [!UICONTROL Experience Targeting] （XT）アクティビティの場合、TNT 文字列の形式は次のようになります。

```
activityID:experienceID:targettype|event
```

[!UICONTROL Auto-Allocate] および [!UICONTROL Auto-Target] アクティビティの場合、TNT 文字列の形式は次のようになります。

```
activityId:experienceId:targettype:algorithmId|event
```

* `targettype` = `targettype` および `algorithmId` は、[!UICONTROL Auto-Allocate] および [!UICONTROL Auto-Target] アクティビティで使用される内部識別子です。
* event = 0 は、エクスペリエンスの開始を表します。
* event = 1 は、エクスペリエンスの訪問を表します。
* event = 2 は、アクティビティのインプレッションを表します。
* Event = 3-32766 は、Analytics 成功指標 ID を表します。
* event = 32767 は、アクティビティのコンバージョンを表します。
* イベント -1 または 65535 は、ユーザーがアクティビティまたはエクスペリエンスから削除されたことを表します。 この状況は、訪問者がコンバージョンするときによく発生します。 訪問者はエクスペリエンスからリリースされ、他のエクスペリエンスの対象として使用できるようになりました。

[ ブラウザーインポート ](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/browser-import.html?lang=en) または [FTP インポート ](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/import-file.html?lang=en) を使用して、UI から分類ファイルを頻繁にインポートできます。 また、エンジニアリングサービスと連携して、クリックストリームデータフィードと同時にルックアップテーブルとしてファイルを取得できます。

+++
