---
keywords: apple;ITP；インテリジェントトラッキング防止；experience cloud id;ecid
description: Adobe [!DNL Target] と、Safariユーザーのプライバシーを保護しようとするApple Intelligent Tracking Prevention(ITP)イニシアチブの影響について説明します。
title: ' [!DNL Target] Apple ITPのサポートの処理方法'
feature: プライバシーとセキュリティ
role: Developer
exl-id: 05a62be5-ccfb-4d5c-b511-35023b95e567
source-git-commit: dd20791535e47c83d0f0ac60addfe0888748f86a
workflow-type: tm+mt
source-wordcount: '910'
ht-degree: 52%

---

# Apple Intelligent Tracking Prevention（ITP）2.x

Experience CloudID(ECID)ライブラリ4.3によるAppleのITP 2.xの[!DNL Adobe Target]サポートに関する情報です。

Intelligent Tracking Prevention（ITP）は、Safari ユーザーのプライバシーを保護するための Apple の取り組みです。ITP の最初のリリース（2017 年）では、サードパーティ Cookie の使用を対象としていました。実際、Apple は、サードパーティ Cookie を完全にブロックしましたが、サードパーティ Cookie は、訪問者の追跡および訪問者データの収集に一般的に使用されていたので、広告技術およびマーケティング技術会社にとって深刻な頭痛の種となりました。現在、Apple は、Safari 内でのファーストパーティ Cookie の使用方法に制限や制約を課すことに移行しています。

ITP のこれらのバージョンには、次の制限が含まれています。

