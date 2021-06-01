---
keywords: ターゲットドキュメントの変更ログ;ドキュメントの更新;新しいトピック;編集;アップデート;更新
description: Adobe [!DNL Target] 製品ドキュメントに関する重要な追加や変更を反映し、最新の状態に保ちます。
title: Target に関するドキュメントのアップデートはどこで確認できますか。
feature: リリースノート
exl-id: 36d19598-eb46-4be6-a652-658b653287cb
source-git-commit: 7bb1f896dd92b41d04eb0dfd39116ff1c132fe50
workflow-type: tm+mt
source-wordcount: '1349'
ht-degree: 52%

---

# ドキュメントの変更点

このページでは、[!DNL Adobe Target] 製品キュメントに加えられた重要な変更を一覧表示します。

## Adobe[!DNL Target] Standard/Premium 21.4.1（2021年4月20日）

| 日付 | トピック | 変更点 |
| --- | --- | --- |
| 6 月 2 日 | [CNAMEおよび [!DNL Target]](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md) | 以下の FAQ を追加しました。<ul><li>CNAMEでのオプトアウトリンクの使用方法</li></ul> |
|  | [プライバシー](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/privacy.md) | オプトアウトリンクをCNAMEで使用する方法について説明するために、「オプトアウトリンク」の節を更新しました。 |
|  | [[!DNL Adobe Analytics] as the reporting source for [!DNL Adobe Target] (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md) | [!DNL Adobe Experience Platform Web SDK]に関する情報を追加しました。 |
|  | [実装用 [!DNL Target] のAnalytics](/help/c-integrating-target-with-mac/a4t/a4timplementation.md#platform) | 次の新しいセクションを追加しました。<ul><li>[!DNL Adobe Experience Platform Web SDK]実装の実装手順</li></ul> |
|  | [リダイレクトオファー - A4T FAQ](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#platform) | A4TとPlatform Web SDKでのリダイレクトオファーの使用に関する情報を追加しました。 |
|  | [レスポンストークン](/help/administrating-target/response-tokens.md) | [!DNL Adobe Experience Platform Web SDK]でのレスポンストークンの使用に関する情報を追加しました。 |
|  | [Target リリースノート（現行）](/help/r-release-notes/release-notes.md) | Adobe Experience Platform Web SDK 2.6.0（2021年6月2日）リリースに関する情報を追加しました。 |
| 5 月 28 日 | [制限](/help/r-troubleshooting-target/target-limits.md) | [!DNL Target] API呼び出しに関する節を追加しました。 上限は、1分あたり50コールです。 |
| 5 月 21 日 | [オンデバイス判定](/help/c-implementing-target/c-api-and-sdk-overview/on-device-decisioning.md) | AdobeTechブログの次のブログ投稿へのリンクを追加しました。<ul><li>Adobeテクニカルブログ — パート2:エッジプラットフォームで実験とパーソナライゼーションを行うために[!DNL Adobe Target] NodeJS SDKを実行する(AWS Lambda@Edge)</li></ul> |
|  | [既知の問題と解決された問題](/help/r-release-notes/known-issues-resolved-issues.md) | 次の既知の問題を追加しました。 &quot;[!UICONTROL 自動ターゲット]アクティビティのアーカイブは、同期の問題を引き起こす可能性があります。&quot; |
| 17 年 5 月 | [Target リリースノート（現行）](/help/r-release-notes/release-notes.md) | at.js 2.5.0 リリースに関する情報を追加しました。 |
|  | [アクティビティ QA](/help/c-activities/c-activity-qa/activity-qa.md) | at.js 2.5.0（およびそれ以降）を使用した[!UICONTROL Automated Personalization](AP)アクティビティでプレビューリンクを使用できることを示すようにトピックを更新しました。 |
|  | [サポートされているブラウザー](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md) | at.js 2.5.0リリースで、Microsoft Internet Explorer 10、Internet Explorer 11およびすべての古いバージョンのサポートが削除されたことを示しました。 Microsoft Edgeは、at.js 2.5.0以降で引き続きサポートされます。 |
|  | [拡張Experience Composerに関連する問題のト [!UICONTROL ラブルシューティング]](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshooting-issues-related-to-the-enhanced-experience-composer-eec.md) | IPアドレスのリストを更新し、し許可リストました。 |
| 12 年 5 月 | [[!DNL Target] リリースノート（プレリリース）](/help/r-release-notes/target-release-notes.md) | 以下のプレリリースノートを追加しました。<ul><li>Adobe Experience Platform Web SDK（2021年5月18日）</li><li>Target Standard Premium 21.5.2</li></ul> |
| 10 年 5 月 | [[!DNL Recommendations] FAQ](/help/c-recommendations/c-recommendations-faq/recommendations-faq.md) | 次のFAQを追加しました。&quot;[!DNL Recommendations Premium]の[!DNL Adobe Recommendations Classic]で作成されたアルゴリズムを使用できますか？&quot; |
|  | [ [!DNL Target] using [!DNL Dynamic Tag Manager] (DTM)の実装](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-using-dynamic-tag-management.md) | [!DNL Adobe Dynamic Tag Manager]がサポートされなくなったことを示しました。 代わりに、[!DNL Adobe]は[[!DNL Adobe Experience Platform Launch]](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md)と共にを実装することをお勧めします。 |
| 5 月 7 日 | [Recommendations FAQ](/help/c-recommendations/c-recommendations-faq/recommendations-faq.md) | 次の FAQ を追加しました。<ul><li>[!UICONTROL Recommendations]アクティビティ、オファー、プロモーション、または条件の設定を変更してサイトに反映されるまで、どのくらいの時間がかかりますか。</li><li>ユーザーの行動（製品Aをクリックし、製品Bを購入するなど）が、*ユーザーが受け取るレコメンデーション*&#x200B;に反映されるまで、どの程度の時間がかかりますか。</li><li>ユーザーの行動（製品Aのクリックや製品Bの購入など）がレコメンデーション&#x200B;*他の*&#x200B;ユーザーが受け取るレコメンデーションに反映されるまで、どのくらい時間がかかりますか。</li></ul> |
|  | [オンデバイス判定](/help/c-implementing-target/c-api-and-sdk-overview/on-device-decisioning.md) | AdobeTechブログの次のブログ投稿へのリンクを追加しました。<ul><li>パート1:エッジプラットフォーム(Akamai Edge Workers)での実験とパーソナライゼーションのためのAdobe Target NodeJS SDKの実行</li></ul> |
| 5 年 5 月 | [Target のお知らせとイベント](/help/r-release-notes/target-announcements.md) | 2021年5月12日（水）午前8時に開催されるAdobe TargetコミュニティQ&amp;Aコーヒーブレークに関する情報を追加しました。(PDT、GMT-7)。 |
| 27 年 4 月 | [Cookie の設定](/help/c-implementing-target/c-implementing-target-for-client-side-web/atjs-cookies.md) | at.jsバージョン2.3.1以降では、Cookieの期間（`deviceIdLifetime`設定）が上書き可能であることを示すようにトピックを更新しました。 |
|  | [Adobe Targetガイド](/help/target-home.md) | Summitに関する情報をAdobeしました。 |
| 26 年 4 月 | [at.jsのオンデバイス判定のトラブルシューティング](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/troubleshooting-on-device-decisioning.md) | 新規トピックです。 |
| 19 年 4 月 | [オンデバイス判定](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md) | 次の新しい記事を追加しました。<ul><li>[オンデバイス判定](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md)</li><li>[オンデバイス判定でサポートされる機能](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/supported-features.md)</li><li>[オンデバイス判定ルールのアーティファクト](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/rule-artifact.md)</li></ul> |
|  | [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#on-device-decisioning) | `decisioningMethod`に関する情報を追加しました。 |
|  | [adobe.target.getOffers() - at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md) | 次の内容を追加しました。<ul><li>`decisioningMethod`キーに関する情報。</li><li>「getCallOffers()を使用してデバイス上での判定をおこなう例」を示します。</li></ul> |
|  | [at.js カスタムイベント](/help/c-implementing-target/c-implementing-target-for-client-side-web/atjs-custom-events.md) | 以下の情報を追加しました。<ul><li>デバイス上の判定アーティファクトが成功しました</li><li>デバイス上の判定アーティファクトが失敗しました</li></ul> |
|  | [アクティビティ](/help/c-activities/activities.md) | デバイス上判定に関する情報を追加しました。 |
|  | [at.js のバージョンの詳細](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | at.js 2.5.0 に関する情報を追加しました。 |
|  | [タグマネージャーを使用しない Target の実装](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md) | デバイス上判定に関する情報を追加しました。 |
|  | [アクティビティ QA](/help/c-activities/c-activity-qa/activity-qa.md) | [!UICONTROL Automated Personalization]アクティビティのプレビューリンクのサポートが[at.js 2.5.0](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)で追加されました。 |
|  | [動的および静的インクルージョンルールの使用](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#operators) | 次の新しい演算子に関する情報を追加しました。<ul><li>リストに含まれる</li><li> リストに含まれない</li><li>リストに</li><li>リストに</li><li>List Contains All Items In</li><li>List Does Not Contain All Items In</li></ul> |
|  | [Adobe Target cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-target.html)<br>(*Experience Cloudサービスおよび* 管理ガイド) | 「セッションID」に関する情報を追加しました。 |
|  | [リリースノート](/help/r-release-notes/release-notes.md)：21.4.1 | このリリースには、機能強化および修正が含まれています。それらについての説明を読み、リリースノートからドキュメントへのリンクをたどることができます。このリリースでは、ヘルプ全体で多くのドキュメントの更新もおこなっています。 |

## Adobe[!DNL Target] Standard/Premium 21.2.1（2021年3月10日）

| 日付 | トピック | 変更点 |
| --- | --- | --- |
| 9 年 4 月 | [Target リリースノート（プレリリース）](/help/r-release-notes/target-release-notes.md) | at.jsバージョン2.5.0リリース（2021年4月20日）のプレリリース情報を追加しました |
| 9 年 4 月 | [Target リリースノート（プレリリース）](/help/r-release-notes/target-release-notes.md) | Target Standard/Premium 21.4.1リリース（2021年4月20日）のプレリリース情報を追加しました。 |
|  | [Recommendations と電子メールの統合](/help/c-recommendations/c-recommendations-faq/integrating-recs-email.md) | オプション1および2の容量のガイドラインを説明する注記を追加しました。 |
| 3月30日 | [Recommendations FAQ](/help/c-recommendations/c-recommendations-faq/recommendations-faq.md#persist-across-devices) | 新しいFAQを追加しました。<ul><li>最近表示された品目に基づくレコメンデーションは、1人の訪問者の複数のデバイスで保持されますか。</li></ul> |
| 3月24日 | [ リリースノート ](/help/r-release-notes/release-notes.md) | at.js バージョン 2.4.1 のリリースノートを追加しました。 |
|  | [at.js のバージョンの詳細](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | at.js バージョン 2.4.1 のリリースノートを追加しました。 |
|  | [Recommendations FAQ](/help/c-recommendations/c-recommendations-faq/recommendations-faq.md) | 以下の FAQ を更新しました。<ul><li>カタログの項目を更新してサイトに反映されるまで、どれくらいかかりますか？</li></ul> |
| 3月23日 | [Recommendations フィード処理サーバーで使用される IP アドレス](/help/c-recommendations/c-recommendations-faq/ip-addresses-marketing-cloud.md) | IPアドレスのリストを更新しました。 |
|  | [制限](/help/r-troubleshooting-target/target-limits.md) | 「エンティティ」の下の「エンティティ数」の節を更新しました。 |
|  | [地域](/help/c-target/c-audiences/c-target-rules/geo.md) | at.js 2 に関する情報を追加しました。** xumderの「別の場所からアクセスするユーザーとして、自分のアクティビティをテストするにはどうすればよいですか？」 |
|  | [リリースノート](/help/r-release-notes/release-notes.md)：21.2.1 | 次の節を追加しました。 <ul><li>Recommendationsフィード処理サーバーのIPアドレスの変更（2021年3月17日）</li></ul> |
| 3月20日 | [レポートの表示 - A4T FAQ](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-viewing-reports.md#deactivated) | 以下の FAQ を追加しました。<ul><li>アクティビティを非アクティブ化した後も、引き続き他のインプレッションが表示されるのはなぜですか。</li></ul> |
| 3 月 13 日 | [自動配分と自動ターゲットアクティビティに対する A4T のサポート](/help/c-integrating-target-with-mac/a4t/a4t-at-aa.md#tutorial) | 以下の新しいチュートリアルを追加しました。<ul><li>自動ターゲットアクティビティ用に Analysis Workspace で A4T レポートを設定する方法</li></ul> |
| 3 月 10 日 | [制限](/help/r-troubleshooting-target/target-limits.md#offer-size) | <ul><li>オファーの許容サイズ制限を更新しました。</li><li>categoryId パラメーターの文字制限を修正しました。</li></ul> |
|  | [Target のエッジノードを許可リストに登録する](/help/c-implementing-target/c-considerations-before-you-implement-target/allowlist-edges.md) | [!DNL Target] エッジ IP アドレスを更新しました。 |
|  | [エンティティの属性](/help/c-recommendations/c-products/entity-attributes.md) | entity.value を 10 進数形式にする必要があることを示すテキストを追加しました（例：15,99ではなく15.99）。 |
|  | [リリースノート](/help/r-release-notes/release-notes.md)：21.2.1 | このリリースには、機能強化および修正が含まれています。それらについての説明を読み、リリースノートからドキュメントへのリンクをたどることができます。このリリースでは、ヘルプ全体で多くのドキュメントの更新もおこなっています。 |

## Adobe[!DNL Target] Standard/Premium 21.1.1（2021年1月20日）

| 日付 | トピック | 変更点 |
| --- | --- | --- |
| 2 月 23 日 | [レポートの表示 - A4T FAQ](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-viewing-reports.md) | 以下の FAQ を更新しました。<ul><li>Analysis Workspace でセグメントを適用できる場所はどこですか</li></ul> |
| 2 月 17 日 | [Target リリースノート（プレリリース）](/help/r-release-notes/target-release-notes.md) | プレリリースノートのオファー制限サイズに関するテキストを更新しました。 |
| 2 月 12 日 | [Target の仕組み](/help/c-intro/how-target-works.md) | 「ボット」節を更新しました。 |
| 2 月 11 日 | [Target のお知らせとイベント](/help/r-release-notes/target-announcements.md) | 2021 年 2 月 25 日水曜日の Adobe Target Community Q&amp;A Coffee Break に関する情報を追加しました。 |
| 2 月 9 日 | [Target モバイルのプレビュー](/help/c-target-mobile-app/target-mobile-preview.md) | Adobe モバイル SDK バージョン 4 の AndroidManifest.xml ファイルに追加する必要があるコードスニペットを記載しました。 |
|  | [既知の問題と解決された問題](/help/r-release-notes/known-issues-resolved-issues.md) | 次の既知の問題を追加しました。<ul><li>API を使用して作成されたコレクション、除外、条件、デザインは、Target ユーザーインターフェイスには表示されず、API でのみ編集できます。同様に、Target UI でこれらの項目のいずれかを作成し、後で API を使用して編集した場合、その変更は Target UI には反映されません。API で編集した項目は、変更が失われるのを防ぐため、引き続き API を使用して編集する必要があります。</li></ul> |
| 2 月 2 日 | [Automated Personalization 概要レポート](/help/c-reports/reports-ap.md) | 「よくある質問（FAQ）」の節を追加しました。 |
| 1 月 28 日 | [リダイレクトオファーの作成](/help/c-experiences/c-manage-content/offer-redirect.md) | トピックを更新しました。 |
|  | [リモートオファーを作成](/help/c-experiences/c-manage-content/about-remote-offers.md) | トピックを更新しました。 |
| 1 月 27 日 | [コンバージョン率](/help/c-reports/conversion-rate.md) | Target がスチューデントのt検定で「平方和」を使用する仕組みを明確にしました。 |
| 1 月 23 日 | [コンバージョン率](/help/c-reports/conversion-rate.md#t-test) | 「Target がスチューデントのt検定を使うことを推奨する理由は何ですか？」の節を追加しました。 |
| 1 月 22 日 | [Analytics と Target の統合（A4T）のトラブルシューティング](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md) | 「A4T アクティビティレポートに、多数の「未指定」イベントが入った行が含まれる」の節を追加しました。 |
|  | [レポートの表示 - A4T FAQ](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-viewing-reports.md) | 「Analyticsレポートに「未指定」と表示されるのはなぜですか？これはどういう意味ですか？ 」の節を更新しました。 |
| 1 月 21 日 | [Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md) | 新規トピックです。 |
| 1 月 20 日 | [Target リリースノート（現行）](/help/r-release-notes/release-notes.md) | Target 21.1.1 リリース（2021 年 1 月 20 日）に関する情報を追加しました。 |
|  | [制限](/help/r-troubleshooting-target/target-limits.md) | `productPurchasedID` パラメーターのテキストを更新しました。 |
|  | [既知の問題と解決された問題](/help/r-release-notes/known-issues-resolved-issues.md) | アクティブなプロモーションを使用した [!UICONTROL Recommendation] アクティビティをコピーする際の既知の問題を追加しました。重複アクティビティを変更すると元のアクティビティにも影響します（逆も同様です）。一時的な回避策が含まれます。 |
|  | [リリースノート](/help/r-release-notes/release-notes.md)：21.1.1 | このリリースには、機能強化および修正が含まれています。それらについての説明を読み、リリースノートからドキュメントへのリンクをたどることができます。このリリースでは、ヘルプ全体で多くのドキュメントの更新もおこなっています。 |
