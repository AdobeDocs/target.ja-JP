---
keywords: at.js;ブラウザー user agent;user agent;client hints;user-agent
description: ' [!DNL Adobe Target] が user-agent と Client Hints を使用して、セグメンテーションおよびパーソナライゼーションのために訪問者を選定する方法を説明します。'
title: User Agent と Client Hints
feature: at.js
role: Developer
exl-id: 22d29bfe-e022-44b2-913f-c8c32c65bc48
source-git-commit: a0a20b99a76ba0346f00e3841a345e916ffde8ea
workflow-type: tm+mt
source-wordcount: '1346'
ht-degree: 95%

---

# User-agent と Client Hints

[!DNL Adobe Target]は、user-agent を使用して、セグメンテーションおよびパーソナライゼーションのために訪問者を選定します。

>[!NOTE]
>
>この記事の情報は、次の場所に適用されます。 [at.js バージョン 2.9.0](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank}（またはそれ以降）。


Web ブラウザーがサーバーに対してリクエストを行うたびに、リクエストのヘッダーに含まれているのは、ブラウザーおよびそのブラウザーが実行されている環境に関する情報です。インターネットの初期の頃から、このデータは、user-agent と呼ばれる単一の文字列で集計されています。

以下のテキストに、Safari ブラウザーを使用する Mac OS X ベースのコンピューターの user-agent の例を示します。

```
Mozilla/5.0 (Linux; Android 12; SM-S908E) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/101.0.4951.41 Mobile Safari/537.36 
```

リクエストを受け取ったサーバーは、この user-agent から、ブラウザーおよびオペレーティングシステムに関する以下の情報を識別できます。

| 情報 | 詳細 |
| --- | --- |
| ソフトウェア名 | Chrome |
| ソフトウェアのバージョン | 101 |
| 完全なソフトウェアのバージョン | 101.0.4951.41 |
| レイアウトエンジン名 | AppleWebKit |
| レイアウトエンジンのバージョン | 537.36 |
| オペレーティングシステム | Android |
| オペレーティングシステムのバージョン | Android 12（Snow Cone） |
| デバイス | SM-S908E（Samsung Galaxy S22 Ultra） |

user-agent 文字列に含まれるブラウザーおよびデバイス情報の量は、年々増加しています。

## User-agent の使用例

User-agents は、長い間、マーケティングチームや開発チームに対して、ブラウザー、オペレーティングシステムおよびデバイスがどのようにサイトコンテンツを表示するかに加えて、ユーザーがどのように web サイトとやり取りするかに関する重要なインサイトを提供するために使用されてきました。また、User-agents は、スパムのブロックやサイトをクロールするボットのフィルタリングなど、様々な追加の目的にも使用されます。

しかし、近年、一部のサイト所有者やマーケティングベンダーは、リクエストヘッダーに含まれる他の情報と共に user-agent を使用して、ユーザーが知らないうちにユーザーを特定する手段として使用できる、デジタル指紋を作成しています。サイト所有者にとって user-agent が重要な目的を果たすにもかかわらず、ブラウザー開発者は、サイト訪問者に関する潜在的なプライバシーの問題を制限するために、user-agents の動作方法の変更を決定しました。

User-Agent Client Hints は、ブラウザー開発者が開発したソリューションです。Client Hints を使用すると、サイトはブラウザー、オペレーティングシステムおよびデバイスの必要な情報を収集できる一方で、フィンガープリントのような秘密の追跡方法に対する保護を強化できます。

## Client hints

User-Agent Client Hints は、web サイト所有者に、user-agent で利用できるのとほぼ同じ量の情報にアクセスする機能を、よりプライバシーが保護された方法で提供します。モダンブラウザーが web サーバーに user-agent を送信する場合、それが必要かどうかにかかわらず、すべてのリクエストで user-agent 全体が送信されます。一方、Client Hints は、サーバーがクライアントについて知りたい追加情報をブラウザーに問い合わせる必要があるモデルを強制します。このリクエストを受け取ったブラウザーは、独自のポリシーやユーザー設定を適用して、どのデータが返されるかを決定できます。すべてのリクエストに対してデフォルトで user-agent 全体を公開する代わりに、明示的で監査可能な方法でアクセスが管理されるようになりました。

