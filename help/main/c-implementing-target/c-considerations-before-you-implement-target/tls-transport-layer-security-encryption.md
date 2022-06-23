---
keywords: TLS;TLS 1.0；トランスポート層セキュリティ；暗号化；TLS 1.1;TLS 1.2
description: 方法 [!DNL Target] は、最高のセキュリティ標準を維持し、顧客データの安全を高めるために、TLS(Transport Layer Security) プロトコルを使用します。
title: 方法 [!DNL Target] TLS を使用してセキュリティを提供する
feature: Privacy & Security
role: Developer
exl-id: 964a642a-830a-4556-a92a-d300670cd2fa
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '1148'
ht-degree: 54%

---

# TLS（Transport Layer Security）暗号化の変更

変更方法に関する情報 [!DNL Adobe] および [!DNL Adobe Target] 最高のセキュリティ標準を維持し、顧客データの安全を促進するには、TLS(Transport Layer Security) を使用します。

Transport Layer Security（TLS）は、ネットワークを介してデータを安全に交換する必要のある Web ブラウザや他のアプリケーションで現在使用されている、最も広く展開されているセキュリティプロトコルです。アドビは古いプロトコルの廃止を義務付けるセキュリティコンプライアンス標準規格を持っており、最新でセキュアなバージョンを利用するため TLS 1.2 の使用を必須としています。

>[!IMPORTANT]
>
>2020 年 3 月 1 日以降、Adobe Targetは Visual Experience Composer(VEC)、Enhanced Experience Composer(EEC)、アクティビティ配信、API などに対する TLS 1.1 の暗号化をサポートしなくなります。 問題を回避するには、2020 年 3 月 2 日より前に TLS 1.2 にアップグレードしてください。

この変更が、お客様の顧客のデータやレポートに大きな影響を及ぼすことはないと認識しています。

## 拡張 Experience Composer (EEC) を有効化した Visual Experience Composer (VEC)  {#section_B374B62DEC3344C194AC7BECC2EE0AA0}

2020 年 3 月 1 日現在のデフォルトは TLS 1.2 で、TLS 1.1 はサポートされなくなります。

アドビはお客様に TLS 1.2へと段階的に移行していただく予定です。ドメインが既に 1.2 に対応しているお客様は、何の変更もおこなわずに TLS 1.2 へと移行いただけます。ほとんどのお客様ドメインは既に TLS 1.2 をサポートしています。ただし、お客様のドメインが TLS 1.2 をサポートしていない場合は、それらのドメインを TLS 1.1 に留め置きます（2020 年 3 月まで）。

この移行期間中は問題は発生しないはずです。万一、VEC がそれまでは動作していたサイトの読み込みをおこなわなくなった場合には、[Client Care チケットを開き、](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)考えられる原因としてこの移行を挙げてください。

ただし、TLS 1.2 をサポートしていない TSL 1.1 をご利用のお客様の場合は、ドメイン/インフラストラクチャの TLS 1.2 への移行を計画する必要があります。TLS 1.1 プロトコルは 2020 年 3 月 1 日まで引き続きサポートされます。 2020 年 3 月 1 日以降、Target は、拡張 Experience Composer 機能を介した VEC で使用される TLS 1.1 プロトコルをサポートしません。

今後はすべてのお客様が TLS 1.2 へと移行することを強くお勧めしますが、新規のお客様で TLS 1.2 を&#x200B;*サポートしていない*&#x200B;場合は、拡張 Experience Composer にて TLS 1.1 を利用する必要があることをカスタマーケアまで連絡してください。ただし、2020 年 3 月 1 日以降は TLS 1.2 への移行もサポートされなくなるので、TLS 1.2 への移行を計画してください。

## アクティビティの配信 {#section_46CA5943E4354B259014C2BF340AECD6}

2020 年 3 月 1 日以降、Target サーバーは TLS 1.1 をサポートしません。この変更により、TLS 1.2（またはそれ以降）をサポートしていない旧型のデバイスや Web ブラウザーを使用する訪問者からの要求を Target サーバーが受け入れなくなります。 この結果、TLS 1.1 のみサポートする（あるいはデフォルトで TLS 1.1 をサポートする）旧型のデバイスやブラウザーは、Adobe Target からアクティビティコンテンツを受け取らないこととなります。サイトのデフォルトコンテンツがレンダリングされます。

影響を受ける旧型のデバイスおよびブラウザには以下が含まれます。

* Google Chrome（Android 用 Chrome）バージョン 29 以前
* Opera ブラウザー (Opera Mobile) バージョン 12.17 以前
* Mozilla Firefox（モバイル用 Firefox）バージョン 26 以前
* Android 4.3 およびそれ以前のバージョン
* Windows 7 の Internet Explorer 8-10 およびそれ以前のバージョン
* Windows Phone 8.0 の Internet Explorer 10
* Safari 6.0.4/OS X10.8.4 およびそれ以前のバージョン

この変更を計画する際は、次の点に注意してください（2020 年 3 月 1 日の締切は、これらの項目すべてに影響します）。

* 準拠しているデバイスやブラウザーが、デフォルトのサイトに対応するように準備されていることを確認してください。
* Target レポートの訪問者数で、訪問者数に多少の低下がみられる可能性があることを知っておいてください。
* TLS 1.2 をサポートしていない古いデバイスやブラウザーをターゲットにするために、特別に作成したオーディエンスを変更する必要が生じる場合があります。これらのデバイスやブラウザーへの配信は機能しなくなります。

