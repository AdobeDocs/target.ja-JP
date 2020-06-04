---
keywords: tls;tls 1.0;transport layer security;encryption;tls 1.1;tls 1.2
description: 最高のセキュリティ標準規格の維持と顧客データ安全の促進のための、アドビと Target による TLS（Transport Layer Security）利用方法の変更に関する情報。
title: TLS（Transport Layer Security）暗号化の変更
topic: Standard
uuid: d222b966-ee73-4254-87b7-68099583e0dd
translation-type: tm+mt
source-git-commit: 5b13ad02691a685dd76db2b390e030f8aef30dd9
workflow-type: tm+mt
source-wordcount: '1233'
ht-degree: 61%

---


# TLS（Transport Layer Security）暗号化の変更{#tls-transport-layer-security-encryption-changes}

アドビとアドビのターゲットがTLS(Transport Layer Security)を使用して最高のセキュリティ標準を維持し、顧客データの安全性を高める方法に関する変更について説明します。

Transport Layer Security（TLS）は、ネットワークを介してデータを安全に交換する必要のある Web ブラウザや他のアプリケーションで現在使用されている、最も広く展開されているセキュリティプロトコルです。アドビは古いプロトコルの廃止を義務付けるセキュリティコンプライアンス標準規格を持っており、最新でセキュアなバージョンを利用するため TLS 1.2 の使用を必須としています。

>[!IMPORTANT]
>
>2020年3月1日以降、アドビターゲットは、Visual Experience Composer(VEC)、拡張Experience Composer(EEC)、アクティビティ配信、APIなどに対するTLS 1.1暗号化をサポートしなくなります。 問題を回避するため、2020年3月1日までにTLS 1.2にアップグレードしてください。

この変更が、お客様の顧客のデータやレポートに大きな影響を及ぼすことはないと認識しています。

## 拡張 Experience Composer (EEC) を有効化した Visual Experience Composer (VEC) {#section_B374B62DEC3344C194AC7BECC2EE0AA0}

TLS 1.2は2020年3月1日現在のデフォルトで、TLS 1.1はサポートされなくなります。

アドビはお客様に TLS 1.2へと段階的に移行していただく予定です。ドメインが既に 1.2 に対応しているお客様は、何の変更もおこなわずに TLS 1.2 へと移行いただけます。ほとんどの顧客ドメインは既にTLS 1.2をサポートしています。 ただし、ドメインがTLS 1.2をサポートしていない場合は、現在と同様にTLS 1.1上のドメインを保持します（2020年3月まで）。

この移行期間中は問題は発生しないはずです。万一、VEC がそれまでは動作していたサイトの読み込みをおこなわなくなった場合には、[Client Care チケットを開き、](../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)考えられる原因としてこの移行を挙げてください。

ただし、TLS 1.2をサポートしていないTSL 1.1をご利用のお客様の場合は、ドメイン/インフラストラクチャをTLS 1.2に移動する計画を立てる必要があります。TLS 1.1プロトコルは2020年3月1日まで引き続きサポートされます。 2020年3月1日以降、ターゲットは、拡張Experience Composer機能を介してVECに使用するTLS 1.1プロトコルをサポートしなくなります。

今後はすべてのお客様が TLS 1.2 へと移行することを強くお勧めしますが、新規のお客様で TLS 1.2 を&#x200B;*サポートしていない*&#x200B;場合は、拡張 Experience Composer にて TLS 1.1 を利用する必要があることをカスタマーケアまで連絡してください。ただし、2020年3月1日以降はサポートされないので、TLS 1.2への移行を計画してください。

## Activity delivery {#section_46CA5943E4354B259014C2BF340AECD6}

2020年3月1日以降、ターゲットサーバーはTLS 1.1をサポートしなくなります。この変更により、ターゲットサーバーは、古い訪問者やTLS 1.2以降をサポートしないWebブラウザーからの要求を受け付けなくなります。 この結果、TLS 1.1 のみサポートする（あるいはデフォルトで TLS 1.1 をサポートする）旧型のデバイスやブラウザーは、Adobe Target からアクティビティコンテンツを受け取らないこととなります。サイトのデフォルトコンテンツがレンダリングされます。

