---
keywords: at.js；ブラウザーユーザーエージェント；ユーザーエージェント；クライアントヒント；user-agent
description: 方法 [!DNL Adobe Target] は、ユーザーエージェントとクライアントヒントを使用して、訪問者をセグメント化とパーソナライゼーションの対象に認定します。
title: ユーザーエージェントとクライアントヒント
feature: at.js
role: Developer
exl-id: 22d29bfe-e022-44b2-913f-c8c32c65bc48
source-git-commit: c351044163a6fb32ca72fa015724d3b0388c059a
workflow-type: tm+mt
source-wordcount: '1332'
ht-degree: 3%

---

# ユーザーエージェントとクライアントヒント

[!DNL Adobe Target] はユーザーエージェントを使用して、訪問者をセグメント化とパーソナライゼーションの対象に認定します。

>[!NOTE]
>
>この記事の情報は、次の場所に適用されます。 [at.js バージョン 2.9.0](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) （またはそれ以降）。


Web ブラウザーがサーバーに対してリクエストをおこなうたびに、リクエストのヘッダーに含まれるのは、ブラウザーと、ブラウザーが実行される環境に関する情報です。 インターネットの初期の頃から、このデータは user-agent と呼ばれる単一の文字列に集計されていました。

以下は、Safari ブラウザーを使用したMac OS X ベースのコンピューターのサンプルユーザーエージェントです。

```
Mozilla/5.0 (Linux; Android 12; SM-S908E) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/101.0.4951.41 Mobile Safari/537.36 
```

このユーザーエージェントから、要求を受け取ったサーバーは、ブラウザーとオペレーティングシステムに関する次の情報を識別できます。

| 情報 | 詳細 |
| --- | --- |
| ソフトウェア名 | Chrome |
| ソフトウェアバージョン | 101 |
| 完全なソフトウェアバージョン | 101.0.4951.41 |
| レイアウトエンジン名 | AppleWebKit |
| レイアウトエンジンのバージョン | 537.36 |
| オペレーティングシステム | Android |
| オペレーティングシステムのバージョン | Android 12（スノーコーン） |
| デバイス | SM-S908E (Samsung Galaxy S22 Ultra) |

長年にわたり、ユーザーエージェント文字列に含まれるブラウザーおよびデバイス情報の量は増加しています。

## ユーザーエージェントの使用例

ユーザーエージェントは、長い間、マーケティングチームと開発者チームに、ブラウザーやオペレーティングシステムに関する重要なインサイトを提供してきました。 およびデバイスは、サイトのコンテンツ、およびユーザーが web サイトとどのようにやり取りするかを表示します。 また、ユーザーエージェントは、スパムをブロックし、さまざまな追加目的でサイトをクロールするボットをフィルタリングするためにも使用されます。

しかし、近年、サイトの所有者やマーケティングベンダーの中には、要求ヘッダーに含まれる他の情報と共に、ユーザーエージェントを使用して、ユーザーを知らないユーザーを識別する手段として使用できるデジタルフィンガープリントを作成している。 ユーザーエージェントがサイトの所有者に提供する重要な目的にもかかわらず、ブラウザー開発者は、ユーザーエージェントの動作方法を変更して、サイト訪問者に対する潜在的なプライバシーの問題を制限することにしました。

User-Agent Client Hints は、ソリューションブラウザー開発者が開発したヒントです。 クライアントヒントを使用すると、サイトで必要なブラウザー、オペレーティングシステム、デバイス情報を収集できる一方で、フィンガープリントなどのコバートトラッキング方法に対する保護も強化できます。

## クライアントヒント

User-Agent Client Hints を使用すると、Web サイトの所有者は、ユーザーエージェントで使用可能な同じ情報の多くにアクセスできますが、よりプライバシーを保持する方法でアクセスできます。 最新のブラウザーがユーザーエージェントを Web サーバーに送信する場合、必要かどうかに関係なく、要求ごとにユーザーエージェント全体が送信されます。 一方、クライアントヒントは、サーバーがブラウザーに対して、クライアントに関して知りたい追加情報を要求する必要があるモデルを適用します。 このリクエストを受け取ると、ブラウザーは独自のポリシーまたはユーザー設定を適用して、返されるデータを決定できます。 すべてのリクエストでデフォルトでユーザーエージェント全体を公開する代わりに、明示的で監査可能な方法でアクセスを管理するようになりました。

