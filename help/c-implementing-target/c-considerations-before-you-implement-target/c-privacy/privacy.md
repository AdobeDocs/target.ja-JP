---
keywords: privacy;ip address;geosegmentation;opt out;optout;opt-out;data privacy;government regulations;regulations;gdpr;ccpa
description: Adobe Target のプロセスおよび設定はプライバシーを考慮した設計になっており、個人情報保護法に準拠した方法で Target を使用できます。
title: プライバシー
feature: Privacy & Security
translation-type: tm+mt
source-git-commit: 6bb75e3b818a71af323614d9150e50e3e9f611b7
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 78%

---


# プライバシー

[!DNL Adobe Target] のプロセスおよび設定はプライバシーを考慮した設計になっており、個人情報保護法に準拠した方法で を使用できます。[!DNL Target]

## IPアドレスの収集{#section_91BDB8105EBF4B85B7B8B8A14675AC85}

Web サイトの訪問者の IP アドレスは、Adobe Data Processing Center（DPC）に送信されます。訪問者のネットワーク設定によっては、この IP アドレスが訪問者のコンピューターの IP アドレスと一致しないことがあります。例えば、この IP アドレスは、Network Address Translation（NAT）ファイアウォール、HTTP プロキシ、またはインターネットゲートウェイの外部 IP アドレスである可能性があります。Target は、ユーザーの IP アドレスまたは個人情報（PII）を保存しません。IP アドレスは、セッション（メモリ内、永続化されません）の有効期間中に Target によってのみ使用されます。

## IPアドレスの最終オクテットの置き換え{#section_AE84EB0D7CE04E93B279B77732ADD61E}

アドビは、Adobe ClientCare が Adobe Target に関して有効化できる新しい「プライバシーバイデザイン」設定を開発しました。この設定を有効にすると、アドビが IP アドレスを収集する際に、IP アドレスの最終オクテット（最後の部分）が隠されます。この匿名化処理は、IP アドレスに何らかの処理（オプションとしておこなわれる IP アドレスの地域ルックアップを含む）を加える前に実行されます。

この機能を有効にすると、IP アドレスの匿名性が高まり、個人情報を特定できなくなります。そのため、個人情報の収集を認めない各国の個人情報保護法に準拠した形で Adobe Target をご利用いただくことができます。IP アドレスの不明化をおこなうと、市レベルの情報の取得が著しく困難になる場合があります。地域レベルおよび国レベルの情報の取得に関しては、それほど大きな影響はありません。

以下の設定を使用できます。

* 不明化なし：ターゲットは、IPアドレスの一部を非表示にしません。
* 最終オクテット：ターゲットは、IPアドレスの最後のオクテットを非表示にします。
* フルIP:ターゲットはIPアドレス全体を非表示にします。

ターゲットは、完全なIPアドレスを受信し、指定に従って、そのアドレスを不明化します（最終オクテットまたはフルIPに設定されている場合）。 次に、ターゲットは、セッション中、メモリ内の不明化されたIPアドレスを保持します。

>[!NOTE]
>
>[現在使用している設定やIPの不明化機能を有効にする場合は、Adobeクライアント](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) ケアにお問い合わせください。

## 地理特性 {#section_BB69F96559BD44BDA4177537C4A5345A}

IP アドレスの最終オクテットの置き換えを有効にした場合、Adobe Target のレポートでは、IP アドレスの残りの部分が分析されます。IP アドレスの最終オクテットを不明化しなかった場合は、Adobe Target では完全な IP アドレスが分析されます。地理特性機能を使用して、地理的な地域によって訪問者の位置を把握できます。地理特性データの精度は市レベルまたは郵便番号レベルにとどまり、個人レベルでの特定はできません。

IP アドレスが完全に不明化されている場合、地理特性と GeoTargeting は使用できません。

## オプトアウトリンク{#section_E7A62B7B99C94B3A806CB262D16E27FC}

訪問者がカウントやコンテンツ配信をすべて停止（オプトアウト）できるオプトアウトリンクを、サイトに追加できます。

1. サイトに次のリンクを追加します。

   `<a href="https://clientcode.tt.omtrdc.net/optout"> Your Opt Out Language Here</a>`
1. `clientcode` をお客様のクライアントコードに置き換え、このオプトアウト URL にリンクさせるテキストまたは画像を追加します。

このリンクをクリックした訪問者は、Cookie を削除するか、最初に訪問してから 2 年経過するまで、閲覧しているセッションから呼び出される mbox リクエストに含まれません。`disableClient` ドメイン内の「`clientcode.tt.omtrdc.net`」という訪問者に Cookie が設定され、この機能が適用されます。

ファーストパーティ Cookie の導入を使用している場合でも、提供されたオプトアウトは、サードパーティ Cookie を使用するように設定されます。クライアントがファーストパーティ Cookie のみを使用している場合は、オプトアウト Cookie が設定されているかどうかをチェックします。

## プライバシーとデータ保護規制

欧州和集合のGDPR(General Data Protection Regulation)、カリフォルニア消費者プライバシー法(CCPA)、その他の国際的なプライバシー要件、およびこれらの規制が貴社やAdobe Targetに与える影響については、[プライバシーとデータ保護に関する規則](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md)を参照してください。
