---
keywords: リリースノート;リリース;更新;今後のリリース;機能強化;新機能;修正;アップデート;プレリリース
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の次回のリリースに含まれている新機能、機能強化および修正について説明します。
title: 次回の [!DNL Target] リリースには、どのような新機能や機能強化が含まれていますか？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 8da8daf7da0cfe3e4936cb48b4c594c464708775
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# [!DNL Target]リリースノート（プレリリース）

この記事には、SDK、API、JavaScript ライブラリなど、次回の [!DNL Adobe Target] リリースのプレリリース情報が含まれています。

**最終更新日：2023年9月4日（PT）**

>[!NOTE]
>
>リリース日、機能などの情報は、予告なく変更されることがあります。
>
>最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。これらのページの情報は、リリースのタイミングによって異なる場合があります。括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

## [!DNL Target] Standard/Premium 23.9.1（2023 年 9 月 7 日）

このリリースは、以下の時差スケジュールに従って利用できます。

* **9月6日（PT）**：アメリカ地域
* **9月7日（PT）**：ヨーロッパ、中東、アフリカ（EMEA）地域
* **9月11日（PT）**：アジア太平洋（APAC）地域

このリリースには、以下の機能強化および修正が含まれています。

* レポートデータの不一致が [!DNL Target] UI と [!DNL Adobe Analytics] の UI [!UICONTROL 自動配分] を使用するアクティビティ [!UICONTROL Analytics for Target] (A4T) をレポートソースとして使用する場合。 （TGT-46112）
* タイムアウトエラーを回避するため、Target Delivery API に対するPUT呼び出しのタイムアウトを 15 秒に増やしました。 （TGT-46091）
* レポート名が正しく表示されない問題を修正しました。 [!UICONTROL テーブル表示] そして [!UICONTROL 自動セグメント] および [!UICONTROL 重要な属性] レポート。 （TGT-46040）
* 拡張された [!UICONTROL Visual Experience Composer] (VEC) で Lightning DOM（Web コンポーネント）をサポートします。 （TGT-45422）
* VEC アクションが正しくない順序で適用される問題を修正しました。 場合によっては、VEC が一部の変更を非同期で適用し、要素に追加の変更を適用した後にその要素が表示されるとエラーが発生していました。 [!UICONTROL 挿入] アクション。 （TGT-45983）
* VEC でシングルページアプリケーション (SPA) ページを開き、参照モードに切り替えると、戻る矢印と進む矢印が正しく機能しなかった問題を修正しました。 （TGT-45956）
* シングルページアプリケーション (SPA)Web サイトを閲覧する際に、URL が一貫して更新されない問題を修正しました。 （TGT-45417）

## その他のリリースノートとバージョンの詳細

| リソース | 詳細 |
|--- |--- |
| [リリースノート：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=ja) | Platform Web SDK の各バージョンの変更点に関する詳細です。 |
| [at.js のバージョンの詳細](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=ja){target=_blank} | [!DNL Adobe Target] at. js JavaScript ライブラリの各バージョンの変更点についての詳細です。 |

## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

[!DNL Target] およびその他の [!DNL Adobe Experience Cloud] ソリューションの今後の製品強化に関する事前通知を受信するには、[!DNL Adobe Priority Product Update] に新規登録します。

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
