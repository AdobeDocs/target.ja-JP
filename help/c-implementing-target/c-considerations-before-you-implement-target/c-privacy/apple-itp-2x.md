---
description: Experience Cloud ID（ECID）ライブラリ 4.3 による Target での Apple の ITP 2.1 および ITP 2.2 のサポートについて説明します。
keywords: apple;ITP;intelligent tracking prevention
seo-description: Experience Cloud ID（ECID）ライブラリ 4.3 による Adobe Target での Apple の ITP 2.1 および ITP 2.2 のサポートについて説明します。
seo-title: Adobe Target と Apple ITP サポート
solution: 'Target '
subtopic: 導入
title: Apple ITP 2.x
topic: Standard
translation-type: tm+mt
source-git-commit: 1c78ca901ba240ce5f9dad6b3982cfe95ef41950

---


# Apple Intelligent Tracking Prevention（ITP）2.x

Intelligent Tracking Prevention（ITP）は、Safari ユーザーのプライバシーを保護するための Apple の取り組みです。ITP の最初のリリース（2017 年）では、サードパーティ Cookie の使用を対象としていました。実際、Apple は、サードパーティ Cookie を完全にブロックしましたが、サードパーティ Cookie は、訪問者の追跡および訪問者データの収集に一般的に使用されていたので、広告技術およびマーケティング技術会社にとって深刻な頭痛の種となりました。現在、Apple は、Safari 内でのファーストパーティ Cookie の使用方法に制限や制約を課すことに移行しています。

ITP のこれらのバージョンには、次の制限が含まれています。

| バージョン | 詳細 |
| --- | --- |
| [ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) | `document.cookie` API を使用してブラウザーに配置されたクライアント側 Cookie の有効期限の上限は 7 日間になりました。<br>2019 年 2 月 21 日にリリースされました。 |
| [ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/) | 7 日間の有効期限の上限が 1 日に大幅に短縮されました。<br>2019 年 4 月 24 日にリリースされました。 |

## Adobe Target のお客様にはどのような影響がありますか？

[!DNL Target] は、ページにデプロイするための JavaScript ライブラリを提供し、これにより、[!DNL Target] によるリアルタイムパーソナライゼーションを訪問者に実現できます。Target JavaScript ライブラリは 3 つあり（[at.js 1.*x* と at.js 2 の両方について示しています。*x*](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) および [mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md)）、これによって、`document.cookie` API を使用して訪問者のブラウザーにクライアント側 [!DNL Target] Cookie を配置します。結果として、[!DNL Target] Cookie は、Apple の ITP 2.1 および 2.2 の影響を受け、7 日後（ITP 2.1）または 1 日後（ITP 2.2）に期限が切れます。

Apple ITP 2.1 および 2.2 は、次の領域で [!DNL Target] に影響を与えます。

| 影響 | 詳細 |
| --- | --- |
| 個別訪問者数が増加する可能性 | 有効期限が 7 日間（ITP 2.1）または 1 日間（ITP 2.2）に設定されるので、Safari ブラウザーからの個別訪問者が増加しているように見えます。訪問者が 7 日後（ITP 2.1）または 1 日後（ITP 2.2）にドメインに再訪すると、[!DNL Target] は、期限切れの Cookie の代わりにドメインの新しい [!DNL Target] Cookie を配置するよう強制されます。新しい [!DNL Target] Cookie は、ユーザーが同じであっても、新しい個別訪問者と解釈されます。 |
| [!DNL Target] アクティビティのルックバック期間の短縮 | [!DNL Target] アクティビティの訪問者プロファイルは、決定のためのルックバック期間が短縮した可能性があります。[!DNL Target] Cookie は、訪問者を特定するために活用され、パーソナライゼーション用にユーザープロファイル属性を格納します。[!DNL Target] Cookie は Safari 上で 7 日後（ITP 2.1）または 1 日後（ITP 2.2）に期限切れになる可能性があるとすると、パージされた [!DNL Target] Cookie に結び付けられたユーザープロファイルデータは、決定に使用できません。 |

## 現在の [!DNL Target] の実装は影響を受けますか？

Safari ブラウザーでは、[!DNL Target] JavaScript ライブラリを持つ Web サイトにナビゲートします。[!DNL Target] Cookie が CNAME のコンテキストで設定されている（`analytics.company.com` など）のを確認した場合、ITP 2.1 または 2.2 の影響は受けません。

Target JavaScript ライブラリに加えて Experience Cloud ID（ECID）ライブラリを使用している場合、実装は、[Safari ITP 2.1 の Adobe Experience Cloud および Experience Platform のお客様への影響](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac)の記事に記載されているような影響を受けます。

## ITP 2.1、ITP 2.2 および将来の ITP リリースの [!DNL Target] に対する影響を緩和する方法を教えてください。

ITP 2.1、ITP 2.2 および将来の ITP リリースの [!DNL Target] に対する影響を緩和するには、次の作業を実行します。

1. ページに Experience Cloud ID（ECID）ライブラリをデプロイします。

   ECID ライブラリは、Experience Cloud Core ソリューションの人物識別フレームワークを有効にします。ECID ライブラリを使用すると、永続的な一意の識別子を割り当てることによって、様々な Experience Cloud ソリューションで同じサイト訪問者およびそのデータを識別できます。ECID ライブラリは、頻繁に更新され、実装に影響を与える ITP 関連の変更を緩和するのに役立ちます。

   ITP 2.1およびITP 2.2の場合、緩和のために [ECIDライブラリ4.3.0+を](https://docs.adobe.com/content/help/en/id-service/using/release-notes/release-notes.html) 使用する必要があります。

1. アドビの CNAME を使用して、Adobe Analytics の Managed Certificate Program に登録します。

   ECID ライブラリ 4.3.0 以降のインストール後、Adobe Analytics の CNAME および Managed Certificate Program を活用できます。このプログラムを利用すると、ファーストパーティ Cookie に対するファーストパーティ証明書を追加費用なしで実装できます。CNAME の活用は、[!DNL Target] のお客様が ITP 2.1 および ITP 2.2 の影響を緩和するのに役立ちます。

   If you are not leveraging CNAME, you can start the process by talking with your account representative and enrolling in the [Adobe Managed Certificate Program](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-first-party.html#adobe-managed-certificate-program).

CNAME を活用するために Target JavaScript ライブラリを ECID ライブラリ v4.3.0 以降と共にデプロイして Adobe Managed Certificate Program に登録したら、ITP 関連の変更に対する堅牢な長期間の緩和計画を得ることになります。

業界はお客様向けにより安全な Web を作成する方向に進んでおり、[!DNL Adobe Target] では、訪問者のプライバシーに対する期待を満たし、超えると同時に、パーソナライズされたエクスペリエンスを配信することに全力で取り組んでいます。[!DNL Adobe Target] は、Apple の ITP 2.1 および ITP 2.2 に加えて、[Google の SameSite Chrome ポリシー](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/google-chrome-samesite-cookie-policies.md)をサポートすることが既にアナウンスされています。

お客様を保護するためにポリシーが継続的に発展するのに伴い、[!DNL Adobe] は、お客様がクラス最高のパーソナライズされたエクスペリエンスを提供するのを支援しながら、[!DNL Target] でのこれらの取り組みも継続的にサポートします。
