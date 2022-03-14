---
keywords: システム図；ちらつき；at.js；実装；javascript ライブラリ；js;atjs
description: 詳しくは、 [!DNL Target] ページの読み込み時のワークフローを理解するのに役立つ、システム図を含む at.js JavaScript ライブラリ関数。
title: at.js Javascript ライブラリの仕組み
feature: at.js
role: Developer
exl-id: 2193c02a-2a85-4ae1-bfbd-40fa7b87f0a0
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1106'
ht-degree: 85%

---

# at.js の仕組み

実装するには [!DNL Adobe Target] クライアント側では、at.js JavaScript ライブラリを使用する必要があります。

クライアント側での [!DNL Adobe Target] の実装では、[!DNL Target] アクティビティに関連付けられたエクスペリエンスをクライアントブラウザーに直接配信します。ブラウザーは、表示するエクスペリエンスを決定して表示します。クライアント側の実装では、WYSIWYG エディターの [Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) （VEC）または非ビジュアルインターフェイスである[フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md) を使用して、テストエクスペリエンスとパーソナライゼーションエクスペリエンスを作成できます。

## at.js について

at.js ライブラリは、Target の新しい実装ライブラリです。at.js ライブラリは、Web 実装のページ読み込み時間を改善し、シングルページアプリケーション向けのより優れた実装オプションを提供します。at.js は推奨される実装ライブラリであり、頻繁にアップデートされて新しい機能が追加されます。すべてのお客様に対して、[at.js の最新バージョン](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A)を実装するか、最新バージョンに移行することをお勧めします。

