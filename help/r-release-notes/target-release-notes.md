---
keywords: リリースノート;リリース;更新;今後のリリース;機能強化;新機能;修正;アップデート;プレリリース
description: SDK、API、JavaScript ライブラリなど、Adobe Target の次回のリリースに含まれている新機能、機能強化および修正について説明します。
title: 次回のリリースで追加される新機能
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: afa370a38921ab76babf5e49edc1e4b23ee807b0
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 100%

---

# Target リリースノート（プレリリース）

この記事には、プレリリース情報が含まれています。リリース日、機能などの情報は、予告なく変更されることがあります。

**最終更新日：2021 年 8 月 24 日**

最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。これらのページの情報は、リリースのタイミングによっては同じになる可能性があります。 括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

>[!IMPORTANT]
>
>**mbox.js のサポート**：2021 年 3 月 31 日（PT）をもって、[!DNL Adobe Target]mbox.js ライブラリのサポートは終了しました。 2021 年 3 月 31 日（PT）以降、mbox.js からのすべての呼び出しはエラーなく失敗し、デフォルトコンテンツを提供することで [!DNL Target] アクティビティを実行しているページに影響を与えます。
>
>サイトで発生する可能性のある問題を回避するには、 [!DNL Adobe Experience Platform Web SDK] または at.js JavaScript ライブラリの最新バージョンに移行します。詳しくは、[概要：クライアントサイド web に対する Target の実装](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)を参照してください。

## [!DNL Target Standard/Premium] 21.8.1（2021年8月10日（PT））

このメンテナンスリリースには、次の顧客向けの変更を含む、多くのバックエンドの機能強化が含まれています。

* [!UICONTROL フォームベースの Experience Composer ]で作成された[!UICONTROL 自動パーソナライズ機能]アクティビティのレポートで、削除されたオファーが参照される問題を修正しました。この問題により、次のエラーメッセージが表示されました。「このレポートのデータの取得に問題があります。問題が解決しない場合は、アドビのカスタマーケアにお問い合わせください。」 （TGT-41028）

## ターゲット配信 API（2021 年 8 月 3 日）

このリリースには、次の機能拡張が含まれています。

* mbox パラメーターの上限が 100 パラメーターに増えました。以前の上限は 50 パラメーターでした。（TNT-41717）
* `categoryId` の制限が 256 文字に増えました。 以前の上限は 128 文字でした。
* 配信 API に次の [!DNL Adobe Audience Manager]（AAM）の詳細が追加されました。

   * AAM UUID：ユーザーを一意に識別するために使用される内部 AAM ID。
   * dataPartnerId：データパートナーの ID。
   * dataPartnerUserId：データパートナーから提供されたユーザー ID。

   以前は、配信 API には `dcsLocationHint` と `blob` のみが含まれていました。 （TNT-41644）

## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
