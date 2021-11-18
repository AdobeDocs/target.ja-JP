---
keywords: リリースノート;リリース;更新;今後のリリース;機能強化;新機能;修正;アップデート;プレリリース
description: SDK、API、JavaScript ライブラリなど、Adobe Target の次回のリリースに含まれている新機能、機能強化および修正について説明します。
title: 次回のリリースで追加される新機能
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 89b995f20491fe0a51c91f8a1fe7e6b1ccc7f974
workflow-type: tm+mt
source-wordcount: '479'
ht-degree: 100%

---

# Target リリースノート（プレリリース）

この記事には、プレリリース情報が含まれています。リリース日、機能などの情報は、予告なく変更されることがあります。

**最終更新日：2021年10月28日（PT）**

最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。これらのページの情報は、リリースのタイミングによっては同じになる可能性があります。 括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

>[!IMPORTANT]
>
>**mbox.js のサポート終了**：2021 年 3 月 31 日（PT）をもって、[!DNL Adobe Target] mbox.js ライブラリのサポートは終了しました。 2021 年 3 月 31 日（PT）以降、mbox.js からのすべての呼び出しはエラーなく失敗し、デフォルトコンテンツを提供することで [!DNL Target] アクティビティを実行しているページに影響を与えます。
>
>サイトで発生する可能性のある問題を回避するには、 [!DNL Adobe Experience Platform Web SDK] または at.js JavaScript ライブラリの最新バージョンに移行します。詳しくは、[概要：クライアントサイド web に対する Target の実装](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)を参照してください。

## at.js バージョン 2.7.0（2021年10月28日（PT））

このリリースで強化された機能は次のとおりです。

* [Web コンポーネント](https://developer.mozilla.org/ja/docs/Web/Web_Components)のサポートを追加しました。このバージョンの at.js は、カスタム要素およびカスタム要素内の要素に対して、パーソナライズされたエクスペリエンスとオファーを作成し、テストするために必要です。この機能は、[!DNL Target Standard/Premium] 21.10.5 リリースに含まれています。

## [!DNL Target Standard/Premium] 21.10.5（2021年10月28日（PT））

このメンテナンスリリースで強化された機能は次のとおりです。

| 機能 | 詳細 |
| --- | --- |
| [!UICONTROL Visual Experience Composer]（VEC） | [Web コンポーネント](https://developer.mozilla.org/en-US/docs/Web/Web_Components)のサポートを追加しました。パーソナライズされたエクスペリエンスとオファーを、カスタム要素およびカスタム要素内の要素に対して作成し、テストできます。<br>詳しくは、「[Visual Experience Composer オプション](/help/c-experiences/c-visual-experience-composer/viztarget-options.md#custom)」を参照してください。 |

## [!DNL Target Standard/Premium] 21.10.4（2021年10月21日（PT））

このメンテナンスリリースで強化された機能は次のとおりです。

| 機能 | 詳細 |
| --- | --- |
| 買い物かごベースの推奨事項 | 訪問者の買い物かごの内容に基づいて推奨事項を提供する、新しいアルゴリズムファミリーが追加されました。<br>詳しくは、「[条件の作成](/help/c-recommendations/c-algorithms/create-new-algorithm.md)」の「買い物かごベース」および「[推奨事項のプランと実装](/help/c-recommendations/plan-implement.md)」の「買い物かごへの追加／買い物かごの表示／チェックアウトのページ」と「訪問者の買い物かごにすでにあるアイテムを除外」を参照してください。 |

## [!DNL Target Standard/Premium] 21.10.3（2021年10月19日（PT））

このメンテナンスリリースには、以下の機能強化、修正および変更が含まれています。

* [!DNL Target] アクティビティレポートで「[!UICONTROL Analytics で表示]」ボタンをクリックしても [!DNL Analysis Workspace] の [!UICONTROL A4T] パネルが開かない問題を修正しました。（TGT-42099、TGT-42100）
* [!UICONTROL フォームベースのエクスペリエンスコンポーザー]を使用して「[!UICONTROL A/B テスト]」および「[!UICONTROL エクスペリエンスのターゲット設定]（XT）」アクティビティを編集しているときに「[!UICONTROL デザインを編集]」ボタンが表示されない問題を修正しました。（TGT-41980）
* 新しい [!UICONTROL Recommendations] アクティビティの作成時に「[!UICONTROL 互換性]」チェックボックスが条件の選択に表示されない問題を修正しました。（TGT-42053）
* [!DNL Analytics] の権限がないので [!DNL Analytics] をレポートソース（A4T）として選択できない場合に表示される誤ったエラーメッセージを修正しました。（TGT-41954）
* アクセシビリティに関する複数の修正を実装して、[!DNL Target] UI 全体のキーボードナビゲーションを改善しました。

## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
