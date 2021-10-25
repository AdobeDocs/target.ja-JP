---
keywords: リリースノート;リリース;更新;今後のリリース;機能強化;新機能;修正;アップデート;プレリリース
description: SDK、API、JavaScript ライブラリなど、Adobe Target の次回のリリースに含まれている新機能、機能強化および修正について説明します。
title: 次回のリリースで追加される新機能
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 8a011f9076cd4d5041fa17485441c83de43581e5
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 52%

---

# Target リリースノート（プレリリース）

この記事には、プレリリース情報が含まれています。リリース日、機能などの情報は、予告なく変更されることがあります。

**最終更新日: 2021 年10月25日**

最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。これらのページの情報は、リリースのタイミングによっては同じになる可能性があります。 括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

>[!IMPORTANT]
>
>**mbox.js のサポート**：2021 年 3 月 31 日（PT）をもって、[!DNL Adobe Target]mbox.js ライブラリのサポートは終了しました。 2021 年 3 月 31 日（PT）以降、mbox.js からのすべての呼び出しはエラーなく失敗し、デフォルトコンテンツを提供することで [!DNL Target] アクティビティを実行しているページに影響を与えます。
>
>サイトで発生する可能性のある問題を回避するには、 [!DNL Adobe Experience Platform Web SDK] または at.js JavaScript ライブラリの最新バージョンに移行します。詳しくは、[概要：クライアントサイド web に対する Target の実装](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)を参照してください。

## [!DNL Target Standard/Premium] 21.10.5 (2021 年10月26日)

このメンテナンスリリースには、次の機能強化が含まれています。

| 機能 | 詳細 |
| --- | --- |
| [!UICONTROL Visual Experience Composer]（VEC） | Web コンポーネントのサポートが追加されました [ ](https://developer.mozilla.org/en-US/docs/Web/Web_Components) 。 カスタムエレメントやカスタムエレメント内のエレメントについて、パーソナライズされたエクスペリエンスとキャンペーンを作成およびテストできます。 |

## [!DNL Target Standard/Premium] 21.10.4 (2021 年10月21日)

このメンテナンスリリースには、次の機能強化が含まれています。

| 機能 | 詳細 |
| --- | --- |
| カートに基づく推奨事項 | ビジターのカートの内容に基づいて推奨されるアルゴリズムを新しく追加しました。<br>詳細については、作成基準「カートベース」、 [ ](/help/c-recommendations/c-algorithms/create-new-algorithm.md) 「カートビュー/チェックアウトページ」および「カート内に既に存在するアイテムを除外する」という推奨設定を参照してください [ ](/help/c-recommendations/plan-implement.md) 。 |

## [!DNL Target Standard/Premium] 21.10.3 (2021 年10月19日)

このメンテナンスリリースには、以下の機能強化、修正および変更が含まれています。

*  [!DNL Analysis Workspace] [!UICONTROL  アクティビティレポートの「分析でビューを表示」ボタンをクリックして、の A4T パネル ] [!DNL Target] を開くことができない問題を修正していました。（TGT-42099、TGT-42100）
*  フォームベースのエクスペリエンスコンポーザーを使用して、「デザインの編集」ボタンを使用して [!UICONTROL  、A/B テスト ] および [!UICONTROL  対象化 ] (XT) アクティビティ  を編集しているときに、「デザインを編集」ボタンが表示されない問題を修正しました。（TGT-41980）
*  新しい推奨事項を作成する際に、互換性チェックボックスが検索条件を選択したときに表示されない問題を修正しました  。（TGT-42053）
* 「 [!DNL Analytics] レポートソース (A4T) として選択できない場合に、アクセス許可が不足しているために間違ったエラーメッセージが表示されるように [!DNL Analytics] なります。 （TGT-41954）
* UI でのキーボード操作を改善するための複数のアクセシビリティ修正を実装しました [!DNL Target] 。

## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
