---
keywords: リリースノート；新機能；リリース；更新；更新；リリース；機能強化；修正；バグ修正；更新
description: SDK、API、JavaScript ライブラリなど、Adobe Target の現在のリリースに含まれている新機能、機能強化および修正について説明します。
title: 現在のリリースに含まれる新機能
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
translation-type: tm+mt
source-git-commit: dba3044c94502ea9e25b21a3034dc581de10f431
workflow-type: tm+mt
source-wordcount: '632'
ht-degree: 35%

---

# Target リリースノート（現行）

以下のリリースノートでは、各[!DNL Adobe Target Standard]および[!DNL Target Premium]リリースの機能、拡張機能および修正点に関する情報を提供しています。 また、ターゲットAPI、SDK、JavaScriptライブラリ(at.js)およびその他のプラットフォームの変更に関するリリースノートも適宜含まれています。

>[!IMPORTANT]
>
>**mbox.jsの提供終了**:2021年3月31日をもって、mbox.jsライブラリをサポートし [!DNL Adobe Target] なくなりました。2021年3月31日以降、mbox.jsからのすべての呼び出しが正常に失敗し、[!DNL Target]アクティビティが実行されているページにはデフォルトコンテンツが提供されます。
>
>サイトに問題が発生する可能性を回避するため、新しい[!DNL Adobe Experience Platform Web SDK]またはat.js JavaScriptライブラリの最新バージョンにこの日より前に移行してください。 詳しくは、[概要：クライアント側web](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)のターゲットを実装します。

（括弧内の問題番号は [!DNL Adobe] 内部で使用されます。）

## Target Standard／Premium 21.4.1（2021 年 4 月 19 日）

このリリースには、次の新機能および機能強化が含まれています。 括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

| 機能 | 詳細 |
| --- | --- |
| at.js<br>のオンデバイス判定のサポート（発表日） | オンデバイス判定機能を使用すると、マーケターと開発者は、ユーザーのブラウザー上で実験とパーソナライズをほぼゼロの待ち時間で行うことができます。<br>詳しくは、at.jsの [オンデバイス判定を参照してください。](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md) |
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
* [プレビュー](/help/c-activities/c-activity-qa/activity-qa.md) リンクは、Automated Personalizationアクティビティをサポートします。

このリリースでは、Microsoft Internet Explorer 10以降のバージョンのサポートも削除されます。

## その他のリリースノートとバージョンの詳細

| リソース | 詳細 |
|--- |--- |
| [at.js のバージョンの詳細](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | [!DNL Adobe Target] at. js JavaScript ライブラリの各バージョンの変更点についての詳細です。 |

## ドキュメントの変更、過去のリリースノートおよび Experience Cloud リリースノート

追加情報については、各リリースのリリースノートに加えて、以下のリソースを参照してください。

| リソース | 詳細 |
|--- |--- |
| ドキュメントの変更点 | このガイドの更新に関する表示の詳細情報（リリースノートには含まれていません）。<br>詳しくは、「[ドキュメントの変更](/help/r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C)」を参照してください。 |
| 以前のリリースのリリースノート | 以前のリリースの Target Standard および Target Premium の新機能および機能拡張に関する情報を確認してください。<br>詳しくは、「[以前のリリースのドキュメントの変更](/help/r-release-notes/release-notes-for-previous-releases.md)」を参照してください。 |
| Adobe Experience Cloud リリースノート | Adobe Experience Cloud ソリューションの最新のリリースノートが表示されます。<br>詳しくは、「 [Experience Cloudリリースノート](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html)」を参照してください。 |

## プレリリース情報 {#section_5D588F0415A2435B851A4D0113ACA3A0}

次のリソースでは、次の Target リリースの内容を確認できます。

| リソース | 詳細 |
|--- |--- |
| Adobe優先度製品の更新 | Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。<br>[https://adobe.com/subscription/priority-product-update.html](https://adobe.com/subscription/priority-product-update.html) |
| 今後のリリースノート | プレリリース情報など今月の Target リリースについては、[Target リリースノート - プレリリース](/help/r-release-notes/target-release-notes.md)ページを参照してください。 |
