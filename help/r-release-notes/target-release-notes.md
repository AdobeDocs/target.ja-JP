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
source-git-commit: 0a9cf0e98f5f833402b96f37df5513325222ad19

---


# Target リリースノート（プレリリース）{#target-release-notes-prerelease}

これらのリリースノートでは、最新または今後 [!DNL Adobe Target] のリリースの機能、機能強化および修正点について説明しています。

**最終更新日：2019年10月18日**

>[!NOTE]
>
>これらのリリースノートには、プレリリース情報が含まれています。リリース日、機能などの情報は、予告なく変更されることがあります。最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。これらのページの情報は、リリースのタイミングによって異なる場合があります。
>
>括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

## ターゲットプラットフォーム

| 機能／拡張機能 | 説明 |
| --- | --- |
| Node.js SDKバージョン1.0<br>（2019年10月9日） | Target Node.js SDKを使用すると、Targetサーバー側をデプロイできます。<br>このNode.js SDKを使用すると、TargetをAdobe Experience Cloud Identity Service、Adobe Analytics、Adobe Audience Managerなどの他のExperience cloudソリューションと簡単に統合できます。<br>Node.js SDKは、アドビの配信APIを使用してAdobe targetと統合する際に、ベストプラクティスを導入し、複雑さを排除して、エンジニアリングチームがビジネスロジックに集中できるようにします。 最新バージョンで導入される主な機能は次のとおりです。<ul><li>キャッシュを使用してパフォーマンスを最適化できるプリフェッチと通知のサポート。</li><li>Webページとサーバー側の両方でTargetをハイブリッド統合している場合のパフォーマンス最適化のサポート。 at.js 2.2がエクスペリエンスを取得するための追加のサーバー呼び出しを行わないように、サーバー側で取得したエクスペリエンスによって設定されるという設定が導入されます。 `serverState` このアプローチは、ページ読み込みのパフォーマンスを最適化します。</li><li> 新しい配信APIで可能になった、Node.js SDKを介したVECで作成されたアクティビティの取得のサポート。</li><li>開発者がNode.js SDKに貢献できるように、オープンソースです。</li></ul>詳しくは、リリースノー [ト — Target Node.js SDKを参照してください](/help/c-implementing-target/c-api-and-sdk-overview/releases-nodejs.md)。 |
| Delivery API<br>（2019年10月9日） | まったく新しい配信APIエンドポイント（/v1/配信）が実稼働環境で使用できるようになります。 主な機能は次のとおりです。<ul><li>1つ以上のmboxのエクスペリエンスを取得するための1つのエンドポイント。</li><li>APIを使用してVECで作成されたアクティビティを取得します。</li><li>シングルページアプリ(SPA)およびモバイルアプリケーションで使用されるビューと呼ばれる、まったく新しいオブジェクトのサポート。</li></ul>詳しくは、リリースノート — [Targetサーバー側APIを参照してください](/help/c-implementing-target/c-api-and-sdk-overview/releases-server-side.md)。 |
| at.jsバージョン2.2<br><br>およびat.jsバージョン1.8<br>（2019年10月11日） | at.jsの次のバージョンは、<ul><li>WebページでExperience Cloud IDサービス(ECID)v4.4とat.js 2.2またはat.js 1.8の両方を使用する場合のパフォーマンスが向上しました。</li><li>以前は、at.jsがエクスペリエンスを取得する前に、ECIDは2回のブロック呼び出しを行いました。 これは1回の呼び出しに短縮され、パフォーマンスが大幅に向上しました。</li></ul> これらのパフォーマンス改善を活用するには、ECIDライブラリv4.4.<br>at.js 2.2と共にat.js 2.2またはat.js 1.8にアップグレードします。<ul><li>**serverState**:at.js v2.2以降で使用できる設定で、Targetのハイブリッド統合が実装されている場合に、ページのパフォーマンスを最適化するために使用できます。 ハイブリッド統合とは、クライアント側でat.js v2.2以降と、サーバー側で配信APIまたはTarget SDKの両方を使用してエクスペリエンスを配信することです。 `serverState` は、at.js v2.2以降で、サーバー側で取得されたコンテンツからエクスペリエンスを直接適用し、提供されるページの一部としてクライアントに返す機能を提供します。<br>詳しくは、targetGlobalSettingsの「serverState」を参照してく [ださい](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#server-state)。</li></ul> |


## Target Standard／Premium 19.10.1（2019 年 10 月 22 日）

| 機能／拡張機能 | 説明 |
| --- | --- |
| ![Premiumバッジ](/help/assets/premium.png) User-Based Recommendations | 各訪問者の閲覧、閲覧、購入履歴に基づいて品目をレコメンドします。 これらの品目は、一般に「推奨」と呼ばれます。<br>この条件を使用すると、新規訪問者と再訪問者の両方に対して、パーソナライズされたコンテンツとエクスペリエンスを配信できます。 レコメンデーションのリストは、訪問者の最新のアクティビティに重み付けされ、セッション内で更新され、訪問者がサイトを閲覧するにつれて、よりパーソナライズされます。 |

### 機能強化、修正および変更

* Adobe Unified shellの変更点です。

   アドビは、すべてのソリューションでエクスペリエンスを統合し、向上させるために、既存のシェル(ソリューションの上部に [!DNL Experience Cloud] ある黒いバー)を更新し [!DNL Adobe Experience Cloud] ています。

   現在のワークフローには変更はありません。これらのシンプルに見える変更は、小さくて重要な方法での生活をより簡単にするように設計されています。

   にログインすると、新し [!DNL Adobe Experience Cloud]い統合シェルに移動します。 前のシェルの上部に黒いバーが表示されているのと非常に似ていますが、次の点が改善されています。

   * IMS(Identity Management System)組織間または別のExperience cloudソリューション間の切り替えが [!E容易に] 。
   * ユーザーヘルプの改善：検索結果には、製品ドキュメントの結 [!DNL Target] 果、コミュニティフォーラムやビデオコンテンツなどが含まれ、より多くのコンテンツに簡単にアクセスして最大限の活用を図ることができま [!DNL Target]す。 また、ヘルプメニューにフィードバックのメカニズムが追加され、問題の報告やアイデアの共有が容易になりました。
   * ネットプロモータースコア(NPS)機能を改善しました。 調査の頻度が、意図したよ [!DNL Target] りも高い場合もあります。 さらに、作業の流れを妨げる調査モーダルを使用します。 この機能は完全に更新されたので、もう押し付けがましい小さな調査になります。 さらに、新しい設計により、調査の頻度をより適切に制御できるようになりました。
   * ログインフローが改善されました。 以前は、すべての顧客 [!DNL Target] がシェル上のアイコンをクリックした後、Targetのランディングペ [!DNL Target] ージにランディングしました。 その後、このページでは、次に示すように、お客様がRecommendations Classic [!DNL Target Standard/Premium]、 [!DNl]Recommendations [!DNL Search&Promote]Classic、またはを使用できました。

      ![ランディングページ](/help/r-release-notes/assets/landing.png)

      このランディングページをすべてのお客様に対して削除しました。 アイコンをクリックすると、常にアクティビティリ [!UICONTROL ストページに] 直接移動するようにな [!DNL Target] りました。

      使用する場合は、 [!DNL Recommendations Classic]次に示すように、ソリューションに直接移動するか、「 [!UICONTROL Recommendations] 」タブで作成した短いリンクから移動できます。

      ![Recs Classicディープリンク](/help/r-release-notes/assets/recs-classic.png)

      を使用する場合 [!DNL Search&Promote]は、リンクに直接移動する必要があります。 の内部からSearch&amp;Promoteに到達するパスは完全に [!DNL Adobe Target] 削除されました。
   * 現在、シェル [!DNL Target] の「通知」ドロップダウンには [!UICONTROL 通知が表示されなくなりました] 。
   >[!NOTE]
   >
   >これらの機能は一度に展開されたり、すべての顧客に一括して展開されることはありません。 これらの機能は、19.10.1（2019年10月22日）リリースから数日 [!DNL Target Standard/Premium] 後にロールアウトされます。
   >
   >新しいシェルの展開の一環として、URLの変更もいくつか見てとれます。 以前にブックマークされたリンクは、引き続き機能しますが、すばやく開くために新しいリンクをブックマークすることをお勧めします。

## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。

[https://adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
