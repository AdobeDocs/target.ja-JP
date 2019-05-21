---
description: 以下のリリースノートでは、Target Standard および Target Premium の各リリースの機能、機能強化、修正および既知の問題について説明します。
keywords: リリースノート、プレリリース版
seo-description: これらのリリースノートでは、Adobe Target Standard およびTarget Premiumの各リリースの機能、機能強化、修正および既知の問題について説明します。
seo-title: Target リリースノート（現行）
solution: 'Target '
title: Target リリースノート（現行）
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: dda07f19bddb870b20dabc484a1b97d55bcc5775

---


# Target リリースノート（現行）{#target-release-notes-current}

これらのリリースノートでは、Target Standard と Target Premium の各リリースの機能、機能強化および修正点について説明します。

## 発表

以下の重要なお知らせに注意してください。

* 2019年2月21日に、ヨーロッパ、日本、APACの各地域でAdobe Targetインフラストラクチャがアップグレードされ、TLS1.1以降をサポートしていない古いデバイスまたはWebブラウザーを使用したエンドユーザーからデータを収集することがなくなりました。このアップグレードは、2019年4月1日の **北米地域向けに予定**されています。TLS 1.2 への移行により、セキュリティが向上します。重要なのは、詳細を調べて、スムーズな移行を実現するためにITチームによる変更を計画することです。詳しくは [、TLS（Transport Layer Security）暗号化の変更](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md)を参照してください。
* [!DNL Target] と [!DNL Adobe Marketing Cloud] は、2019 年 3 月に Microsoft Internet Explorer 11 のサポートを終了します。この変更は [!DNL Target] オーサリングにのみ影響します。この変更は、エクスペリエンス配信に影響しません。Microsoft Edge か別のブラウザーに切り替えてください。詳しくは、「[サポートされているブラウザー](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md)」を参照してください。

## [!DNL Target] Standard/Premium19.5.1（2019年5月22日） {#tgt-19-5-1}

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
| Mobile App Visual Experience Composer（VEC） | Mobile App VECを使用すると、継続的な開発依存関係やアプリリリースサイクルを使用せずに、アクティビティを作成し、ネイティブモバイルアプリケーションにコンテンツをパーソナライズできます。<br>詳しくは、以下を参照してください。<ul><li>[モバイルアプリケーション Visual Experience Composer](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md)</li><li>[Android - モバイルアプリケーションのセットアップ](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer-android.md)</li><li>[iOS - モバイルアプリケーションのセットアップ](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer-ios.md)</li><li>[モバイル VEC でのクリック追跡のセットアップ](/help/c-target-mobile-app/c-mobile-visual-experience-composer/set-up-click-tracking-in-the-mobile-vec.md)</li></ul> |

## ドキュメントの変更、過去のリリースノートおよび Experience Cloud リリースノート {#section_1BC5F5208DA548E9B4344A0836E4B943}

追加情報については、各リリースのリリースノートに加えて、以下のリソースを参照してください。

| リソース | 詳細 |
|--- |--- |
| ドキュメントの変更点 | リリースノートに含まれない可能性のある、このガイドの更新点に関する詳細情報が表示されます。<br>詳しくは [、「ドキュメントの変更](../r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C)」を参照してください。 |
| 以前のリリースのリリースノート | 以前のリリースの Target Standard および Target Premium の新機能および機能拡張に関する情報を確認してください。<br>詳しくは、以前のリリースの [リリースノート](../r-release-notes/release-notes-for-previous-releases.md)を参照してください。 |
| Adobe Experience Cloud リリースノート | Adobe Experience Cloud ソリューションの最新のリリースノートが表示されます。<br>詳しくは [、Experience Cloudリリースノート](https://marketing.adobe.com/resources/help/en_US/whatsnew/)を参照してください。 |

## プレリリース情報 {#section_5D588F0415A2435B851A4D0113ACA3A0}

次のリソースでは、次の Target リリースの内容を確認できます。

| リソース | 詳細 |
|--- |--- |
| Adobe Priority Product Update リスト | Targetおよびその他のAdobe Experience Cloudソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Updateにサインアップします。<br>[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html) |
| 今後のリリースノート | プレリリース情報など今月の Target リリースについては、[Target リリースノート - プレリリース](/help/r-release-notes/target-release-notes.md)ページを参照してください。 |