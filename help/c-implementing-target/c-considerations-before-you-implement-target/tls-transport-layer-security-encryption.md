---
keywords: tls;tls 1.0；トランスポート層セキュリティ；暗号化；tls 1.1;tls 1.2
description: ' [!DNL Target] がTLS(Transport Layer Security)プロトコルを使用して最高のセキュリティ標準を維持し、顧客データの安全性を高める方法について説明します。'
title: ' [!DNL Target] TLSを使用してセキュリティを提供する方法'
feature: プライバシーとセキュリティ
role: Developer
exl-id: 964a642a-830a-4556-a92a-d300670cd2fa
source-git-commit: f028d2b439fee5c2a622748126bb0a34d550a395
workflow-type: tm+mt
source-wordcount: '1140'
ht-degree: 54%

---

# TLS（Transport Layer Security）暗号化の変更

[!DNL Adobe]と[!DNL Adobe Target]がTLS(Transport Layer Security)を使用して最高のセキュリティ標準を維持し、顧客データの安全を促進する方法に関する変更に関する情報です。

Transport Layer Security（TLS）は、ネットワークを介してデータを安全に交換する必要のある Web ブラウザや他のアプリケーションで現在使用されている、最も広く展開されているセキュリティプロトコルです。アドビは古いプロトコルの廃止を義務付けるセキュリティコンプライアンス標準規格を持っており、最新でセキュアなバージョンを利用するため TLS 1.2 の使用を必須としています。

>[!IMPORTANT]
>
>2020年3月1日以降、Adobe Targetは、Visual Experience Composer(VEC)、拡張Experience Composer(EEC)、アクティビティ配信、APIなどに対するTLS 1.1の暗号化をサポートしなくなります。 問題を回避するため、2020年3月2日までにTLS 1.2にアップグレードしてください。

この変更が、お客様の顧客のデータやレポートに大きな影響を及ぼすことはないと認識しています。

## 拡張 Experience Composer (EEC) を有効化した Visual Experience Composer (VEC)  {#section_B374B62DEC3344C194AC7BECC2EE0AA0}

2020年3月1日現在のTLS 1.2はデフォルトで、TLS 1.1はサポートされなくなります。

アドビはお客様に TLS 1.2へと段階的に移行していただく予定です。ドメインが既に 1.2 に対応しているお客様は、何の変更もおこなわずに TLS 1.2 へと移行いただけます。ほとんどのお客様ドメインは既にTLS 1.2をサポートしています。ただし、お客様のドメインがTLS 1.2をサポートしていない場合は、そのドメインをTLS 1.1に留め置きます（2020年3月まで）。

この移行期間中は問題は発生しないはずです。万一、VEC がそれまでは動作していたサイトの読み込みをおこなわなくなった場合には、[Client Care チケットを開き、](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)考えられる原因としてこの移行を挙げてください。

ただし、TLS 1.2をサポートしていないTSL 1.1をご利用のお客様の場合は、ドメイン/インフラストラクチャのTLS 1.2への移行を計画する必要があります。TLS 1.1プロトコルは2020年3月1日まで引き続きサポートされます。 2020年3月1日以降、Targetは、拡張Experience Composer機能を介したVECで使用されるTLS 1.1プロトコルをサポートしません。

今後はすべてのお客様が TLS 1.2 へと移行することを強くお勧めしますが、新規のお客様で TLS 1.2 を&#x200B;*サポートしていない*&#x200B;場合は、拡張 Experience Composer にて TLS 1.1 を利用する必要があることをカスタマーケアまで連絡してください。ただし、2020年3月1日以降はサポートされなくなるので、TLS 1.2への移行を計画してください。

## アクティビティ配信 {#section_46CA5943E4354B259014C2BF340AECD6}

2020年3月2日以降、TargetサーバーはTLS 1.1をサポートしません。この変更により、Targetサーバーは、TLS 1.2（またはそれ以降）をサポートしていない旧型のデバイスやWebブラウザーを使用する訪問者からの要求を受け入れなくなります。 この結果、TLS 1.1 のみサポートする（あるいはデフォルトで TLS 1.1 をサポートする）旧型のデバイスやブラウザーは、Adobe Target からアクティビティコンテンツを受け取らないこととなります。サイトのデフォルトコンテンツがレンダリングされます。

影響を受ける旧型のデバイスおよびブラウザには以下が含まれます。

* Google Chrome(Chrome for Android)バージョン29以前
* Operaブラウザー(Opera Mobile)バージョン12.17以前
* Mozilla Firefox（モバイル用Firefox）バージョン26以前
* Android 4.3 およびそれ以前のバージョン
* Windows 7 の Internet Explorer 8-10 およびそれ以前のバージョン
* Windows Phone 8.0 の Internet Explorer 10
* Safari 6.0.4/OS X10.8.4 およびそれ以前のバージョン

この変更を計画する際は、次の点に注意してください（2020年3月1日の締め切りは、これらの項目すべてに影響します）。

* 準拠しているデバイスやブラウザーが、デフォルトのサイトに対応するように準備されていることを確認してください。
* Target レポートの訪問者数で、訪問者数に多少の低下がみられる可能性があることを知っておいてください。
* TLS 1.2をサポートしていない古いデバイスやブラウザーをターゲットにするために作成されたオーディエンスを変更する必要が生じる場合があります。これらのデバイスやブラウザーへの配信は機能しなくなります。

