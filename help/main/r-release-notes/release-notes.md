---
keywords: リリースノート;新機能;リリース;アップデート;アップデート;リリース;機能強化;機能強化;修正;バグ修正;アップデート
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の現在のリリースに含まれている新機能、機能強化および修正について説明します。
landing-page-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
short-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
title: 現在のリリースの内容
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: dbf9a51044f317d02a705f2331d6dc58b6549606
workflow-type: tm+mt
source-wordcount: '804'
ht-degree: 99%

---

# [!DNL Target] リリースノート（最新）

これらのリリースノートは、[!DNL Adobe Target Standard] と [!DNL Target Premium] の各リリースの機能、機能強化および修正点について説明します。また、該当する場合は、[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、JavaScript ライブラリ（at.js）およびその他のプラットフォームの変更に関するリリースノートも含まれます。

（括弧内の問題番号は [!DNL Adobe] 内部で使用するためのものです。）

## [!DNL Target] Standard/Premium 23.9.4（2023 年 10 月 4 日～6 日）

このリリースは、以下の時差スケジュールに従って利用できます。

* **10月4日（PT）**：アジア太平洋（APAC）地域
* **10月5日（PT）**：ヨーロッパ、中東、アフリカ（EMEA）地域
* **10月6日（PT）**：アメリカ地域

このリリースには、以下の機能強化および修正が含まれています。

| 機能 | 詳細 |
| --- | --- |
| [!UICONTROL アクティビティ] UI の更新<P>および<P>[!UICONTROL フィード] UI の更新 | [!DNL Target] ユーザーのユーザーエクスペリエンスを向上させるための [!DNL Adobe Target] チームの継続的な取り組みの一環として、このリリースでは [!DNL Target] UI の[!UICONTROL アクティビティ]ページと [!DNL Recommendations] [!UICONTROL フィード]ページを更新しました。この更新では、以前は一貫性がなかったデザインパターンが統合および標準化されたほか、新しい機能強化が追加されています。<P>詳しくは、[アクティビティ](/help/main/c-activities/activities.md)および[フィード](/help/main/c-recommendations/c-products/feeds.md)を参照してください。 |
| [!DNL Recommendations] 実装パターン | *at.js を使用した Recommendations 実装パターン*&#x200B;の記事は、at.js JavaScript ライブラリを使用する場合の [!DNL Adobe Target Recommendations] 実装の理解と作成に役立ちます。<P>詳しくは、*Adobe Target 開発者ガイド*&#x200B;の [at.js を使用した Recommendations 実装パターンの概要](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/recs-implementation-pattern-atjs.html?lang=ja){target=_blank}を参照してください。 |

* 動的フレームワーク用の [!UICONTROL Visual Experience Composer]（VEC）の機能強化を追加しました。（TGT-44064）
* `getViewInAnalyticsId` リクエストで選択された日付が正しく更新されない問題を修正しました。この修正により、日付範囲と指標レポート設定が変更された場合に、レポートで [!DNL Analytics] リンクを再計算できるようになります。（TGT-46246）

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

## その他のリリースノートとバージョンの詳細

| リソース | 詳細 |
|--- |--- |
| [リリースノート：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=ja) | Platform Web SDK の各バージョンの変更点に関する詳細です。 |
| [at.js のバージョンの詳細](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=ja){target=_blank} | [!DNL Adobe Target] at. js JavaScript ライブラリの各バージョンの変更点についての詳細です。 |

## ドキュメントの変更、過去のリリースノートおよび Experience Cloud リリースノート

追加情報については、各リリースのリリースノートに加えて、以下のリソースを参照してください。

| リソース | 詳細 |
|--- |--- |
| [ドキュメントの変更点](/help/main/r-release-notes/doc-change.md) | リリースノートに記載されていない、このガイドの更新点に関する詳細情報を表示します。 |
| [以前のリリースのリリースノート](/help/main/r-release-notes/release-notes-for-previous-releases.md)。 | 以前のリリースの Target Standard および Target Premium の新機能および拡張機能に関する情報を確認できます。 |
| [Adobe Experience Cloud のリリースノート](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja){target=_blank} | Adobe Experience Cloud ソリューションの最新のリリースノートが表示されます。 |

## プレリリース情報 {#section_5D588F0415A2435B851A4D0113ACA3A0}

以下のリソースでは、以下の Target リリースの内容を確認できます。

| リソース | 詳細 |
|--- |--- |
| [アドビ優先製品アップデート](https://www.adobe.com/subscription/priority-product-update.html){target=_blank} | [!DNL Target] およびその他の [!DNL Adobe Experience Cloud] ソリューションに対する今後の製品の機能強化に関する事前通知を受信します。 |
| [Target リリースノート - プレリリース](/help/main/r-release-notes/target-release-notes.md){target=_blank} | プレリリース情報など、当月の Target リリースに関する情報です。 |
