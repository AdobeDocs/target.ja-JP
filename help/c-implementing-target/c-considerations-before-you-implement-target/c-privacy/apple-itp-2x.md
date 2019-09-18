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
| 個別訪問者数の増加の可能性 | 有効期限が7日（ITP 2.1を使用）と1日（ITP 2.2を使用）に設定されているため、Safariブラウザーからの個別訪問者数が増加する場合があります。 訪問者が7日後(ITP 2.1)または1日後にドメインを再訪問した場合(ITP 2.2)、期限切れのcookieの代わりに新しい [!DNL Target][!DNL Target] cookieをドメインに配置する必要があります。 新しいcookie [!DNL Target] は、ユーザーが同じであっても、新しい個別訪問者に変換されます。 |
| アクティビティのルックバック期間の [!DNL Target] 短縮 | アクティビティの訪問者プ [!DNL Target] ロファイルでは、判定のルックバック期間が短くなった可能性があります。 [!DNL Target] cookieは、訪問者を識別し、パーソナライゼーションのためにユーザープロファイル属性を保存するために使用されます。 cookieが7日 [!DNL Target] (ITP 2.1)または1日(ITP 2.2)の間にSafariで有効期限切れになる場合があるので、削除されたcookieに結び付けられたユーザープロファイルデータを判定に使用することはで [!DNL Target] きません。 |

## 現在の実装に影響があ [!DNL Target] るか。

Safariブラウザーで、 [!DNL Target] JavaScriptライブラリがあるWebサイトに移動します。 例えば、CNAMEのコ [!DNL Target] ンテキストにCookieが設定されている場合、 `analytics.company.com`ITP 2.1または2.2の影響を受けません。

Target javaScriptライブラリに加えてExperience Cloud ID(ECID)ライブラリを使用している場合は、この記事に示す方法で実装に影響が及びます。Safari ITP 2.1がAdobe Experience cloudおよびExperience Platformのお客様に与える影響 [](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac)。

## ITP 2.1、ITP 2.2および今後のITPリリースの影響を軽減するにはどうすればよいです [!DNL Target]か。

ITP 2.1、ITP 2.2および今後のITPリリースの影響を軽減するには、次の [!DNL Target]タスクを実行します。

1. Experience Cloud ID(ECID)ライブラリをページにデプロイします。

   ECIDライブラリを使用すると、Experience cloudコアソリューションの人物識別フレームワークを有効にできます。 ECIDライブラリを使用すると、永続的な識別子と一意の識別子を割り当てることで、異なるExperience cloudソリューション内の同じサイト訪問者とそのデータを識別できます。 ECIDライブラリは頻繁に更新され、導入に影響を与えるITP関連の変更を軽減できるようになります。

   ITP 2.1およびITP 2.2の場合、緩和のために [ECIDライブラリ4.3.0+を](https://docs.adobe.com/content/help/en/id-service/using/release-notes/release-notes.html) 使用する必要があります。

1. アドビのCNAMEを使用し、Adobe Analyticsの管理対象証明書プログラムに登録します。

   ECIDライブラリ4.3.0以降をインストールした後は、Adobe AnalyticsのCNAMEおよび管理された証明書プログラムを利用できます。 このプログラムを使用すると、ファーストパーティcookie用のファーストパーティ証明書を無料で実装できます。 CNAMEを活用すると、ITP 2.1 [!DNL Target] およびITP 2.2の影響を軽減できます。

   CNAMEを利用しない場合は、アカウント担当者に問い合わせて、 [Adobe Managed Certificate Programに登録することで、プロセスを開始できます](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-first-party.html#adobe-managed-certificate-program)。

ECIDライブラリv4.3.0以降と組み合わせてTarget javaScriptライブラリをデプロイし、CNAMEを活用するためにAdobe Managed Certificate Programに登録すると、ITP関連の変更に対する堅牢で長期的な緩和計画を立てることができます。

As the industry makes strides to create a more secure web for consumers, [!DNL Adobe Target] is absolutely committed to delivering personalized experiences while meeting and exceeding the privacy expectations of visitors. [!DNL Adobe Target] は、Appleの [ITP 2.1およびITP 2.2のサポートに加えて](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/google-chrome-samesite-cookie-policies.md) 、GoogleのSameSite Chromeポリシーのサポートを既に発表しています。

消費者を保護するためのポリシーの発展が続く中で、お客様がクラス最高のパーソナライズされたエクスペリエンスを提供できるよう、これらのイニシアチ [!DNL Adobe][!DNL Target]ブも引き続きサポートしていく予定です。
