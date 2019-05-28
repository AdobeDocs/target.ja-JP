---
description: これらのリリースノートでは、最新または今後の Target リリースの機能、機能強化、修正および既知の問題について説明します。
keywords: リリースノート
seo-description: これらのリリースノートには、最新または今後のAdobe Targetリリースの機能、機能強化、修正および既知の問題に関する情報が記載されています
seo-title: Target リリースノート（プレリリース）
solution: 'Target '
title: Target リリースノート（プレリリース）
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 9f1cab87057a7b8803f795c852a7ffe839dd8f1c

---


# Target リリースノート（プレリリース）{#target-release-notes-prerelease}

これらのリリースノートでは、最新または今後 [!DNL Adobe Target] のリリースの機能、機能強化および修正点について説明しています。

**最終更新日：2019 年 5 月 28 日**

>[!NOTE]
>
>これらのリリースノートには、プレリリース情報が含まれています。リリース日、機能などの情報は、変更されることがあります。現在のリリースに関する情報を表示するには [、Targetリリースノート](release-notes.md)を参照してください。これらのページの情報は、リリースのタイミングによって異なる場合があります。

## at. jsバージョン2.1.0（2019年6月3日）

at. js2.1.0では、以下のエキサイティングな機能をお知らせします。

| 機能/拡張機能 | 説明 |
| --- | --- |
| アドビオプトインサポート | アドビオプトインは、アドビソリューション統合を、同意管理プラットフォームと単純化するための手段です。<br>アドビのオプトインについて詳しくは [、プライバシーおよび一般的なデータ保護規則（GGPR）](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md)を参照してください。 |
| 業界標準CSP準拠 | at. jsは、eval（）を使用してJavaScriptを実行しなくなりました。 |
| クライアント側の分析ログ | 顧客側またはサーバー側でAnalyticsデータをAdobe Analyticsに送信する方法をユーザーが自由に制御できます。 |
| 通知の送信 | エクスペリエンスが使用 `applyOffer()` せずにコードによってレンダリングされたときに、開発者が通知を送信できるように `applyOffers()`します。 |
| ファイルサイズの削減 | at. jsのサイズは24%減少します。ファイルサイズが小さければページの読み込みパフォーマンスが向上し、ページにat. jsをダウンロードする時間が短縮されます。 |

## [!DNL Target] Standard/Premium19.5.1（2019年5月22日） {#release-19-5-1-prerelease}

このリリースには、次の機能、変更点、および機能強化が含まれています。

（括弧内の問題番号は [!DNL Adobe] 内部で使用されます）。

### 機能の更新

| 機能/拡張機能 | 説明 |
| --- | --- |
| シングルページアプリケーションの Visual Experience Composer（SPA VEC） | SPA VEC に、作業を高速化または効率化するための以下の機能が追加されました。<ul><li>SPA内のアクションをクリックすると、このアクションが適用されるサイト上の要素が強調表示されます。ビューで作成される各VECアクションには、対応する4つのアイコンがあります。情報、編集、移動および削除。このリリースで新しい「移動」機能を使用すると、変更パネルにあるページ読み込みイベントまたはその他の表示にアクションを移動できます。（TGT-33746）</li><li>VEC でページがロードされる前や、ページを読み込めなかった場合（例えば、カスタムコードが動作しなくなった場合など）には、様々なアクションを実行できます。サイト読み込み前に編集できないアクションは、Target UI では無効化されます。（TGT-33851 および TGT-34149）</li></ul>詳細については、「[シングルページアプリケーション（SPA）の Visual Experience Composer](/help/c-experiences/spa-visual-experience-composer.md)」を参照してください。 |

### 機能強化、修正、変更点

* VEC 内でページの読み込みをキャンセルした後、ツールバーアイコンが適切に表示されます。ページが完全に読み込まれるまで特定の操作が実行できない場合、関連するツールバーアイコンが無効になります。（TGT-33811）

## Mobile App Visual Experience Composer（2019年5月14日）{mobile- vec}

| 機能/拡張機能 | 説明 |
| --- | --- |
| Mobile App Visual Experience Composer（VEC） | Mobile App VECを使用すると、継続的な開発依存関係やアプリリリースサイクルを使用せずに、アクティビティを作成し、ネイティブモバイルアプリケーションにコンテンツをパーソナライズできます。<br>詳しくは、以下を参照してください。<ul><li>[モバイルアプリケーション Visual Experience Composer](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md)</li><li>[Android - モバイルアプリケーションのセットアップ](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer-android.md)</li><li>[iOS - モバイルアプリケーションのセットアップ](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer-ios.md)</li><li>[モバイル VEC でのクリック追跡のセットアップ](/help/c-target-mobile-app/c-mobile-visual-experience-composer/set-up-click-tracking-in-the-mobile-vec.md)</li><li>[ビデオ:Mobile App Visual Experience Composer](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md#video)</li></ul> |

## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Targetおよびその他のAdobe Experience Cloudソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Updateにサインアップします。

[https://adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
