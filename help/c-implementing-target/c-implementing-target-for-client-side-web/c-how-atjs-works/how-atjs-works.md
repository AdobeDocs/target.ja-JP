---
description: at.js を使用する自動作成されたグローバル mbox 用に送信または収集した呼び出しおよび情報の流れを表す Target システム図です。
keywords: システム図;ちらつき;Target Standard;at.js;実装
seo-description: at.js を使用している自動作成されたグローバル mbox 用に送信または収集した呼び出しおよび情報の流れを表す、Adobe Target のシステム図です。
seo-title: Adobe Target の at.js の仕組み
solution: 'Target '
title: at.js の仕組み
topic: Standard
uuid: 8ed04881-3dd9-496f-9c9c-feb9c740ed80
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# at.js の仕組み{#how-at-js-works}

クライアント側を実装 [!DNL Adobe Target] するには、at. jsライブラリを使用する必要があります。

クライアント側の実装では、 [!DNL Adobe Target]アクティビティに関連付けられたエクスペリエンスを直接クライアントブラウザーに [!DNL Target] 配信します。ブラウザーは、表示するエクスペリエンスを決定して表示します。クライアント側の実装では、WYSIWYGエディター、 [Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) （VEC）、またはフォームベースのExperience Composer（ [フォームベースのExperience Composer](/help/c-experiences/form-experience-composer.md)）を使用して、テストエクスペリエンスとパーソナライゼーションエクスペリエンスを作成できます。

## at. jsとは