Chrome では、バージョン 89 以降、ユーザーエージェントクライアントヒントを使用できます。 Microsoft Edge、Opera、Brave、Chrome Android、Opera Android、Samsung Internet など、Chromium ベースの最新バージョンもクライアントヒント API をサポートしています。

ブラウザーが Web サーバーに対しておこなう最初のリクエストのヘッダーに含まれるクライアントヒントには、ブラウザーのブランド、ブラウザーのメジャーバージョンおよびクライアントがモバイルデバイスかどうかを示すインジケーターが含まれます。 次の例に示すように、データの各部には独自のヘッダー値があり、1 つのユーザーエージェント文字列にグループ化されるのではありません。

```
Sec-CH-UA: "Chromium";v="101", "Google Chrome";v="101", " Not;A Brand";v="99" 
Sec-CH-UA-Mobile: ?0 
Sec-CH-UA-Platform: "macOS"
```

以下のサンプルは、同じブラウザーのユーザーエージェントです。

```
Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/101.0.4951.54 Safari/537.36 
```

情報は似ていますが、サーバへの最初の要求には、user-agent 文字列に含まれる情報のサブセットのみが含まれるクライアントヒントが含まれます。 リクエストに見つからないのは、OS アーキテクチャ、フル OS バージョン、レイアウトエンジン名、レイアウトエンジンバージョン、フルブラウザーバージョンです。 ただし、後続のリクエストでは、クライアントヒント API を使用して、Web サーバーがデバイスに関する追加の高エントロピーな詳細を要求できるようにします。 これらの高エントロピー値が要求された場合、ブラウザーのポリシーまたはユーザーの設定に応じて、ブラウザーの応答にその情報が含まれる場合があります。

次の例は、高エントロピー値が要求された場合にクライアントヒント API から返される JSON オブジェクトです。

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

高エントロピー値には、デフォルトのクライアントヒント情報では利用できない追加の情報が含まれます。 次の表に、デフォルトの要求で使用可能なデータと、高エントロピーの User-Agent Client Hints 情報の詳細を示します。

| HTTP ヘッダー | JavaScript | User-agent | クライアントのヒント | 高エントロピークライアントヒント |
| --- | --- | --- | --- | --- |
| Sec-CH-UA | ブランド | ○ | ○ | × |
| Sec-CH-UA-Platform | プラットフォーム | ○ | ○ | × |
| Sec-CH-UA-Mobile | モバイル | ○ | ○ | × |
| Sec-CH-UA-Platform-Version | platformVersion | ○ | × | ○ |
| Sec-CH-UA-Arch | アーキテクチャ | ○ | × | ○ |
| Sec-CH-UA-Model | model | ○ | × | ○ |
| Sec-CH-UA-Bitness | ビットネス | ○ | × | ○ |
| Sec-CH-UA-Full-Version-List | fullVersionList | ○ | × | ○ |

## クライアントヒントへの移行

現在、Chromium ベースのブラウザーは、Web サーバーに対して行われたリクエストのヘッダーにあるクライアントヒントと共に、ユーザーエージェントを送信し続けます。 ただし、2022 年 4 月以降、2023 年 2 月までは、ユーザーエージェント文字列に含まれるデータ量が削減されます。 Safari や Firefox などの他のブラウザーでは、引き続きユーザーエージェント文字列が利用されます。しかし、それらもそれに含まれる情報の量を減らします。

## [!DNL Target] クライアントヒントが必要な使用例

Target の次の使用例には、クライアントヒントが必要です。

### オーディエンス属性

次を使用する場合、 [!DNL Target] オーディエンスを作成し、次のオーディエンス属性のいずれかを使用する。 [!DNL Target] 正しいセグメント化を実行するには、クライアントヒントが必要です。

* ブラウザー
* オペレーティングシステム
* モバイル

### プロファイルスクリプト

