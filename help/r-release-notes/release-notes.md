---
keywords: リリースノート；新機能；リリース；更新；更新；リリース；機能強化；修正；バグ修正
description: これらのリリースノートでは、Adobe Target Standard および Target Premium の各リリースの機能、機能強化、修正および既知の問題について説明します。
title: 'Adobe Target リリースノート（現行） '
topic: Recommendations
uuid: f6c3e64d-de1e-416c-a56f-2122a58b613e
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Target リリースノート（現行）{#target-release-notes-current}

これらのリリースノートでは、Target Standard と Target Premium の各リリースの機能、機能強化および修正点について説明します。また、Target API、SDK、JavaScriptライブラリ(at.js)およびその他のプラットフォームの変更に関するリリースノートも、該当する場合は含まれます。

括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

## Targetプラットフォーム（2019年10月31日）

| 機能／拡張機能 | 説明 |
| --- | --- |
| Java SDK | Java SDKを使 [!DNL Target] 用すると、サーバー側 [!DNL Target] をデプロイできます。 このJava SDKを使用すると、、、などの他のソ [!DNL Target] リューシ [!DNL Adobe Experience Cloud] ョンとの統合を簡単に [!DNL Adobe Experience Cloud Identity Service]行うこ [!DNL Adobe Analytics]とができま [!DNL Adobe Audience Manager]す。<br>Java SDKは、アドビの配信APIを使用して統合する際に、ベストプラクティスを導入し、複雑 [!DNL Target] さを排除して、エンジニアリングチームがビジネスロジックに焦点を当てられるようにします。 最新バージョンで導入される主な機能は次のとおりです。<ul><li>キャッシュを使用してパフォーマンスを最適化できるプリフェッチと通知のサポート。</li><li>Webページとサーバー側の両方でのハイブリッド統合を使用する場合のパフ [!DNL Target] ォーマンスの最適化のサポートを追加しました。 at.js 2.2がエクスペリエンスを取得するための追加のサーバー呼び出しを行わないように、サーバー側で取得したエクスペリエンスによって設定されるという設定が導入されます。 `serverState` このアプローチは、ページ読み込みのパフォーマンスを最適化します。</li><li>Java SDKを使用したVECで作成されたアクティビティの取得のサポートが追加されました。これは、新しい配信APIで可能になりました。</li><li>開発者が [Target Java SDKに貢献できるように、オープンソースです](https://github.com/adobe/target-java-sdk)。</li></ul>詳しくは、リリースノート — [Target Java SDK（英語のみ）を参照してください](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md)。<br>新しいTarget Java SDKを使用したサーバ側の最適化に関するアドビ [のテクニカルブログ（英語）で詳しく説明します](https://medium.com/adobetech/server-side-optimization-with-the-new-target-java-sdk-421dc418a3f2)。 |

## Target Standard／Premium 19.10.2（2019 年 10 月 31 日）

| 機能／拡張機能 | 説明 |
| --- | --- |
| ![Premiumバッジ](/help/assets/premium.png) Multi-value Attributes | 複数の値を持つフィールドを使用する場合もあります。 次の例をご覧ください。<ul><li>ユーザに映画を提供する。 ある映画には複数の俳優がいる。</li><li>コンサートのチケットを売る。 特定のユーザーには、複数のお気に入りのバンドがあります。</li><li>あなたは服を売る。 1枚のシャツは複数のサイズで購入できます。</li></ul>これらのシナリオでのレコメンデーションを処理するには、複数値のデータをTarget Recommendationsに渡し、特別な複数値の演算子を使用します。<br>詳しくは、複数値の属 [性の操作を参照してください](/help/c-recommendations/c-algorithms/work-with-multi-value-attributes.md)。 |

## Target Standard／Premium 19.10.1（2019 年 10 月 22 日）

| 機能／拡張機能 | 説明 |
| --- | --- |
| ![Premiumバッジ](/help/assets/premium.png) User-Based Recommendations<br>（2019年10月25日） | 各訪問者の閲覧、閲覧、購入履歴に基づいて品目をレコメンドします。 これらの品目は、一般に「推奨」と呼ばれます。<br>この条件を使用すると、新規訪問者と再訪問者の両方に対して、パーソナライズされたコンテンツとエクスペリエンスを配信できます。 レコメンデーションのリストは、訪問者の最新のアクティビティに重み付けされ、セッション内で更新され、訪問者がサイトを閲覧するにつれて、よりパーソナライズされます。<br>詳しくは、条件/アルゴリズムの「ユーザーベースのレコメンデーション」 [を参照してください](/help/c-recommendations/c-algorithms/algorithms.md#criteria-algorithms)。 |

### Adobe Experience cloudのナビゲーション

* にログインすると、新しいヘ [!DNL Adobe Experience Cloud]ッダーナビゲーションが表示されます。 前のナビゲーションの上部に黒いバーが表示されているのと非常に似ていますが、次の点が改善されました。

   * (IMS)組織間 [!DNL Identity Management System] または別のソリューションへの切り替えが容易になりました。
   * ユーザーヘルプの改善：検索結果には、製品ドキュメントの結 [!DNL Target] 果、コミュニティフォーラムやビデオコンテンツなどが含まれ、より多くのコンテンツに簡単にアクセスして最大限の活用を図ることができま [!DNL Target]す。 また、ヘルプメニューにフィードバックのメカニズムが追加さ [!UICONTROL れ] 、問題の報告やアイデアの共有が簡単になりました。

   * ネットプロモータースコア(NPS)のフィードバック機能が改善され、調査モーダルが作業の流れを妨げないようになりました。
   * ログインフローが改善されました。 以前は、すべての顧客 [!DNL Target] はヘッダーのアイコンをクリックした後、Targetのランディングペ [!DNL Target] ージにランディングしました。 その後、このページでは、次のように、顧客が [!DNL Target Standard/Premium]、、、ま [!DNL Search&Promote]たは [!DNL Recommendations Classic]を進めることができました。

      ![ランディングページ](/help/r-release-notes/assets/landing.png)

      このランディングページをすべてのお客様に対して削除しました。 新しいヘッダーナビゲーションバーのアイコンをクリ [!UICONTROL ックすると] 、常にアクティビティリスト [!DNL Target] ページに直接移動するようになりました。

      使用する場合は、 [!DNL Recommendations Classic]次に示すように、ソリューションに直接移動するか、「 [!UICONTROL Recommendations] 」タブで作成した短いリンクから移動できます。

      ![Recs Classicディープリンク](/help/r-release-notes/assets/recs-classic.png)

      使用する場 [!DNL Search&Promote]合は、 [Search&amp;Promote URL](https://center.atomz.com/center/?ims=1) (https://center.atomz.com/center/?ims=1)に直接移動する必要があります。 の内側から到達す [!DNL Search&Promote] るパスが完全 [!DNL Adobe Target] に削除されました。

   * の通知は、現 [!DNL Target] 在、ヘッダーの「通知  」ドロップダウンでは使用できません。
   >[!NOTE]
   >
   >これらの機能は一度に展開されたり、すべての顧客に一括して展開されることはありません。 これらの機能は、 [!DNL Target Standard/Premium] 19.10.1（2019年10月22日）リリースから、今後数週間のうちに公開されます。
   >
   >新しいナビゲーションバーの展開の一部として、URLの変化にも気付きます。 以前にブックマークされたリンクは、引き続き機能しますが、すばやく開くために新しいリンクをブックマークすることをお勧めします。

## at.jsバージョン2.2および1.8（2019年10月11日）

| 機能／拡張機能 | 説明 |
| --- | --- |
| at.jsバージョン2.2<br><br>およびat.jsバージョン1.8 | at.jsの次のバージョンは、<ul><li>WebページでExperience Cloud IDサービス(ECID)v4.4とat.js 2.2またはat.js 1.8の両方を使用する場合のパフォーマンスが向上しました。</li><li>以前は、at.jsがエクスペリエンスを取得する前に、ECIDは2回のブロック呼び出しを行いました。 これは1回の呼び出しに短縮され、パフォーマンスが大幅に向上しました。</li></ul> これらのパフォーマンス改善を活用するには、ECIDライブラリv4.4.<br>at.js 2.2と共にat.js 2.2またはat.js 1.8にアップグレードします。<ul><li>**serverState**:at.js v2.2以降で使用できる設定で、Targetのハイブリッド統合が実装されている場合に、ページのパフォーマンスを最適化するために使用できます。 ハイブリッド統合とは、クライアント側でat.js v2.2以降と、サーバー側で配信APIまたはTarget SDKの両方を使用してエクスペリエンスを配信することです。 `serverState` は、at.js v2.2以降で、サーバー側で取得されたコンテンツからエクスペリエンスを直接適用し、提供されるページの一部としてクライアントに返す機能を提供します。<br>詳しくは、targetGlobalSettingsの「serverState」を参照してく [ださい](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#server-state)。</li></ul> |

## Targetプラットフォーム（2019年10月9日）

| 機能／拡張機能 | 説明 |
| --- | --- |
| Node.js SDKバージョン1.0 | Target Node.js SDKを使用すると、Targetサーバー側をデプロイできます。<br>このNode.js SDKを使用すると、TargetをAdobe Experience Cloud Identity Service、Adobe Analytics、Adobe Audience Managerなどの他のExperience cloudソリューションと簡単に統合できます。<br>Node.js SDKは、アドビの配信APIを使用してAdobe targetと統合する際に、ベストプラクティスを導入し、複雑さを排除して、エンジニアリングチームがビジネスロジックに集中できるようにします。 最新バージョンで導入される主な機能は次のとおりです。<ul><li>キャッシュを使用してパフォーマンスを最適化できるプリフェッチと通知のサポート。</li><li>Webページとサーバー側の両方でTargetをハイブリッド統合している場合のパフォーマンス最適化のサポート。 at.js 2.2がエクスペリエンスを取得するための追加のサーバー呼び出しを行わないように、サーバー側で取得したエクスペリエンスによって設定されるという設定が導入されます。 `serverState` このアプローチは、ページ読み込みのパフォーマンスを最適化します。</li><li> 新しい配信APIで可能になった、Node.js SDKを介したVECで作成されたアクティビティの取得のサポート。</li><li>開発者がNode.js SDKに貢献できるように、オープンソースです。</li></ul><br>詳しくは、リリースノー [ト — Target Node.js SDKを参照してください](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md)。<br>Adobe Tech BlogのOpen Sourcing the New Adobe Target Node.js SDKで、Target Node.js SDKの詳細をご覧くだ [さい](https://medium.com/adobetech/open-sourcing-the-new-adobe-target-node-js-sdk-b6feafd828bc)。 |
| 配信API | 完全に新しい配信APIエンドポイント（/v1/配信）が実稼働環境で使用できます。 主な機能は次のとおりです。<ul><li>1つ以上のmboxのエクスペリエンスを取得するための1つのエンドポイント。</li><li>APIを使用してVECで作成されたアクティビティを取得します。</li><li>シングルページアプリ(SPA)およびモバイルアプリケーションで使用されるビューと呼ばれる、まったく新しいオブジェクトのサポート。</li></ul><br>詳しくは、リリースノート — [Targetサーバー側APIを参照してください](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md)。 |

## その他のリリースノートとバージョンの詳細

| リソース | 詳細 |
|--- |--- |
| [リリースノート — Targetサーバー側API](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md) | Adobe targetのサーバー側APIに関するリリースノートです。 |
| [リリースノート — Target Node.js SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md) | Adobe targetのNode.js SDKに関するリリースノートです。 |
| [リリースノート — Target Java SDK](/help/c-implementing-target/c-api-and-sdk-overview/releases-target-java-sdk.md) | Adobe targetのJava SDKに関するリリースノートです。 |
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
