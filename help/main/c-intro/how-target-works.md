---
keywords: Adobe Experience Platform Web SDK;aep web sdk;aep sdk;検索エンジンの最適化;検索エンジンの最適化;seo;エッジクラスター;セントラルクラスター;at.js;mbox.js;
description: JavaScript ライブラリ（AEP Web SDK at.js）、サーバーコールの使用戦略、使用状況、Adobe データセンター、SEO テスト、ボットなど、 [!DNL Adobe Target] の仕組みについて説明します。
title: ' [!DNL Target]  の仕組み'
feature: Overview
exl-id: 8a93e061-0be7-4ecc-b511-2210094547f2
TQID: https://experienceleague.adobe.com/KZR3HivCPj0FVhB7fmt-WEjsniUsupTK1-52UqwtbKE
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
subfeature_v2:
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
topic_v2:
  - id: a09a5a04-e30b-4d55-b031-38e6f5ec86db
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: cc72dcf1-72e1-48cc-b434-e7c27d62d67c
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
  - id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 2421
ht-degree: 25%

---

# [!DNL Adobe Target] の仕組み

JavaScript ライブラリ （[!DNL Adobe Experience Platform Web SDK]およびat.js）の詳細など、[!DNL Adobe Target]の仕組みについて説明します。 この記事では、作成できる様々なアクティビティタイプ、[!DNL Target]個の使用状況カウント戦略、[!DNL Target]個のEdge Network、SEO、およびボット検出についても説明します。

重要なポイントは次のとおりです。

* **JavaScript ライブラリ**: [!DNL Target] JavaScript ライブラリの詳細：[!DNL Adobe Experience Platform Web SDK]およびat.js
* **サーバー呼び出しの使用戦略**: エンドポイント、単一のmbox、バッチ mbox、実行、プリフェッチ、通知の呼び出しなど、[!DNL Target]が様々なサーバー呼び出しをカウントする方法を理解します。
* **Edge Network**: [!DNL Target]が[!DNL Adobe Experience Platform Edge Network]とどのように関わっているかを確認します。
* **保護されたユーザーエクスペリエンス**: [!DNL Adobe]がターゲティングインフラストラクチャの可用性とパフォーマンスをどのように確保するかを説明します。
* **SEO ガイドライン**: [!DNL Target]のアクティビティをSEO ガイドラインに合わせるためのベストプラクティスに従います。
* **ボットトラフィック**: Targetがボットトラフィックをどのように処理して、歪んだテストとパーソナライゼーションアルゴリズムを回避するかを説明します。

## [!DNL Adobe Target] JavaScript ライブラリ {#libraries}

Targetは、[!DNL Experience Platform Web SDK]またはat.jsを使用してWeb サイトと統合します。