詳細については、「[Target JavaScript ライブラリ](/help/main/c-intro/how-target-works.md#libraries)」を参照してください。

内 [!DNL Target] 下の図に示す実装。 [!DNL Adobe Experience Cloud] ソリューションが実装されます。Analytics、Target およびAudience Manager。 さらに、次のExperience Cloudコアサービスが実装されています。 [!DNL Adobe Experience Platform], [!DNL Audiences]、および [!DNL Visitor ID Service].

## at.js 1.*x* と at.js 2.x のワークフロー図の違いは何ですか？

2.0 と 1. のバージョン間の違いについて詳しくは、「[at.js 1.x から at.js 2.x へのアップグレード](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/upgrading-from-atjs-1x-to-atjs-20.md)」を参照してください。*x*.

抽象度の高い表示では、2 つのバージョン間にいくつかの違いがあります。

* at.js 2.x は、グローバル mbox リクエストの概念がなく、ページ読み込みリクエストを使用します。ページ読み込みリクエストは、Web サイトの最初のページ読み込み時に適用されるコンテンツを取得するリクエストとして表示できます。
* at.js 2.x は、シングルページアプリケーション (SPA) で使用される、ビューと呼ばれる概念を管理します。 at.js 1.*x* はこの概念に対応していません。

## at.js 2.x 図

次の図は、ビューを使用した at.js 2 ワークフローと、これが SPA 統合をどのように強化するかについて説明しています。at.js 2.x で使用されている概念に関するより詳しい概要については、「[シングルページアプリケーションの実装](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md)」を参照してください。

![at.js 2.x での Target のフロー](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/assets/system-diagram-atjs-20.png)

| 手順 | 詳細 |
| --- | --- |
| 1 | 呼び出しユーザーが認証されると、呼び出しが [!DNL Experience Cloud ID]を返し、別の呼び出しが顧客 ID を同期します。 |
| 2 | at.js ライブラリがドキュメント本文を同期的に読み込み、非表示にします。<br>at.js は、ページに実装されているオプションの非表示スニペットを使用して非同期で読み込むこともできます。 |
| 3 | すべての設定済みパラメーター（MCID、SDID および顧客 ID）を含む、ページ読み込みリクエストがおこなわれます。 |
| 4 | プロファイルスクリプトが実行されてから、プロファイルストアにフィードされます。ストアは、オーディエンスライブラリから正規のオーディエンスをリクエストします（例えば、Adobe Analytics、Audience Management などから共有されたオーディエンス）。<br>顧客属性がバッチ処理でプロファイルストアに送信されます。 |
| 5 | URL リクエストパラメーターとプロファイルデータに基づいて、[!DNL Target] が現在のページおよび将来のビューでどのアクティビティおよびエクスペリエンスを訪問者に返すかを決定します。 |
| 6 | ターゲットコンテンツが（オプションで、追加のパーソナライゼーションに関するプロファイル値を含めて）ページに送り返されます。<br>デフォルトコンテンツがちらつくことなく、可能な限り迅速に現在のページ上のターゲットコンテンツが表示されます。<br>SPAでのユーザーアクションの結果として表示されるビューのターゲットコンテンツはブラウザーにキャッシュされるので、ビューがを通じてトリガーされる際に、追加のサーバー呼び出しなしで即座に適用できます `triggerView()`. |
| 7 | Analytics データがデータ収集サーバーに送信されます。 |
| 8 | ターゲットデータは、SDID を使用して Analytics データに適合され、Analytics レポートストレージへと処理されます。<br>A4T レポートを使用して、Analytics データが Analytics と Target の両方に表示できるようになります。 |

これで、`triggerView()` が SPA のどこに 実装されているかに関わらず、ビューとアクションはキャッシュから取得され、サーバー呼び出しなしでユーザーに表示されるようになります。`triggerView()` は、インプレッション数を増分して記録するために、[!DNL Target] バックエンド に通知リクエストもおこないます。ビューを使用した SPA での at.js について詳しくは、「[シングルページアプリケーションの実装](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md)」を参照してください。

![Target フローの at.js 2.x triggerView](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/assets/atjs-20-triggerview.png)

| 手順 | 詳細 |
| --- | --- |
| 1 | `triggerView()` は SPA で呼び出され、ビューをレンダリングし、ビジュアル要素を変更ためのアクションを適用します。 |
| 2 | ビューのターゲットコンテンツがキャッシュから読み取られます。 |
| 3 | デフォルトコンテンツがちらつくことなく、可能な限り迅速にターゲットコンテンツが表示されます。 |
| 4 | 通知リクエストが [!DNL Target] プロファイルストア に送信され、アクティビティで訪問者がカウントされ、指標が増分されます。 |
| 5 | Analytics データがデータ収集サーバーに送信されます。 |
| 6 | Target データは、SDID を使用して Analytics データに適合され、Analytics レポートストレージへと処理されます。A4T レポートを使用して、Analytics データが Analytics と Target の両方に表示できるようになります。 |

### ビデオ — at.js 2.x のアーキテクチャ図

at.js 2.x は、Adobe Target の SAP のサポートを強化し、Adobe Target と他の Experience Cloud を統合します。このビデオでは、すべてがどのように結び付いているかを説明します。

>[!VIDEO](https://video.tv.adobe.com/v/26250)

詳しくは、 [at.js 2.x の仕組みについて](https://helpx.adobe.com/target/kt/using/atjs20-diagram-technical-video-understand.html) を参照してください。

## at.js 1.x の図

![Target フロー - at.js 1.x](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/assets/target-flow.png)

| 手順 | 説明 | 呼び出し | 説明 |
|--- |--- |--- |--- |
| 1 | ユーザーが認証されると、呼び出しが [!DNL Experience Cloud ID]（MCID）を返し、別の呼び出しが顧客 ID を同期します。 | 2 | at.js ライブラリがドキュメント本文を同期的に読み込み、非表示にします。 |
| 3 | すべての設定済みパラメーター、MCID、SDID および顧客 ID（オプション）を含む、グローバル mbox リクエストがおこなわれます。 | 4 | プロファイルスクリプトが実行されてから、プロファイルストアにフィードされます。ストアは、[!UICONTROL オーディエンスライブラリ]から正規のオーディエンスをリクエストします（例えば､[!DNL Adobe Analytics]、[!DNL Audience Manager] などから共有されたオーディエンス）。<br>顧客属性がバッチ処理で [!DNL Profile Store] に送信されます。 |
| 5 | URL、mbox パラメーターおよびプロファイルデータに基づいて、[!DNL Target] がどのアクティビティおよびエクスペリエンスを訪問者に返すかを決定します。 | 6 | ターゲットとなるコンテンツが（オプションで、追加のパーソナライゼーションに関するプロファイル値を含めて）ページに送り返されます。<br>デフォルトコンテンツがちらつくことなく、可能な限り迅速にエクスペリエンスが表示されます。 |
| 7 | [!DNL Analytics] データがデータ収集サーバーに送信されます。 | 8 | [!DNL Target] データは、SDID を使用して [!DNL Analytics] データに適合され、[!DNL Analytics] レポートストレージへと処理されます。<br>[!DNL Analytics]（A4T）レポートを使用して、[!DNL Analytics] データが [!DNL Target] と [!DNL Analytics for Target] の両方に表示できるようになります。 |

### ビデオ — 営業時間：at.js のヒントと概要（2019 年 6 月 27 日）

このビデオは、「Office Hours」（アドビカスタマーケアチーム主導による取り組みの 1 つ）の録画です。

* at.js を使用する利点
* at.js の設定
* ちらつき処理
* at.js のデバッグ
* 既知の問題
* FAQ

>[!VIDEO](https://video.tv.adobe.com/v/27959)

## at.js による HTML コンテンツを使用したオファーのレンダリング方法 {#render}

HTML コンテンツを使用してオファー をレンダリングする場合、at.js は次のアルゴリズムを適用します。

1. 画像がプリロードされます（HTML コンテンツに `<img>` タグがある場合）。

1. HTML コンテンツが DOM ノードに添付されます。

1. インラインスクリプトが実行されます（`<script>` タグで囲まれたコード）。

1. リモートスクリプトが非同期的に読み込まれ、実行されます（`src` 属性の `<script>` タグ）。

重要事項：

* at.js は、非同期的に読み込まれるので、リモートスクリプトの実行順序を保証しません。
* インラインスクリプトは、後で読み込まれて実行されるので、リモートスクリプトへの依存関係を持たせないようにします。
