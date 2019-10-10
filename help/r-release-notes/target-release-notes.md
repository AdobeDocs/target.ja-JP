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
source-git-commit: e11f8dfee9bcdfae530efc75b239f0d7af045005

---


# Target リリースノート（プレリリース）{#target-release-notes-prerelease}

これらのリリースノートでは、最新または今後 [!DNL Adobe Target] のリリースの機能、機能強化および修正点について説明しています。

**最終更新日：2019年10月2日**

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

## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。

[https://adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