* **[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/ja/docs/target-dev/developer/client-side/aep/aep-web-sdk-overview){target=_blank}**：このクライアントサイドのJavaScript ライブラリを使用すると、[!DNL Adobe Experience Cloud]のお客様は[!DNL Experience Platform Edge Network]を通じて様々なサービスと対話できます。 [!DNL Adobe]様は、新しい[!DNL Target]のお客様が[!DNL Experience Platform Web SDK]を実装することを推奨しています。
* **[at.js](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/at-js-implementation/deploy-at-js/how-to-deployatjs){target=_blank}**: [!DNL Target]用のこの実装ライブラリは、web実装のページ読み込み時間を改善し、シングルページアプリケーションのより優れたオプションを提供します。 頻繁に更新される新機能により、[!DNL Adobe]では、すべての[at.js ユーザーに最新バージョン &#x200B;](https://experienceleague-review.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank}への更新を推奨しています。

>[!NOTE]
>
>mbox.js ライブラリは、[!DNL Target]のレガシー実装であり、2021年3月31日をもってサポートされなくなりました。 [!UICONTROL Experience Platform Web SDK] （推奨）または最新バージョンのat.jsにアップグレードします。

サイトのすべてのページで[!UICONTROL Experience Platform Web SDK]またはat.jsを参照してください。 例えば、次のいずれかのライブラリをグローバルヘッダーに追加します。 または、Adobe Experience Platform[&#128279;](https://experienceleague.adobe.com/ja/docs/experience-platform/tags/home){target=_blank}の タグを使用して[!DNL Target]を実装します。

次のリソースには、[!DNL Experience Platform Web SDK] または at.js の実装に役立つ詳細情報が含まれています。

* [[!DNL Adobe Experience Platform Web SDK] 拡張機能](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/sdk/overview.html?lang=ja){target=_blank}
* [&#x200B; [!DNL Adobe Experience Platform]を使用して [!DNL Target] を実装](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/at-js-implementation/deploy-at-js/implement-target-using-adobe-launch){target=_blank}

訪問者が[!DNL Target]用に最適化されたページをリクエストするたびに、リアルタイムのリクエストがターゲティングシステムに送信され、提供するコンテンツが決定されます。 このリクエストは、マーケターが管理するアクティビティとエクスペリエンスによって管理され、ページが読み込まれるたびに実行されます。 コンテンツはサイト訪問者一人ひとりをターゲットにして、レスポンス率、獲得率、売上を最大化します。 コンテンツをパーソナライズすることで、訪問者の反応やインタラクション、購買を促進できます。

[!DNL Target]では、ページ上の各要素は、複数の要素を含めることができる単一のエクスペリエンスの一部です。

表示されるコンテンツは、作成するアクティビティのタイプによって異なります。

### [!UICONTROL A/B テスト]

基本的なA/B テストでは、割り当てられたエクスペリエンスからコンテンツがランダムに選択されます。 各エクスペリエンスのトラフィック割り当て率を設定できます。 当初、トラフィックはランダム分割により不均等に分散される可能性がありますが、トラフィックが増えるにつれて等しくなります。 例えば、2つのエクスペリエンスでは、開始エクスペリエンスがランダムに選択されます。 トラフィックが少ない場合、訪問者の割合をひとつのエクスペリエンスに偏らせる可能性がありますが、この状況は、より多くのトラフィックとバランスが取れます。

各エクスペリエンスの目標の割合を指定します。 表示するエクスペリエンスを選択するために、ランダムな数値が生成されます。 計算結果のパーセンテージはターゲットと正確に一致しない可能性がありますが、トラフィックが多いほど、ターゲット目標に近い値になります。

1. 顧客がサーバーにページをリクエストすると、ブラウザーに表示されます。
1. 1st パーティ Cookieは、顧客のブラウザーに設定され、顧客の行動を保存します。
1. ページから、ターゲティングシステムが呼び出されます。
1. アクティビティルールに基づいてコンテンツが表示されます。

詳細については、「[A/B テストの作成](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)」を参照してください。

### [!UICONTROL 自動配分]

[!UICONTROL 自動割り当て]は、2つ以上のオプションの中から勝者エクスペリエンスを特定します。 そして、より多くのトラフィックが勝者に自動的に再配分され、テストの実行と学習を続けることでコンバージョンが増加します。

詳しくは、[[!UICONTROL 自動割り当て]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)を参照してください。

### [!UICONTROL 自動ターゲット &#x200B;] （AT）

[!UICONTROL 自動ターゲット &#x200B;]は、高度な機械学習を活用して、複数の高性能なマーケター定義エクスペリエンスから選択します。 [!UICONTROL 自動ターゲット &#x200B;]は、個々の顧客プロファイルと、類似プロファイルを持つ以前の訪問者の行動に基づいて、各訪問者に最もカスタマイズされたエクスペリエンスを提供します。 [!UICONTROL 自動ターゲット &#x200B;]を使用して、コンテンツをパーソナライズし、コンバージョンを促進します。

詳細については、[自動ターゲット](/help/main/c-activities/auto-target/auto-target-to-optimize.md)を参照してください。

### [!UICONTROL Automated Personalization]（AP）

[!UICONTROL Automated Personalization] （AP）は、オファーまたはメッセージを組み合わせ、高度な機械学習を使用して、各訪問者に対して異なるバリエーションを一致させます。 APは、個々の顧客プロファイルにもとづいてコンテンツをパーソナライズし、売上を向上させます。

詳しくは、[Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9)を参照してください。

### [!UICONTROL エクスペリエンスのターゲット設定]（XT）

[!UICONTROL &#x200B; エクスペリエンスのターゲット設定] （XT）は、マーケターが定義したルールと条件に基づいて、特定のオーディエンスにコンテンツを配信します。 地域ターゲティングを含め、特定のエクスペリエンスやコンテンツを特定のオーディエンスにターゲティングするルールを定義するのに役立ちます。 アクティビティでは、複数のルールを設定して、様々なコンテンツのバリエーションを様々なオーディエンスに配信できます。 訪問者がサイトを閲覧すると、XTはその訪問者を評価し、その訪問者が基準を満たしているかどうかを判断します。 その人が適格であれば、そのアクティビティに参加し、その人に合わせて設計されたエクスペリエンスを確認します。 単一のアクティビティ内で、複数のオーディエンスに対してエクスペリエンスを作成できます。

詳しくは、[エクスペリエンスのターゲット設定](/help/main/c-activities/t-experience-target/experience-target.md#task_A53DF336CB9F4D7BB87EF2106099EFC4)を参照してください。

### [!UICONTROL 多変量分析テスト] （MVT）

[!UICONTROL Multivariate Testing] （MVT）は、ページ要素のオファーの組み合わせを比較して、特定のオーディエンスに対してどの組み合わせが最も効果的かを判断します。 MVT は、アクティビティの成功に最も影響を与える要素を特定するのに役立ちます。

詳しくは、[多変量分析テスト](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md#concept_628695CDC71B449B8DCC2F5654C11499)を参照してください。

### [!UICONTROL レコメンデーション]

[!UICONTROL Recommendations]のアクティビティでは、以前のアクティビティやその他のアルゴリズムに基づいて、顧客が関心を持つ可能性のある製品やコンテンツが自動的に表示されます。 商品レコメンデーションは、顧客が見つけられなかった関連商品を顧客に提供するのに役立ちます。

詳細については、[レコメンデーション](/help/main/c-recommendations/recommendations.md#concept_7556C8A4543942F2A77B13A29339C0C0)を参照してください。

<!--
## How [!DNL Target] counts server-call usage {#usage}

[!DNL Target] counts only server calls that provide value to customers. The following table shows how [!DNL Target] counts endpoints, single mbox, batch mbox calls, execute, prefetch, and notification calls.

The following information helps you understand the counting strategy used for [!DNL Target] server calls, as shown in the table below:

* **Count Once**: Counts once per API call.
* **Count the Number of mboxes**: Counts the number of mboxes under the array in the payload of a single API call.
* **Ignore**: Is not counted at all.
* **Count the Number of Views (Once)**: Counts the number of views under the array in the payload. In a typical implementation, a view notification has only one view under the notifications array, making this equivalent to counting once in most implementations.

|Endpoint|Fetch type|Options|Counting strategy|
|--- |--- |--- |-- |
|`rest//v1/mbox`|Single|[!UICONTROL execute]|Count once|
|`rest/v2/batchmbox`|Batch|[!UICONTROL execute]|Count the number of mboxes|
||Batch|[!UICONTROL prefetch]|Ignore|
||Batch|[!UICONTROL notifications]|Count the number of mboxes|
|`/ubox/[raw\|image\|page]`|Single|[!UICONTROL execute]|Count once|
|`rest/v1/delivery`<p>`/rest/v1/target-upstream`|Single|[!UICONTROL execute] > [!UICONTROL pageLoad]|Count once|
||Single|[!UICONTROL prefetch] > [!UICONTROL pageLoad]|Ignore|
||Single|[!UICONTROL prefetch] > [!UICONTROL views]|Ignore|
||Batch|[!UICONTROL execute] > [!UICONTROL mboxes]|Count the number of mboxes|
||Batch|[!UICONTROL prefetch] > [!UICONTROL mboxes]|Ignore|
||Batch|[!UICONTROL notifications] > [!UICONTROL views]|Count the number of views (once)|
||Batch|[!UICONTROL notifications] > [!UICONTROL pageLoad]|Count once|
||Batch|[!UICONTROL notifications] > type ([!UICONTROL conversions])|Count once|
||Batch|[!UICONTROL notifications] > [!UICONTROL mboxes]|Count the number of mboxes|

-->

## エッジネットワーク {#concept_0AE2ED8E9DE64288A8B30FCBF1040934}

「Edge」は、場所に関係なく、コンテンツをリクエストする訪問者に最適な応答時間を保証する、地理的に分散したサービスアーキテクチャです。

応答時間を改善するために、[!DNL Target] Edge はアクティビティロジック、キャッシュされたプロファイル、およびオファー情報のみをホストします。

アクティビティとコンテンツのデータベース、[!DNL Analytics]個のデータ、API、マーケターのユーザーインターフェイスは、[!DNL Adobe]個の中央クラスターに格納されています。 更新は[!DNL Target] エッジに送信されます。このエッジは、中央クラスターと自動的に同期され、キャッシュされたアクティビティデータが継続的に更新されます。 すべての1:1 モデリングも各エッジに保存され、複雑なリクエストをローカルで処理できます。

各Edge クラスターには、訪問者のコンテンツリクエストに対応し、分析データを追跡するために必要なすべての情報が含まれています。 訪問者のリクエストは、最寄りのエッジクラスターに転送されます。

詳しくは、『[Adobe Target セキュリティの概要](https://www.adobe.com/content/dam/cc/en/security/pdfs/AdobeTargetSecurityOverview.pdf)』ホワイトペーパーを参照してください。

[!DNL Target]は、世界中のAdobeが所有するデータセンターとAdobeがリースするデータセンターでホストされています。

中央クラスターの場所には、データ収集とデータ処理センターの両方が格納されます。 Edge Clusterの場所には、データ収集センターのみが含まれます。 個々のレポートスイートは特定のデータ処理センターに割り当てられています。

お客様のサイトアクティビティデータは、最も近い7つのEdge クラスターによって収集されます。 その後、このデータは、処理のために事前に決定された中央クラスターの宛先（オレゴン、ダブリン、またはシンガポール）に送信されます。 訪問者プロファイルデータは、サイト訪問者に最も近いエッジクラスターに保存されます。 Edgeクラスターの場所には、中央クラスターの場所だけでなく、バージニア、ムンバイ、シドニー、東京が含まれます。

1つの場所からすべてのターゲティングリクエストを処理する代わりに、ビジターに最も近いEdge クラスターでリクエストが処理されます。 このアプローチにより、ネットワークとインターネットの移動時間の影響を軽減できます。

![各種の Target サーバーを示すマップ](/help/main/c-intro/assets/target-servers.png)

[!DNL Target] 中央クラスターは、以下を含む、Amazon ウェブサービス（AWS）でホストされています。

* オレゴン（米国）
* ダブリン（アイルランド）
* シンガポール共和国

AWS でホストされる [!DNL Target] のエッジクラスターには、以下が含まれます。

* ムンバイ（インド）
* 東京（日本）
* バージニア（米国）
* オレゴン（米国）
* シドニー（オーストラリア）
* ダブリン（アイルランド）
* シンガポール共和国

[!DNL Target Recommendations] サービスはオレゴンの [!DNL Adobe] データセンターでホストされています。

>[!IMPORTANT]
>
>現在、[!DNL Target]には中国のEdge クラスターがありません。この地域の[!DNL Target]人のお客様の訪問者のパフォーマンスが制限されています。 ファイアウォールとEdge Clustersの欠如は、サイトエクスペリエンスに影響を与え、レンダリングとページ読み込み時間が遅くなる可能性があります。 さらに、マーケターは[!DNL Target] オーサリング UIを使用する際に遅延が発生する可能性があります。

必要に応じて、[!DNL Target] のエッジクラスターを許可リストに追加できます。 詳しくは、[Target のエッジノードを許可リストに登録する](https://experienceleague.adobe.com/ja/docs/target-dev/developer/implementation/privacy/allowlist-edges){target=_blank}を参照してください。

## ユーザーエクスペリエンスの保護 {#concept_40A5E781D90A41E4955F80EA9E5F8F96}

[!DNL Adobe]は、ターゲティングインフラストラクチャの可用性とパフォーマンスが可能な限り信頼できるものであることを保証します。 ただし、訪問者のブラウザーと[!DNL Adobe]台のサーバーの間の通信が切断されると、コンテンツ配信が中断される可能性があります。

サービスの中断や接続の問題を防ぐために、すべての場所は、デフォルトコンテンツ（クライアントが定義）を含めるように設定されています。 このデフォルトのコンテンツは、訪問者のブラウザーが[!DNL Target]に接続できない場合に表示されます。

訪問者のブラウザーが定義されたタイムアウト期間内に接続できない場合（デフォルトは15秒）、ページに変更は加えられません。 このタイムアウトのしきい値に達した場合、デフォルトの場所のコンテンツが表示されます。

[!DNL Adobe] は、パフォーマンスを最適化し、安全性を保つことで、ユーザーエクスペリエンスを保護します。

* [!DNL Adobe]は、[!UICONTROL Adobe サービスレベル契約]で保証されている業界標準に基づいて、パフォーマンスのベンチマークを保証します。
* エッジネットワークによって、タイムリーなデータ配信を実現しています。
* [!UICONTROL Adobe]は、アプリケーションを保護するために多層的なアプローチを採用しており、お客様に最高レベルの可用性と信頼性を提供します。
* [!DNL Target] コンサルティングは、導入支援と継続的な製品サポートを行っています。

## 検索エンジン最適化（SEO）対応テスト {#concept_C0C865663CAB4251B66A1F250FD25E6A}

[!DNL Adobe Target] はテストのための検索エンジンガイドラインに従っています。 [!DNL Google]はユーザーテストを推奨し、A/Bおよび[!UICONTROL Multivariate Testing]はオーガニック検索エンジンのランキングに影響を与えないと述べています。

[!DNL Adobe Target] はテストのための検索エンジンガイドラインに従っています。

詳しくは、次の Google のリソースを参照してください。

* [ウェブテストが Google 検索に与える影響](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html)
* [実験とクローキング](https://support.google.com/analytics/answer/12979939?hl)


ガイドラインは[Google ウェブマスター向け公式ブログ](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html)の投稿として公表されています。 この投稿は2012年までさかのぼりますが、この件に関する[!DNL Google]の最新の声明は残っており、ガイドラインは依然として関連しています。

* **クローキングなし**: クローキングでは、ボットを特定して別のコンテンツを入力することにより、1つのコンテンツのセットをユーザーに表示し、別のセットを検索エンジンボットに表示します。

  [!DNL Target]は、検索エンジン ボットを任意のユーザーと同じように処理するように設定されています。 したがって、ボットをランダムに選択してテストのバリエーションを「参照」すると、アクティビティにボットを含めることができます。

* **rel=&quot;canonical&quot;**&#x200B;を使用：A/B テストでバリエーションのURLが異なる場合があります。 このような場合、すべてのバリエーションには、元の（コントロール） URLを参照するrel=&quot;canonical&quot; タグを含める必要があります。 例えば、[!DNL Adobe]が各バリエーションに対して異なるURLを持つホームページをテストしている場合、各バリエーションの`<head>` タグにホームページの次の正規タグを配置する必要があります。

  `<link rel="canonical" href="https://www.adobe.com" />`

* **302 （一時的）リダイレクトを使用**：テストのバリエーション ページに個別のURLを使用する場合、[!DNL Google]は302 リダイレクトを使用して、テストのバリエーションにトラフィックを誘導することをお勧めします。 302 リダイレクトは、テストの実行中にのみ、リダイレクトが一時的でアクティブであることを検索エンジンに通知します。

  302 リダイレクトはサーバーサイドのリダイレクトですが、[!DNL Target]やほとんどの最適化プロバイダーはクライアントサイド機能を使用しています。 したがって、[!DNL Target]は、[!DNL Google]のリダイレクトに関する推奨事項に完全に準拠していません。 しかし、これはテストのほんの一部に影響します。 [!DNL Target]を通じてテストを実行するための標準的なアプローチでは、1つのURL内のコンテンツを変更して、リダイレクトを行う必要がなくなります。 テストのバリエーションに複数のURLが必要な場合、[!DNL Target]はJavaScript `window.location` コマンドを使用します。このコマンドでは、リダイレクトが301または302のいずれであるかを指定しません。

  [!DNL Adobe]は、検索エンジンのガイドラインに完全に準拠するためのソリューションを積極的に探しています。 テスト用に個別のURLを必要とするクライアントの場合、[!DNL Adobe]は、規範的なタグを正しく実装することで、関連するリスクが軽減されると考えています。

* **必要な期間のみ実験を実行する**: [!DNL Adobe]は、統計的有意性に到達するために必要な時間として「必要な期間」を定義します。 [!DNL Target]では、テストがこのポイントに達したタイミングを判断するためのベストプラクティスと[!DNL Adobe Target] [&#x200B; サンプルサイズ計算](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6)が提供されます。 [!DNL Adobe]は、勝つテストのハードコードされた実装をテストワークフローに組み込み、適切なリソースを割り当てることをお勧めします。

  [!DNL Target]を使用して勝者テストを「公開」することは、恒久的なソリューションとしては推奨されません。 勝者テストが常に100%のユーザーに対して公開されている場合、このアプローチは、勝者テストをハードコーディングしながら一時的に使用できます。

  テスト内容の変更を検討してください。 ボタンの色などの軽微な更新は、オーガニック検索の順位には影響しません。 ただし、テキストの変更はハードコードする必要があります。

  また、テストするページのアクセシビリティも考慮してください。 そのページが検索エンジンからアクセスできず、オーガニック検索でのランク付けを意図していなかった場合、これらの考慮事項は適用されません。 例えば、メールキャンペーン専用のランディングページがあります。

Google によると、これらのガイドラインに従えば、「テストがサイトの検索結果に及ぼす影響はほとんどあるいはまったくない。」とのことです。

これらのガイドラインに加えて、Google はまた、Content Experiments ツールのドキュメンテーションでもう 1 つのガイドラインを提供しています。

* 「バリエーションの各ページは、元来のページ内容の主旨を保持する必要があります。 こういったバリエーションは、元来の内容に対しユーザーが持つ全般的イメージを変えてはいけません。」

Google は例として、「ユーザーに表示される組み合わせに関連しないキーワードでサイトの元来のページが読み込まれる場合、そのサイトを Google のインデックスから外すことがあります」と記述しています。

[!UICONTROL Adobe]は、テストのバリエーション内の元のコンテンツの意味を意図せずに変更するのは難しいと感じています。 ただし、[!UICONTROL Adobe]では、ページ上のキーワードテーマを認識し、それらのテーマを維持することをお勧めします。 ページ内容を変更、特に関連のあるキーワードを追加したり削除したりすると、オーガニック検索でのその URL のランキングが変わってしまう場合があります。 [!DNL Adobe] では、テストプロセスの一環として、SEO パートナーに協力を仰ぐことをお勧めします。

## ボット {#bots}

[!DNL Target]は、[DeviceAtlas](https://deviceatlas.com/device-data/user-agent-tester/)指標「isRobot」を使用して、リクエストヘッダーで渡されたユーザーエージェント文字列に基づいて既知のボットを検出します。

>[!NOTE]
>
> [!DNL Server-Side] リクエストの場合、[リクエストの「コンテキスト」ノード](https://developers.adobetarget.com/api/delivery-api/#tag/Delivery-API)に渡された値は、ボット検出用のユーザーエージェント文字列よりも優先されます。

ボット生成として特定されたトラフィックには、引き続きコンテンツが配信されます。 ボットは通常のユーザーと同様に扱われ、[!DNL Target]がSEO ガイドラインに準拠していることを確認します。 しかし、ボットトラフィックを通常のユーザーと同じように扱うと、A/B テストやパーソナライゼーションアルゴリズムが歪む可能性があります。 したがって、[!DNL Target] アクティビティ内の既知のボットトラフィックは、異なる方法で処理されます。 ボットトラフィックを削除することで、ユーザーアクティビティをより正確に測定できます。

既知のボットトラフィックの場合、[!DNL Target]は次を実行しません：

* 訪問者プロファイルの作成または取得
* プロファイル属性のログ記録またはプロファイルスクリプトの実行
* [!DNL Adobe Audience Manager]（AAM）セグメントの検索（該当する場合）
* [!UICONTROL Recommendations]、[!UICONTROL 自動ターゲット &#x200B;]、[!UICONTROL Automated Personalization]、[!UICONTROL 自動割り当て] アクティビティのパーソナライズされたコンテンツのモデリングまたは配信にボットトラフィックを使用する
* レポート用のアクティビティ訪問の記録
* [!DNL Adobe Experience Cloud] プラットフォームに送信されたログデータ

既知のボットトラフィックに対して、[!UICONTROL Analytics for Target] （A4T）を使用する場合、[!DNL Target]は次を実行しません。

* [!DNL Analytics] にイベントを送信

`client_side` ログを使用する際の既知のボットトラフィックの場合、[!DNL Target]は次を返しません。

* `tnta payload`
