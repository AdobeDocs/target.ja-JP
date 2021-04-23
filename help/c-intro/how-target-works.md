---
keywords: Adobe Experience PlatformWeb SDK;aep web sdk;aep sdk；検索エンジンの最適化；検索エンジンの最適化；seo;edge clusters, central clusters;at.js;mbox.js;
description: Adobe [!DNL Target] works, including information about the [!DNL Target] JavaScriptライブラリ（at.jsおよびAEP Web SDK）、Adobeデータセンター、SEOテストの仕組みを説明します。
title: ' [!DNL Target] 機能の仕組み'
feature: 概要
exl-id: 8a93e061-0be7-4ecc-b511-2210094547f2
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '2565'
ht-degree: 31%

---

# Adobe[!DNL Target]の仕組み

[!DNL Adobe Target]の仕組みを学びます。[!DNL Adobe Experience Platform Web SDK]およびJavaScriptライブラリ（at.jsとmbox.js）に関する情報も含まれます。 この記事では、[!DNL Target]を使用して作成できる様々なアクティビティタイプについても紹介します。 また、[!DNL Target]エッジネットワーク、検索エンジン最適化(SEO)、および[!DNL Target]がボットを検出する方法についても学習できます。

## ターゲットプラットフォームWeb SDKおよびJavaScriptライブラリ{#libraries}

[!DNL Target] webサイトとの統合( [!DNL AEP Web SDK] またはJavaScriptライブラリを使用):