プロファイルスクリプトを使用し、 `user.browser` 属性（ユーザーエージェントを参照する）の場合、1 つ以上のクライアントヒントも確認するために、プロファイルスクリプトを更新する必要が生じる場合があります。 関数を使用して、任意のクライアントヒントにアクセスできます `user.clientHint('sec-ch-ua-xxxxx')`. クライアントヒントのヘッダー名はすべて小文字にする必要があります。

次の例は、プロファイルスクリプトで Windows OS を適切に検出する方法を示しています。

```
"return (((user.browser != null) && (user.browser.indexOf(\"Windows\") > -1)) || " + 
      "((user.clientHint('sec-ch-ua-platform') != null) && 
(user.clientHint('sec-ch-ua-platform') === 'Windows')));" 
```

以下の節では、クライアントヒントヘッダーと、対応するプロファイルスクリプト使用セマンティクスを示します。

#### Sec-CH-UA

エントロピー：低レベルのドキュメント： [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA){target=_blank} オーディエンス属性：ブラウザープロファイルスクリプトの使用： `user.clientHint('sec-ch-ua')`

#### Sec-CH-UA-Arch

エントロピー：高度なドキュメント： [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Arch](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Arch){target=_blank} オーディエンス属性：プロファイルスクリプトを使用してユーザーに公開される。
プロファイルスクリプトの使用： `user.clientHint('sec-ch-ua-arch')`

#### Sec-CH-UA-Bitness

エントロピー：高度なドキュメント： [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Bitness](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Bitness){target=_blank} オーディエンス属性：プロファイルスクリプトを使用してユーザーに公開される。
プロファイルスクリプトの使用： `user.clientHint('sec-ch-ua-bitness')`

#### Sec-CH-UA-Full-Version-List

エントロピー：高度なドキュメント： [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Full-Version-List](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Full-Version-List){target=_blank} オーディエンス属性：ブラウザープロファイルスクリプトの使用： `user.clientHint('sec-ch-ua-full-version-list')`

#### Sec-CH-UA-Mobile

エントロピー：低レベルのドキュメント： [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Mobile](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Mobile){target=_blank} オーディエンス属性：モバイルプロファイルスクリプトの使用： `user.clientHint('sec-ch-ua-mobile')`

#### Sec-CH-UA-Model

エントロピー：高度なドキュメント： [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Model](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Model){target=_blank} オーディエンス属性：モバイルプロファイルスクリプトの使用： `user.clientHint('sec-ch-ua-model')`

#### Sec-CH-UA-Platform

エントロピー：低レベルのドキュメント： [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Platform](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Platform){target=_blank} オーディエンス属性：オペレーティングシステムプロファイルスクリプトの使用： `user.clientHint('sec-ch-ua-platform')`

#### Sec-CH-UA-Platform-Version

エントロピー：高度なドキュメント： [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Platform-Version](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Platform-Version){target=_blank} オーディエンス属性：プロファイルスクリプトを使用してユーザーに公開される。
プロファイルスクリプトの使用： `user.clientHint('sec-ch-ua-platform-version')`

## クライアントヒントをに渡す方法 [!DNL Adobe Target]

次のセクションでは、クライアントヒントを渡す方法の詳細を説明します。 [!DNL Target] 実装。

### at.js バージョン 2.9.0（以降）

at.js 2.9.0 以降、ユーザーエージェントクライアントヒントは、ブラウザーから自動的に収集され、に送信されます。 [!DNL Target] when `getOffer/getOffers()` が呼び出されます。 デフォルトでは、at.js は「低エントロピー」クライアントヒントのみを収集します。 前の節で「高エントロピー」と分類されたデータに基づいてオーディエンスのセグメント化を実行する場合、またはプロファイルスクリプトを使用する場合、を介して「高エントロピー」クライアントヒントをブラウザーから収集するように at.js を設定する必要があります `targetGlobalSettings`.

`window.targetGlobalSettings = { allowHighEntropyClientHints: true };`

### サーバー側 SDK

サーバー側 SDK を使用してクライアントヒントを渡す方法について詳しくは、 [クライアントヒント](https://adobetarget-sdks.gitbook.io/docs/core-principles/audience-targeting#client-hints){target=_blank} *Adobe Target SDK* ドキュメント。
