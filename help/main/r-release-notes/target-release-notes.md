---
keywords: リリースノート;リリース;更新;今後のリリース;機能強化;新機能;修正;アップデート;プレリリース
description: SDK、API、JavaScript ライブラリなど、Adobe Target の次回のリリースに含まれている新機能、機能強化および修正について説明します。
title: 次回のリリースではどのような新機能や機能強化が追加されますか？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 07d71ccf934a1c638c37285372c3ec3199ec2000
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 32%

---

# Target リリースノート（プレリリース）

この記事には、プレリリース情報が含まれています。リリース日、機能などの情報は、予告なく変更されることがあります。

**最終更新日：2022年7月9日（PT）**

最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。これらのページの情報は、リリースのタイミングによっては同じになる可能性があります。括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

## [!DNL Target] Standard/Premium 22.10.1（2022 年 10 月 4 日～ 6 日タッガリリリース）

このリリースは、以下の時差スケジュールに従って利用できるようになります。

* **10 月 4 日**:ヨーロッパ、中東、アフリカ (EMEA) 地域
* **10 月 5 日**:アジア太平洋 (APAC) 地域
* **10 月 6 日**:アメリカ地域

このリリースには、次の新機能、機能強化および修正が含まれています。

| 機能 | 詳細 |
| --- | --- |
| 新規 [!UICONTROL Visual Experience Composer] Google Chrome 用拡張機能 | 新しい [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] Chrome 用 (VEC) 拡張機能は、Chrome Web Store で入手できます。<br>2023 年 1 月から、現在の [!DNL Target] Googleでは Manifest V2 を使用した拡張機能が許可されないので、VEC ヘルパー拡張機能はGoogle Chrome では動作しなくなります。 新しい拡張機能をダウンロードして、で Web サイトの視覚的なオーサリングを続行します。 [!DNL Target] 新年から始まる。 |
| 最適化された A4T 指標： [!UICONTROL 自動配分] および [!UICONTROL 自動ターゲット]<br>（正確なリリース日は決定されます。） | 次の変更点に注意してください。<ul><li>バイナリ指標と最大化指標のサポートを [!UICONTROL Analytics for Target] A4T レポートの対象 [!UICONTROL 自動配分] および [!UICONTROL 自動ターゲット] アクティビティ</li><li>次のバイナリ指標警告メッセージを削除しました： [!UICONTROL 自動ターゲット] アクティビティ</li><li>2023 年 2 月 20 日まで、既存のアクティビティの動作が保持されました。 この日以降、既存のアクティビティを新しい動作に強制的に移行するため、アクティビティは停止されます</li><li>2023 年 2 月 20 日以降、のサポート `averagetimespentonsite`, `bouncerate`、および `entries` 指標 [!DNL Target] アクティビティは非推奨となります。</li></ul> |

* オーディエンスルールの情報が [!UICONTROL Audiences の絞り込み] 情報ウィンドウ。 （TGT-43917）
* のパフォーマンスを向上しました [!DNL Target] UI ( [ターゲット設定ルールの推奨制限](/help/main/r-troubleshooting-target/target-limits.md#targeting-rules). （TGT-43675）
* 一部のコンポーネントが [!UICONTROL 変更] パネル [!UICONTROL エクスペリエンス] ページ (VEC でアクティビティを作成または編集する際、 [!UICONTROL 作成] から [!UICONTROL 参照] モード。 （TGT-43300）
* 一部の顧客をアーカイブできない問題を修正しました [!UICONTROL A/B テスト] 使用するアクティビティ [!UICONTROL 自動ターゲット]. （TGT-40978）
* 1 つのレポートグループ内の複数の場所で 1 つのオファーを自動的に使用する機能が追加されました。 （TGT-43974）
* エクスペリエンスフラグメントをタイプ (HTMLまたは JSON) でフィルタリングする機能を [!UICONTROL オファー] リスト。 （TGT-43121）
* 顧客が JSON を挿入できる問題を修正しました。 [!UICONTROL エクスペリエンスフラグメント] オファーを表示するようになりました。 JSON オファーは、 [!UICONTROL フォームベースのエクスペリエンス] 作成者 （TGT-43846）

## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

[!DNL Target] およびその他の [!DNL Adobe Experience Cloud] ソリューションの今後の製品強化に関する事前通知を受信するには、[!DNL Adobe Priority Product Update] に新規登録します。

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
