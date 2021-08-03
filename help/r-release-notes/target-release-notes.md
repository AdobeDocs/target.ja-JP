---
keywords: リリースノート;リリース;更新;今後のリリース;機能強化;新機能;修正;アップデート;プレリリース
description: SDK、API、JavaScript ライブラリなど、Adobe Target の次回のリリースに含まれている新機能、機能強化および修正について説明します。
title: 次回のリリースで追加される新機能
feature: リリースノート
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: ade66cbef912bcf4de5d43aebf5c3bc79e92a30e
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 61%

---

# Target リリースノート（プレリリース）

この記事には、プレリリース情報が含まれています。リリース日、機能などの情報は、予告なく変更されることがあります。

**最終更新日：2021 年 8 月 3 日**

最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。これらのページの情報は、リリースのタイミングによっては同じになる可能性があります。 括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

>[!IMPORTANT]
>
>**mbox.js のサポート**：2021 年 3 月 31 日（PT）をもって、[!DNL Adobe Target]mbox.js ライブラリのサポートは終了しました。 2021 年 3 月 31 日（PT）以降、mbox.js からのすべての呼び出しはエラーなく失敗し、デフォルトコンテンツを提供することで [!DNL Target] アクティビティを実行しているページに影響を与えます。
>
>サイトで発生する可能性のある問題を回避するには、 [!DNL Adobe Experience Platform Web SDK] または at.js JavaScript ライブラリの最新バージョンに移行します。詳しくは、[概要：クライアントサイド web に対する Target の実装](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)を参照してください。

## [!DNL Target Standard/Premium] 21.8.1（2021年8月5日）

このメンテナンスリリースには、お客様向けの次の変更を含む、多くのバックエンドの機能強化が含まれています。

* [!UICONTROL フォームベースのExperience Composer]で作成された[!UICONTROL 自動パーソナライゼーション]アクティビティのレポートで、削除されたオファーがレポートで参照される問題を修正しました。 この問題が発生すると、「このレポートのデータを取得できません。 問題が解決しない場合は、AdobeのClientCareにお問い合わせください。」 （TGT-41028）

## Target Delivery API（2021年8月4日）

このリリースで強化された機能は次のとおりです。

* mboxパラメーターの制限が100パラメーターに増えました。 以前の制限は50パラメーターでした。 （TNT-41717）
* `categoryId`の制限が256文字に増えました。 以前の上限は128文字でした。
* Delivery APIに次の[!DNL Adobe Audience Manager](AAM)の詳細が追加されました。

   * AAM UUID(Adobe Audience Managerの一意のユーザーID)
   * dataPartnerId
   * dataPartnerUserId

   以前は、Delivery APIには`dcsLocationHint`と`blob`のみが含まれていました。 （TNT-41644）

## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
