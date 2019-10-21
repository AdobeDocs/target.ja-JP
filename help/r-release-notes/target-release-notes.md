---
description: Adobe targetの最新リリースまたは今後のリリースに関する機能、拡張機能および修正に関する情報を提供するリリースノートです。
keywords: リリースノート；リリース；更新；将来のリリース；拡張；新機能；修正点
seo-description: DNL Adobe targetの最新リリースまたは今後のリリースに関する機能、拡張機能および修正に関する情報を提供するリリースノートです。
seo-title: Adobe targetプレリリースノート
solution: 'Target '
title: Target リリースノート（プレリリース）
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 956a6b88fac9a13b98ede655e930aa016fe82533

---


# Target リリースノート（プレリリース）{#target-release-notes-prerelease}

これらのリリースノートでは、最新または今後 [!DNL Adobe Target] のリリースの機能、機能強化および修正点について説明しています。

**最終更新日：2019年10月18日**

>[!NOTE]
>
>これらのリリースノートには、プレリリース情報が含まれています。リリース日、機能などの情報は、予告なく変更されることがあります。最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。これらのページの情報は、リリースのタイミングによって異なる場合があります。
>
>括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

## Target Standard／Premium 19.10.1（2019 年 10 月 22 日）

| 機能／拡張機能 | 説明 |
| --- | --- |
| ![Premiumバッジ](/help/assets/premium.png) User-Based Recommendations<br>（2019年10月25日） | 各訪問者の閲覧、閲覧、購入履歴に基づいて品目をレコメンドします。 これらの品目は、一般に「推奨」と呼ばれます。<br>この条件を使用すると、新規訪問者と再訪問者の両方に対して、パーソナライズされたコンテンツとエクスペリエンスを配信できます。 レコメンデーションのリストは、訪問者の最新のアクティビティに重み付けされ、セッション内で更新され、訪問者がサイトを閲覧するにつれて、よりパーソナライズされます。<br>詳しくは、条件/アルゴリズムの「ユーザーベースのレコメンデーション」 [を参照してください](/help/c-recommendations/c-algorithms/algorithms.md#criteria-algorithms)。 |

### 機能強化、修正および変更

* にログインすると、新しいヘ [!DNL Adobe Experience Cloud]ッダーナビゲーションが表示されます。 前のナビゲーションの上部に黒いバーが表示されているのと非常に似ていますが、次の点が改善されました。

   * (IMS)組織間 [!DNL Identity Management System] または別のソリューションへの切り替えが容易になりました。
   * ユーザーヘルプの改善：検索結果には、製品ドキュメントの結 [!DNL Target] 果、コミュニティフォーラムやビデオコンテンツなどが含まれ、より多くのコンテンツに簡単にアクセスして最大限の活用を図ることができま [!DNL Target]す。 また、ヘルプメニューにフィードバックのメカニズムが追加さ [!UICONTROL れ] 、問題の報告やアイデアの共有が簡単になりました。

   * ネットプロモータースコア(NPS)のフィードバック機能が改善され、調査モーダルが作業の流れを妨げないようになりました。
   * ログインフローが改善されました。 以前は、すべての顧客 [!DNL Target] はヘッダーのアイコンをクリックした後、Targetのランディングペ [!DNL Target] ージにランディングしました。 その後、このページでは、次に示すように、お客様はRecommendations Classic [!DNL Target Standard/Premium]、 [!DNL Search&Promote]または [!DNl Recommendations]Classicを使用できるようになりました。

      ![ランディングページ](/help/r-release-notes/assets/landing.png)

      このランディングページをすべてのお客様に対して削除しました。 新しいヘッダーナビゲーションバーのアイコンをクリ [!UICONTROL ックすると] 、常にアクティビティリスト [!DNL Target] ページに直接移動するようになりました。

      使用する場合は、 [!DNL Recommendations Classic]次に示すように、ソリューションに直接移動するか、「 [!UICONTROL Recommendations] 」タブで作成した短いリンクから移動できます。

      ![Recs Classicディープリンク](/help/r-release-notes/assets/recs-classic.png)

      を使用する場合 [!DNL Search&Promote]は、リンクに直接移動する必要があります。 の内側から到達す [!DNL Search&Promote] るパスが完全 [!DNL Adobe Target] に削除されました。

   * の通知は、現 [!DNL Target] 在、ヘッダーの「通知  」ドロップダウンでは使用できません。
   >[!NOTE]
   >
   >これらの機能は一度に展開されたり、すべての顧客に一括して展開されることはありません。 これらの機能は、19.10.1（2019年10月22日）リリースから数日 [!DNL Target Standard/Premium] 後にロールアウトされます。
   >
   >新しいナビゲーションバーの展開の一部として、URLの変化にも気付きます。 以前にブックマークされたリンクは、引き続き機能しますが、すばやく開くために新しいリンクをブックマークすることをお勧めします。

## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。

[https://adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
