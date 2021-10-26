---
keywords: リリースノート;リリース;更新;今後のリリース;機能強化;新機能;修正;アップデート;プレリリース
description: SDK、API、JavaScript ライブラリなど、Adobe Target の次回のリリースに含まれている新機能、機能強化および修正について説明します。
title: 次回のリリースで追加される新機能
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 3fb58864e265653b48e851c8dff404589bb867a6
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 51%

---

# Target リリースノート（プレリリース）

この記事には、プレリリース情報が含まれています。リリース日、機能などの情報は、予告なく変更されることがあります。

**最終更新日：2021 年 10 月 26 日**

最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。これらのページの情報は、リリースのタイミングによっては同じになる可能性があります。 括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

>[!IMPORTANT]
>
>**mbox.js のサポート**：2021 年 3 月 31 日（PT）をもって、[!DNL Adobe Target]mbox.js ライブラリのサポートは終了しました。 2021 年 3 月 31 日（PT）以降、mbox.js からのすべての呼び出しはエラーなく失敗し、デフォルトコンテンツを提供することで [!DNL Target] アクティビティを実行しているページに影響を与えます。
>
>サイトで発生する可能性のある問題を回避するには、 [!DNL Adobe Experience Platform Web SDK] または at.js JavaScript ライブラリの最新バージョンに移行します。詳しくは、[概要：クライアントサイド web に対する Target の実装](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)を参照してください。

## [!DNL Target Standard/Premium] 21.10.5（2021 年 10 月 29 日）

このメンテナンスリリースで強化された機能は次のとおりです。

| 機能 | 詳細 |
| --- | --- |
| [!UICONTROL Visual Experience Composer]（VEC） | のサポートを追加しました。 [Web コンポーネント](https://developer.mozilla.org/en-US/docs/Web/Web_Components). パーソナライズされたエクスペリエンスとオファーを、カスタム要素およびカスタム要素内の要素で作成およびテストできます。<br>このリリースは、at.js バージョン 2.7.0 のリリースと同時におこなわれます。 |

## [!DNL Target Standard/Premium] 21.10.4（2021 年 10 月 22 日）

このメンテナンスリリースで強化された機能は次のとおりです。

| 機能 | 詳細 |
| --- | --- |
| 買い物かごベースのRecommendations | 訪問者の買い物かごの内容に基づくレコメンデーションを配信する新しいアルゴリズムファミリーが追加されました。<br>詳しくは、 [条件の作成](/help/c-recommendations/c-algorithms/create-new-algorithm.md) および「買い物かごへの追加/買い物かご表示/チェックアウトページ」および「訪問者の買い物かごに既に存在する項目を除外」 [Recommendationsの計画と実装](/help/c-recommendations/plan-implement.md). |

## [!DNL Target Standard/Premium] 21.10.3（2021 年 10 月 20 日）

このメンテナンスリリースには、以下の機能強化、修正および変更が含まれています。

* お客様が [!UICONTROL A4T] パネル [!DNL Analysis Workspace] クリックして [!UICONTROL Analytics で表示] ボタン [!DNL Target] アクティビティレポート。 （TGT-42099、TGT-42100）
* 「 [!UICONTROL デザインを編集] ボタンが編集中に表示されない [!UICONTROL A/B テスト] および [!UICONTROL エクスペリエンスのターゲット設定] (XT) アクティビティ [!UICONTROL フォームベースの Experience Composer]. （TGT-41980）
* 「 [!UICONTROL 互換性] 新しい作成時の条件選択での表示からのチェックボックス [!UICONTROL Recommendations] アクティビティ。 （TGT-42053）
* 選択できない場合に誤ったエラーメッセージが表示される問題を修正しました。 [!DNL Analytics] が不足しているため、レポートソース (A4T) として [!DNL Analytics] 権限。 （TGT-41954）
* 複数のアクセシビリティ修正を実装し、 [!DNL Target] UI

## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
