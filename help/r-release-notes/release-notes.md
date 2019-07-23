---
description: 以下のリリースノートでは、Target Standard および Target Premium の各リリースの機能、機能強化、修正および既知の問題について説明します。
keywords: リリースノート、プレリリース版
seo-description: これらのリリースノートでは、Adobe Target Standard および Target Premium の各リリースの機能、機能強化、修正および既知の問題について説明します。
seo-title: Adobe Targetリリースノート（現在）
solution: 'Target '
title: Target リリースノート（現行）
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: 2cc1918610950ea8474def526d9596ec709456a2

---


# Target リリースノート（現行）{#target-release-notes-current}

これらのリリースノートでは、Target Standard と Target Premium の各リリースの機能、機能強化および修正点について説明します。

## Target Standard／Premium 19.7.1（2019 年 7 月 24 日）{#tgt-19-7-1}

このリリースには、次の新機能および機能強化が含まれています。

（括弧内の問題番号はアドビ社内で使用されます。）

| 機能／拡張機能 | 説明 |
| --- | --- |
| モバイルアプリケーション Visual Experience Composer | Mobile App VECに、クリック追跡用に設定した要素を表示する新しい変更パネルが表示されます。(TGT-31741)<br> See [Set up click tracking in the Mobile App](/help/c-target-mobile-app/c-mobile-visual-experience-composer/set-up-click-tracking-in-the-mobile-vec.md). |
| ![A/Bテストおよびエクスペリエンスターゲット設定（XT）アクティビティ](/help/assets/premium.png)<br>のプレミアムバッジ | Recommendationsオファー（アルゴリズム）のステータスは、Recommendationsオファーを含むA/BテストおよびXTアクティビティの概要ページに表示されます。次のようなステータスがあります。結果準備完了、結果が準備されていない、フィード失敗。(TGT-33649)<br>See [Recommendations as an offer](/help/c-recommendations/recommendations-as-an-offer.md#status). |
| Experience Cloud ID（ECID）ライブラリを使用したat. js2.0以降のクロスドメイントラッキングサポート | 以前は、クロスドメイントラッキングはat. js2ではサポートされていませんでした。*x*. このリリースでは、at. js2.0以上を使用するお客様は、ECIDライブラリを通じてクロスドメイントラッキングを利用できるようになりました。クロスドメイントラッキングを機能させるには、ページにEIDライブラリをat. js2.0以上と組み合わせてインストールする必要があります。[Experience Cloud IDライブラリ4.3.0以降を使用する](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-release-notes.html) 必要があります。<br>at. js2. xの [クロスドメイントラッキングのサポート](/help/c-implementing-target/c-implementing-target-for-client-side-web/upgrading-from-atjs-1x-to-atjs-20.md#cross-domain)を参照してください。 |
| Experience Cloud ID（ECID）ライブラリ4.3を使用したAppleのTP2.1およびITP2.2のTargetサポート | 今日、Targetのお客様は、アドビのCNAME認定プログラムを利用してAppleのTP2.1およびITP2.2を軽減することができます。<br>このリリースでは、Targetは、EIDライブラリ4.3とシームレスに統合して、サーバー側のcookieを利用してITP2.1およびITP2.2を軽減します。TargetのJavaScriptライブラリと共に [EIDライブラリ4.3以上](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-release-notes.html) をデプロイして将来のASTリリースを緩和することを強くお勧めします。EIDライブラリは、ブラウザーによって導入されるCookieポリシーの変更に堅牢なソリューションを提供する、ロールアウト機能の強化を継続します。<br>[Apple Intelligent Tracking Prevention（ITP）2. xを参照](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md)してください。 |

**機能強化、修正、変更点**

* 重複値を追加するとRecommendationsアクティビティの除外値がクリアされない問題を修正しました。（TGT-34996）
* ターゲットページから、Recommendationsアクティビティのデザインを削除できるようになりました（3つのガイドによるワークフローの手順2）。デザインを削除するには、複数のデザインが選択されている必要があります。（TGT-35118）
* 一部の顧客がTarget UIで適切に読み込まれるか、編集可能になるためにカスタム条件カードが使用できない問題を修正しました。（TGT-35170）

## at. jsバージョン2.1.1（2019年7月24日）

at. jsのこのリリースはメンテナンスリリースであり、次の機能強化および修正が含まれています。

（括弧内の問題番号はアドビ社内で使用されます。）

* Visual Experience Composer（VEC）の目標と設定ページの「クリック追跡」指標を使用すると、複数のビーコンが起動する問題を修正しました。（TNT-32812）
* Fixed an issue that caused `triggerView()` to not render offers more than once. （TNT-32780）
* Fixed an issue with `triggerView()` to ensure that the request contains Marketing Cloud ID (MCID) information. （TNT-32776）
* Fixed an issue that prevented the `triggerView()` notification to fire even if there are no saved views. （TNT-32614）
* URLに形式設定されたクエリ文字列パラメーターが含まれていると、DecodeURIComponentの使用によってエラーが発生する問題を修正しました。（TNT-32710）
* `Navigator.sendBeacon()` API経由で送信される配信リクエストのコンテキストで、ビーコンフラグが"true"に設定されるようになりました。（TNT-32683）
* 数名の顧客のWebサイトにRecommendationsオファーが表示されない問題を修正しました。お客様は、配信API呼び出しでオファーコンテンツを表示できますが、オファーはWebサイトに適用されませんでした。（TNT-32680）
* 複数のエクスペリエンスにわたるクリック追跡が期待どおりに動作しない問題を修正しました。（TNT-32644）
* 最初の指標のレンダリングに失敗した後に、at. jsが2番目の指標を適用できない問題を修正しました。（TNT-32628）
* `mboxThirdPartyId``targetPageParams` リクエストのペイロードがクエリパラメーターまたはリクエストのペイロードに存在しない場合に、リクエストのペイロードが送信されない問題を修正しました。（TNT-32613）
* Chromeベースのブラウザー（Google Chromeを含む）で表示およびクリック通知応答がブロックされる問題を修正しました。（TNT-32290）

For information about this and previous versions of at.js, see [at.js version details](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md).

## ドキュメントの変更、過去のリリースノートおよび Experience Cloud リリースノート {#section_1BC5F5208DA548E9B4344A0836E4B943}

追加情報については、各リリースのリリースノートに加えて、以下のリソースを参照してください。

| リソース | 詳細 |
|--- |--- |
| ドキュメントの変更点 | リリースノートに含まれない可能性のある、このガイドの更新点に関する詳細情報が表示されます。<br>詳しくは、「[ドキュメントの変更](../r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C)」を参照してください。 |
| 以前のリリースのリリースノート | 以前のリリースの Target Standard および Target Premium の新機能および機能拡張に関する情報を確認してください。<br>詳しくは、「[以前のリリースのドキュメントの変更](../r-release-notes/release-notes-for-previous-releases.md)」を参照してください。 |
| Adobe Experience Cloud リリースノート | Adobe Experience Cloud ソリューションの最新のリリースノートが表示されます。<br>詳しくは [、Experience Cloudリリースノート](https://marketing.adobe.com/resources/help/en_US/whatsnew/)を参照してください。 |

## プレリリース情報 {#section_5D588F0415A2435B851A4D0113ACA3A0}

次のリソースでは、次の Target リリースの内容を確認できます。

| リソース | 詳細 |
|--- |--- |
| Adobe Priority Product Update リスト | Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority 製品アップデート（<br>[](https://www.adobe.com/subscription/priority-product-update.html)https://www.adobe.com/subscription/priority-product-update.html）にサインアップします。 |
| 今後のリリースノート | プレリリース情報など今月の Target リリースについては、[Target リリースノート - プレリリース](/help/r-release-notes/target-release-notes.md)ページを参照してください。 |