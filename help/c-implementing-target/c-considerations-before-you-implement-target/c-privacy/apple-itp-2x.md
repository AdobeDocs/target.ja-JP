---
description: Experience Cloud ID（ECID）ライブラリ4.3を使用したAppleのTP2.1およびITP2.2のTargetサポートについて取り上げます。
keywords: apple;ITP;インテリジェントトラッキングの防止
seo-description: Experience Cloud ID（ECID）ライブラリ4.3を使用したAppleのTP2.1およびITP2.2に対するAdobe Targetのサポートについて取り上げます。
seo-title: Adobe TargetおよびApple Ipのサポート
solution: 'Target '
subtopic: 導入
title: Apple ITP2. x
topic: Standard
translation-type: tm+mt
source-git-commit: 71419ee6053eeb86ab6595cfba2f05d8506e05b3

---


# Apple Intelligent Tracking Prevention（ITP）2. x

インテリジェントトラッキング防止（ISP）は、Safariユーザーのプライバシーを保護するAppleのイニシアチブです。2017年のITPの最初のリリースでは、サードパーティcookieの使用をターゲットにしていました。実際、Appleはサードパーティcookieをブロックしていましたが、サードパーティcookieは一般的に訪問者の追跡や訪問者データの収集に使用されるので、広告テックおよびマーチャンダイジング会社にとっては深刻な頭痛が発生していました。現在、Appleは、Safari内でファーストパーティcookieを使用する方法の制限と制限について説明しています。

これらのバージョンのIMPには、次の制限があります。

| バージョン | 詳細 |
| --- | --- |
| [ITP2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) | `document.cookie` APIを使用して7日間の有効期限に配置された、クライアントサイドのcookieを保護したもの。<br>2019年2月21日リリース。 |
| [ITP2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/) | 7日間の有効期限を大幅に短縮しました。<br>2019年4月24日リリース。 |

## Adobe Targetのお客様としての影響は何ですか?

[!DNL Target] はJavaScriptライブラリを提供して、訪問者にリアルタイムのパーソナライゼーションを提供 [!DNL Target] できるようにページにデプロイします。There are three Target JavaScript libraries ([at.js 1.*x*&#x200B;およびat. js2.*x*](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)および [mbox. js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md)）を使用して、API経由で訪問者のブラウザーにクライアント側 [!DNL Target] Cookieを配置 `document.cookie` します。As a result, [!DNL Target] cookies are impacted by Apple’s ITP 2.1 and 2.2 and will expire after seven days (with ITP 2.1) and after one day (with ITP 2.2).

Apple ITP 2.1 and 2.1 impact [!DNL Target] in the following areas:

| 影響 | 詳細 |
| --- | --- |
| 個別訪問者数の潜在的な増加 | 有効期限ウィンドウが7日間（TP2.1の場合）と1日（TP2.2の場合）に設定されているため、Safariブラウザーからの個別訪問者数が増加する可能性があります。If your visitors revisit your domain after seven days (ITP 2.1) or one day (ITP 2.2), [!DNL Target] is forced to place a new [!DNL Target] cookie on your domain in place of the expired cookie. The new [!DNL Target] cookie translates to a new unique visitor even though the user is the same. |
| Decreased lookback periods for [!DNL Target] activities | Visitor profiles for [!DNL Target] activities might have a decreased lookback period for decisioning. [!DNL Target] cookieは、訪問者を識別し、パーソナライゼーションのためにユーザープロファイル属性を格納するために使用されます。Given that [!DNL Target] cookies can be expired on Safari after seven days (ITP 2.1) or one day (ITP 2.2), the user profile data that was tied to the purged [!DNL Target] cookie cannot be used for decisioning. |

## [!DNL Target] 現在の実装が影響を受けているか。

In a Safari browser, navigate to your website on which you have a [!DNL Target] JavaScript library. If you see a [!DNL Target] cookie set in the context of a CNAME, such as `analytics.company.com`, then you are not impacted by ITP 2.1 or 2.2.

If you are using the Experience Cloud ID (ECID) library in addition to the Target JavaScript library, your implementation will be impacted in the ways listed in this article: [Safari ITP 2.1 Impact on Adobe Experience Cloud and Experience Platform Customers](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac).

## How can I mitigate the impact of ITP 2.1, ITP 2.2, and future ITP releases to [!DNL Target]?

To mitigate the impact of ITP 2.1, ITP 2.2, and future ITP releases to [!DNL Target], complete the following tasks:

1. Experience Cloud ID（ECID）ライブラリをページにデプロイします。

   ECIDライブラリを使用すると、Experience Cloudコアソリューションのユーザー識別フレームワークを有効にすることができます。ECIDライブラリを使用すると、永続的な識別子と一意の識別子を割り当てることで、異なるExperience Cloudソリューションで同じサイト訪問者とそのデータを識別できます。ECIDライブラリは頻繁に更新され、導入に影響を与えるITP関連の変更を軽減することができます。

   For ITP 2.1 and ITP 2.2, [ECID library 4.3.0+](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-release-notes.html) must be utilized for mitigation.

1. Adobe Analyticsの「管理対象証明書プログラム」にAdobeのCNAMEを使用し、登録します。

   EIDライブラリ4.3.0以上をインストールした後、Adobe AnalyticsのCNAMEおよびManaged Certificate Programを利用できます。このプログラムでは、ファーストパーティcookieのファーストパーティ証明書を無料で実装できます。Leveraging CNAME will help [!DNL Target] customers mitigate the impact of ITP 2.1 and ITP 2.2.

   If you are not leveraging CNAME, you can start the process by talking with your account representative and enrolling in the [Adobe Managed Certificate Program](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/adobe_managed_cert_pgm.html).

Target JavaScriptライブラリをEIDライブラリv4.3.0以上と組み合わせてデプロイし、Adobe Managed Certificate Programに登録してCNAMEを活用すると、Ip関連の変更について、堅牢で長期的な作業を簡単に計画できます。

As the industry makes strides to create a more secure web for consumers, [!DNL Adobe Target] is absolutely committed to delivering personalized experiences while meeting and exceeding the privacy expectations of visitors. [!DNL Adobe Target] は、AppleのITP2.1およびITP2.2のサポートに加え [て、Googleのサマーサイトクロムポリシー](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/google-chrome-samesite-cookie-policies.md) のサポートを既に発表しています。

As policies continue to evolve to protect our consumers, [!DNL Adobe] will also continue to support these initiatives in [!DNL Target], while helping our customers provide the best-in-class personalized experiences.
