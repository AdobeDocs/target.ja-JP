---
description: 以下のリリースノートでは、Target Standard および Target Premium の各リリースの機能、機能強化、修正および既知の問題について説明します。
keywords: リリースノート；新機能；リリース；更新；更新；リリース；機能強化；修正；バグ修正
seo-description: これらのリリースノートでは、Adobe Target Standard および Target Premium の各リリースの機能、機能強化、修正および既知の問題について説明します。
seo-title: 'Adobe Target リリースノート（現行） '
solution: 'Target '
title: Target リリースノート（現行）
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: 71d94ef5d2351dc8410c0d418096088a0a900f03

---


# Target リリースノート（現行）{#target-release-notes-current}

これらのリリースノートでは、Target Standard と Target Premium の各リリースの機能、機能強化および修正点について説明します。また、Target API、SDK、JavaScriptライブラリ(at.js)およびその他のプラットフォームの変更に関するリリースノートも、該当する場合は含まれます。

## Targetプラットフォーム（2019年10月9日）

| 機能／拡張機能 | 説明 |
| --- | --- |
| Node.js SDKバージョン1.0 | Target Node.js SDKを使用すると、Targetサーバー側をデプロイできます。<br>このNode.js SDKを使用すると、TargetをAdobe Experience Cloud Identity Service、Adobe Analytics、Adobe Audience Managerなどの他のExperience cloudソリューションと簡単に統合できます。<br>Node.js SDKは、アドビの配信APIを使用してAdobe targetと統合する際に、ベストプラクティスを導入し、複雑さを排除して、エンジニアリングチームがビジネスロジックに集中できるようにします。 最新バージョンで導入される主な機能は次のとおりです。<ul><li>キャッシュを使用してパフォーマンスを最適化できるプリフェッチと通知のサポート。</li><li>Webページとサーバー側の両方でTargetをハイブリッド統合している場合のパフォーマンス最適化のサポート。 at.js 2.2がエクスペリエンスを取得するための追加のサーバー呼び出しを行わないように、サーバー側で取得したエクスペリエンスによって設定されるという設定が導入されます。 `serverState` このアプローチは、ページ読み込みのパフォーマンスを最適化します。</li><li> 新しい配信APIで可能になった、Node.js SDKを介したVECで作成されたアクティビティの取得のサポート。</li><li>開発者がNode.js SDKに貢献できるように、オープンソースです。</li></ul><br>詳しくは、リリースノー [ト — Target Node.js SDKを参照してください](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md)。 |
| 配信API | 完全に新しい配信APIエンドポイント（/v1/配信）が実稼働環境で使用できます。 主な機能は次のとおりです。<ul><li>1つ以上のmboxのエクスペリエンスを取得するための1つのエンドポイント。</li><li>APIを使用してVECで作成されたアクティビティを取得します。</li><li>シングルページアプリ(SPA)およびモバイルアプリケーションで使用されるビューと呼ばれる、まったく新しいオブジェクトのサポート。</li></ul><br>詳しくは、リリースノート — [Targetサーバー側APIを参照してください](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md)。 |

## Target Standard/Premium 19.9.2（2019 年 9 月 30 日）

このメンテナンスリリースで強化された機能は次のとおりです。

* Visual Experience Composer（VEC）のリッチテキストエディター（RTE）に対するセキュリティ更新を含む、いくつかのセキュリティを修正しました。（TGT-35383）
* A/Bテストとエクスペリエンスのターゲット設定アクティビティで、DIVに加えて、DIV以外の要素（P、UL、H1など）にレコメンデーションオファーを追加できるようになりました。 （TGT-34333）
* イベント通知（Target UIのベルのアイコン）は使用できなくなりました。 通知の新しいルックが近日公開されます。

## Target Standard/Premium 19.9.1（2019 年 9 月 10 日）

| 機能／拡張機能 | 説明 |
| --- | --- |
| ![Premiumバッジ](/help/assets/premium.png) Enterprise権限 | Target 2019年9月のリリースでは、Enterprise Permissionsで次のアクセス制御を利用できます。<UL><li>統合を適用できるワークスペースを選択できます。</li><li>Adobe I/O 統合（承認者、編集者または監視者）に役割を適用できます。</li></ul>操作手順と詳細情報については、[ワークスペースに対する Adobe I/O 統合のアクセス権の付与と役割の割り当て](/help/administrating-target/c-user-management/property-channel/configure-adobe-io-integration.md)を参照してください。 |

## その他のリリースノートとバージョンの詳細

| リソース | 詳細 |
|--- |--- |
| [リリースノート — Targetサーバー側API](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md) | Adobe targetのサーバー側APIに関するリリースノートです。 |
| [リリースノート — Target Node.js SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md) | Adobe targetのNode.js SDKに関するリリースノートです。 |
| [at.js のバージョンの詳細](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) | Adobe Target at.js javaScriptライブラリの各バージョンの変更に関する詳細。 |
| [mbox.js のバージョンの詳細](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mboxjs-change-log.md) | このページには、mbox.js の各バージョンに対する変更が表示されます。<br>mbox.jsライブラリは開発されなくなります。 すべてのお客様が mbox.js から at.js に移行する必要があります。 |

## ドキュメントの変更、過去のリリースノートおよび Experience Cloud リリースノート {#section_1BC5F5208DA548E9B4344A0836E4B943}

追加情報については、各リリースのリリースノートに加えて、以下のリソースを参照してください。

| リソース | 詳細 |
|--- |--- |
| ドキュメントの変更点 | リリースノートに含まれない可能性のある、このガイドの更新点に関する詳細情報が表示されます。<br>詳しくは、「[ドキュメントの変更](../r-release-notes/doc-change.md#reference_366123CF00994BACBBF9BBDF2C4D840C)」を参照してください。 |
| 以前のリリースのリリースノート | 以前のリリースの Target Standard および Target Premium の新機能および機能拡張に関する情報を確認してください。<br>詳しくは、「[以前のリリースのドキュメントの変更](../r-release-notes/release-notes-for-previous-releases.md)」を参照してください。 |
| Adobe Experience Cloud リリースノート | Adobe Experience Cloud ソリューションの最新のリリースノートが表示されます。<br>詳しくは、 [Experience cloudリリースノートを参照してください](https://docs.adobe.com/content/help/en/release-notes/experience-cloud/current.html)。 |

## プレリリース情報 {#section_5D588F0415A2435B851A4D0113ACA3A0}

次のリソースでは、次の Target リリースの内容を確認できます。

| リソース | 詳細 |
|--- |--- |
| Adobe Priority Product Update リスト | Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority 製品アップデート（<br>[](https://www.adobe.com/subscription/priority-product-update.html)https://www.adobe.com/subscription/priority-product-update.html）にサインアップします。 |
| 今後のリリースノート | プレリリース情報など今月の Target リリースについては、[Target リリースノート - プレリリース](/help/r-release-notes/target-release-notes.md)ページを参照してください。 |
