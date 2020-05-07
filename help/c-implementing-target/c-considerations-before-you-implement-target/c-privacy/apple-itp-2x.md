---
keywords: apple;ITP;intelligent tracking prevention
description: Experience Cloud ID(ECID)ライブラリ4.3を使用したAppleのITP 2.xのアドビターゲットサポートに関する情報です。
title: Adobe Target と Apple ITP サポート
subtopic: Getting Started
topic: Standard
translation-type: tm+mt
source-git-commit: a24d932f02d49ff11da6299eb46d73f4f385b866
workflow-type: tm+mt
source-wordcount: '887'
ht-degree: 52%

---


# Apple Intelligent Tracking Prevention（ITP）2.x

Intelligent Tracking Prevention（ITP）は、Safari ユーザーのプライバシーを保護するための Apple の取り組みです。ITP の最初のリリース（2017 年）では、サードパーティ Cookie の使用を対象としていました。実際、Apple は、サードパーティ Cookie を完全にブロックしましたが、サードパーティ Cookie は、訪問者の追跡および訪問者データの収集に一般的に使用されていたので、広告技術およびマーケティング技術会社にとって深刻な頭痛の種となりました。現在、Apple は、Safari 内でのファーストパーティ Cookie の使用方法に制限や制約を課すことに移行しています。

ITP のこれらのバージョンには、次の制限が含まれています。

| バージョン | 詳細 |
| --- | --- |
| [ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) | `document.cookie` API を使用してブラウザーに配置されたクライアント側 Cookie の有効期限の上限は 7 日間になりました。<br>2019 年 2 月 21 日にリリースされました。 |
| [ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/) | 7 日間の有効期限の上限が 1 日に大幅に短縮されました。<br>2019 年 4 月 24 日にリリースされました。 |
| [ITP 2.3](https://webkit.org/blog/9521/intelligent-tracking-prevention-2-3/) | localStorageの使用やJavaScriptの使用など、いくつかの回避策を取り除き `Document.referrer property`ました。<br>2019年9月23日リリース。 |

## What is the impact to me as an Adobe Target customer? {#impact}

[!DNL Target] は、ページにデプロイするための JavaScript ライブラリを提供し、これにより、[!DNL Target] によるリアルタイムパーソナライゼーションを訪問者に実現できます。Target JavaScript ライブラリは 3 つあり（[at.js 1.x, at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md), and [mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md)) that place client-side [!DNL Target] cookies on your visitors&#39; browsers via the `document.cookie` API. As a result, [!DNL Target] cookies are impacted by Apple’s ITP 2.x and will expire after seven days (with ITP 2.1) and after one day (with ITP 2.2 and ITP 2.3).

Apple ITP 2.xは、次 [!DNL Target] の領域に影響します。

| 影響 | 詳細 |
| --- | --- |
| 個別訪問者数が増加する可能性 | 有効期限枠が7日（ITP 2.1の場合）と1日（ITP 2.2とITP 2.3の場合）に設定されているので、Safariブラウザーからの個別訪問者数が増加している場合があります。 If your visitors revisit your domain after seven days (ITP 2.1) or one day (ITP 2.2 and ITP 2.3), [!DNL Target] is forced to place a new [!DNL Target] cookie on your domain in place of the expired cookie. 新しい [!DNL Target] Cookie は、ユーザーが同じであっても、新しい個別訪問者と解釈されます。 |
| [!DNL Target] アクティビティのルックバック期間の短縮 | [!DNL Target] アクティビティの訪問者プロファイルは、決定のためのルックバック期間が短縮した可能性があります。[!DNL Target] Cookie は、訪問者を特定するために活用され、パーソナライゼーション用にユーザープロファイル属性を格納します。Given that [!DNL Target] cookies can be expired on Safari after seven days (ITP 2.1) or one day (ITP 2.2 and 2.3), the user profile data that was tied to the purged [!DNL Target] cookie cannot be used for decisioning. |
| サードパーティIDに基づくプロファイルスクリプト | 有効期限枠が7日（ITP 2.1を使用）に設定され、1日（ITP 2.2およびITP 2.3を使用）に設定されているため、有効期限が切れると、3rdPartyID cookieに基づく [プロファイルスクリプト](/help/c-target/c-visitor-profile/profile-parameters.md) は機能しなくなります。 |
| iOSデバイスでのQA/プレビューURL | 有効期限枠が7日（ITP 2.1を使用）および1日に設定されているので（ITP 2.2およびITP 2.3を使用）、 [QA/プレビューのURL](/help/c-activities/c-activity-qa/activity-qa.md) は、有効期限が切れると機能を停止します。これは、URLがサードパーティID cookieに基づいているためです。 |

