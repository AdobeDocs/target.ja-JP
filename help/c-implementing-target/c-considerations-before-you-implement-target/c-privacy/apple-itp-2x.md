---
keywords: apple;ITP；インテリジェントトラッキング防止；experience cloud id;ecid;itp
description: Adobe [!DNL Target] と、Safariユーザーのプライバシーを保護しようとするApple Intelligent Tracking Prevention(ITP)イニシアチブの影響について説明します。
title: ' [!DNL Target] Apple ITPのサポートの処理方法'
feature: プライバシーとセキュリティ
role: Developer
exl-id: 05a62be5-ccfb-4d5c-b511-35023b95e567
source-git-commit: 898a18cbd9c6f499f9e7b74078575bc149c9a292
workflow-type: tm+mt
source-wordcount: '591'
ht-degree: 38%

---

# Apple Intelligent Tracking Prevention（ITP）2.x

Intelligent Tracking Prevention（ITP）は、Safari ユーザーのプライバシーを保護するための Apple の取り組みです。ITP の最初のリリース（2017 年）では、サードパーティ Cookie の使用を対象としていました。実際、Apple は、サードパーティ Cookie を完全にブロックしましたが、サードパーティ Cookie は、訪問者の追跡および訪問者データの収集に一般的に使用されていたので、広告技術およびマーケティング技術会社にとって深刻な頭痛の種となりました。現在、Apple は、Safari 内でのファーストパーティ Cookie の使用方法に制限や制約を課すことに移行しています。

ITP のこれらのバージョンには、次の制限が含まれています。

| バージョン | 詳細 |
| --- | --- |
| [ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) | `document.cookie` API を使用してブラウザーに配置されたクライアント側 Cookie の有効期限の上限は 7 日間になりました。<br>2019 年 2 月 21 日にリリースされました。 |
| [ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/) | 7 日間の有効期限の上限が 1 日に大幅に短縮されました。<br>2019 年 4 月 24 日にリリースされました。 |
| [ITP 2.3](https://webkit.org/blog/9521/intelligent-tracking-prevention-3-2/) | localStorageの使用やJavaScript `Document.referrer property`の使用など、いくつかの回避策を排除しました。<br>2019年9月24日にリリースされました。<br>Safari 14、macOS Big Sur、Catalina、Mojave、iOS 14およびiPadOS 14でリリースされたITPに対するCNAMEクローキングの防御機能。サードパーティのCNAMEクロークHTTP応答で作成されたすべてのcookieは、7日後に期限切れに設定されます。<br>2020年11月13日に発表されました。 |

## Adobe[!DNL Target]のお客様に与える影響は何ですか。 {#impact}

[!DNL Target] は、ページにデプロイするための JavaScript ライブラリを提供し、これにより、[!DNL Target] によるリアルタイムパーソナライゼーションを訪問者に実現できます。`document.cookie` APIを使用して訪問者のブラウザーにクライアント側の[!DNL Target] Cookieを配置する、at.js 1.xおよびat.js 2.xの3つのTarget JavaScriptライブラリがあります。 その結果、[!DNL Target] Cookieは、AppleのITP 2.1、2.2および2.3の影響を受け、7日後(ITP 2.1)または1日後（ITP 2.2およびITP 2.3）に期限が切れます。

Apple ITP 2.xは、次の領域で[!DNL Target]に影響を与えます。

| 影響 | 詳細 |
| --- | --- |
| 個別訪問者数が増加する可能性 | 有効期限が7日(ITP 2.1)および1日（ITP 2.2およびITP 2.3）に設定されているので、Safariブラウザーからの個別訪問者数が増加している可能性があります。 訪問者が7日後(ITP 2.1)または1日後（ITP 2.2およびITP 2.3）にドメインに再訪問した場合、[!DNL Target]は、期限切れのCookieの代わりに、ドメインに新しい[!DNL Target] Cookieを配置するよう強制されます。 新しい [!DNL Target] Cookie は、ユーザーが同じであっても、新しい個別訪問者と解釈されます。 |
| [!DNL Target] アクティビティのルックバック期間の短縮 | [!DNL Target] アクティビティの訪問者プロファイルは、決定のためのルックバック期間が短縮した可能性があります。[!DNL Target] Cookie は、訪問者を特定するために活用され、パーソナライゼーション用にユーザープロファイル属性を格納します。Safariでは、[!DNL Target] Cookieの有効期限が7日後(ITP 2.1)または1日後（ITP 2.2および2.3）に切れる場合があるので、パージされた[!DNL Target] Cookieに結び付けられたユーザープロファイルデータは、判定に使用できません。 |
| サードパーティ ID に基づくプロファイルスクリプト | 有効期限が7日（ITP 2.1を使用）および1日（ITP 2.2およびITP 2.3を使用）に設定されているので、3rdPartyID cookieに基づく[プロファイルスクリプト](/help/c-target/c-visitor-profile/profile-parameters.md)は、有効期限が切れると機能しなくなります。 |
| iOS デバイスでの QA／プレビュー URL | 有効期限は7日（ITP 2.1を使用）および1日（ITP 2.2およびITP 2.3を使用）に設定されるので、 [QA/プレビューURL](/help/c-activities/c-activity-qa/activity-qa.md)は、URLが3rdPartyID Cookieに基づいているので、有効期限が切れると機能しなくなります。 |

## 現在の [!DNL Target] の実装は影響を受けますか？

[!DNL Target] JavaScriptライブラリに加えてExperience CloudID(ECID)ライブラリを使用している場合は、この記事に示す方法で実装に影響が及びます。[Safari ITP 2.1がAdobe Experience CloudおよびExperience Platformのお客様に与える影響](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac)。
