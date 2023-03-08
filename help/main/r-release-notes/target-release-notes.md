---
keywords: リリースノート;リリース;更新;今後のリリース;機能強化;新機能;修正;アップデート;プレリリース
description: SDK、API、JavaScript ライブラリなど、Adobe Target の次回のリリースに含まれている新機能、機能強化および修正について説明します。
title: 次回の  [!DNL Target]  リリースには、どのような新機能や機能強化が含まれますか？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: e458793e4d0110d97f3f5124cbe6e54520d3f0e9
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 57%

---

# Target リリースノート（プレリリース）

この記事には、プレリリース情報が含まれています。リリース日、機能などの情報は、予告なく変更されることがあります。

**最終更新日：2023 年 8 月 4 日**

最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。これらのページの情報は、リリースのタイミングによっては同じになる可能性があります。括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

## [!DNL Target] Standard/Premium 22.15.1（2023 年 3 月 9 日）

このリリースは、以下の時差スケジュールに従って利用できるようになります。

* **3 月 9 日**:アメリカ地域
* **3 月 9 日**:ヨーロッパ、中東、アフリカ (EMEA) 地域
* **3 月 9 日**:アジア太平洋 (APAC) 地域

このリリースには、次の新機能および機能強化が含まれています。

| 機能 | 詳細 |
| --- | --- |
| 最適化された A4T 指標： [!UICONTROL 自動配分] および [!UICONTROL 自動ターゲット] | [!DNL Target] を使用すると、バイナリイベントに基づいて指標を選択したり、 [!UICONTROL A4T] 対象 [!UICONTROL 自動配分] および [!UICONTROL 自動ターゲット] アクティビティ。<P>サポートされる指標には、次の変更点があることに注意してください。<ul><li>[!DNL Target] は、（日付が決定される）まで、既存のアクティビティの以前の動作を保持していました。 この日以降、サポートされていない指標を使用するアクティビティは、既存のアクティビティを新しい動作に強制的に移行するために、終了します。</li></ul>詳しくは、 [サポートされる目標指標](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md#supported) in *自動配分と自動ターゲットアクティビティに対する A4T のサポート*. |
| [!UICONTROL 自動配分] using [!UICONTROL Analytics for Target] (A4T) | 新しいチュートリアル：<ul><li>[での A4T レポートの設定 [!DNL Analysis Workspace] 対象 [!UICONTROL 自動配分] アクティビティ](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html){target=_blank}</li></ul> |
| [!UICONTROL 自動ターゲット] using [!UICONTROL Analytics for Target] (A4T) | 新しいチュートリアル：<ul><li>[での A4T レポートの設定 [!DNL Analysis Workspace] 対象 [!UICONTROL 自動ターゲット] アクティビティ](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html?lang=ja){target=_blank}</li></ul> |

## at.js バージョン 2.10.2（2023 年 3 月 7日）

* 次の問題を修正しました： `trackEvent` 関数を使用して、常にエラーを返します。

すべての at.js リリースについて詳しくは、[at.js のバージョンの詳細](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} in the [Adobe Target Developer Guide](https://developer.adobe.com/target/){target=_blank}を参照してください。

## その他のリリースノートとバージョンの詳細

| リソース | 詳細 |
|--- |--- |
| [リリースノート：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=ja) | Platform Web SDK の各バージョンの変更点に関する詳細です。 |
| [at.js のバージョンの詳細](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | [!DNL Adobe Target] at. js JavaScript ライブラリの各バージョンの変更点についての詳細です。 |


## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

[!DNL Target] およびその他の [!DNL Adobe Experience Cloud] ソリューションの今後の製品強化に関する事前通知を受信するには、[!DNL Adobe Priority Product Update] に新規登録します。

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
