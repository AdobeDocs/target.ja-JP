---
keywords: リリースノート;リリース;更新;今後のリリース;機能強化;新機能;修正;アップデート;プレリリース
description: SDK、API、JavaScript ライブラリなど、Adobe Target の次回のリリースに含まれている新機能、機能強化および修正について説明します。
title: 次回のリリースではどのような新機能や機能強化が追加されますか？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 80481a149d436f13bd510c4c4287d447799afbb4
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 54%

---

# Target リリースノート（プレリリース）

この記事には、プレリリース情報が含まれています。リリース日、機能などの情報は、予告なく変更されることがあります。

**最終更新日：2022年10月19日（PT）**

最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。これらのページの情報は、リリースのタイミングによっては同じになる可能性があります。括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

## [!DNL Target] Standard／Premium 22.10.3（時差リリース 2022年25月10～27日（PT））

このリリースは、以下の時差スケジュールに従って利用できるようになります。

* **10月25日（PT）**：ヨーロッパ、中東、アフリカ（EMEA）地域
* **26月10日（PT）**：アジア太平洋（APAC）地域
* **10月27日（PT）**：アメリカ地域

このリリースには、以下の新機能、拡張機能および修正が含まれています。

| 機能 | 詳細 |
| --- | --- |
| 連続指標 | 売上高などの継続的な指標を [!UICONTROL 自動ターゲット] および [!UICONTROL 配分 — 配分] アクティビティ。<br>以前は、 [!UICONTROL 自動ターゲット] および [!UICONTROL 自動配分] モデルは、バイナリ（コンバージョンベース）の指標のみを扱うように最適化されています。 (TGT-43649および TGT-43649)<BR>この機能は、一部のお客様のみ利用できます。 この機能は、今後のリリースですべてのお客様が利用できるようになります。 |
| [!DNL Recommendations] わかりやすい名前 | わかりやすい名前を [!UICONTROL Analytics for Target] A4T レポート。 以前は、 [!DNL Target] リストに表示されたエクスペリエンス ID のみ。 この強化により、 [!DNL Adobe Analytics] および [!DNL Target] お客様が A4T でレポートを合理化するのに役立ちます。 (TGT-41853 |

* ツールチップを [!DNL Target] UI を使用して、顧客がオーディエンスビルダーをより効率的にナビゲートし、一般的でない機能の使用方法を学習します。 （TGT-44139）
* ユーザーが [!DNL Target] サポートされていない指標を使用しているので。 UI のメッセージは、アクティビティを複製してコンバージョン指標を更新するように顧客に指示します。

   このリリースでは `averagetimespentonsite`, `bouncerate`、および `entries` 指標 [!DNL Target] アクティビティは、新しいアクティビティでは非推奨となります。 既存のアクティビティでは、2023 年 2 月 7 日まで、これらの指標を引き続き使用できます。 (TGT-43860、TGT-43861、および TGT-43650)

* にツールチップを追加しました。 [!DNL Target] 顧客が最適化条件を選択し、 [!UICONTROL 自動ターゲット] A4T を使用するアクティビティ （TGT-43713）

## その他のリリースノートとバージョンの詳細

| リソース | 詳細 |
|--- |--- |
| [リリースノート：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=ja) | Platform Web SDK の各バージョンの変更点に関する詳細です。 |
| [at.js のバージョンの詳細](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} | [!DNL Adobe Target] at. js JavaScript ライブラリの各バージョンの変更点についての詳細です。 |


## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

[!DNL Target] およびその他の [!DNL Adobe Experience Cloud] ソリューションの今後の製品強化に関する事前通知を受信するには、[!DNL Adobe Priority Product Update] に新規登録します。

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
