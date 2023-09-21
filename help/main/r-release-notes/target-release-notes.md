---
keywords: リリースノート;リリース;更新;今後のリリース;機能強化;新機能;修正;アップデート;プレリリース
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の次回のリリースに含まれている新機能、機能強化および修正について説明します。
title: 次回の [!DNL Target] リリースには、どのような新機能や機能強化が含まれていますか？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 11b5915d75b72a3891572d841de0a353f68dcbf3
workflow-type: tm+mt
source-wordcount: '603'
ht-degree: 72%

---

# [!DNL Target]リリースノート（プレリリース）

この記事には、SDK、API、JavaScript ライブラリなど、次回の [!DNL Adobe Target] リリースのプレリリース情報が含まれています。

**最終更新日：2023年9月18日（PT）**

>[!NOTE]
>
>リリース日、機能などの情報は、予告なく変更されることがあります。
>
>最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。これらのページの情報は、リリースのタイミングによって異なる場合があります。括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

## [!DNL Target] Standard/Premium 23.9.3（2023 年 9 月 19 日）

このリリースには、以下の機能強化および修正が含まれています。

* 拡張された [!UICONTROL Visual Experience Composer] (VEC) で Lightning Web コンポーネント (Light DOM) をサポートします。 （TGT-45422）
* VEC アクションが正しくない順序で適用される問題を修正しました。 場合によっては、VEC が一部の変更を非同期で適用し、要素に追加の変更を適用した後にその要素が表示されるとエラーが発生していました。 [!UICONTROL 挿入] アクション。 また、VEC の URL が修正され、アンカーのリンクをクリックすると更新されるようになりました。 （TGT-45983）
* VEC の問題を修正しました [!UICONTROL オーバーレイ] 機能を使用して、シャドウ DOM で要素をサポートするようになりました。 （TGT-45202 および TGT-45262）
* VEC でシングルページアプリケーション (SPA) ページを開き、 [!UICONTROL 参照] モードで戻る矢印と進む矢印が正しく機能しない問題を修正しました。 （TGT-45956）
* VEC で一部の Web ページを読み込めなかった問題を修正しました。 （TGT-45983）

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

* 以下に対して最適化条件の選択を有効にしました： [!DNL Adobe Analytics] 指標。
* Sling ジョブを使用した外部オーディエンスの同期を有効にしました。
* 名前にドット文字を含む SC レポートスイートがサポートされない問題を修正しました。
* 顧客が組み込みのオーディエンスを削除および編集できる機能を有効にしました。

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