User-Agent Client Hints は、Chrome バージョン 89 以降で利用できます。Chromium ベースのブラウザー（Microsoft Edge、Opera、Brave、Chrome Android、Opera Android および Samsung Internet）の最近のバージョンも、Client Hints API をサポートしています。

ブラウザーから web サーバーに送信される最初のリクエストのヘッダーに含まれる Client Hints には、ブラウザーのブランド、ブラウザーのメジャーバージョン、クライアントがモバイルデバイスであるかどうかのインジケーターが含まれます。以下の例に示すように、単一の user-agent 文字列にグループ化されるのではなく、各データが独自のヘッダー値を持ちます。

```
Sec-CH-UA: "Chromium";v="101", "Google Chrome";v="101", " Not;A Brand";v="99" 
Sec-CH-UA-Mobile: ?0 
Sec-CH-UA-Platform: "macOS"
```

以下に、同じブラウザーに対する user-agent の例を示します。

```
Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/101.0.4951.54 Safari/537.36 
```

情報は似ていますが、サーバーへの最初のリクエストには、user-agent 文字列で利用可能なもののサブセットのみを含む Client Hints が含まれています。リクエストに含まれていないのは、OS アーキテクチャ、完全な OS のバージョン、レイアウトエンジン名、レイアウトエンジンのバージョンおよび完全なブラウザーのバージョンです。ただし、その後のリクエストでは、Client Hints API を使用すると、web サーバーは、デバイスに関する追加の高エントロピーの詳細を依頼できます。これらの高エントロピー値がリクエストされた場合、ブラウザーのポリシーやユーザー設定によっては、ブラウザーの応答にその情報が含まれることがあります。

以下に、高エントロピー値がリクエストされた場合に Client Hints API によって返される JSON オブジェクトの例を示します。

```
{ 

    "architecture":"x86", 
    "bitness":"64", 
    "brands":[ 
        { 
            "brand":" Not A;Brand", 
            "version":"99" 
        }, 
        { 
            "brand":"Chromium", 
            "version":"100" 
        }, 
        { 
            "brand":"Google Chrome", 
            "version":"100" 
        } 
    ], 
    "fullVersionList":[ 
        { 
            "brand":" Not A;Brand", 
            "version":"99.0.0.0" 
        }, 
        { 
            "brand":"Chromium", 
            "version":"100.0.4896.127" 
        }, 
        { 
            "brand":"Google Chrome", 
            "version":"100.0.4896.127" 
        } 
    ], 
    "mobile":false, 
    "model":"", 
    "platformVersion":"12.2.1" 
} 
```

高エントロピー値には、デフォルトの Client Hints 情報では利用できない、いくつかの追加情報が含まれます。以下の表に、デフォルトのリクエストと高エントロピーの User-Agent Client Hints 情報で利用できるデータの比較を示します。

| HTTP ヘッダー | JavaScript | User-agent | Client hint | 高エントロピーの Client hint |
| --- | --- | --- | --- | --- |
| Sec-CH-UA | brands | ○ | ○ | × |
| Sec-CH-UA-Platform | platform | ○ | ○ | × |
| Sec-CH-UA-Mobile | mobile | ○ | ○ | × |
| Sec-CH-UA-Platform-Version | platformVersion | ○ | × | ○ |
| Sec-CH-UA-Arch | architecture | ○ | × | ○ |
| Sec-CH-UA-Model | model | ○ | × | ○ |
| Sec-CH-UA-Bitness | ビット数 | ○ | × | ○ |
| Sec-CH-UA-Full-Version-List | fullVersionList | ○ | × | ○ |

## Client Hints への移行

現在、Chromium ベースのブラウザーは、web サーバーに対するリクエストのヘッダーで、Client Hints と共に user-agent を送信し続けています。ただし、2022年4月から2023年2月までは、user-agent 文字列に含まれるデータ量が削減されます。Safari や Firefox などの他のブラウザーは、引き続き user-agent 文字列を利用しますが、そこに含まれる情報量は削減される予定です。

## Clint Hints を必要とする [!DNL Target] の使用例

以下に、Client Hints を必要とする Target の使用例を示します。

### オーディエンス属性

[!DNL Target] オーディエンスを使用し、以下のオーディエンス属性のいずれかを使用する場合、[!DNL Target] では正しいセグメンテーションを実行するために Client Hints が必要です。

* ブラウザー
* オペレーティングシステム
* モバイル

### プロファイルスクリプト

