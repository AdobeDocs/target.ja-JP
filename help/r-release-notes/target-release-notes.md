---
description: Adobe targetの最新リリースまたは今後のリリースに関する機能、拡張機能および修正に関する情報を提供するリリースノートです。
keywords: release notes;releases;updates;future release;enhancements;new features;fixes
seo-description: DNL Adobe targetの最新リリースまたは今後のリリースに関する機能、拡張機能および修正に関する情報を提供するリリースノートです。
seo-title: Adobe Target prerelease notes
solution: 'Target '
title: Target リリースノート（プレリリース）
topic: Standard
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: 285a09503ba6abaf2bfe19fc2b214c32ebd2de3a

---


# Target リリースノート（プレリリース）{#target-release-notes-prerelease}

これらのリリースノートでは、最新または今後 [!DNL Adobe Target] のリリースの機能、機能強化および修正点について説明しています。

**Last Updated: October 2, 2019**

>[!NOTE]
>
>これらのリリースノートには、プレリリース情報が含まれています。リリース日、機能などの情報は、予告なく変更されることがあります。最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。これらのページの情報は、リリースのタイミングによって異なる場合があります。
>
>括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

## Target platform (Dates to be determined)

| 機能／拡張機能 | 説明 |
| --- | --- |
| Node.js SDK version 1.0 | The Target Node.js SDK lets you deploy Target server-side.<br>This Node.js SDK helps you easily integrate Target with other Experience Cloud solutions, such as the Adobe Experience Cloud Identity Service, Adobe Analytics, and Adobe Audience Manager.<br>The Node.js SDK introduces best practices and removes complexities when integrating with Adobe Target via our delivery API so that your engineering teams can focus on business logic. The following are notable features that we are introducing in the latest version:<ul><li>Support for prefetching and notifications that allows you to optimize for performance via caching.</li><li>Support for optimizing performance when you have a hybrid integration of Target on both your web pages and server-side. We are introducing a setting called  that will be populated by experiences retrieved via the server-side so that at.js 2.2 will no longer make an additional server call to retrieve the experiences. `serverState`This approach optimizes page load performance.</li><li> 新しい配信APIで可能になった、Node.js SDKを介したVECで作成されたアクティビティの取得のサポート。</li><li>Open sourced so your developers can contribute to the Node.js SDK.</li></ul> |
| 配信API | An entirely new delivery API endpoint (/v1/delivery) will be available in production. 主な機能は次のとおりです。<ul><li>1つ以上のmboxのエクスペリエンスを取得するための1つのエンドポイント。</li><li>APIを使用してVECで作成されたアクティビティを取得します。</li><li>シングルページアプリ(SPA)およびモバイルアプリケーションで使用されるビューと呼ばれる、まったく新しいオブジェクトのサポート。</li></ul> |
| at.jsバージョン2.2<br><br>およびat.jsバージョン1.8 | at.jsの次のバージョンは、<ul><li>WebページでExperience Cloud IDサービス(ECID)v4.4とat.js 2.2またはat.js 1.8の両方を使用する場合のパフォーマンスが向上しました。</li><li>以前は、ECIDは、at.jsがエクスペリエンスを取得する前に2回のブロック呼び出しを行いました。 これは1回の呼び出しに短縮され、パフォーマンスが大幅に向上しました。</li></ul> これらのパフォーマンス改善を活用するには、ECIDライブラリv4.4と共にat.js 2.2またはat.js 1.8にアップグレードします。 |


## Target Standard／Premium 19.10.1（2019 年 10 月 22 日）

| 機能／拡張機能 | 説明 |
| --- | --- |
| ![Premium badge](/help/assets/premium.png) User-Based Recommendations | 各訪問者の閲覧、閲覧、購入履歴に基づいて品目をレコメンドします。 これらの品目は、一般に「推奨」と呼ばれます。<br>この条件を使用すると、新規訪問者と再訪問者の両方に対して、パーソナライズされたコンテンツとエクスペリエンスを配信できます。 レコメンデーションのリストは、訪問者の最新のアクティビティに重み付けされ、セッション内で更新され、訪問者がサイトを閲覧するにつれて、よりパーソナライズされます。 |

## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Target およびその他の Adobe Experience Cloud ソリューションの今後の製品強化に関する事前通知を受信するには、Adobe Priority Product Update にサインアップします。

[https://adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