影響を受ける旧型のデバイスおよびブラウザには以下が含まれます。

* Google Chrome(Chrome for Android)バージョン29以前
* Operaブラウザー(Opera Mobile)バージョン12.17以前
* Mozilla Firefox（Mobile用Firefox）バージョン26以前
* Android 4.3 およびそれ以前のバージョン
* Windows 7 の Internet Explorer 8-10 およびそれ以前のバージョン
* Windows Phone 8.0 の Internet Explorer 10
* Safari 6.0.4/OS X10.8.4 およびそれ以前のバージョン

この変更を計画している場合は、次の点に注意してください（2020年3月1日の期限は、これらすべての項目に影響します）。

* 準拠しているデバイスやブラウザーが、デフォルトのサイトに対応するように準備されていることを確認してください。
* Target レポートの訪問者数で、訪問者数に多少の低下がみられる可能性があることを知っておいてください。
* 古いターゲットのデバイスやTLS 1.2をサポートしないブラウザに対して作成したオーディエンスを変更する必要が生じる場合があります。これらのデバイスやブラウザへの配信は機能しなくなります。

For more details about supported browsers and their versions, see [Supported Browsers](../../c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md#reference_01B4BF99E7D545A7998773202A2F6100).

## Adobe Target API {#section_88797FA5434049EC89F908853CC76903}

2020年3月1日以降、ターゲットAPIはTLS 1.1暗号化をサポートしなくなります。 API にアクセスするお客様は、この変更による影響の有無を確認してください。

* デフォルト設定で Java 7 を使用する API クライアントは、TLS 1.2 をサポートするための変更が必要です。詳細は、Java の Web サイトにある「[Changing default TLS protocol version for client end points: TLS 1.0 to TLS 1.2](https://www.java.com/en/configure_crypto.html)」を参照してください。
* Java 8 を使用している API クライアントは、デフォルト設定が TLS 1.2 なので、影響を受けません。
* その他のフレームワークを使用している API クライアントは、TLS 1.2 のサポートについてベンダーにお問い合わせください。

## Access to Experience Cloud Solutions interfaces {#section_748870ADE77B4CBEB18518DC784E64E5}

Target Standard/Premium のインターフェイスは既に[最新の Web ブラウザー](../../c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md#reference_01B4BF99E7D545A7998773202A2F6100)を要件に定めているので、この変更で問題が生じる可能性はないと想定されます。Target に接続できない場合は、ブラウザーを最新バージョンにアップグレードしてください。

## How to check which TLS version your browser uses {#section_44716DA2CEFF492BABD95AE32B1A3FC6}

Google Chromeを使用してWebサイトのTLSバージョンを確認するには：

1. 影響を受けるWebサイトをChromeで開きます。
1. Chromeメニュー（3つの垂直な三点リーダー）で、その他のツール/開発者ツールをクリックします。

   ![Chrome Developer Tools](/help/c-implementing-target/c-considerations-before-you-implement-target/assets/chrome-developer-tools.png)

1. 「セキュリティ」タブを開き、「接続」でTLSのバージョン情報を確認します。

   ![TLSバージョンの詳細](/help/c-implementing-target/c-considerations-before-you-implement-target/assets/chrome-tls-version.png)

>[!NOTE]
>
>これらの手順は、発行時点で最新のもので、変更されることがあります。 これらの手順が変更された場合は、インターネットのクイック検索が役立ちます。  他のブラウザーも同様の手順を実行します。

## 1.2未満のTLSバージョンをサポートするブラウザーでの予期される動作 {#section_B5DA97A34EF248EB927610A5DA71EF2F}

この節では、at.jsまたはmbox.js実装を使用する場合にのみ、1.2より前のTLSバージョンをサポートするブラウザーでの期待値について説明します。 比較のため、この節では、TLS 1.2をサポートするブラウザでの期待値についても説明します。

### 中央エンドポイント

| Target JavaScript 実装 | 詳細 |
|--- |--- |
| at.js | TLS 1.0またはTLS 1.1が有効な場合：<ul><li>ブラウザーの開発者ツールの「ネットワーク」タブには「200 OK」と表示されます。これは、リクエストが成功したことを意味します。</li><li>ユーザーには、「このページに安全に接続できません」という内容のメッセージが表示されます。このメッセージは、サイトで廃止済みの TLS セキュリティ設定または安全でない TLS セキュリティ設定が使用されているためにこの問題が発生した可能性があることを示しています。</li><li>コンソールエラーは表示されません。</li></ul>TLS 1.2 が有効な場合：<ul><li>at.js ファイルがダウンロードされます。</li></ul> |
| mbox.js | TLS 1.0またはTLS 1.1が有効な場合：<ul><li>ブラウザーの開発者ツールの「ネットワーク」タブには「200 OK」と表示されます。これは、リクエストが成功したことを意味します。</li><li>ユーザーには、「このページに安全に接続できません」という内容のメッセージが表示されます。このメッセージは、サイトで廃止済みの TLS セキュリティ設定または安全でない TLS セキュリティ設定が使用されているためにこの問題が発生した可能性があることを示しています。</li><li>コンソールエラーは表示されません。</li></ul>TLS 1.2 が有効な場合：<ul><li>mbox.js ファイルがダウンロードされます。</li></ul> |

### エッジの端点

| Target JavaScript 実装 | 詳細 |
|--- |--- |
| at.js | TLS 1.0またはTLS 1.1が有効な場合：<ul><li>ブラウザーの開発者ツールの「ネットワーク」タブには「200 OK」と表示されます。これは、リクエストが成功したことを意味します。</li><li>ユーザーには、「このページに安全に接続できません」という内容のメッセージが表示されます。このメッセージは、サイトで廃止済みの TLS セキュリティ設定または安全でない TLS セキュリティ設定が使用されているためにこの問題が発生した可能性があることを示しています。</li><li>コンソールエラーは表示されません。</li><li>デフォルトコンテンツが配信されます。</li></ul>TLS 1.2 が有効な場合：<ul><li>オファーコンテンツが配信されます。</li></ul> |
| mbox.js | TLS 1.0またはTLS 1.1が有効な場合：<ul><li>ブラウザーの開発者ツールの「ネットワーク」タブには「200 OK」と表示されます。これは、リクエストが成功したことを意味します。</li><li>ユーザーには、「このページに安全に接続できません」という内容のメッセージが表示されます。このメッセージは、サイトで廃止済みの TLS セキュリティ設定または安全でない TLS セキュリティ設定が使用されているためにこの問題が発生した可能性があることを示しています。</li><li>コンソールエラーは表示されません。</li><li>デフォルトコンテンツが配信されます。</li></ul>TLS 1.2 が有効な場合：<ul><li>オファーコンテンツが配信されます</li></ul> |

### ブラウザーのバージョンオーディエンスを対象としたアクティビティ（Internet Explorer、バージョン6、7または8）

>[!NOTE]
>
>オーディエンスが機能しなくなります。

| Target JavaScript 実装 | 詳細 |
|--- |--- |
| at.js | at.js は、バージョン 10 よりも古い Internet Explorer ではサポートされていません。 |
| mbox.js | TLS 1.0またはTLS 1.1が有効な場合：<ul><li>デフォルトコンテンツが配信されます。</li><li>Target リクエストは送信されません。</li><li>コンソールエラーは表示されません。</li><li>ブラウザーの開発者ツールの「ネットワーク」タブには「200 OK」と表示されます。これは、リクエストが成功したことを意味します。</li></ul>TLS 1.2 が有効な場合：<ul><li>オファーコンテンツが配信されます。</li></ul> |