---
keywords: apple;ITP；インテリジェントトラッキング防止；エクスペリエンスクラウドid;ecid
description: Experience CloudID(ECID)ライブラリ4.3を使用したAppleのITP 2.xのAdobe Targetサポートに関する情報です。
title: ターゲットおよびApple ITPのサポート
feature: Privacy & Security
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '905'
ht-degree: 51%

---


# Apple Intelligent Tracking Prevention（ITP）2.x

Experience CloudID(ECID)ライブラリ4.3を使用したAppleのITP 2.xの[!DNL Adobe Target]サポートに関する情報です。

Intelligent Tracking Prevention（ITP）は、Safari ユーザーのプライバシーを保護するための Apple の取り組みです。ITP の最初のリリース（2017 年）では、サードパーティ Cookie の使用を対象としていました。実際、Apple は、サードパーティ Cookie を完全にブロックしましたが、サードパーティ Cookie は、訪問者の追跡および訪問者データの収集に一般的に使用されていたので、広告技術およびマーケティング技術会社にとって深刻な頭痛の種となりました。現在、Apple は、Safari 内でのファーストパーティ Cookie の使用方法に制限や制約を課すことに移行しています。

ITP のこれらのバージョンには、次の制限が含まれています。

| バージョン | 詳細 |
| --- | --- |
| [ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) | `document.cookie` API を使用してブラウザーに配置されたクライアント側 Cookie の有効期限の上限は 7 日間になりました。<br>2019 年 2 月 21 日にリリースされました。 |
| [ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/) | 7 日間の有効期限の上限が 1 日に大幅に短縮されました。<br>2019 年 4 月 24 日にリリースされました。 |
| [ITP 2.3](https://webkit.org/blog/9521/intelligent-tracking-prevention-2-3/) | localStorageの使用やJavaScript `Document.referrer property`の使用など、いくつかの回避策を排除。<br>2019年9月23日リリース。 |

## Adobe Targetのお客様としての私の影響は？{#impact}

[!DNL Target] は、ページにデプロイするための JavaScript ライブラリを提供し、これにより、[!DNL Target] によるリアルタイムパーソナライゼーションを訪問者に実現できます。Target JavaScript ライブラリは 3 つあり（[at.js 1.`document.cookie` APIを使用して訪問者のブラウザーにクライアント側の[!DNL Target] cookieを配置するx、at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)、および[mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md))。 その結果、[!DNL Target] cookieはAppleのITP 2.xの影響を受け、7日後（ITP 2.1の場合）と1日後（ITP 2.2とITP 2.3の場合）に有効期限が切れます。

Apple ITP 2.xは、次の領域で[!DNL Target]に影響します。

| 影響 | 詳細 |
| --- | --- |
| 個別訪問者数が増加する可能性 | 有効期限枠が7日（ITP 2.1の場合）と1日（ITP 2.2とITP 2.3の場合）に設定されているので、Safariブラウザーからの個別訪問者数が増加している場合があります。 7日後(ITP 2.1)または1日後に訪問者がドメインを再訪問した場合（ITP 2.2およびITP 2.3）、[!DNL Target]は、期限切れのcookieの代わりに新しい[!DNL Target] cookieをドメインに配置するよう強制されます。 新しい [!DNL Target] Cookie は、ユーザーが同じであっても、新しい個別訪問者と解釈されます。 |
| [!DNL Target] アクティビティのルックバック期間の短縮 | [!DNL Target] アクティビティの訪問者プロファイルは、決定のためのルックバック期間が短縮した可能性があります。[!DNL Target] Cookie は、訪問者を特定するために活用され、パーソナライゼーション用にユーザープロファイル属性を格納します。Safariでは、7日後(ITP 2.1)または1日後（ITP 2.2および2.3）に[!DNL Target] cookieの有効期限が切れる可能性があるので、パージされた[!DNL Target] cookieに結び付けられたユーザープロファイルデータを判定に使用できません。 |
| サードパーティIDに基づくプロファイルスクリプト | 有効期限枠が7日（ITP 2.1を使用）および1日（ITP 2.2およびITP 2.3を使用）に設定されているので、有効期限が切れると、[サードパーティID cookieに基づくプロファイルスクリプト](/help/c-target/c-visitor-profile/profile-parameters.md)が機能しなくなります。 |
| iOSデバイスでのQA/プレビューURL | 有効期限枠が7日（ITP 2.1を使用）および1日（ITP 2.2およびITP 2.3を使用）に設定されているので、[QA/プレビューURL](/help/c-activities/c-activity-qa/activity-qa.md)は、URLが3rdPartyID cookieに基づいているので、有効期限が切れると機能しなく。 |