サポートされているブラウザーとそのバージョンについて詳しくは、「[サポートされているブラウザー](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md#reference_01B4BF99E7D545A7998773202A2F6100)」を参照してください。

## Adobe[!DNL Target] API {#section_88797FA5434049EC89F908853CC76903}

2020年3月1日以降、Target APIはTLS 1.1の暗号化をサポートしません。 API にアクセスするお客様は、この変更による影響の有無を確認してください。

* デフォルト設定で Java 7 を使用する API クライアントは、TLS 1.2 をサポートするための変更が必要です。詳細は、Java の Web サイトにある「[Changing default TLS protocol version for client end points: TLS 1.0 to TLS 1.2](https://www.java.com/en/configure_crypto.html)」を参照してください。
* Java 8 を使用している API クライアントは、デフォルト設定が TLS 1.2 なので、影響を受けません。
* その他のフレームワークを使用している API クライアントは、TLS 1.2 のサポートについてベンダーにお問い合わせください。

## Experience Cloud・ソリューション・インターフェイスへのアクセス {#section_748870ADE77B4CBEB18518DC784E64E5}

Target Standard/Premium のインターフェイスは既に[最新の Web ブラウザー](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md#reference_01B4BF99E7D545A7998773202A2F6100)を要件に定めているので、この変更で問題が生じる可能性はないと想定されます。Target に接続できない場合は、ブラウザーを最新バージョンにアップグレードしてください。

## ブラウザーで使用されているTLSバージョンの確認方法 {#section_44716DA2CEFF492BABD95AE32B1A3FC6}

Google Chromeを使用してWebサイトでTLSのバージョンを確認するには：

1. 影響を受けるWebサイトをChromeで開きます。
1. Chromeメニュー（縦並びの省略記号）から、その他のツール/開発者ツールをクリックします。

   ![Chrome Developer Tools](/help/c-implementing-target/c-considerations-before-you-implement-target/assets/chrome-developer-tools.png)

1. 「セキュリティ」タブを開き、「接続」でTLSバージョン情報を確認します。

   ![TLSバージョンの詳細](/help/c-implementing-target/c-considerations-before-you-implement-target/assets/chrome-tls-version.png)

>[!NOTE]
>
>これらの手順は、公開時点で最新で、変更される可能性があります。 これらの手順が変更された場合は、インターネット検索が簡単になります。  その他のブラウザーの手順も同様です。

## バージョン1.2未満のTLSをサポートするブラウザーで予想される動作 {#section_B5DA97A34EF248EB927610A5DA71EF2F}

この節では、at.js実装を使用する場合にのみ、1.2未満のTLSバージョンをサポートするブラウザーで期待される動作について説明します。 比較のために、この節では、TLS 1.2をサポートするブラウザーで期待される動作についても説明します。

### 中央のエンドポイント

| Target JavaScript 実装 | 詳細 |
|--- |--- |
| at.js | TLS 1.0またはTLS 1.1を有効にした場合：<ul><li>ブラウザーの開発者ツールの「ネットワーク」タブには「200 OK」と表示されます。これは、リクエストが成功したことを意味します。</li><li>ユーザーには、「このページに安全に接続できません」という内容のメッセージが表示されます。このメッセージは、サイトで廃止済みの TLS セキュリティ設定または安全でない TLS セキュリティ設定が使用されているためにこの問題が発生した可能性があることを示しています。</li><li>コンソールエラーは表示されません。</li></ul>TLS 1.2 が有効な場合：<ul><li>at.js ファイルがダウンロードされます。</li></ul> |

### エッジの端点

| Target JavaScript 実装 | 詳細 |
|--- |--- |
| [!DNL Adobe Experience Platform Web SDK] | TLS 1.0またはTLS 1.1を有効にした場合：<ul><li>ブラウザーの開発者ツールの「ネットワーク」タブには「200 OK」と表示されます。これは、リクエストが成功したことを意味します。</li><li>ユーザーには、「このページに安全に接続できません」という内容のメッセージが表示されます。このメッセージは、サイトで廃止済みの TLS セキュリティ設定または安全でない TLS セキュリティ設定が使用されているためにこの問題が発生した可能性があることを示しています。</li><li>コンソールエラーは表示されません。</li><li>デフォルトコンテンツが配信されます。</li></ul>TLS 1.2 が有効な場合：<ul><li>オファーコンテンツが配信されます。</li></ul> |
| at.js | TLS 1.0またはTLS 1.1を有効にした場合：<ul><li>ブラウザーの開発者ツールの「ネットワーク」タブには「200 OK」と表示されます。これは、リクエストが成功したことを意味します。</li><li>ユーザーには、「このページに安全に接続できません」という内容のメッセージが表示されます。このメッセージは、サイトで廃止済みの TLS セキュリティ設定または安全でない TLS セキュリティ設定が使用されているためにこの問題が発生した可能性があることを示しています。</li><li>コンソールエラーは表示されません。</li><li>デフォルトコンテンツが配信されます。</li></ul>TLS 1.2 が有効な場合：<ul><li>オファーコンテンツが配信されます。</li></ul> |

### ブラウザーのバージョン（Internet Explorerバージョン6、7または8）のオーディエンスをターゲットとするアクティビティ

>[!NOTE]
>
>オーディエンスが機能しなくなります。

| Target JavaScript 実装 | 詳細 |
|--- |--- |
| [!DNL Adobe Experience Platform Web SDK] | Platform SDKは、バージョン10より前のInternet Explorerではサポートされていません。 |
| at.js | at.js は、バージョン 10 よりも古い Internet Explorer ではサポートされていません。 |
