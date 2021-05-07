---
keywords: リリースノート;リリース;更新;今後のリリース;機能強化;新機能;修正;アップデート;プレリリース
description: SDK、API、JavaScript ライブラリなど、Adobe Target の次回のリリースに含まれている新機能、機能強化および修正について説明します。
title: 次回のリリースで追加される新機能
feature: リリースノート
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
translation-type: tm+mt
source-git-commit: dba3044c94502ea9e25b21a3034dc581de10f431
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 32%

---

# Target リリースノート（プレリリース）

この記事には、プレリリース情報が含まれています。リリース日、機能などの情報は、予告なく変更されることがあります。

**最終更新日：2021年4月17日**

最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。リリースのタイミングに応じて、これらのページの情報は同じになる場合があります。 括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

>[!IMPORTANT]
>
>**mbox.jsの提供終了**:2021年3月31日をもって、mbox.jsライブラリをサポートし [!DNL Adobe Target] なくなりました。2021年3月31日以降、mbox.jsから行われたすべての呼び出しが正常に失敗し、[!DNL Target]アクティビティが実行されているページにデフォルトコンテンツが提供されるようになりました。
>
>サイトに発生する可能性のある問題を回避するには、新しい[!DNL Adobe Experience Platform Web SDK]またはat.js JavaScriptライブラリの最新バージョンに移行します。 詳しくは、[概要：クライアントサイド web に対する Target の実装](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)を参照してください。

## Target Standard／Premium 21.4.1（2021 年 4 月 19 日）

このリリースには、次の新機能および機能強化が含まれています。 括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

| 機能 | 詳細 |
| --- | --- |
| at.jsのオンデバイス判定のサポート | オンデバイス判定機能を使用すると、マーケターと開発者は、ユーザーのブラウザー上で実験とパーソナライズをほぼゼロの待ち時間で行うことができます。<br>詳しくは、at.jsの [オンデバイス判定を参照してください。](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md)<br>（発表期日） |
| ![エンティティフィルタールール用の](/help/assets/premium.png) PremiumListベースの演算子 | [!DNL Target Recommendations] は、エンティティのフィルタリングルールに新しいリストベースの演算子をサポートしています。(TGT-39234)<br>新たに追加された演算子は次のとおりです。<br><ul><li>リストに含まれる</li><li>リストに含まれない</li><li>リストに</li><li>リストに</li><li>リストにすべての項目が含まれる</li><li>リストに</li></ul>詳しくは、[動的および静的包含ルールの使用](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#operators)の「使用可能な演算子」を参照してください。 |

このリリースには、次の修正が含まれています。

* オーディエンスを[!UICONTROL すべての訪問者]に変更した後、アクティビティが同期できない問題を修正しました。 （TGT-40259）
* 「[!UICONTROL オファーを許可しない]」オプションが有効になっている場合でも、[!UICONTROL Automated Personalization]アクティビティの異なる場所で使用すると重複が複製されない問題を修正しました。 （TGT-39567）
* [!UICONTROL 管理]/[!UICONTROL Scene7構成]ページが正しく読み込まれない問題を修正しました。 （TGT-39918）
* プロパティが正しくないワークスペースにマップされる問題を修正しました。 （TGT-39869）
* レコメンデーションの除外の作成中に環境を変更した後にリクエストが失敗した場合、無限に読み込まれる問題を修正しました。 （TGT-39948）

## at.jsバージョン2.5.0（発表日）

at.jsのこのリリースには、次の機能強化および変更が含まれています。

* [at.jsのオンデバイス](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md) 判定のサポート。
* [プレビュー](/help/c-activities/c-activity-qa/activity-qa.md) リンクAutomated Personalizationアクティビティのサポート

このリリースでは、Microsoft Internet Explorer 10以降のバージョンのサポートも削除されます。

## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