## 現在の [!DNL Target] の実装は影響を受けますか？

Safari ブラウザーでは、[!DNL Target] JavaScript ライブラリを持つ Web サイトにナビゲートします。`analytics.company.com`など、CNAMEのコンテキストに[!DNL Target] cookieが設定されている場合、ITP 2.xの影響を受けません。

Target JavaScript ライブラリに加えて Experience Cloud ID（ECID）ライブラリを使用している場合、実装は、[Safari ITP 2.1 の Adobe Experience Cloud および Experience Platform のお客様への影響](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac)の記事に記載されているような影響を受けます。

## 将来のITP 2.xリリースがターゲットに与える影響を軽減するにはどうしたらよいですか。

将来のITP 2.xリリースがターゲットに与える影響を軽減するには、次のタスクを実行します。

1. ページに Experience Cloud ID（ECID）ライブラリをデプロイします。

   ECID ライブラリは、Experience Cloud Core ソリューションの人物識別フレームワークを有効にします。ECID ライブラリを使用すると、永続的な一意の識別子を割り当てることによって、様々な Experience Cloud ソリューションで同じサイト訪問者およびそのデータを識別できます。ECID ライブラリは、頻繁に更新され、実装に影響を与える ITP 関連の変更を緩和するのに役立ちます。

   ITP 2.xの場合は、[ECIDライブラリ4.3.0+](https://experienceleague.adobe.com/docs/id-service/using/release-notes/release-notes.html)を緩和のために使用する必要があります。

1. アドビの CNAME を使用して、Adobe Analytics の Managed Certificate Program に登録します。

   ECID ライブラリ 4.3.0 以降のインストール後、Adobe Analytics の CNAME および Managed Certificate Program を活用できます。このプログラムを利用すると、ファーストパーティ Cookie に対するファーストパーティ証明書を追加費用なしで実装できます。CNAMEを活用すると、[!DNL Target]様のお客様はITP 2.xの影響を緩和できます。

   CNAMEを活用していない場合は、アカウント担当者と話し合い、[Adobe管理証明書プログラム](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html#adobe-managed-certificate-program)に登録することで、プロセスを開始できます。

CNAME を活用するために Target JavaScript ライブラリを ECID ライブラリ v4.3.0 以降と共にデプロイして Adobe Managed Certificate Program に登録したら、ITP 関連の変更に対する堅牢な長期間の緩和計画を得ることになります。

業界はお客様向けにより安全な Web を作成する方向に進んでおり、[!DNL Adobe Target] では、訪問者のプライバシーに対する期待を満たし、超えると同時に、パーソナライズされたエクスペリエンスを配信することに全力で取り組んでいます。[!DNL Adobe Target] は、 [AppleのITP 2.xのサポートに加え、](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/google-chrome-samesite-cookie-policies.md) GoogleのSameSite Chrome Policieのサポートを既に発表しています。

お客様を保護するためにポリシーが継続的に発展するのに伴い、[!DNL Adobe] は、お客様がクラス最高のパーソナライズされたエクスペリエンスを提供するのを支援しながら、[!DNL Target] でのこれらの取り組みも継続的にサポートします。