プロファイルスクリプトを使用して、（user-agent を参照する） `user.browser` 属性を参照する場合、1 つ以上の Client Hints も確認するようにプロファイルスクリプトを更新する必要がある可能性があります。関数 `user.clientHint('sec-ch-ua-xxxxx')` を使用して、任意の Client Hints にアクセスすることもできます。Client Hint ヘッダー名は、すべて小文字である必要があります。

以下の例に、プロファイルスクリプトで Windows OS を適切に検出する方法を示します。

```
"return (((user.browser != null) && (user.browser.indexOf(\"Windows\") > -1)) || " + 
      "((user.clientHint('sec-ch-ua-platform') != null) && 
(user.clientHint('sec-ch-ua-platform') === 'Windows')));" 
```

以下の節に、Client Hints ヘッダーとその対応するプロファイルスクリプトの使用法のセマンティクスを示します。

#### Sec-CH-UA

エントロピー：低
ドキュメント：[https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA) {target=_blank}
オーディエンス属性：ブラウザー
プロファイルスクリプトの使用法：`user.clientHint('sec-ch-ua')`

#### Sec-CH-UA-Arch

エントロピー：高
ドキュメント：[https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Arch](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Arch) {target=_blank}
オーディエンス属性：プロファイルスクリプトを使用してユーザーに公開される。
プロファイルスクリプトの使用法：`user.clientHint('sec-ch-ua-arch')`

#### Sec-CH-UA-Bitness

エントロピー：高
ドキュメント：[https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Bitness](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Bitness) {target=_blank}
オーディエンス属性：プロファイルスクリプトを使用してユーザーに公開される。
プロファイルスクリプトの使用法：`user.clientHint('sec-ch-ua-bitness')`

#### Sec-CH-UA-Full-Version-List

エントロピー：高
ドキュメント：[https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Full-Version-List](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Full-Version-List) {target=_blank}
オーディエンス属性：ブラウザー
プロファイルスクリプトの使用法：`user.clientHint('sec-ch-ua-full-version-list')`

#### Sec-CH-UA-Mobile

エントロピー：低
ドキュメント：[https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Mobile](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Mobile) {target=_blank}
オーディエンス属性：モバイル
プロファイルスクリプトの使用法：`user.clientHint('sec-ch-ua-mobile')`

#### Sec-CH-UA-Model

エントロピー：高
ドキュメント：[https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Model](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Model) {target=_blank}
オーディエンス属性：モバイル
プロファイルスクリプトの使用法：`user.clientHint('sec-ch-ua-model')`

#### Sec-CH-UA-Platform

エントロピー：低
ドキュメント：[https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Platform](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Platform) {target=_blank}
オーディエンス属性：オペレーティングシステム
プロファイルスクリプトの使用法：`user.clientHint('sec-ch-ua-platform')`

#### Sec-CH-UA-Platform-Version

エントロピー：高
ドキュメント：[https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Platform-Version](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Platform-Version) {target=_blank}
オーディエンス属性：プロファイルスクリプトを使用してユーザーに公開される。
プロファイルスクリプトの使用法：`user.clientHint('sec-ch-ua-platform-version')`

## Client Hints を [!DNL Adobe Target] に渡す方法

以下の節に、[!DNL Target] 実装に応じた Client Hints の渡し方に関する詳細情報を示します。

### at.js バージョン 2.9.0（またはそれ以降）

at.js 2.9.0 以降では、`getOffer/getOffers()` が呼び出されると、User Agent Client Hints がブラウザーから自動的に収集されて、[!DNL Target] に送信されます。デフォルトでは、at.js は、「低エントロピー」の Client Hints のみを収集します。前の節で「高エントロピー」に分類されたデータに基づいてオーディエンスセグメンテーションを実行したり、プロファイルスクリプトを使用したりする場合、`targetGlobalSettings` を使用してブラウザーから「高エントロピー」の Client Hints を収集するように at.js を設定する必要があります。

`window.targetGlobalSettings = { allowHighEntropyClientHints: true };`

### サーバーサイド SDK

サーバー側 SDK を使用してクライアントヒントを渡す方法について詳しくは、 [クライアントヒント](https://developer.adobe.com/target/implement/server-side/sdk-guides/core-principles/audience-targeting/){target=_blank} の下 *オーディエンスのターゲティング* 内 *Adobe Target SDK* ドキュメント。