| バージョン | 詳細 |
| --- | --- |
| [ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) | `document.cookie` API を使用してブラウザーに配置されたクライアント側 Cookie の有効期限の上限は 7 日間になりました。<br>2019 年 2 月 21 日にリリースされました。 |
| [ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/) | 7 日間の有効期限の上限が 1 日に大幅に短縮されました。<br>2019 年 4 月 24 日にリリースされました。 |
| [ITP 2.3](https://webkit.org/blog/9521/intelligent-tracking-prevention-2-3/) | localStorageの使用やJavaScript `Document.referrer property`の使用など、いくつかの回避策を排除しました。<br>2019年9月24日にリリースされました。 |

## Adobe[!DNL Target]のお客様に与える影響は何ですか。 {#impact}

[!DNL Target] は、ページにデプロイするための JavaScript ライブラリを提供し、これにより、[!DNL Target] によるリアルタイムパーソナライゼーションを訪問者に実現できます。`document.cookie` APIを使用して訪問者のブラウザーにクライアント側の[!DNL Target] Cookieを配置する、at.js 1.xおよびat.js 2.xの3つのTarget JavaScriptライブラリがあります。 その結果、[!DNL Target] CookieはAppleのITP 2.xの影響を受け、7日後(ITP 2.1)または1日後（ITP 2.2およびITP 2.3）に期限が切れます。

Apple ITP 2.xは、次の領域で[!DNL Target]に影響を与えます。

| 影響 | 詳細 |
| --- | --- |
| 個別訪問者数が増加する可能性 | 有効期限が7日(ITP 2.1)および1日（ITP 2.2およびITP 2.3）に設定されているので、Safariブラウザーからの個別訪問者数が増加している可能性があります。 訪問者が7日後(ITP 2.1)または1日後（ITP 2.2およびITP 2.3）にドメインに再訪問した場合、[!DNL Target]は、期限切れのCookieの代わりに、ドメインに新しい[!DNL Target] Cookieを配置するよう強制されます。 新しい [!DNL Target] Cookie は、ユーザーが同じであっても、新しい個別訪問者と解釈されます。 |
| [!DNL Target] アクティビティのルックバック期間の短縮 | [!DNL Target] アクティビティの訪問者プロファイルは、決定のためのルックバック期間が短縮した可能性があります。[!DNL Target] Cookie は、訪問者を特定するために活用され、パーソナライゼーション用にユーザープロファイル属性を格納します。Safariでは、[!DNL Target] Cookieの有効期限が7日後(ITP 2.1)または1日後（ITP 2.2および2.3）に切れる場合があるので、パージされた[!DNL Target] Cookieに結び付けられたユーザープロファイルデータは、判定に使用できません。 |
| サードパーティ ID に基づくプロファイルスクリプト | 有効期限が7日（ITP 2.1を使用）および1日（ITP 2.2およびITP 2.3を使用）に設定されているので、3rdPartyID cookieに基づく[プロファイルスクリプト](/help/c-target/c-visitor-profile/profile-parameters.md)は、有効期限が切れると機能しなくなります。 |
| iOS デバイスでの QA／プレビュー URL | 有効期限は7日（ITP 2.1を使用）および1日（ITP 2.2およびITP 2.3を使用）に設定されるので、 [QA/プレビューURL](/help/c-activities/c-activity-qa/activity-qa.md)は、URLが3rdPartyID Cookieに基づいているので、有効期限が切れると機能しなくなります。 |

## 現在の [!DNL Target] の実装は影響を受けますか？

Safari ブラウザーでは、[!DNL Target] JavaScript ライブラリを持つ Web サイトにナビゲートします。[!DNL Target] CookieがCNAMEのコンテキストで設定されている（例：`analytics.company.com`）場合、ITP 2.xの影響は受けません。

Target JavaScript ライブラリに加えて Experience Cloud ID（ECID）ライブラリを使用している場合、実装は、[Safari ITP 2.1 の Adobe Experience Cloud および Experience Platform のお客様への影響](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac)の記事に記載されているような影響を受けます。

## 今後のITP 2.xリリースのTargetに対する影響を緩和する方法を教えてください。

今後のITP 2.xリリースのTargetに対する影響を軽減するには、次の作業を実行します。

1. ページに Experience Cloud ID（ECID）ライブラリをデプロイします。

   ECID ライブラリは、Experience Cloud Core ソリューションの人物識別フレームワークを有効にします。ECID ライブラリを使用すると、永続的な一意の識別子を割り当てることによって、様々な Experience Cloud ソリューションで同じサイト訪問者およびそのデータを識別できます。ECID ライブラリは、頻繁に更新され、実装に影響を与える ITP 関連の変更を緩和するのに役立ちます。

   ITP 2.xの影響を緩和するには、 [ECIDライブラリ4.3.0以降](https://experienceleague.adobe.com/docs/id-service/using/release-notes/release-notes.html?lang=ja)を使用する必要があります。

1. アドビの CNAME を使用して、Adobe Analytics の Managed Certificate Program に登録します。

   ECID ライブラリ 4.3.0 以降のインストール後、Adobe Analytics の CNAME および Managed Certificate Program を活用できます。このプログラムを利用すると、ファーストパーティ Cookie に対するファーストパーティ証明書を追加費用なしで実装できます。CNAMEの活用は、[!DNL Target]のお客様がITP 2.xの影響を緩和するのに役立ちます。

   CNAMEを活用していない場合は、アカウント担当者に問い合わせて、[Adobe管理証明書プログラム](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html#adobe-managed-certificate-program)に登録することで、プロセスを開始できます。

CNAME を活用するために Target JavaScript ライブラリを ECID ライブラリ v4.3.0 以降と共にデプロイして Adobe Managed Certificate Program に登録したら、ITP 関連の変更に対する堅牢な長期間の緩和計画を得ることになります。

業界はお客様向けにより安全な Web を作成する方向に進んでおり、[!DNL Adobe Target] では、訪問者のプライバシーに対する期待を満たし、超えると同時に、パーソナライズされたエクスペリエンスを配信することに全力で取り組んでいます。[!DNL Adobe Target] は、AppleのITP 2.xのサ [ポートに加えて、GoogleのSameSite Chrome](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/google-chrome-samesite-cookie-policies.md) ポリシーをサポートすることを既に発表しています。

お客様を保護するためにポリシーが継続的に発展するのに伴い、[!DNL Adobe] は、お客様がクラス最高のパーソナライズされたエクスペリエンスを提供するのを支援しながら、[!DNL Target] でのこれらの取り組みも継続的にサポートします。
