---
keywords: リリースノート;リリース;更新;今後のリリース;機能強化;新機能;修正;アップデート;プレリリース
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の次回のリリースに含まれている新機能、機能強化および修正について説明します。
title: 次回の [!DNL Target] リリースには、どのような新機能や機能強化が含まれていますか？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: dbf9a51044f317d02a705f2331d6dc58b6549606
workflow-type: tm+mt
source-wordcount: '784'
ht-degree: 81%

---

# [!DNL Target]リリースノート（プレリリース）

この記事には、SDK、API、JavaScript ライブラリなど、次回の [!DNL Adobe Target] リリースのプレリリース情報が含まれています。

**最終更新日：2023年10月3日（PT）**

>[!NOTE]
>
>リリース日、機能などの情報は、予告なく変更されることがあります。
>
>最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。これらのページの情報は、リリースのタイミングによって異なる場合があります。括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

## [!DNL Target] Standard/Premium 23.9.4（2023 年 10 月 4 日～6 日）

このリリースは、以下の時差スケジュールに従って利用できます。

* **10月4日（PT）**：アジア太平洋（APAC）地域
* **10月5日（PT）**：ヨーロッパ、中東、アフリカ（EMEA）地域
* **10月6日（PT）**：アメリカ地域

このリリースには、以下の機能強化および修正が含まれています。

| 機能 | 詳細 |
| --- | --- |
| [!UICONTROL アクティビティ] UI の更新<P>および<P>[!UICONTROL フィード] UI の更新 | の一部として [!DNL Adobe Target] のユーザーエクスペリエンスを改善するためのチームの継続的な取り組み [!DNL Target] ユーザー、このリリースでは [!UICONTROL アクティビティ] および [!DNL Recommendations] [!UICONTROL フィード] ページ ( [!DNL Target] UI この更新により、新しい機能強化を追加しながら、以前は一貫性がなかったデザインパターンを統合し、標準化します。<P>詳しくは、 [アクティビティ](/help/main/c-activities/activities.md) および [フィード](/help/main/c-recommendations/c-products/feeds.md). |
| [!DNL Recommendations] 実装パターン | The *at.js を使用したRecommendations実装パターン* 記事は、 [!DNL Adobe Target Recommendations] at.js JavaScript ライブラリを使用する場合の実装を参照してください。<P>詳しくは、 [at.js を使用したRecommendations実装パターンの概要](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/recs-implementation-pattern-atjs.html){target=_blank} （内） *Adobe Target Developer Guide*. |

* 追加済み [!UICONTROL Visual Experience Composer] (VEC) 動的フレームワークの機能強化。 （TGT-44064）
* 選択された日付が `getViewInAnalyticsId` リクエストが正しく更新されませんでした。 この修正により、 [!DNL Analytics] 日付範囲と指標レポートの設定が変更された際のレポート内のリンク。 （TGT-46246）

## [!DNL Target] Standard／Premium 23.9.3（2023年9月18日（PT））

このリリースには、以下の機能強化および修正が含まれています。

* Lightning web コンポーネント（Light DOM）をサポートするために [!UICONTROL Visual Experience Composer]（VEC）を強化しました。（TGT-45422）
* VEC アクションが正しくない順序で適用される問題を修正しました。場合によっては、VEC で一部の変更を非同期的に適用し、要素に追加の変更を行うと、[!UICONTROL 挿入]アクションの後にその要素が表示された場合に、エラーが発生することがありました。また、アンカーリンクをクリックすると更新されるようになった VEC の URL の修正も行っています。（TGT-45983）
* VEC の[!UICONTROL オーバーレイ]機能に関する問題を修正しました。これにより、シャドウ DOM の要素をサポートするようになりました。（TGT-45202 および TGT-45262）
* VEC で単一ページアプリケーション（SPA）ページを開いて[!UICONTROL 参照]モードに移行すると、戻る矢印と進む矢印が正しく機能しなくなる問題を修正しました。（TGT-45956）
* 一部の web ページが VEC で読み込めない問題を修正しました。（TGT-45983）

## [!DNL Target] Standard／Premium 23.9.2（2023年9月12日～14日（PT））

このリリースは、以下の時差スケジュールに従って利用できます。

* **9月12日（PT）**：アメリカ地域
* **9月13日（PT）**：アジア太平洋（APAC）地域
* **9月14日（PT）**：ヨーロッパ、中東、アフリカ（EMEA）地域

このリリースには、以下の機能強化および修正が含まれています。

* [!DNL Analytics] API を新しい [!DNL Analytics] API バージョン 2.0 に変更しました。（TGT-45345）
* [!DNL Target] バックエンドでのアクティビティのタイムリーな同期や、プレビューリンクで予期されるエクスペリエンスの提供など、一部のお客様の [!UICONTROL Automated Personalization]（AP）アクティビティに影響していた問題を修正しました。（TGT-46202）

## [!DNL Target] Standard／Premium 23.9.1（2023年9月6日～11日（PT））

このリリースは、以下の時差スケジュールに従って利用できます。

* **9月6日（PT）**：アメリカ地域
* **9月7日（PT）**：ヨーロッパ、中東、アフリカ（EMEA）地域
* **9月11日（PT）**：アジア太平洋（APAC）地域

このリリースには、以下の機能強化および修正が含まれています。

* [!UICONTROL Analytics for Target]（A4T）をレポートソースとして使用する[!UICONTROL 自動配分]アクティビティの [!DNL Target] UI と [!DNL Adobe Analytics] UI でレポートデータが不一致になる問題を修正しました。（TGT-46112）
* タイムアウトエラーを回避するために、Target 配信 API への PUT 呼び出しのタイムアウトを 15 秒に増加しました。（TGT-46091）
* 単一ページアプリケーション（SPA）web サイトを参照する際に URL が一貫して更新されない問題を修正しました。（TGT-45417）

## [!DNL Target] Standard／Premium 23.5.2（日付未定）

このリリースには、以下の機能強化および修正が含まれています。

* [!DNL Adobe Analytics] 指標の最適化条件の選択を有効にしました。
* Sling ジョブを使用した外部オーディエンスの同期を有効にしました。
* 名前にドット記号を含む SC レポートスイートがサポートされない問題を修正しました。
* お客様が組み込みのオーディエンスを削除および編集できる機能を有効にしました。

## [!DNL Target] Standard／Premium 23.5.3（日付未定）

このリリースには、次の機能拡張が含まれています。

| 機能 | 詳細 |
|--- |--- |
| [!UICONTROL Automated Personalization] アクティビティの [!UICONTROL QA モード] | [!UICONTROL プレビューリンク]機能に代わって、[!UICONTROL Automated Personalization] アクティビティで [!DNL Adobe Target] [!UICONTROL QA モード]が使用できるようになりました。<P>詳しくは、[アクティビティ QA](/help/main/c-activities/c-activity-qa/activity-qa.md) を参照してください。 |

## その他のリリースノートとバージョンの詳細

| リソース | 詳細 |
|--- |--- |
| [リリースノート：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=ja) | Platform Web SDK の各バージョンの変更点に関する詳細です。 |
| [at.js のバージョンの詳細](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=ja){target=_blank} | [!DNL Adobe Target] at. js JavaScript ライブラリの各バージョンの変更点についての詳細です。 |

## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

[!DNL Target] およびその他の [!DNL Adobe Experience Cloud] ソリューションの今後の製品強化に関する事前通知を受信するには、[!DNL Adobe Priority Product Update] に新規登録します。

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
