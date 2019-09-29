---
description: Experience Cloud ID(ECID)ライブラリ4.3を使用したAppleのITP 2.1およびITP 2.2のTargetサポートに関する情報です。
keywords: apple;ITP；インテリジェントトラッキング防止
seo-description: Experience Cloud ID(ECID)ライブラリ4.3を使用したAppleのITP 2.1およびITP 2.2に対するAdobe targetのサポートに関する情報です。
seo-title: Adobe targetとApple ITPのサポート
solution: 'Target '
subtopic: 導入
title: Apple ITP 2.x
topic: Standard
translation-type: tm+mt
source-git-commit: 8dc94ca1ed48366e6b3ac7a75b03c214f1db71d9

---


# Apple Intelligent Tracking Prevention(ITP)2.x

Intelligent Tracking Prevention(ITP)は、Safariユーザーのプライバシーを保護するAppleのイニシアチブです。 2017年のITPの最初のリリースでは、サードパーティcookieの使用がターゲットになっていました。 実際、Appleはサードパーティcookieの全体をブロックし、その結果、サードパーティcookieは一般に訪問者の追跡や訪問者データの収集に使用されるので、広告技術およびハイテク企業にとって大きな頭痛の種となりました。 今、Appleは、Safari内でのファーストパーティcookieの使用に関する制限や制限を設ける方針を進めています。

ITPのこれらのバージョンには、次の制限が含まれます。

| バージョン | 詳細 |
| --- | --- |
| [ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) | 7日間の有効期限までの `document.cookie` APIを使用してブラウザーに配置されるクライアントサイドcookieの上限。<br>2019年2月22日リリース。 |
| [ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/) | 7日間の有効期限を1日に大幅に短縮しました。<br>2019年4月24日リリース。 |

## Adobe targetのお客様にとっての影響は何ですか。

[!DNL Target] は、JavaScriptライブラリをページにデプロイして、訪問者にリアルタ [!DNL Target] イムのパーソナライゼーションを提供します。 3つのTarget javaScriptライブラリ([at.js 1.*x*、at.js 2.**](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)APIを使用して訪問者のブラウザーにクラ [イアント側のcookieを配置するx](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md)、mbox.js [!DNL Target]`document.cookie` )。 その結果、 [!DNL Target] cookieはAppleのITP 2.1および2.2の影響を受け、7日後（ITP 2.1の場合）と1日後（ITP 2.2の場合）に有効期限が切れます。

Apple ITP 2.1および2.1は、次の領域 [!DNL Target] に影響を与えます。

| 影響 | 詳細 |
| --- | --- |
| 個別訪問者数の増加の可能性 | 有効期限が7日（ITP 2.1を使用）と1日（ITP 2.2を使用）に設定されているため、Safariブラウザーからの個別訪問者数が増加する場合があります。 If your visitors revisit your domain after seven days (ITP 2.1) or one day (ITP 2.2),  is forced to place a new  cookie on your domain in place of the expired cookie. [!DNL Target][!DNL Target]The new  cookie translates to a new unique visitor even though the user is the same.[!DNL Target] |
| Decreased lookback periods for  activities[!DNL Target] | Visitor profiles for  activities might have a decreased lookback period for decisioning. [!DNL Target][!DNL Target] cookies are leveraged to identity a visitor and store user profile attributes for personalization. Given that  cookies can be expired on Safari after seven days (ITP 2.1) or one day (ITP 2.2), the user profile data that was tied to the purged  cookie cannot be used for decisioning.[!DNL Target][!DNL Target] |

## Is my current implementation of  impacted?[!DNL Target]

In a Safari browser, navigate to your website on which you have a  JavaScript library. [!DNL Target]If you see a  cookie set in the context of a CNAME, such as , then you are not impacted by ITP 2.1 or 2.2.[!DNL Target]`analytics.company.com`

If you are using the Experience Cloud ID (ECID) library in addition to the Target JavaScript library, your implementation will be impacted in the ways listed in this article: Safari ITP 2.1 Impact on Adobe Experience Cloud and Experience Platform Customers.[](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac)

## How can I mitigate the impact of ITP 2.1, ITP 2.2, and future ITP releases to ?[!DNL Target]

To mitigate the impact of ITP 2.1, ITP 2.2, and future ITP releases to , complete the following tasks:[!DNL Target]

1. Deploy the Experience Cloud ID (ECID) library to your pages.

   The ECID library enables the people identification framework for Experience Cloud Core solutions. The ECID library allows you to identify same site visitors and their data in different Experience Cloud solutions by assigning persistent and unique identifiers. ECIDライブラリは頻繁に更新され、導入に影響を与えるITP関連の変更を軽減できるようになります。

   ITP 2.1およびITP 2.2の場合、緩和のために [ECIDライブラリ4.3.0+を](https://docs.adobe.com/content/help/en/id-service/using/release-notes/release-notes.html) 使用する必要があります。

1. アドビのCNAMEを使用し、Adobe Analyticsの管理対象証明書プログラムに登録します。

   ECIDライブラリ4.3.0以降をインストールした後は、Adobe AnalyticsのCNAMEおよび管理された証明書プログラムを利用できます。 このプログラムを使用すると、ファーストパーティcookie用のファーストパーティ証明書を無料で実装できます。 CNAMEを活用すると、ITP 2.1 [!DNL Target] およびITP 2.2の影響を軽減できます。

   CNAMEを利用しない場合は、アカウント担当者に問い合わせて、 [Adobe Managed Certificate Programに登録することで、プロセスを開始できます](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-first-party.html#adobe-managed-certificate-program)。

ECIDライブラリv4.3.0以降と組み合わせてTarget javaScriptライブラリをデプロイし、CNAMEを活用するためにAdobe Managed Certificate Programに登録すると、ITP関連の変更に対する堅牢で長期的な緩和計画を立てることができます。

As the industry makes strides to create a more secure web for consumers, [!DNL Adobe Target] is absolutely committed to delivering personalized experiences while meeting and exceeding the privacy expectations of visitors. [!DNL Adobe Target] は、Appleの [ITP 2.1およびITP 2.2のサポートに加えて](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/google-chrome-samesite-cookie-policies.md) 、GoogleのSameSite Chromeポリシーのサポートを既に発表しています。

消費者を保護するためのポリシーの発展が続く中で、お客様がクラス最高のパーソナライズされたエクスペリエンスを提供できるよう、これらのイニシアチ [!DNL Adobe][!DNL Target]ブも引き続きサポートしていく予定です。