サポートされているブラウザーとそのバージョンについて詳しくは、 [サポートされているブラウザー](https://developer.adobe.com/target/before-implement/supported-browsers/).

## Adobe [!DNL Target] API {#section_88797FA5434049EC89F908853CC76903}

2020 年 3 月 1 日以降、Target API は TLS 1.1 の暗号化をサポートしません。 API にアクセスするお客様は、この変更による影響の有無を確認してください。

* デフォルト設定で Java 7 を使用する API クライアントは、TLS 1.2 をサポートするための変更が必要です。詳細は、Java の Web サイトにある「[Changing default TLS protocol version for client end points: TLS 1.0 to TLS 1.2](https://www.java.com/en/configure_crypto.html)」を参照してください。
* Java 8 を使用している API クライアントは、デフォルト設定が TLS 1.2 なので、影響を受けません。
* その他のフレームワークを使用している API クライアントは、TLS 1.2 のサポートについてベンダーにお問い合わせください。

## Experience Cloud・ソリューション・インタフェースへのアクセス {#section_748870ADE77B4CBEB18518DC784E64E5}

Target Standard/Premium のインターフェイスは既に[最新の Web ブラウザー](https://developer.adobe.com/target/before-implement/supported-browsers/)を要件に定めているので、この変更で問題が生じる可能性はないと想定されます。Target に接続できない場合は、ブラウザーを最新バージョンにアップグレードしてください。

## ブラウザーで使用されている TLS のバージョンを確認する方法 {#section_44716DA2CEFF492BABD95AE32B1A3FC6}

Google Chrome を使用して Web サイトで TLS のバージョンを確認するには：

1. 影響を受ける Web サイトを Chrome で開きます。
1. Chrome メニュー（縦並びの省略記号）から、その他のツール/開発者ツールをクリックします。

   ![Chrome Developer Tools](/help/main/c-implementing-target/c-considerations-before-you-implement-target/assets/chrome-developer-tools.png)

1. 「セキュリティ」タブを開き、「接続」の下にある TLS バージョン情報を確認します。

   ![TLS バージョンの詳細](/help/main/c-implementing-target/c-considerations-before-you-implement-target/assets/chrome-tls-version.png)

>[!NOTE]
>
>これらの手順は、公開時点で最新で、変更される場合があります。 これらの手順が変更された場合は、クイックインターネット検索が役立ちます。  他のブラウザーも同様の手順を実行します。

## 1.2 未満の TLS バージョンをサポートするブラウザーで予想される動作 {#section_B5DA97A34EF248EB927610A5DA71EF2F}

この節では、at.js 実装を使用する場合にのみ、1.2 未満の TLS バージョンをサポートするブラウザーで期待される動作について説明します。 比較のために、この節では、TLS 1.2 をサポートするブラウザーで期待される動作についても説明します。

### 中央のエンドポイント

| Target JavaScript 実装 | 詳細 |
|--- |--- |
| at.js | TLS 1.0 または TLS 1.1 を有効にした場合：<ul><li>ブラウザーの開発者ツールの「ネットワーク」タブには「200 OK」と表示されます。これは、リクエストが成功したことを意味します。</li><li>ユーザーには、「このページに安全に接続できません」という内容のメッセージが表示されます。このメッセージは、サイトで廃止済みの TLS セキュリティ設定または安全でない TLS セキュリティ設定が使用されているためにこの問題が発生した可能性があることを示しています。</li><li>コンソールエラーは表示されません。</li></ul>TLS 1.2 が有効な場合：<ul><li>at.js ファイルがダウンロードされます。</li></ul> |

### エッジの端点

| Target JavaScript 実装 | 詳細 |
|--- |--- |
| [!DNL Adobe Experience Platform Web SDK] | TLS 1.0 または TLS 1.1 を有効にした場合：<ul><li>ブラウザーの開発者ツールの「ネットワーク」タブには「200 OK」と表示されます。これは、リクエストが成功したことを意味します。</li><li>ユーザーには、「このページに安全に接続できません」という内容のメッセージが表示されます。このメッセージは、サイトで廃止済みの TLS セキュリティ設定または安全でない TLS セキュリティ設定が使用されているためにこの問題が発生した可能性があることを示しています。</li><li>コンソールエラーは表示されません。</li><li>デフォルトコンテンツが配信されます。</li></ul>TLS 1.2 が有効な場合：<ul><li>オファーコンテンツが配信されます。</li></ul> |
| at.js | TLS 1.0 または TLS 1.1 を有効にした場合：<ul><li>ブラウザーの開発者ツールの「ネットワーク」タブには「200 OK」と表示されます。これは、リクエストが成功したことを意味します。</li><li>ユーザーには、「このページに安全に接続できません」という内容のメッセージが表示されます。このメッセージは、サイトで廃止済みの TLS セキュリティ設定または安全でない TLS セキュリティ設定が使用されているためにこの問題が発生した可能性があることを示しています。</li><li>コンソールエラーは表示されません。</li><li>デフォルトコンテンツが配信されます。</li></ul>TLS 1.2 が有効な場合：<ul><li>オファーコンテンツが配信されます。</li></ul> |

### ブラウザーのバージョン（Internet Explorer、バージョン 6、7 または 8）のオーディエンスを使用してターゲット設定されたアクティビティ

>[!NOTE]
>
>オーディエンスが機能しなくなります。

| Target JavaScript 実装 | 詳細 |
|--- |--- |
| [!DNL Adobe Experience Platform Web SDK] | Platform SDK は、バージョン 10 より前の Internet Explorer ではサポートされていません。 |
| at.js | at.js は、バージョン 10 よりも古い Internet Explorer ではサポートされていません。 |
