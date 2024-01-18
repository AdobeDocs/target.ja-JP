---
keywords: ターゲットドキュメントの変更ログ;ドキュメントの更新;新しいトピック;編集;アップデート;更新
description: ' [!DNL Adobe Target]  ドキュメントへの重要な追加や変更について、常に最新の情報を把握します。'
title: ' [!DNL Target] のドキュメントのアップデートはどこで確認できますか？'
feature: Release Notes
exl-id: 36d19598-eb46-4be6-a652-658b653287cb
source-git-commit: a2ffeec1b98ee3c9df2466b245b972a252044c3d
workflow-type: tm+mt
source-wordcount: '2374'
ht-degree: 100%

---

# ドキュメントの変更点

このページでは、[!DNL Adobe Target] 製品キュメントに加えられた重要な変更を一覧表示します。

## [!DNL Target] Standard／Premium 23.11.1（2023年11月13～14日（PT））

| 日付 | トピック | 変更点 |
| --- | --- | --- |
| 1月18日（PT） | [[!DNL Target] リリースノート（プレリリース）](/help/main/r-release-notes/target-release-notes.md) | 今後の [!DNL Target Standard/Premium] 24.1.1 リリースに関するプレリリースノートを追加しました。 |
| 12月13日（PT） | [[!DNL Adobe Target]  のお知らせとイベント](/help/main/r-release-notes/target-announcements.md) | [!DNL Adobe Target] 2024 パーソナライゼーション成熟度ウェビナーシリーズに関する情報を追加しました。 |
|  | [targetGlobalSettings()](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/targetglobalsettings.html?lang=ja){target=_blank} | 次の 2 つの新しいオプション設定を追加しました。 <ul><li>aepSandboxId</li><li>aepSandboxName</li></ul> |
| 12月4日（PT） | [[!DNL Adobe Target]  のお知らせとイベント](/help/main/r-release-notes/target-announcements.md) | 「機械学習および AI レポートと分析」の [!DNL Adobe Target Community] コーヒーブレークセッション（2023年12月6日水曜日（PT））に関する登録情報を追加しました。 |
| 12月1日（PT） | [Adobe Target プロファイル更新 API](https://experienceleague.adobe.com/docs/target-dev/developer/api/profile-apis/profile-api-overview.html?lang=ja){target=_blank} | 従来の API ドキュメントを次の記事に移動しました。<ul><li>[Adobe Target プロファイル API の概要](https://experienceleague.adobe.com/docs/target-dev/developer/api/profile-apis/profile-api-overview.html?lang=ja){target=_blank}</li><li>[Adobe Target 単一プロファイル更新 API](https://experienceleague.adobe.com/docs/target-dev/developer/api/profile-apis/profile-single-api.html?lang=ja){target=_blank}</li><li>[Adobe Target プロファイル一括更新 API](https://experienceleague.adobe.com/docs/target-dev/developer/api/profile-apis/profile-bulk-api.html?lang=ja){target=_blank}</li></ul> |
| 11月29日（PT） | [プロファイル一括更新 API](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/bulk-profile-update-api.html?lang=ja){target=_blank} | [!UICONTROL プロファイル一括更新 API] v2 を使用する場合、[!DNL Target] でまだ確認していないユーザーのプロファイルを作成する際に、[!DNL Target] で顧客属性を処理する方法と v1 の違いを明確にしました。 |
| 11 月 21 日 | [at.js のバージョンの詳細](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=ja){target=_blank} | at.js 2.11.3 のリリースノートを追加しました。 |
| 11 月 17 日 | [管理者の最初の手順](/help/main/administrating-target/start-target.md) | 次の重要な注意点を追加しました。<ul><li>[!DNL Adobe Admin Console] の[!UICONTROL 製品管理者]権限または[!UICONTROL システム管理者]権限を持つユーザーは、[!DNL Target] の役割に関係なく、[!DNL Target] の[!UICONTROL 管理]ページのすべての設定を編集または変更できます。[!DNL Adobe Admin Console] の[!UICONTROL 製品管理者]権限または[!UICONTROL システム管理者]権限を持たないユーザーがこれらの変更を行うには、特定の [!DNL Target] の役割が必要です。1</li></ul> |
|  | [制限](/help/main/r-troubleshooting-target/target-limits.md#in-mbox) | [!DNL Target] が at.js で切り捨てを処理する方法に関する情報を含むセクションを更新しました。*x* と [!DNL Adobe Experience Platform Web SDK]。 |
|  | [配信 API](https://experienceleague.adobe.com/docs/target-dev/developer/api/delivery-api/overview.html?lang=ja){target=_blank} | 現在の配信 API ドキュメントにリダイレクトを追加し、従来のドキュメント（`http://developers.adobetarget.com/api/delivery-api/`）を非推奨にしました。必要に応じて、ブックマークを更新してください。 |
| 11 月 16 日 | [プロファイル一括更新 API](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/bulk-profile-update-api.html?lang=ja){target=_blank} | 次の注意事項を追加しました。「通常、更新は 1 時間未満でおこなわれますが、反映されるまでに 24 時間かかる場合があります。」 |
| 11 月 13 日 | [Target リリースノート（現行）](/help/main/r-release-notes/release-notes.md) | [!DNL Target Standard/Premium] 23.11.1 リリースに関するリリースノートを追加しました。 |

## [!DNL Target] Standard／Premium 23.10.2（2023年10月24日（PT））

| 日付 | トピック | 変更点 |
| --- | --- | --- |
| 11月11日（PT） | [Recommendations API リファレンス](https://developer.adobe.com/target/administer/recommendations-api/){target=_blank} | [!DNL Adobe Target] [!DNL Recommendations] API は、[!DNL Adobe Developer] web サイトに移動しました。必要に応じてブックマークを更新してください。 |
|  | [時間枠](/help/main/c-target/c-audiences/c-target-rules/time-frame.md) | [!DNL Target] の時間のオーディエンスには夏時間（DST）の変更が考慮されていないというメモを追加しました。DST の変更を考慮するには、オーディエンスを手動で更新する必要があります。 |
| 11月8日（PT） | [[!DNL Target] リリースノート（プレリリース）](/help/main/r-release-notes/target-release-notes.md) | 今後の [!DNL Target Standard/Premium] 23.11.1 リリースに関するプレリリースノートを追加しました。 |
| 10月28日（PT） | [at.js のバージョンの詳細](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=ja){target=_blank} | at.js 2.11.2 リリースに関する詳細を追加しました。 |
| 10月25日（PT） | [[!DNL Target] リリースノート（最新）](/help/main/r-release-notes/release-notes.md) | [!UICONTROL アクティビティ]ページのユーザーインターフェイスの更新（2023年10月25日（PT））に関する情報を追加しました |
| 10月24日（PT） | [Target リリースノート（現行）](/help/main/r-release-notes/release-notes.md) | [!DNL Target Standard/Premium] 23.10.2 リリースに関するリリースノートを追加しました。 |

## [!DNL Target] Standard／Premium 23.9.1（2023年9月6日～11日（PT））

| 日付 | トピック | 変更点 |
| --- | --- | --- |
| 10月17日（PT） | [レポートの FAQ](/help/main/c-reports/reporting-frequently-asked-questions.md#section_E4722F6445884130951DF79981C8289B) | 次の FAQ を更新しました。「アクティビティのレポートにデータがないのはなぜでしょうか。」 |
| 10月11日（PT） |  [!DNL Adobe Target]  のレポートソースとしての [[!DNL Adobe Analytics] （A4T）](/help/main/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) | [!DNL Adobe Experience Platform Web SDK] の A4T サポートに関する情報を更新しました。 |
| 10月10日（PT） | [at.js のバージョンの詳細](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=ja){target=_blank} | at.js バージョン 2.11.0 のリリースノートを追加しました。 |
| 10月6日（PT） | [レスポンストークン](/help/main/administrating-target/response-tokens.md) | すべてのコードサンプルを更新しました。 |
|  | [ [!DNL Analysis Workspace]  での[!UICONTROL 自動配分]アクティビティ用 A4T レポートの設定](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html?lang=ja){target=_blank} | *[!UICONTROL Adobe Target チュートリアル]*&#x200B;ガイドのチュートリアル全体を更新しました。 |
| 10月4日（PT） | [アクティビティ](/help/main/c-activities/activities.md) | [!DNL Target] 23.9.4 リリースに含まれる UI の更新を反映するために、テキストと画像を更新しました。 |
|  | [フィード](/help/main/c-recommendations/c-products/feeds.md) | [!DNL Target] 23.9.4 リリースに含まれる UI の更新を反映するために、テキストと画像を更新しました。 |
| 10月2日（PT） | [[!DNL Target] リリースノート（最新）](/help/main/r-release-notes/release-notes.md) | [!DNL Target Standard/Premium] 23.9.3 リリースに関するリリースノートを追加しました。 |
|  | [[!DNL Recommendations] 実装パターン](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/recs-implementation-pattern-atjs.html?lang=ja){target=_blank} | at.js *のアーティクルを使った新しい* Recommendations の実装パターンは、at.js JavaScript ライブラリを使うときに、[!DNL Adobe Target Recommendations] の実装を理解して作成するのに役立ちます。<P>[!DNL Target] パターンに関する一般的な情報については、*Adobe Target 開発者ガイド*&#x200B;の[実装パターンの概要](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/pattern-overview.html?lang=ja){target=_blank}を参照してください。<P>新しい Recommendations の実装パターンは、次の記事で構成されています。<ul><li>[at.js を使用した Recommendations 実装パターンの概要](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/recs-implementation-pattern-atjs.html?lang=ja){target=_blank}</li><ul><li>[SDK の初期化](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/initialize-sdk.html?lang=ja){target=_blank}</li><li>[データ収集の設定](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/data-collection.html?lang=ja){target=_blank}</li><li>[エクスペリエンスのレンダリング](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/render-experiences.html?lang=jp){target=_blank}</li><li>[通知 [!DNL Target]](https://experienceleague.adobe.com/docs/target-dev/developer/implementation-patterns/atjs/notify-target.html?lang=jp){target=_blank}</li></ul></ul> |
| 9月30日（PT） | [[!DNL Target] リリースノート（プレリリース）](/help/main/r-release-notes/target-release-notes.md) | [!DNL Target Standard/Premium] 23.9.3 リリースに関するプレリリースノートを追加しました。 |
|  | [Java SDK の初期化](https://experienceleague.corp.adobe.com/docs/target-dev/developer/server-side/java/initialize-sdk.html?lang=ja){target=_blank} | 表に以下の新規パラメーターを追加しました。<ul><li>`connectionTtlMs`</li><li>`idleConnectionValidationMs`</li><li>`evictIdleConnectionsAfterSecs`</li></ul> |
| 9月22日（PT） | [[!UICONTROL Experience Composer の強化]](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshooting-issues-related-to-the-enhanced-experience-composer-eec.md#section_D29E96911D5C401889B5EACE267F13CF)に関連する問題のトラブルシューティング | IP アドレスのリストを更新し、許可リストに加えました。 |
| 9月18日（PT） | [[!DNL Target] リリースノート（最新）](/help/main/r-release-notes/release-notes.md) | [!DNL Target Standard/Premium] 23.9.3 リリースに関するリリースノートを追加しました。 |
| 9月15日（PT） | [[!DNL Target] リリースノート（プレリリース）](/help/main/r-release-notes/target-release-notes.md) | [!DNL Target Standard/Premium] 23.9.3 リリースに関するプレリリースノートを追加しました。 |
| 9月12日（PT） | [[!DNL Target] リリースノート（最新）](/help/main/r-release-notes/release-notes.md) | [!DNL Target Standard/Premium] 23.9.2 リリースに関するリリースノートを追加しました。 |
|  | [at.js のバージョンの詳細](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=ja){target=_blank} | at.js バージョン 2.10.3 のリリースノートを追加しました。 |
| 9月11日（PT） | [[!DNL Target] リリースノート（プレリリース）](/help/main/r-release-notes/target-release-notes.md) | [!DNL Target Standard/Premium] 23.9.2 リリースに関するプレリリースノートを追加しました。 |
| 9月6日（PT） | [Target リリースノート（現行）](/help/main/r-release-notes/release-notes.md) | [!DNL Target Standard/Premium] 23.9.1 リリースに関するリリースノートを追加しました。 |

## [!DNL Target] Standard／Premium 23.8.1（2023年8月9日（PT））

| 日付 | トピック | 変更点 |
| --- | --- | --- |
| 9月1日（PT） | [環境](/help/main/administrating-target/environments.md##section_4F8539B07C0C45E886E8525C344D5FB0) | 「レポート用のデフォルト環境を設定」のメモを更新しました。 |
| 8月30日（PT） | [プライバシー](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/privacy/privacy.html?lang=ja#aep){target=_blank} | 新しい節「Adobe Experience Platform Web SDK を使用する場合のデータストリームレベルの IP 難読化」を追加しました。 |
|  | [アクティビティの設定 - A4T FAQ](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-activity-setup.md#section_9F8092BE4225442896F926540292F221) | 次の FAQ のレポートにデータが表示されると予想される時間枠を修正しました。「アクティビティを作成しました。データが表示されないのはなぜですか？」 |
| 8月29日（PT） | [オンデバイス判定でサポートされる機能](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/on-device-decisioning/supported-features.html?lang=ja){target=_blank} | クライアントサイドでオンデバイス判定（ODD）を使用する場合のターゲティングでサポートされる地域属性のリストを追加しました。 |
|  | [オンデバイス判定の概要](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/on-device-decisioning/overview.html?lang=ja){target=_blank} | サーバーサイドでオンデバイス判定（ODD）を使用する場合のターゲティングでサポートされる地域属性のリストを追加しました。 |
|  | [Web ビューを使用したネイティブアプリでの AEP Mobile SDK による Target の実装](https://experienceleague.adobe.com/docs/target-dev/developer/mobile-apps/native-app.html?lang=ja){target=_blank} | 新しい記事。 |
|  | [[!DNL Adobe Target]  のお知らせとイベント](/help/main/r-release-notes/target-announcements.md) | 今後の Adobe Target コミュニティコーヒーブレーク（2023年8月30日（PT））に関する次の情報を追加しました：「ピークシーズンに備えて ROI 効果を最大化するための戦略化」ウェビナーのフォローアップ。 |
| 8月15日 | [アクティビティ QA](/help/main/c-activities/c-activity-qa/activity-qa.md) | 空の値を含むページをサイトに読み込んでもブラウザーから QA cookie が削除され&#x200B;*ない*&#x200B;ことを明確にする情報を追加しました（at.js 2.*x* がデプロイされている場合）。 |
|  | [A/Bn テストでの統計計算](/help/main/c-reports/statistical-methodology/statistical-calculations.md) | 「信頼性」の定義を更新しました。 |
|  | [オファー](/help/main/c-experiences/c-manage-content/manage-content.md) | 画像オファーが[!UICONTROL エンタープライズユーザー権限]モデルの一部ではないことを説明するメモを追加しました。 |
| 8月9日（PT） | [Target モバイルのプレビュー](https://experienceleague.adobe.com/docs/target-dev/developer/mobile-apps/target-mobile-preview.html?lang=ja){target=_blank} | [!DNL Adobe Experience Platform Mobile SDK] の現在のバージョンに関する情報を含むトピックを更新しました。 |
| 8月9日（PT） | [Target モバイルのプレビュー](https://experienceleague.adobe.com/docs/target-dev/developer/mobile-apps/target-mobile-preview.html?lang=ja){target=_blank} | [!DNL Adobe Experience Platform Mobile SDK] の現在のバージョンに関する情報を含むトピックを更新しました。 |
|  | [[!DNL Adobe Target]  のお知らせとイベント](/help/main/r-release-notes/target-announcements.md) | 2023年8月17日（PT）に予定されている&#x200B;*ピークシーズンに備えて ROI 効果を最大化するための戦略化*&#x200B;のウェビナーに関する情報を追加しました。 |
|  | [Target リリースノート（現行）](/help/main/r-release-notes/release-notes.md) | [!DNL Target Standard/Premium] 23.8.1 リリースに関するリリースノートを追加しました。 |

## [!DNL Target] Standard／Premium 23.7.1（2023年7月24～26日（PT））

| 日付 | トピック | 変更点 |
| --- | --- | --- |
|  | [[!DNL Adobe Target]  のお知らせとイベント](/help/main/r-release-notes/target-announcements.md) | 2023年8月17日（PT）に予定されている&#x200B;*ピークシーズンに備えて ROI 効果を最大化するための戦略化*&#x200B;のウェビナーに関する情報を追加しました。 |
| 8月7日（PT） | [at.js のバージョンの詳細](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=ja){target=_blank} | at.js のサポート対象バージョンに関する情報を明確にしました。 |
| 7月25日（PT） | [[!DNL Target] リリースノート（最新）](/help/main/r-release-notes/release-notes.md#edge) | 2023年8月9日（PT）に予定されているエッジインフラストラクチャのアップグレードに関する情報を追加しました。 |
|  | [Target のエッジノードを許可リストに登録](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/privacy/allowlist-edges.html?lang=ja){target=_blank} | エッジデプロイメント 41～48 の NAT と IP／ドメインを更新しました。 |
| 7 月 25 日 | [Target リリースノート（現行）](/help/main/r-release-notes/release-notes.md) | [!DNL Target Standard/Premium] 23.7.1 リリースに関するリリースノートを追加しました。 |

## [!DNL Target] Standard／Premium 23.6.1（2023年6月27～29日（PT））

| 日付 | トピック | 変更点 |
| --- | --- | --- |
| 7月20日（PT） | [コンテンツセキュリティポリシー（CSP）指令](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/privacy/content-security-policy.html?lang=ja){target=_blank} | *Adobe Target 開発者ガイド*&#x200B;に「自分のサイトが外部ドメインに iFrame として埋め込まれることを許可または禁止するにはどうすればよいですか？」という FAQ を追加しました。 |
| 7月10日（PT） | [考慮事項と既知の制限事項](https://experienceleague.adobe.com/docs/target-dev/developer/api/delivery-api/known-limitations.html?lang=ja){target=_blank} | 小文字のヘッダー名を適用する HTTP/2 に関する情報を *Target 配信 API* ドキュメントに追加しました。 |
| 6月27日（PT） | [アクティビティ QA](/help/main/c-activities/c-activity-qa/activity-qa.md) | アクティビティ QA を、[!UICONTROL Automated Personalization]（AP）アクティビティを含む、すべてのターゲットアクティビティタイプで使用できるようになりました。プレビューリンクに関する情報を削除しました。 |
|  | プレビュー URL | すべてのアクティビティタイプでアクティビティ QA がサポートされるようになったので、このトピックを削除し、[アクティビティ QA](/help/main/c-activities/c-activity-qa/activity-qa.md) トピックにリダイレクトするようにしました。 |
|  | [Target リリースノート（現行）](/help/main/r-release-notes/release-notes.md) | [!DNL Target Standard/Premium] 23.6.1 リリースに関するリリースノートを追加しました。 |

## [!DNL Target] Standard／Premium 23.5.1（2023年5月23～25日（PT））

| 日付 | トピック | 変更点 |
| --- | --- | --- |
| 6月26日（PT） | [モバイルアプリのための Target](https://experienceleague.adobe.com/docs/target-dev/developer/mobile-apps/overview.html?lang=ja){target=_blank} | モバイルアプリでの [!DNL Adobe Experience Cloud] の実装チュートリアルへのリンクを追加しました。 |
| 6月12日（PT） | [Adobe Target の Cookie](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/cookies-target.html?lang=ja){target=_blank} | [!DNL Target] で使用される Cookie について説明した *Experience Cloud 中央インターフェイスコンポーネントガイド*&#x200B;の記事を更新しました。 |
|  | [Java SDK の初期化](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/java/initialize-sdk.html?lang=ja){target=_blank} | 「環境」パラメーターに関する情報を追加しました。 |
|  | [Python SDK の初期化](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/python/initialize-sdk.html?lang=ja){target=_blank} | 「環境」パラメーターに関する情報を追加しました。 |
| 6月6日（PT） | [[!DNL Adobe Target]  のお知らせとイベント](/help/main/r-release-notes/target-announcements.md) | 次のイベントに関する情報を更新しました。<ul><li>[!DNL Adobe Target Recommendations] コーヒーブレイク（2023年6月7日水曜日（PT））の登録リンクを更新しました</li><li>最近のウェビナー「認証済み環境向けのモバイルエクスペリエンスの最適化とパーソナライゼーション」に関する情報を追加し、録画へのリンクを追加しました。</li></ul> |
|  | [成功指標へのレポート用オーディエンスの適用](/help/main/c-target/apply-reporting-audience-success-metric.md) | 「考慮事項」の節を更新し、「例」の節を追加しました。 |
|  | [ターゲットとオーディエンスに関する FAQ](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md#url-targeting) | 「URL ターゲティング」の節を更新しました。 |
| 5月30日（PT） | [[!DNL Target] リリースノート（最新）](/help/main/r-release-notes/release-notes.md) | [!DNL Target Standard/Premium] 23.5.2 リリースに関するリリースノートを追加しました。 |
|  | [ [!DNL Real-Time Customer Data Platform]](/help/main/c-integrating-target-with-mac/integrating-with-rtcdp.md) との統合 | HTML オファーと JSON オファーで使用するための [!UICONTROL Real-Time CDP プロファイル属性]の [!DNL Target] との共有に関する情報を含む記事を更新しました。 |
|  | [[!DNL Adobe Target]  のお知らせとイベント](/help/main/r-release-notes/target-announcements.md) | 以下に今後のコーヒーブレイクイベントに関する情報を追加しました。<ul><li>[!DNL Adobe Target Recommendations] コーヒーブレーク（6月7日（PT））</li><li>パーソナライゼーションプログラム対応ウェビナーのフォローアップ（6月21日（PT））</li></ul> |
| 5月23日（PT） | [Target のエッジノードを許可リストに登録](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/privacy/allowlist-edges.html?lang=ja){target=_blank} | 重要なメモを更新しました。 |
|  | [[!DNL Target] リリースノート（プレリリース）](/help/main/r-release-notes/target-release-notes.md) | 今後のリリースのプレリリースノートを更新しました。 |
|  | [Target リリースノート（現行）](/help/main/r-release-notes/release-notes.md) | [!DNL Target Standard/Premium] 23.5.1 リリースに関するリリースノートを追加しました。 |

## [!DNL Target] Standard／Premium 23.4.1（2023年4月25～27日（PT））

| 日付 | トピック | 変更点 |
| --- | --- | --- |
| 5月22日（PT） | [ [!DNL Real-Time Customer Data Platform]](/help/main/c-integrating-target-with-mac/integrating-with-rtcdp.md#videos-blogs) との統合 | 次の新しいビデオを追加しました。<ul><li>[!DNL Real-Time Customer Data Platform] での [!DNL Adobe Target] の宛先の設定</li><li>セグメントとプロファイル属性のアクティブ化</li><li>[!DNL Target] での [!DNL Real-Time CDP] セグメントの使用</li><li>[!DNL Adobe Target] での [!DNL Real-Time CDP] プロファイル属性の使用</li></ul> |
|  | [Target のエッジノードを許可リストに加える](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/privacy/allowlist-edges.html?lang=ja){target=_blank} | 重要なメモを更新しました。 |
| 5月19日（PT） | [[!DNL Target] リリースノート（プレリリース）](/help/main/r-release-notes/target-release-notes.md) | 今後のリリースのプレリリースノートを更新しました。 |
| 5月17日（PT） | [[!DNL Adobe Target]  のお知らせとイベント](/help/main/r-release-notes/target-announcements.md) | 2023年5月24日水曜日（PT）の [!UICONTROL Adobe Target コミュニティ] Q&amp;A のコーヒーブレイクに関する情報を追加しました。 |
| 5月16日（PT） | [エンティティの属性](/help/main/c-recommendations/c-products/entity-attributes.md) | 「スペース」は `entity.id` 値では使用できないことを示しました。 |
|  | [targetGlobalSettings()](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/targetglobalsettings.html?lang=ja){target=_blank} | `viewsEnabled` の説明を更新しました。 |
|  | [シングルページアプリケーションの実装](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/deploy-at-js/target-atjs-single-page-application.html?lang=ja){target=_blank} | 次の更新を行いました。<ul><li>「Adobe Target ビューの実装」の手順 2 の後にメモを追加しました。</li><li>「最初のページ読み込みの操作の順序」の手順 2「Target リクエストを実行」を更新しました。</li></ul> |
| 5月4日（PT） | [Adobe Target API の認証の設定](https://experienceleague.adobe.com/docs/target-dev/developer/api/configure-authentication.html?lang=ja){target=_blank} | JWT 資格情報から OAuth サーバー間の資格情報に移行する必要があることを説明するメモを追加しました。 |
| 5月3日（PT） | [レポートの表示 - A4T FAQ](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-viewing-reports.md#activity-impressions) | 以下の FAQ を追加しました。<ul><li>[!UICONTROL Analytics for Target]（A4T）を使用している場合、[!DNL Analysis Workspace] でアクティビティのインプレッションを追跡するにはどうすればよいですか？</li></ul> |
| 4月26日（PT） | [AEM [!UICONTROL エクスペリエンスフラグメント]および[!UICONTROL コンテンツフラグメント]の概要](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md) | [!UICONTROL AEM コンテンツフラグメント]機能を、すべての [!DNL Target customers] で利用できるようになりました。 |
|  | [[!UICONTROL AEM コンテンツフラグメント]](/help/main/c-integrating-target-with-mac/aem/content-fragments-aem.md) | [!UICONTROL AEM コンテンツフラグメント]機能を、すべての [!DNL Target customers] で利用できるようになりました。 |
|  | [*Adobe Target デベロッパーガイド*](https://experienceleague.adobe.com/docs/target-dev/developer/overview.html?lang=ja){target=_blank} | *Adobe Target デベロッパーガイド*&#x200B;は、*[!UICONTROL Adobe Experience League]* に移動されました。*[!UICONTROL Experience League]* への移行により、追加言語でのテキストのローカライゼーションが簡単になり、*Experience League* 内の検索が統合されて、*[!UICONTROL Adobe Target ビジネス実践者ガイド]*&#x200B;と *[!UICONTROL Adobe Target デベロッパーガイド]*&#x200B;の両方からの検索結果が提供され、追加のメリットが得られます。<P>以前の場所から *[!UICONTROL Experience League]* へと自動的にリダイレクトされます。必要に応じてブックマークを更新してください。 |
| 4月24日（PT） | [[!DNL Adobe Target]  のお知らせとイベント](/help/main/r-release-notes/target-announcements.md) | 次の Adobe Target コミュニティコーヒーブレーク Q＆A に関する情報を追加しました。<ul><li>認証済み環境向けのモバイルエクスペリエンスの最適化とパーソナライゼーション</li></ul> |
|  | [Target リリースノート（現行）](/help/main/r-release-notes/release-notes.md) | [!DNL Target Standard/Premium] 23.4.1 リリースに関するリリースノートを追加しました。 |

## [!DNL Target] Standard／Premium 23.3.1（2023年3月28～30日（PT））

| 日付 | トピック | 変更点 |
| --- | --- | --- |
| 4月19日（PT） | [[!UICONTROL 場所の貢献度]レポート（MVT）](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md) | メモの情報を更新しました。 |
| 4月13日（PT） | [[!DNL Target] リリースノート（プレリリース）](/help/main/r-release-notes/target-release-notes.md) | [!DNL Target] Standard／Premium 23.4.1 リリース（2023年4月25～27日（PT））に関する情報を追加しました。 |
| 4月12日（PT） | [[!DNL Adobe Target]  のお知らせとイベント](/help/main/r-release-notes/target-announcements.md) | 以下のウェビナーに登録するためのリンクを追加しました。<ul><li>毎回パーソナライズされた顧客体験を提供しましょう</li></ul> |
|  | [重要な属性レポート](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md#models-api) | 以下の FAQ を追加しました。<ul><li>モデルでトレーニングに使用する必要がない属性が 1 つ以上表示されます。これらの属性をトレーニングモデルから削除できますか？</li></ul> |
|  | [Enterprise ユーザーの権限](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#multiple-roles) | 以下の FAQ を追加しました。<ul><li>ユーザーに複数の役割と権限がある場合はどうなりますか？</li></ul> |
|  | [AEM コンテンツフラグメント](/help/main/c-integrating-target-with-mac/aem/content-fragments-aem.md) | 新規トピックです。この機能は、テスト目的で「プレリリース」ステータスになっています。 |
| 4月5日（PT） | [オファーの決定の使用](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md) | [!UICONTROL レポートソースとしての Analytics]（A4t）は、オファーの決定を使用するアクティビティではサポートされていないことを示すテキストを追加しました。 |
| 4月3日（PT） | [[!DNL Adobe Target]  のお知らせとイベント](/help/main/r-release-notes/target-announcements.md) | 2023年4月12日水曜日（PT）に予定されている [!UICONTROL Adobe Target コミュニティ]のコーヒーブレイクに関する情報を追加しました。 |
|  | [Target のエッジノードを許可リストに登録](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/privacy/allowlist-edges.html?lang=ja){target=_blank} | [!DNL Adobe Analytics] のすべての IP アドレスブロックを許可リストに登録するためのメモを追加しました。 |
| 3月30日（PT） | [Target リリースノート（最新）](/help/main/r-release-notes/release-notes.md) | [!UICONTROL 自動配分]および[!UICONTROL 自動ターゲット]機能用に最適化された A4T 指標のリリースに関するリリースノートを更新しました。これにより、[!UICONTROL 自動配分]および[!UICONTROL 自動ターゲット]アクティビティに [!UICONTROL A4T] を使用する際に、二項イベントに基づく指標または連続イベントに基づく指標を選択できます。 |
|  | [[!UICONTROL 自動配分]と[!UICONTROL 自動ターゲット]アクティビティに対する A4T のサポート](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md#supported) | 更新された「サポート対象の目標指標」の節には、[!UICONTROL Analytics for Target]（A4T）を使用した[!UICONTROL 自動配分]および[!UICONTROL 自動ターゲット]アクティビティ用のサポート対象（およびサポート対象外）の指標に関する情報が含まれます。 |
|  | [Adobe Target チュートリアル](https://experienceleague.adobe.com/docs/target-learn/tutorials/overview.html?lang=ja){target=_blank} | 次のチュートリアルを更新しました。<ul><li>[ [!DNL Analysis Workspace]  での[!UICONTROL 自動配分]アクティビティ用 A4T レポートの設定](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html?lang=ja){target=_blank}</li><li>[ [!DNL Analysis Workspace]  での [!UICONTROL 自動ターゲット]アクティビティ用 A4T レポートの設定](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html?lang=ja){target=_blank}</li></ul> |
|  | [Target リリースノート（プレリリース）](/help/main/r-release-notes/target-release-notes.md) | [!DNL Adobe Experience Manager]（AEM）および [!DNL Adobe Target] [!UICONTROL コンテンツフラグメント]のリリースに関する情報を追加しました。（2023年4月6日（PT）） |
| 3月28日（PT） | [Target リリースノート（現行）](/help/main/r-release-notes/release-notes.md) | [!DNL Target Standard/Premium] 23.3.1 リリースに関するリリースノートを追加しました。 |

## [!DNL Target]Standard／Premium 22.15.1（2023年3月8日、9日）

| 日付 | トピック | 変更点 |
| --- | --- | --- |
|  | [アクティビティを編集またはドラフトとして保存](/help/main/c-activities/edit-activity.md) | 「ベストプラクティス」セクションを追加しました。 |
|  | [変更](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md) | 「カスタムコードのトラブルシューティング」セクションに次の注意事項を追加しました。<ul><li>オプションとして `{page: false}` を使用して `triggerView()` が呼び出される場合、VEC のカスタムコードオファーは再レンダリングされません。</li></ul> |
|  | [Target リリースノート（現行）](/help/main/r-release-notes/release-notes.md) | at.js 2.10.2 リリースに関する情報を追加しました。 |
|  | [Target リリースノート（現行）](/help/main/r-release-notes/release-notes.md) | [!DNL Target Standard/Premium] 22.15.1 リリースに関するリリースノートを追加しました。 |

## [!DNL Target] Standard／Premium 22.13.3（2023年1月25日（PT））

| 日付 | トピック | 変更点 |
| --- | --- | --- |
| 2月21日（PT） | [Target のエッジノードを許可リストに登録する](https://experienceleague.corp.adobe.com/docs/target-dev/developer/implementation/privacy/allowlist-edges.html?lang=ja){target=_blank} | [Adobe Target 開発者ガイド](https://experienceleague.corp.adobe.com/docs/target-dev/developer/overview.html?lang=ja){target=_blank}で、すべての地域の許可リストに対する IP アドレスのリストを更新しました。 |
|  | [変更](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md) | JQuery を使用した例では、[!DNL Target] がオファーを実行する際に、顧客の web サイトのページで jQuery が使用可能であることを前提としていることを説明するテキストを追加しました。 |
| 2月10日（PT） | [Target リリースノート（現行）](/help/main/r-release-notes/release-notes.md) | [!DNL Target Standard/Premium] 22.14.5 リリースに関するリリースノートを追加しました。 |
| 2月8日（PT） | [Target リリースノート（現行）](/help/main/r-release-notes/release-notes.md) | at.js 2.10.1 のリリースノートを追加しました。 |
| 2月2日（PT） | [Visual Experience Composer に関連する問題のトラブルシューティング](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshooting-issues-related-to-the-visual-experience-composer-vec.md#section_FA2A18E8FD6A4274B2E395DBAA2FB407) | 以下の節が更新されました。<ul><li>参照モードを使用すると、VEC が壊れているように見える</li></ul> |
|  | [Target でのオーディエンスの構築](/help/main/c-target/c-audiences/create-audience.md) | オーディエンス名で使用できない文字と文字シーケンスのリストを追加しました。 |
| 1月31日（PT） | [制限](/help/main/r-troubleshooting-target/target-limits.md#mbox-names) | mbox 名に使用できる文字と使用できない文字のリストを追加しました。 |
| 1月25日（PT） | [JSON オファーの作成](/help/main/c-experiences/c-manage-content/create-json-offer.md) | フォームベースの Experience Composer を使用した [!UICONTROL Automated Personalization]（AP）アクティビティでの JSON オファーのサポートが利用可能になったことを示しました。 |
|  | [Adobe Target のお知らせとイベント](/help/main/r-release-notes/target-announcements.md) | 以下のイベントに関する情報を追加しました。<ul><li>[!DNL Adobe Target] コミュニティ Q＆A コーヒーブレーク：エクスペリエンスの最適化のためのモバイルおよび認証済みのユースケース</li></ul> |
|  | [Target リリースノート（現行）](/help/main/r-release-notes/release-notes.md) | [!DNL Target Standard/Premium] 22.13.3 リリースに関するリリースノートを追加しました。 |
