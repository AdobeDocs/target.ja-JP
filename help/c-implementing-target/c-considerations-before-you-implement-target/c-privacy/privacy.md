---
keywords: プライバシー；ipアドレス；地理特性；オプトアウト；オプトアウト；データプライバシー；政府規制；規制；gdpr;ccpa
description: Adobe [!DNL Target] が、IPアドレスの収集や処理、オプトアウト手順など、適用されるデータプライバシー法に準拠する方法を説明します。
title: ' [!DNL Target] はプライバシーに関する問題をどのように処理しますか。'
feature: プライバシーとセキュリティ
role: Developer
exl-id: fb632923-fa36-4553-88a6-f27860472eb6
source-git-commit: 2403f63a6b993818fdc845d17f1a0dde72be664d
workflow-type: tm+mt
source-wordcount: '728'
ht-degree: 58%

---

# プライバシー

[!DNL Adobe Target] のプロセスおよび設定はプライバシーを考慮した設計になっており、個人情報保護法に準拠した方法で を使用できます。[!DNL Target]

## IPアドレスの収集 {#section_91BDB8105EBF4B85B7B8B8A14675AC85}

Web サイトの訪問者の IP アドレスは、Adobe Data Processing Center（DPC）に送信されます。訪問者のネットワーク設定によっては、この IP アドレスが訪問者のコンピューターの IP アドレスと一致しないことがあります。例えば、この IP アドレスは、Network Address Translation（NAT）ファイアウォール、HTTP プロキシ、またはインターネットゲートウェイの外部 IP アドレスである可能性があります。Target は、ユーザーの IP アドレスまたは個人情報（PII）を保存しません。IPアドレスは、セッション中にTargetでのみ使用されます（メモリ内、永続化されません）。

## IPアドレスの最終オクテットの置き換え {#section_AE84EB0D7CE04E93B279B77732ADD61E}

アドビは、Adobe ClientCare が Adobe Target に関して有効化できる新しい「プライバシーバイデザイン」設定を開発しました。この設定を有効にすると、アドビが IP アドレスを収集する際に、IP アドレスの最終オクテット（最後の部分）が隠されます。この匿名化は、IPアドレスを処理する前（オプションのIPアドレスの地域ルックアップを含む）に実行されます。

この機能を有効にすると、IP アドレスの匿名性が高まり、個人情報を特定できなくなります。そのため、個人情報の収集を認めない各国の個人情報保護法に準拠した形で Adobe Target をご利用いただくことができます。IP アドレスの不明化をおこなうと、市レベルの情報の取得が著しく困難になる場合があります。地域レベルおよび国レベルの情報の取得に関しては、それほど大きな影響はありません。

以下の設定を使用できます。

* 難読化なし：Targetは、IPアドレスの一部を非表示にしません。
* 最後のオクテット：Targetは、IPアドレスの最後のオクテットを非表示にします。
* 完全IP:TargetはIPアドレス全体を非表示にします。

Targetは、完全なIPアドレスを受け取り、指定に従って（最終オクテットまたは完全なIPに設定されている場合）不明化します。 次に、Targetは、セッション中に、不明化されたIPアドレスをメモリに保持します。

>[!NOTE]
>
>[Adobeクライア](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) ントケアに問い合わせて、現在使用している設定またはIP難読化機能を有効にする設定を確認します。

## 地理特性 {#section_BB69F96559BD44BDA4177537C4A5345A}

IP アドレスの最終オクテットの置き換えを有効にした場合、Adobe Target のレポートでは、IP アドレスの残りの部分が分析されます。IP アドレスの最終オクテットを不明化しなかった場合は、Adobe Target では完全な IP アドレスが分析されます。地理特性機能を使用して、地理的な地域によって訪問者の位置を把握できます。地理特性データの精度は市レベルまたは郵便番号レベルにとどまり、個人レベルでの特定はできません。

IP アドレスが完全に不明化されている場合、地理特性と GeoTargeting は使用できません。

## オプトアウトリンク {#section_E7A62B7B99C94B3A806CB262D16E27FC}

訪問者がカウントやコンテンツ配信をすべて停止（オプトアウト）できるオプトアウトリンクを、サイトに追加できます。

1. サイトに次のリンクを追加します。

   `<a href="https://clientcode.tt.omtrdc.net/optout"> Your Opt Out Language Here</a>`

1. （条件付き）CNAMEを使用している場合、リンクには次のように「client=`clientcode`」パラメーターが含まれている必要があります。
https://my.cname.domain/optout?client=clientcode.

1. `clientcode`をお使いのクライアントコードに置き換え、このオプトアウトURLにリンクさせるテキストまたは画像を追加します。

このリンクをクリックした訪問者は、Cookie を削除するか、最初に訪問してから 2 年経過するまで、閲覧しているセッションから呼び出される mbox リクエストに含まれません。`disableClient` ドメイン内の「`clientcode.tt.omtrdc.net`」という訪問者に Cookie が設定され、この機能が適用されます。

ファーストパーティ Cookie の導入を使用している場合でも、提供されたオプトアウトは、サードパーティ Cookie を使用するように設定されます。クライアントがファーストパーティ Cookie のみを使用している場合は、オプトアウト Cookie が設定されているかどうかをチェックします。

## 機能使用状況データの収集 {#feature-usage}

[!DNL Adobe]内部の目的で個々の機能使用データを収集し、[!DNL Target]機能が意図したとおりに実行されているか、または使用されていない機能を識別します。 パフォーマンスに関する問題に対処するために、様々な遅延測定値が収集されます。 個人データは収集されません。

設定ファイルの`telemetryEnabled`を`false`に設定すると、使用状況データのレポートをオプトアウトできます。

## プライバシーとデータ保護規制

欧州連合の一般データ保護規則(GDPR)、カリフォルニア州消費者プライバシー法(CCPA)およびその他の国際的なプライバシー要件、およびこれらの規制が組織およびAdobe Targetに与える影響について詳しくは、[プライバシーとデータ保護規則](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md)を参照してください。