## 現在の [!DNL Target] の実装は影響を受けますか？

Safari ブラウザーでは、[!DNL Target] JavaScript ライブラリを持つ Web サイトにナビゲートします。If you see a [!DNL Target] cookie set in the context of a CNAME, such as `analytics.company.com`, then you are not impacted by ITP 2.x.

Target JavaScript ライブラリに加えて Experience Cloud ID（ECID）ライブラリを使用している場合、実装は、[Safari ITP 2.1 の Adobe Experience Cloud および Experience Platform のお客様への影響](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac)の記事に記載されているような影響を受けます。

## 将来のITP 2.xリリースがターゲットに与える影響を軽減するにはどうしたらよいですか。

将来のITP 2.xリリースがターゲットに与える影響を軽減するには、次のタスクを実行します。

1. ページに Experience Cloud ID（ECID）ライブラリをデプロイします。

   ECID ライブラリは、Experience Cloud Core ソリューションの人物識別フレームワークを有効にします。ECID ライブラリを使用すると、永続的な一意の識別子を割り当てることによって、様々な Experience Cloud ソリューションで同じサイト訪問者およびそのデータを識別できます。ECID ライブラリは、頻繁に更新され、実装に影響を与える ITP 関連の変更を緩和するのに役立ちます。

   ITP 2.xの場合、 [ECIDライブラリ4.3.0以降を緩和のために使用する必要](https://docs.adobe.com/content/help/en/id-service/using/release-notes/release-notes.html) があります。

1. アドビの CNAME を使用して、Adobe Analytics の Managed Certificate Program に登録します。

   ECID ライブラリ 4.3.0 以降のインストール後、Adobe Analytics の CNAME および Managed Certificate Program を活用できます。このプログラムを利用すると、ファーストパーティ Cookie に対するファーストパーティ証明書を追加費用なしで実装できます。Leveraging CNAME will help [!DNL Target] customers mitigate the impact of ITP 2.x.

   If you are not leveraging CNAME, you can start the process by talking with your account representative and enrolling in the [Adobe Managed Certificate Program](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-first-party.html#adobe-managed-certificate-program).

CNAME を活用するために Target JavaScript ライブラリを ECID ライブラリ v4.3.0 以降と共にデプロイして Adobe Managed Certificate Program に登録したら、ITP 関連の変更に対する堅牢な長期間の緩和計画を得ることになります。

業界はお客様向けにより安全な Web を作成する方向に進んでおり、[!DNL Adobe Target] では、訪問者のプライバシーに対する期待を満たし、超えると同時に、パーソナライズされたエクスペリエンスを配信することに全力で取り組んでいます。[!DNL Adobe Target] は、AppleのITP 2.xのサポートに加えて、 [GoogleのSameSite Chromeポリシー](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/google-chrome-samesite-cookie-policies.md) （英語のみ）のサポートを既に発表しています。

お客様を保護するためにポリシーが継続的に発展するのに伴い、[!DNL Adobe] は、お客様がクラス最高のパーソナライズされたエクスペリエンスを提供するのを支援しながら、[!DNL Target] でのこれらの取り組みも継続的にサポートします。
