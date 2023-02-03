---
keywords: リリースノート;リリース;更新;今後のリリース;機能強化;新機能;修正;アップデート;プレリリース
description: SDK、API、JavaScript ライブラリなど、Adobe Target の次回のリリースに含まれている新機能、機能強化および修正について説明します。
title: 次回のリリースではどのような新機能や機能強化が追加されますか？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: da159c10bd5100519b58cf2cb9c3d4ce15c4b2d0
workflow-type: tm+mt
source-wordcount: '594'
ht-degree: 100%

---

# Target リリースノート（プレリリース）

この記事には、プレリリース情報が含まれています。リリース日、機能などの情報は、予告なく変更されることがあります。

**最終更新日：2023年1月26日（PT）**

最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。これらのページの情報は、リリースのタイミングによっては同じになる可能性があります。括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

## [!DNL Target] Standard／Premium 22.13.3（2023年1月25〜26日（PT）） 

このリリースは、以下の時差スケジュールに従って利用できるようになります。

* **1月25日（PT）**：ヨーロッパ、中東、アフリカ（EMEA）地域
* **1月25日（PT）**：アジア太平洋（APAC）地域
* **1月26日（PT）**：アメリカ地域

このリリースには、以下の新機能、拡張機能および修正が含まれています。

| 機能 | 詳細 |
| --- | --- |
| Automated Personalization（AP）での [JSON オファー](/help/main/c-experiences/c-manage-content/create-json-offer.md)のサポート | フォームベースの Experience Composer を使用して、[!UICONTROL Automated Personalization]（AP）アクティビティで JSON オファーのサポートを追加しました。（TGT-41460） |
| [AEM エクスペリエンスフラグメント](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md) | [!DNL Target] に書き出された [!DNL Adobe Experience Manager] フラグメント（AEM XF）タイプ間を区別できる機能を追加しました。「エクスペリエンスフラグメント」オプションの代わりに、[!DNL Target] で「HTML XF」および「JSON XF」によるフィルタリングと検索ができるようになりました。（TGT-44132） |

* 推奨事項を含む [!UICONTROL A/B テスト]および[!UICONTROL エクスペリエンスのターゲット設定] (XT) アクティビティで「500 エラー」が発生する問題を修正しました。この問題は、[!DNL Target] が [!DNL Target] UI や [!DNL Recommendations] バックエンドから使用されていない条件オブジェクトを削除できなかったことが原因です。（TGT-44383）
* [!UICONTROL Automated Personalization]アクティビティの[!UICONTROL オファー レベル]レポートに表示されるオファー名から場所を削除しました。この変更により、レポートが読みやすくなります。 （TGT-44294）
* [!DNL Target] UI の AP および[!UICONTROL 自動ターゲット][!UICONTROL パーソナライゼーションインサイト]と[!UICONTROL 重要な属性]レポートから 45 日間と 90 日間のカレンダーオプションを削除しました。使用パターンおよびパフォーマンス向上のため、これらの日付範囲は非推奨（廃止予定）になりました。現在許可されている範囲（15 日、30 日および 60 日）を反映するように UI を更新しました。（TGT-39357）
* アクティビティがライブになった後、[!UICONTROL 目標と設定]ページで[!UICONTROL 最適化目標と同じ]設定を変更する機能を無効にしました。（TGT-43923）
* [!DNL Target Standard] から [!DNL Target Premium] へのアップグレード時に、[!DNL Target] バックエンドのデフォルトワークプレースで発生する問題を修正しました。（TGT-44081 および TGT-44306）
* 名前にドット文字「.」を含む [!DNL Analytics] レポートスイートを[!DNL Target] UI で使用して、[!DNL Analytics] 分類フィードを作成できるように変更しました。
* サポート対象のすべての SDK（Node.js、Java、.NET、および Python）でオンデバイス決定の使用方法を説明するページを指すように、「オンデバイス決定による実装方法」の[!UICONTROL 実装]ページ（[!UICONTROL 管理]／[!UICONTROL 実装]）のリンクを変更をしました。詳しくは、[Target SDK の開始方法](https://developer.adobe.com/target/implement/server-side/sdk-guides/getting-started/){target=_blank} in the [Adobe Target Developer Guide](https://developer.adobe.com/target/){target=_blank}を参照してください。
* [!DNL Scene7] および [!DNL Target] を使用する際のファイルのアップロードに関する問題を修正しました。
* 内部のユーザビリティ監査の結果を使用して、障害のあるユーザー向けの [!DNL Target] UI のアクセシビリティを強化しました。これらのアクセシビリティの強化には、以前はキーボードからアクセスできなかった機能へのアクセス、代替テキストの機能強化、UI の一部をより使いやすくするためのズーム機能、キーボードフォーカスの改善などが含まれます。   （TGT-42759）
* [!DNL Target] UI 全体でさまざまなローカライゼーションの修正を行いました。

## その他のリリースノートとバージョンの詳細

| リソース | 詳細 |
|--- |--- |
| [リリースノート：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=ja) | Platform Web SDK の各バージョンの変更点に関する詳細です。 |
| [at.js のバージョンの詳細](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | [!DNL Adobe Target] at. js JavaScript ライブラリの各バージョンの変更点についての詳細です。 |


## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

[!DNL Target] およびその他の [!DNL Adobe Experience Cloud] ソリューションの今後の製品強化に関する事前通知を受信するには、[!DNL Adobe Priority Product Update] に新規登録します。

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