[at. jsライブラリ](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#concept_8AC8D169E02944B1A547A0CAD97EAC17) は、Targetの新しい実装ライブラリです。at.js ライブラリは、Web 実装のページ読み込み時間を改善し、シングルページアプリケーション向けのより優れた実装オプションを提供します。at.js は推奨される実装ライブラリであり、頻繁にアップデートされて新しい機能が追加されます。すべてのお客様に対して、[at.js の最新バージョン](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A)を実装するか、最新バージョンに移行することをお勧めします。

詳しくは [、Target JavaScriptライブラリ](/help/c-intro/how-target-works.md#libraries)を参照してください。

下の図に示す [!DNL Target] 実装では、Analytics、Target、およびAudience Management の [!DNL Adobe Experience Cloud] ソリューションが実装されています。さらに、Adobe Launch、オーディエンスおよび訪問者 ID サービスの Experience Cloud コアサービスが実装されています。

## at.js 1.*x* およびat. js2. xワークフローダイアグラム

2. O [から2. Oに導入された違いについて詳しくは、at. js1. xからat. js2. x](/help/c-implementing-target/c-implementing-target-for-client-side-web/upgrading-from-atjs-1x-to-atjs-20.md) へのアップグレードを参照してください。*x*.

抽象度の高い表示では、2 つのバージョン間にいくつかの違いがあります。

* at. js2. xは、グローバルmboxリクエストの概念を持ちませんが、ページロードリクエストではありません。ページ読み込みリクエストは、Web サイトの最初のページ読み込み時に適用されるコンテンツを取得するリクエストとして表示できます。
* at. js2. xは、単一ページアプリケーション（SPA）に使用されるビューの概念を管理します。at.js 1.*x* はこの概念に対応していません。

## at.js 2.x 図

以下の図では、at. js2. xのワークフローを把握し、これによりSPA統合を強化する方法について説明します。at. js2. xで使用される概念のより優れた紹介を行うには、 [「シングルページアプリケーションの実装](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md)」を参照してください。

![at. js2. xを使用したTargetフロー](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/system-diagram-atjs-20.png)

| 手順 | 詳細 |
| --- | --- |
| 1 | 呼び出しユーザーが認証されると、呼び出しが [!DNL Experience Cloud ID]を返し、別の呼び出しが顧客 ID を同期します。 |
| 2 | at.js ライブラリがドキュメント本文を同期的に読み込み、非表示にします。<br>at.js は、ページに実装されているスニペットを非表示にするオプションを使用して非同期で読み込むこともできます。 |
| 3 | すべての設定済みパラメーター（MCID、SDID および顧客 ID）を含む、ページ読み込みリクエストがおこなわれます。 |
| 4 | プロファイルスクリプトが実行されてから、プロファイルストアにフィードされます。ストアは、オーディエンスライブラリから正規のオーディエンスをリクエストします（例えば、Adobe Analytics、Audience Management などから共有されたオーディエンス）。<br>顧客属性がバッチ処理でプロファイルストアに送信されます。 |
| 5 | URL リクエストパラメーターとプロファイルデータに基づいて、[!DNL Target] が現在のページおよび将来のビューでどのアクティビティおよびエクスペリエンスを訪問者に返すかを決定します。 |
| 6 | ターゲットコンテンツが（オプションで、追加のパーソナライゼーションに関するプロファイル値を含めて）ページに送り返されます。<br>デフォルトコンテンツがちらつくことなく、可能な限り迅速に現在のページ上のターゲットコンテンツが表示されます。<br>SPA でのユーザーアクションの結果として表示されるビューのターゲットコンテンツは、ブラウザーにキャッシュされます。そのため、`triggerView()` を介してビューがトリガーされたときに追加のサーバー呼び出しをおこなわずに即座にターゲットコンテンツを適用できます。 |
| 7 | Analytics データがデータ収集サーバーに送信されます。 |
| 8 | ターゲットデータは、SDID を使用して Analytics データに適合され、Analytics レポートストレージへと処理されます。Analytics for Target（A4T）レポートを使用して、<br>Analytics データが Analytics および Target に表示できるようになります。 |

これで、`triggerView()` が SPA に実装されます。ビューとアクションはキャッシュから取得され、サーバー呼び出しを行うことなくユーザーに表示されるようになります。また、`triggerView()` は、インプレッション数の増加および記録のために [!DNL Target] バックエンドへの通知リクエストも行います。ビューを使用した SPA での at.js について詳しくは、「[シングルページアプリケーションの実装](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md)」を参照してください。

![Targetのフローat. js2. xのトリガービュー](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/atjs-20-triggerview.png)

| 手順 | 詳細 |
| --- | --- |
| 1 | `triggerView()` は SPA で呼び出され、ビューをレンダリングし、ビジュアル要素を変更ためのアクションを適用します。 |
| 2 | ビューのターゲットコンテンツがキャッシュから読み取られます。 |
| 3 | デフォルトコンテンツがちらつくことなく、可能な限り迅速にターゲットコンテンツが表示されます。 |
| 4 | 通知リクエストが [!DNL Target] プロファイルストア に送信され、アクティビティで訪問者がカウントされ、指標が増分されます。 |
| 5 | Analytics データがデータ収集サーバーに送信されます。 |
| 6 | Target データは、SDID を使用して Analytics データに適合され、Analytics レポートストレージへと処理されます。A4T レポートを使用して、Analytics データが Analytics と Target の両方に表示できるようになります。 |

## at.js 1.x の図

![](assets/target-flow.png)

| 手順 | 説明 | 呼び出し | 説明 |
|--- |--- |--- |--- |
| 1 | ユーザーが認証されると、呼び出しが [!DNL Experience Cloud ID]（MCID）を返し、別の呼び出しが顧客 ID を同期します。 | 2 | at.js ライブラリがドキュメント本文を同期的に読み込み、非表示にします。 |
| 3 | すべての設定済みパラメーター、MCID、SDID および顧客 ID（オプション）を含む、グローバル mbox リクエストがおこなわれます。 | 4 | プロファイルスクリプトが実行されてから、プロファイルストアにフィードされます。ストアは、[!UICONTROL オーディエンスライブラリ]から正規のオーディエンスをリクエストします（例えば､[!DNL Adobe Analytics]、[!DNL Audience Manager] などから共有されたオーディエンス）。<br>顧客属性がバッチ処理で [!DNL Profile Store] に送信されます。 |
| 5 | URL、mbox パラメーターおよびプロファイルデータに基づいて、[!DNL Target] がどのアクティビティおよびエクスペリエンスを訪問者に返すかを決定します。 | 6 | ターゲットとなるコンテンツが（オプションで、追加のパーソナライゼーションに関するプロファイル値を含めて）ページに送り返されます。<br>デフォルトコンテンツがちらつくことなく、可能な限り迅速にエクスペリエンスが表示されます。 |
| 7 | [!DNL Analytics] データがデータ収集サーバーに送信されます。 | 8 | [!DNL Target] データは、SDID を使用して [!DNL Analytics] データに適合され、[!DNL Analytics] レポートストレージへと処理されます。[!DNL Analytics for Target]（A4T）レポートを使用して、<br>[!DNL Analytics] データが [!DNL Analytics] と [!DNL Target] の両方に表示できるようになります。 |

## トレーニングビデオ:at. js2. xアーキテクチャ図

at. js2. xは、Adobe TargetのSPAサポートを強化し、他のExperience Cloudソリューションと統合します。このビデオでは、すべてがどのように結び付いているかを説明します。

>[!VIDEO](https://video.tv.adobe.com/v/26250)

詳しくは、at. js2. xの仕組み [](https://helpx.adobe.com/target/kt/using/atjs20-diagram-technical-video-understand.html) についてを参照してください。