* **Adobe Experience PlatformWeb SDK:** AEP Web  [](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md) SDKは、新しいクライアント側のJavaScriptライブラリです。AEP Web SDKを使用すると、[!DNL Adobe Experience Cloud]のお客様は、[!DNL AEP] Edgeネットワークを介して、[!DNL Experience Cloud]の様々なサービス（[!DNL Target]を含む）とやり取りできます。 Adobeでは、新しい[!DNL Target]ユーザー全員に[!DNL AEP Web SDK]を導入することを推奨します。
* **at.js:** at.jsライブラリは、 [の実装ラ](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#concept_8AC8D169E02944B1A547A0CAD97EAC17) イブラリ [!DNL Target]です。at.js ライブラリは、Web 実装のページ読み込み時間を改善し、シングルページアプリケーション向けのより優れた実装オプションを提供します。at.jsは新しい機能で頻繁に更新されます。 at.jsを使用するすべてのお客様に、実装を[最新バージョンのat.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A)に更新することをAdobeでお勧めします。
* **mbox.js:** mbox.jsライブラリは、の [レガシー実装ライブラリ](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md)  [!DNL Target]です。mbox.jsライブラリは2021年3月31日までサポートされます。ただし、機能の更新はありません。

>[!IMPORTANT]
>
>すべてのお客様は、at.jsの[!DNL AEP Web SDK]または最新バージョンに移行する必要があります。 詳しくは、[Adobe Experience PlatformWeb SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md)または[mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA)からat.jsへの移行を参照してください。

サイトの各ページの[!DNL AEP Web SDK]またはat.jsを参照します。 例えば、グローバルヘッダーにこれらのライブラリの1つを追加できます。 または、[AdobePlatform launch](https://experienceleague.adobe.com/docs/launch/using/overview.html)を使用して[!DNL Target]を実装することを検討してください。

次のリソースには、AEP Web SDKまたはat.jsの実装に役立つ詳細情報が含まれています。

* [Adobe Experience PlatformWeb SDK拡張機能](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/aep-extension/overview.html?lang=en#configure-the-aep-web-sdk-extension)
* [Adobe Experience Platform Launchを使用したターゲットの実装](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md)

訪問者が[!DNL Target]用に最適化されたページをリクエストするたびに、リクエストがターゲット設定システムに送信されます。 このリクエストは、その訪問者に提供するコンテンツを決定するのに役立ちます。 このプロセスはリアルタイムで発生します。 ページが読み込まれるたびに、コンテンツに対するリクエストが作成され、システムで処理されます。 コンテンツは、マーケティング担当者が制御するアクティビティおよびエクスペリエンスのルールによって管理され、個々のサイト訪問者がターゲットになります。各サイト訪問者が最も反応し、やり取りをする可能性が高い、または最終的に購入する可能性の高いコンテンツが提供されます。 コンテンツをパーソナライズすることで、回答率、獲得率および売上高を最大化できます。

[!DNL Target]では、ページ上の各要素は、ページ全体の単一のエクスペリエンスの一部です。 各エクスペリエンスには、ページ上の複数のエレメントを含めることができます。

訪問者に表示されるコンテンツは、作成するアクティビティのタイプによって異なります。

### A/B テスト

基本的なA/Bテストで表示されるコンテンツは、アクティビティに割り当てたエクスペリエンスからランダムに選択されます。 各エクスペリエンスにトラフィック配分の割合を割り当てることができます。 このランダムなトラフィック分割の結果、トラフィックの割合が均等になる前に、初期トラフィックの量がかなり多くなる可能性があります。 例えば、2 つのエクスペリエンスを作成した場合、最初のエクスペリエンスはランダムに選択されます。トラフィック量がほとんどない場合は、訪問者の割合が一方のエクスペリエンスに偏っている可能性があります。トラフィックが増えるに従って、割合は等しくなります。

エクスペリエンスごとに割合のターゲットを指定できます。この場合、乱数が生成され、その乱数を使用して、表示するエクスペリエンスが選択されます。結果の割合が指定したターゲットと完全に一致しないこともありますが、トラフィックが多いほど、エクスペリエンスがターゲットに近い割合で分割されます。

1. 訪問者が、サーバー上のページをリクエストしてブラウザーに表示します。
1. 顧客の行動を保存するために、顧客のブラウザーにファーストパーティCookieが設定されます。
1. ページから、ターゲット設定システムが呼び出されます。
1. アクティビティのルールに基づいてコンテンツが表示されます。

詳細については、「[A/B テストの作成](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)」を参照してください。

### 自動配分

自動配分は、2つ以上のエクスペリエンスのうちの勝者を識別します。 自動配分は、より多くのトラフィックを勝者エクスペリエンスに自動的に再割り当てするので、テストの実行と学習が継続する間にコンバージョンを増やすのに役立ちます。

詳細については、「[自動配分](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)」を参照してください。

### 自動ターゲット（AT）

自動ターゲットでは、高度な機械学習を使用して、複数のパフォーマンスの高いマーケティング担当者が定義したエクスペリエンスから選択します。 自動ターゲットは、各訪問者に最も合わせたエクスペリエンスを提供します。 エクスペリエンスの配信は、個々の顧客プロファイルと、類似のプロファイルを持つ以前の訪問者の行動に基づきます。 自動ターゲットを使用して、コンテンツをパーソナライズし、コンバージョンを促進します。

詳細については、「[自動ターゲット](/help/c-activities/auto-target/auto-target-to-optimize.md)」を参照してください。

### 自動パーソナライゼーション（AP）

Automated Personalization(AP)は、オファーやメッセージを組み合わせ、高度な機械学習を使用して各訪問者のオファーのバリエーションを一致させます。 エクスペリエンスの配信は、コンテンツをパーソナライズして上昇率を高めるための個々のお客様のプロファイルに基づいています。

詳しくは、[自動パーソナライゼーション](/help/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9)を参照してください。

### エクスペリエンスターゲット設定（XT）

エクスペリエンスのターゲット設定（XT）では、マーケティング担当者が定義した一連のルールや条件を基にして、特定のオーディエンスにコンテンツを配信します。

エクスペリエンスのターゲット設定（ジオターゲティングを含む）は、特定のオーディエンスに特定のエクスペリエンスまたはコンテンツをターゲット設定するルールを定義する際に有効です。アクティビティで複数のルールを定義して、様々なオーディエンスに異なるコンテンツのバリエーションを提供します。訪問者がサイトを表示すると、エクスペリエンスのターゲット設定（XT）は、その訪問者を評価して、設定した条件を満たしているかどうかを判断します。条件に一致した場合、その訪問者はアクティビティに組み込まれて、条件が一致したオーディエンス用に設計されたエクスペリエンスが表示されます。単一のアクティビティ内で、複数のオーディエンスに対してエクスペリエンスを作成できます。

詳しくは、[エクスペリエンスのターゲット設定](/help/c-activities/t-experience-target/experience-target.md#task_A53DF336CB9F4D7BB87EF2106099EFC4)を参照してください。

### 多変量分析テスト（MVT）

Multivariate Testing(MVT)は、ページ上のオファー内の要素の組み合わせを比較して、特定のオーディエンスに対して最も高いパフォーマンスを発揮する組み合わせを判断します。 MVTは、アクティビティの成功に最も影響を与える要素を特定するのに役立ちます。

詳しくは、[多変量分析テスト](/help/c-activities/c-multivariate-testing/multivariate-testing.md#concept_628695CDC71B449B8DCC2F5654C11499)を参照してください。

### Recommendations

Recommendations のアクティビティは、以前のユーザーアクティビティまたはその他のアルゴリズムを基にして、顧客が興味を持つ可能性のある製品またはコンテンツを自動的に表示します。Recommendations により、顧客が関心を持ちそうな商品を積極的に紹介することが可能になります。

詳細については、「[Recommendations ](/help/c-recommendations/recommendations.md#concept_7556C8A4543942F2A77B13A29339C0C0)」を参照してください。

## エッジネットワーク{#concept_0AE2ED8E9DE64288A8B30FCBF1040934}

「Edge」は、コンテンツを要求する訪問者が世界中のどこにいるかに関係なく、最適な応答時間を確保できる、地理的に分散された配信アーキテクチャです。

応答時間を改善するために、[!DNL Target]エッジはアクティビティロジック、キャッシュされたプロファイル、およびオファー情報のみをホストします。

アクティビティおよびコンテンツのデータベース、[!DNL Analytics]データ、API、およびマーケティング担当者向けのユーザーインターフェイスは、AdobeのCentral Clustersに格納されます。 次に、[!DNL Target]エッジに更新が送信されます。 Central ClustersとEdge Clustersは自動的に同期され、キャッシュされたアクティビティデータが継続的に更新されます。 すべての1:1モデリングも各エッジに保存されるので、より複雑なリクエストもエッジで処理できます。

各Edge Clusterには、訪問者のコンテンツリクエストに応答し、そのリクエストに関する分析データを追跡するために必要なすべての情報が含まれます。 訪問者リクエストは、最も近いエッジクラスターにルーティングされます。

詳しくは、『[Adobe Target Security Overview](https://www.adobe.com/content/dam/cc/en/security/pdfs/AdobeTargetSecurityOverview.pdf)』ホワイトペーパーを参照してください。

[!DNL Target]ソリューションは、世界中のAdobeが所有するデータセンターとAdobeがリースしたデータセンターでホストされています。

Central Clusterの場所には、データ収集センターとデータ処理センターの両方が設置されています。 Edge Clusterの場所には、データ収集センターのみが設置されています。 個々のレポートスイートは特定のデータ処理センターに割り当てられています。

顧客サイトのアクティビティデータは、最も近い7つのエッジクラスターによって収集されます。 このデータは、お客様の事前に決定されたCentral Clusterの宛先に送信されます（次の3つの場所のいずれかになります）。オレゴン、ダブリン、シンガポール)を処理します。 訪問者プロファイルデータは、サイト訪問者に最も近いエッジクラスターに保存されます。 エッジクラスターの場所には、Central Clusterの場所と、バージニア、アムステルダム、シドニー、東京、香港が含まれます。

1か所からすべてのターゲティング要求に応答する代わりに、訪問者に最も近いエッジクラスターで要求が処理されます。 このプロセスにより、ネットワークやインターネットでの移動時間の影響を緩和できます。

![様々なタイプのターゲットサーバーを示すマップ](/help/c-intro/assets/target-servers.png)

[!DNL Target] Central Clustersは、以下を含む、Amazonウェブサービス(AWS)でホストされます。

* 米国オレゴン
* アイルランドダブリン
* シンガポール共和国

[!DNL Target] AWSでホストされるエッジクラスターには、以下が含まれます。

* ムンバイ（インド）
* 東京（日本）
* バージニア、米国
* 米国オレゴン
* シドニー、オーストラリア
* アイルランドダブリン
* シンガポール共和国

[!DNL Target Recommendations]サービスはオレゴンの[!DNL Adobe]データセンターでホストされています。

>[!IMPORTANT]
>
>[!DNL Adobe Target] 現在、中国にはEdge Clusterがありません。中国の [!DNL Target] お客様の訪問者パフォーマンスは引き続き制限されます。ファイアウォールと国内のエッジクラスターが不足しているため、[!DNL Target]がデプロイされたサイトの経験に影響が及ぶ可能性があります。 エクスペリエンスのレンダリングが遅くなる場合があり、ページの読み込みに影響する可能性があります。 また、[!DNL Target]オーサリングUIを使用すると遅延が発生する場合があります。

必要に応じて、[!DNL Target]エッジクラスターを許可リストできます。 詳しくは、[許可リストターゲットエッジノード](/help/c-implementing-target/c-considerations-before-you-implement-target/allowlist-edges.md)を参照してください。

## 保護されたユーザーエクスペリエンス{#concept_40A5E781D90A41E4955F80EA9E5F8F96}

アドビは、ターゲット設定インフラストラクチャの可用性とパフォーマンスが可能な限り安定するようにしています。ただし、訪問者のブラウザーとAdobeのサーバー間の通信が切断されると、コンテンツの配信が中断される可能性があります。

サービスの中断や接続の問題を防ぐために、すべての場所でデフォルトコンテンツ（クライアントが定義）が含まれるように設定されています。 このデフォルトコンテンツは、ユーザーのブラウザーが[!DNL Target]に接続できない場合に表示されます。

ユーザーのブラウザーが、定義されたタイムアウト時間（デフォルトは 15 秒）以内に接続できない場合は、ページは変更されず、デフォルトのままになります。このタイムアウトのしきい値に達した場合、デフォルトの場所のコンテンツが表示されます。

アドビは、パフォーマンスの最適化と保護によってユーザーエクスペリエンスを保護しています。

* アドビは、業界標準に基づいたパフォーマンスベンチマークを実施しており、このベンチマークはアドビのサービス契約によって保証されています。
* Edge ネットワークによって、タイムリーなデータ配信を実現しています。
* アプリケーションをセキュリティ保護するための多層型アプローチを使用し、お客様に対して最高レベルの可用性と信頼性を確保しています。
* [!DNL Target] コンサルティングは、導入支援と継続的な製品サポートをおこなっています。

## 検索エンジン最適化（SEO）対応テスト {#concept_C0C865663CAB4251B66A1F250FD25E6A}

[!DNL Adobe Target] はテストのための検索エンジンガイドラインに従っています。

Googleはユーザーテストを推奨しています。 Googleはドキュメントの中で、A/BとMultivariate Testingが、特定のガイドラインに従っても自然検索エンジンのランク付けを損なわないと述べています。

詳しくは、次の Google のリソースを参照してください。

* [ウェブテストが Google 検索に与える影響](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html)
* [ウェブテストとクローキング](https://support.google.com/analytics/answer/2576845?hl=en&amp;ref_topic=1745207)

ガイドラインは[Google ウェブマスター向け公式ブログ](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html)の投稿として公表されています。この投稿は 2012 年のものですが、この問題に関する Google からの最新の発言であり、ガイドラインは現在でも通用します。

* **クロークなし**:クロークとは、ユーザーに対して1組のコンテンツを表示し、検索エンジンボットに対して別の組のコンテンツを表示することです。クロークは、ボットを特別に識別し、意図的に異なるコンテンツをフィードすることで実行されます。

   [!DNL Target] は、プラットフォームとしては検索エンジンボットを他のユーザーと同様に扱うよう設定されています。その結果、ボットがランダムに選択され、テストのバリエーションが「確認」された場合、ボットをアクティビティに含めることができます。

* **rel=&quot;canonical&quot;を使用**:バリエーションに対して異なるURLを使用してA/Bテストを設定する必要がある場合があります。これらの場合、元来の（コントロール）URL を参照する `rel="canonical"` タグをすべてのバリエーションに含ませます。例えば、Adobeがバリエーションごとに異なるURLを使用してホームページをテストしているとします。 ホームページの次のcanonicalタグは、それぞれのバリエーションの`<head>`タグ内に記述します。

   `<link rel="canonical" href="https://www.adobe.com" />`

* **302（一時的）リダイレクトを使用する**:テスト内のバリエーションページで別々のURLが使用される場合、Googleは302リダイレクトを使用してテストバリエーションにトラフィックを誘導することを推奨しています。302リダイレクトは、リダイレクトが一時的で、テストが実行中の場合にのみアクティブであることを検索エンジンに通知します。

   302リダイレクトはサーバー側のリダイレクトで、[!DNL Target]はほとんどの最適化プロバイダーと共に、クライアント側の機能を使用します。 したがって、リダイレクトは、[!DNL Target]がGoogleの推奨に完全に準拠していない領域です。 ただし、この方法はテストのごく一部にしか影響しません。 [!DNL Target]を通じてテストを実行する標準的なアプローチは、1つのURL内でコンテンツを変更することを呼び出すので、リダイレクトは必要ありません。 クライアントがテストのバリエーションを表すために複数のURLを使用する必要がある場合があります。 この場合、[!DNL Target]はJavaScript `window.location`コマンドを使用します。 このコマンドは、テストのバリエーションをユーザーに指示します。テストのバリエーションは、リダイレクトが301か302かを明示的に示しません。

   Adobeは、検索エンジンのガイドラインに完全に合致する実行可能なソリューションを引き続き探しています。 テストに別々のURLを使用する必要があるクライアントの場合、Adobeは、正規タグを適切に実装することで、このアプローチに伴うリスクが軽減されると確信しています。

* **必要な期間のみ実験を行う**:Adobeは、「必要な期間」は、統計的有意性に到達するまでの期間と考えています。[!DNL Target][ は、テストがこの時点に到達した時を判断するためのベストプラクティスを提供](https://docs.adobe.com/content/target-microsite/testcalculator.html)します。Adobeでは、勝者テストのハードコードされた実装をテストワークフローに組み込み、適切なリソースを割り当てることをお勧めします。

   [!DNL Target]プラットフォームを使用して勝者テストを「発行」することは、恒久的なソリューションとして推奨されません。 勝者テストが100%のユーザーの100%に対して発行される場合、このアプローチは、勝者テストをハードコーディングするプロセスが完了している間に使用できます。

   テストが変更した点に留意することも大切です。ページ上のボタンやテキストベースでない小さなアイテムの色を更新しても、自然ランキングには影響しません。 ただし、文字の変更はハードコードする必要があります。

   テストしているページへのアクセスのしやすさに留意することも大切です。検索エンジンからアクセスできず、自然検索でランク付けするように設計されていないページの場合は、上記の考慮事項は一切適用されません。 例えば、電子メールキャンペーン専用のランディングページがあります。

Google によると、これらのガイドラインに従えば、「テストがサイトの検索結果に及ぼす影響はほとんどあるいはまったくない。」とのことです。

これらのガイドラインに加えて、Google はまた、Content Experiments ツールのドキュメンテーションでもう 1 つのガイドラインを提供しています。

* 「バリエーションの各ページは、元来のページ内容の主旨を保持する必要があります。こういったバリエーションは、元来の内容に対しユーザーが持つ全般的イメージを変えてはいけません。」

Google は例として、「ユーザーに表示される組み合わせに関連しないキーワードでサイトの元来のページが読み込まれる場合、そのサイトを Google のインデックスから外すことがあります」と記述しています。

Adobeは、テストのバリエーション内で意図せず元のコンテンツの意味を変更するのは難しいと感じています。 ただし、Adobeでは、ページのキーワードテーマを認識し、それらのテーマを維持することをお勧めします。 ページ内容を変更、特に関連のあるキーワードを追加したり削除したりすると、自然検索でのその URL のランキングが変わってしまう場合があります。Adobeでは、テストプロトコルの一部としてSEOパートナーと提携することを推奨します。

## ボット {#bots}

Adobe[!DNL Target]は、[DeviceAtlas](https://deviceatlas.com/device-data/user-agent-tester/)指標「isRobot」を使用して、リクエストヘッダーで渡されたユーザーエージェント文字列に基づいて既知のボットを検出します。

>[!NOTE]
>
> [!DNL Server-Side]リクエストの場合、[リクエストの「コンテキスト」ノード](https://developers.adobetarget.com/api/delivery-api/#tag/Delivery-API)に渡された値は、ボット検出用のユーザーエージェント文字列よりも優先されます。

ボットによって生成されたと識別されたトラフィックは、引き続きコンテンツを提供します。 ボットは通常のユーザーと同様に扱われ、[!DNL Target]がSEOガイドラインに従っていることを確認します。 ボットトラフィックの使用は、通常のユーザーのように扱われると、A/B テストやパーソナライゼーションアルゴリズムをゆがめる可能性があります。したがって、既知のボットが[!DNL Target]アクティビティで検出された場合、トラフィックに対する扱いは少し異なります。 ボットトラフィックを削除することで、ユーザーアクティビティをより正確に測定できます。

特に、既知のボットトラフィック[!DNL Target]には次の意味はありません。

* 訪問者プロファイルの作成または取得
* プロファイル属性の記録またはプロファイルスクリプトの実行
* Adobe Audience Manager（AAM）セグメントの検索（該当する場合）
* ボットトラフィックを使用して、Recommendations、自動ターゲット、Automated Personalization、自動配分のアクティビティ向けにパーソナライズされたコンテンツをモデリングし、提供する
* レポート用のアクティビティ訪問の記録
* [!DNL Adobe Experience Cloud]プラットフォームに送信するログデータ
