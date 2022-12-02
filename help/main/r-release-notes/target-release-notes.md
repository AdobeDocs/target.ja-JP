---
keywords: リリースノート;リリース;更新;今後のリリース;機能強化;新機能;修正;アップデート;プレリリース
description: SDK、API、JavaScript ライブラリなど、Adobe Target の次回のリリースに含まれている新機能、機能強化および修正について説明します。
title: 次回のリリースではどのような新機能や機能強化が追加されますか？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 8c348f40be8df5018d63c6b6fe75e1f8e804eafc
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 100%

---

# Target リリースノート（プレリリース）

この記事には、プレリリース情報が含まれています。リリース日、機能などの情報は、予告なく変更されることがあります。

**最終更新日：2022年10月19日（PT）**

最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。これらのページの情報は、リリースのタイミングによっては同じになる可能性があります。括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

## [!DNL Target] Standard／Premium 22.10.3（時差リリース 2022年10月25～27日（PT））

このリリースは、以下の時差スケジュールに従って利用できるようになります。

* **10月25日（PT）**：ヨーロッパ、中東、アフリカ（EMEA）地域
* **10月26日（PT）**：アジア太平洋（APAC）地域
* **10月27日（PT）**：アメリカ地域

このリリースには、以下の新機能、拡張機能および修正が含まれています。

| 機能 | 詳細 |
| --- | --- |
| [!UICONTROL 自動配分]および[!UICONTROL 自動ターゲット]<br>用に最適化された A4T 指標（一部のお客様がテストを利用できます。 今後のリリースで、すべてのお客様が利用できるようになります。) | 次の変更点に注意してください。<ul><li>[!UICONTROL Analytics for Target] A4T レポートで、[!UICONTROL 自動配分]および[!UICONTROL 自動ターゲット]アクティビティの非バイナリ指標と最大化指標のサポートを追加</li><li>2023年2月（PT）まで、既存のアクティビティの動作が維持されます。この日以降、既存のアクティビティを新しい動作に強制的に移行するため、アクティビティは廃止されます</li><li>2023年2月20日以降（PT）、[!DNL Target] アクティビティの `averagetimespentonsite`、`bouncerate`および  `entries` 指標のサポートは廃止されます。</li></ul> |

* [!DNL Target] UI にツールチップを追加して、顧客がオーディエンスビルダーをより効率的にナビゲートし、なじみのない機能の使用方法を学習できるようにしました。（TGT-44139）
* サポートされていない指標を使用しているために [!DNL Target] で無効にされたアクティビティを、顧客が編集できないようにする機能を追加しました。UI のメッセージは、顧客にアクティビティを複製してコンバージョン指標を更新するように指示します。

   このリリースでは、[!DNL Target] アクティビティの `averagetimespentonsite`、`bouncerate`、および `entries` 指標は新しいアクティビティに対して非推奨になります。 既存のアクティビティでは、2023年5月までこれらの指標を引き続き使用できます。

* [!DNL Target] UI にツールチップを追加しました。これにより、A4T を使用する[!UICONTROL 自動ターゲット]アクティビティの作成または編集中に、顧客が最適化条件を選択できるようにします。

## その他のリリースノートとバージョンの詳細

| リソース | 詳細 |
|--- |--- |
| [リリースノート：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=ja) | Platform Web SDK の各バージョンの変更点に関する詳細です。 |
| [at.js のバージョンの詳細](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | [!DNL Adobe Target] at. js JavaScript ライブラリの各バージョンの変更点についての詳細です。 |


## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

[!DNL Target] およびその他の [!DNL Adobe Experience Cloud] ソリューションの今後の製品強化に関する事前通知を受信するには、[!DNL Adobe Priority Product Update] に新規登録します。

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
