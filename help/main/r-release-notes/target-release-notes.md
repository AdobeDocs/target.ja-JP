---
keywords: リリースノート;リリース;更新;今後のリリース;機能強化;新機能;修正;アップデート;プレリリース
description: SDK、API、JavaScript ライブラリなど、Adobe Target の次回のリリースに含まれている新機能、機能強化および修正について説明します。
title: 次回のリリースではどのような新機能や機能強化が追加されますか？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: c12df34c9c7392a0ea50e8d1dea32147e8b7b165
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 37%

---

# Target リリースノート（プレリリース）

この記事には、プレリリース情報が含まれています。リリース日、機能などの情報は、予告なく変更されることがあります。

**最終更新日：2023年1月12日（PT）**

最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。これらのページの情報は、リリースのタイミングによっては同じになる可能性があります。括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

## [!DNL Target] Standard/Premium 22.13.3（2023 年 1 月 26 日）

このリリースには、以下の新機能、拡張機能および修正が含まれています。

* での JSON オファーのサポートを追加しました。 [!UICONTROL Automated Personalization] (AP) フォームベースの Experience Composer を使用したアクティビティ （TGT-41460）
* 実装済み [QA モード](/help/main/c-activities/c-activity-qa/activity-qa.md) AP アクティビティ用。 （TGT-44341）
* のエクスペリエンス名 [!DNL Recommendations] アクティビティがわかりやすい名前で表示されるようになり、 [!DNL Adobe Analytics] それを [!DNL Target] UI （TGT-41853）
* 「500 エラー」が [!UICONTROL A/B テスト] および [!UICONTROL エクスペリエンスのターゲット設定] (XT) アクティビティにレコメンデーションを含める。 この問題は、 [!DNL Target] から条件オブジェクトを適切に削除できませんでした [!DNL Target] UI および [!DNL Recommendations] 使用されなくなったバックエンド。 （TGT-44383）
* 場所を [!UICONTROL オファーレベル] 報告する [!UICONTROL Automated Personalization] アクティビティ。 この変更により、レポートが読みやすくなります。 （TGT-44294）
* 「[!UICONTROL エクスペリエンスフラグメント]」オプションが [!UICONTROL Visual Experience Composer] (VEC) ワークフロー。 現在は、「[!UICONTROL HTMLXF].&quot; （TGT-44132）
* オファー情報ツールチップに、エクスペリエンスフラグメントオファーメタデータを表示する機能が追加されました。 （TGT-43838）
* 45 日間および 90 日間のカレンダーオプションを AP から削除し、 [!UICONTROL 自動ターゲット] [!UICONTROL パーソナライゼーションインサイト] および [!UICONTROL 重要な属性] レポート [!DNL Target] UI 使用パターンおよびパフォーマンスを向上させるために、これらの日付範囲は非推奨（廃止予定）となりました。 UI が更新され、現在許可されている範囲が反映されました。15 日、30 日、60 日。 （TGT-39357）
* を変更する機能を禁止 [!UICONTROL 最適化目標と同じ] 設定 [!UICONTROL 目標と設定] ページを開きます。 （TGT-43923）
* のデフォルトの職場での問題を修正しました。 [!DNL Target] ～からアップグレードする際のバックエンド [!DNL Target Standard] から [!DNL Target Premium]. （TGT-44081 および TGT-44306）
* リンクを変更しました。 [!UICONTROL 実装] ページ ([!UICONTROL 管理] > [!UICONTROL 実装]) を参照してください。Node.js、Java、.NET および Python 詳しくは、 [Target SDK の概要](https://developer.adobe.com/target/implement/server-side/sdk-guides/getting-started/){target=_blank} in the [Adobe Target Developer Guide](https://developer.adobe.com/target/){target=_blank}.
* を使用する際にファイルのアップロードに関する問題を修正しました [!DNL Scene7] および [!DNL Target].
* アクセシビリティの強化 [!DNL Target] 内部のユーザビリティ監査の結果を使用して、障碍のあるユーザー向けの UI。 これらのアクセシビリティの強化には、以前はキーボードからアクセスできなかった機能へのアクセス、代替テキストの強化、UI の一部をズームして、より使いやすくしたり、キーボードフォーカスを向上したりする機能などが含まれます。   （TGT-42759）
* の [!DNL Target] UI

## その他のリリースノートとバージョンの詳細

| リソース | 詳細 |
|--- |--- |
| [リリースノート：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=ja) | Platform Web SDK の各バージョンの変更点に関する詳細です。 |
| [at.js のバージョンの詳細](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | [!DNL Adobe Target] at. js JavaScript ライブラリの各バージョンの変更点についての詳細です。 |


## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

[!DNL Target] およびその他の [!DNL Adobe Experience Cloud] ソリューションの今後の製品強化に関する事前通知を受信するには、[!DNL Adobe Priority Product Update] に新規登録します。

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
