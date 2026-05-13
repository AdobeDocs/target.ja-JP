---
keywords: faq；よくある質問；targetの分析；a4T；分類；分類インポーター；tnt後アクション；イベントコード
description: 分類と[!UICONTROL Analytics for Target] （A4T）の使用に関する質問に対する回答を検索します。
title: A4Tでの分類に関する情報はどこで入手できますか？
feature: Analytics for Target (A4T)
exl-id: 875f6c1c-1bda-40a9-96f2-d58c00d91d20
TQID: https://experienceleague.adobe.com/-BIklVbPaO9QGmnjN0eQdbLFXGA7c2sR-3s6OUli8BM
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 318
ht-degree: 27%

---

# 分類 - A4T FAQ

このトピックには、分類に関してよく寄せられる質問に対する回答と、[!DNL Analytics]を[!DNL Target] （A4T）のレポートソースとして使用する回答が含まれています。

## [!UICONTROL Classifications Importer]を使用して分類をダウンロードした後、tnt アクション後の値をアクティビティ名と一致させるにはどうすればよいですか？ {#section_6045DAC488B248418F430E663C38D001}

+++回答
管理ツールの[分類インポーター](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/c-working-with-saint.html)から A4T／TNT 文字列用の分類をダウンロードできます。 この変数は、書き出しリストで「TNT」と呼ばれます。 ダウンロードしたデータには、アクティビティ、エクスペリエンスなどのわかりやすい名前が含まれています。

このルックアップファイルは、[!DNL Adobe]のクリックストリームデータフィードを受け取るお客様に役立ちます。 ファイルは、`post_tnt` および `post_tnt_action` 列のわかりやすい名前を提供します。

標準の[!UICONTROL A/B Test]および[!UICONTROL Experience Targeting] （XT）アクティビティの場合、TNT文字列の形式は次のとおりです。

```
activityID:experienceID:targettype|event
```

[!UICONTROL Auto-Allocate]および[!UICONTROL Auto-Target]のアクティビティの場合、TNT文字列の形式は次のとおりです。

```
activityId:experienceId:targettype:algorithmId|event
```

* `targettype` = `targettype`および`algorithmId`は、[!UICONTROL Auto-Allocate]および[!UICONTROL Auto-Target]のアクティビティで使用される内部識別子です。
* event = 0 は、エクスペリエンスの開始を表します。
* event = 1 は、エクスペリエンスの訪問を表します。
* event = 2 は、アクティビティのインプレッションを表します。
* イベント = 3-32766は、分析成功指標IDを表します。
* event = 32767 は、アクティビティのコンバージョンを表します。
* イベント -1または65535は、ユーザーがアクティビティまたはエクスペリエンスから削除されたことを表します。 この状況は、訪問者がコンバージョンしたときに頻繁に発生します。 訪問者はエクスペリエンスから解放され、他のエクスペリエンスの資格を得られるようになりました。

分類ファイルは、[ ブラウザー読み込み](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/browser-import.html?lang=en)または[FTP読み込み](https://experienceleague.adobe.com/docs/analytics/components/classifications/classifications-importer/import-file.html?lang=en)を使用して、UIから頻繁に読み込むことができます。 また、エンジニアリングサービスと連携して、クリックストリームデータフィードと同時にルックアップテーブルとしてファイルを取得できます。

+++
