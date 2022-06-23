---
keywords: プライバシー;ip アドレス;地理特性;オプトアウト;optout;データプライバシー;政府規制;規制;gdpr;ccpa
description: Adobe  [!DNL Target]  がどのようにして IP アドレスの収集と取り扱い、オプトアウト手順など、適用されるデータプライバシー法に準拠しているかについて説明します。
title: ' [!DNL Target]  ではどのようにしてプライバシーに関する問題に対処していますか？'
feature: Privacy & Security
role: Developer
exl-id: fb632923-fa36-4553-88a6-f27860472eb6
source-git-commit: a0a20b99a76ba0346f00e3841a345e916ffde8ea
workflow-type: tm+mt
source-wordcount: '754'
ht-degree: 92%

---

# プライバシー

[!DNL Adobe Target] のプロセスおよび設定はプライバシーを考慮した設計になっており、個人情報保護法に準拠した方法で [!DNL Target] を使用できます。

## 機能使用状況データの収集

個々の機能使用状況データは、[!DNL Adobe] 内部で [!DNL Target] 機能が意図したとおりに実行されているかを確認する、または使用率が低い機能を特定する目的で収集されます。様々な待ち時間の測定値は、パフォーマンス上の問題に対処するために収集されます。個人データは収集されません。 

SDK での使用状況データのレポートからオプトアウトするには、クライアント初期化オプションで `telemetryEnabled` を false に設定します。詳しくは、[targetGlobalSettings の telemetryEnabled](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/) を参照してください。

## IP アドレスの収集 {#section_91BDB8105EBF4B85B7B8B8A14675AC85}

Web サイトの訪問者の IP アドレスは、Adobe Data Processing Center（DPC）に送信されます。訪問者のネットワーク設定によっては、この IP アドレスが訪問者のコンピューターの IP アドレスと一致しないことがあります。例えば、この IP アドレスは、Network Address Translation（NAT）ファイアウォール、HTTP プロキシ、またはインターネットゲートウェイの外部 IP アドレスである可能性があります。Target は、ユーザーの IP アドレスまたは個人情報（PII）を保存しません。IP アドレスは、セッション（メモリ内、永続化されません）の有効期間中に Target によってのみ使用されます。

## IP アドレスの最終オクテットの置き換え {#section_AE84EB0D7CE04E93B279B77732ADD61E}

アドビは、Adobe Client Care が Adobe Target に関して有効化できる新しい「プライバシーバイデザイン」設定を開発しました。この設定を有効にすると、アドビが IP アドレスを収集する際に、IP アドレスの最終オクテット（最後の部分）が隠されます。この匿名化処理は、IP アドレスに何らかの処理（オプションとして行われる IP アドレスの地域ルックアップを含む）を加える前に実行されます。

この機能を有効にすると、IP アドレスの匿名性が高まり、個人情報を特定できなくなります。そのため、個人情報の収集を認めない各国の個人情報保護法に準拠した形で Adobe Target をご利用いただくことができます。IP アドレスの不明化を行うと、市レベルの情報の取得が著しく困難になる場合があります。地域レベルおよび国レベルの情報の取得に関しては、それほど大きな影響はありません。

以下の設定を使用できます。

* 不明化なし：Target は IP アドレスのどの部分も非表示にしません。
* 最後のオクテット：Target は、IP アドレスの最後のオクテットを非表示にします。
* 完全な IP：Target は、IP アドレス全体を非表示にします。

Target は、完全な IP アドレスを受け取り、指定されたとおりに（最後のオクテットまたは完全な IP に設定されている場合は）不明化します。次に、Target は、セッション中に、不明化された IP アドレスをメモリに保持します。

>[!NOTE]
>
>現在使用している IP の不明化機能の設定、またはこの設定を有効にするには、[Adobe Client Care にお問い合わせ](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)ください。

## 地理特性 {#section_BB69F96559BD44BDA4177537C4A5345A}

IP アドレスの最終オクテットの置き換えを有効にした場合、Adobe Target のレポートでは、IP アドレスの残りの部分が分析されます。IP アドレスの最終オクテットを不明化しなかった場合は、Adobe Target では完全な IP アドレスが分析されます。地理特性機能を使用して、地理的な地域によって訪問者の位置を把握できます。地理特性データの精度は市レベルまたは郵便番号レベルにとどまり、個人レベルでの特定はできません。

IP アドレスが完全に不明化されている場合、地理特性と Geotargeting は使用できません。

## オプトアウトリンク {#section_E7A62B7B99C94B3A806CB262D16E27FC}

訪問者がカウントやコンテンツ配信をすべて停止（オプトアウト）できるオプトアウトリンクを、サイトに追加できます。

1. サイトに次のリンクを追加します。

   `<a href="https://clientcode.tt.omtrdc.net/optout"> Your Opt Out Language Here</a>`

1. （条件付き）CNAME を使用している場合、リンクには &quot;client=`clientcode` を含める必要があります。例：https://my.cname.domain/optout?client=clientcode

1. `clientcode` をお客様のクライアントコードに置き換え、このオプトアウト URL にリンクさせるテキストまたは画像を追加します。

このリンクをクリックした訪問者は、Cookie を削除するか、最初に訪問してから 2 年経過するまで、閲覧しているセッションから呼び出される mbox リクエストに含まれません。`disableClient` ドメイン内の「`clientcode.tt.omtrdc.net`」という訪問者に Cookie が設定され、この機能が適用されます。

ファーストパーティ Cookie の導入を使用している場合でも、提供されたオプトアウトは、サードパーティ Cookie を使用するように設定されます。クライアントがファーストパーティ Cookie のみを使用している場合は、オプトアウト Cookie が設定されているかどうかをチェックします。

## プライバシーとデータ保護規制

詳しくは、 [プライバシーとデータ保護規制](https://developer.adobe.com/target/before-implement/privacy/cmp-privacy-and-general-data-protection-regulation/){target=_blank} を参照してください。
