---
keywords: Adobe Experience Platform Web SDK;aep web sdk;aep sdk;検索エンジンの最適化;検索エンジンの最適化;seo;エッジクラスター;セントラルクラスター;at.js;mbox.js;
description: JavaScript ライブラリ（AEP Web SDK at.js）、アドビデータセンター、SEO テスト、ボットに関する情報などを含む  [!DNL Adobe Target]  の仕組みを説明します。
title: ' [!DNL Target]  の仕組み'
feature: Overview
exl-id: 8a93e061-0be7-4ecc-b511-2210094547f2
source-git-commit: fe1e97710e7692ba7724103853ed7438c3f361b1
workflow-type: tm+mt
source-wordcount: '2465'
ht-degree: 89%

---

# [!DNL Adobe Target] の仕組み

JavaScript ライブラリ（[!DNL Adobe Experience Platform Web SDK] と mbox.js）に関する情報を含む [!DNL Adobe Target] の仕組みを説明します。この記事では、[!DNL Target] を使用して作成できる様々なアクティビティタイプについても紹介します。また、[!DNL Target] エッジネットワーク、検索エンジン最適化（SEO）、および [!DNL Target] によるボットの検出方法についても説明します。

## [!DNL Adobe Target] JavaScript ライブラリ {#libraries}

[!DNL Experience Platform Web SDK] または JavaScript ライブラリを使用して、[!DNL Target] を web サイトに統合することが可能です。

* **[!DNL Adobe Experience Platform Web SDK]：**[Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=ja){target=_blank} は、新しいクライアントサイド JavaScript ライブラリです。[!DNL Experience Platform Web SDK] を使用すると、[!DNL Adobe Experience Cloud] のお客様は [!DNL Experience Platform] エッジネットワークを介して、[!DNL Experience Cloud] の様々なサービス（[!DNL Target] など）を操作できます。[!DNL Adobe] では、新しい [!DNL Target] ユーザー全員に、[!DNL Experience Platform Web SDK] を実装することを推奨します。
* **at.js：** at.js ライブラリは、[!DNL Target] の新しい実装ライブラリです。at.js ライブラリは、Web 実装のページ読み込み時間を改善し、シングルページアプリケーション向けのより優れた実装オプションを提供します。at.js は、頻繁にアップデートされ、新しい機能が追加されます。[!DNL Adobe] では、at.js を使用するすべてのお客様に、実装を[最新バージョンの at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=ja){target=_blank} にアップデートすることをお勧めします。

>[!NOTE]
>
>mbox.js library ライブラリは、[!DNL Target] のレガシー実装ライブラリです。mbox.js ライブラリは、2021年3月31日（PT）以降はサポートされなくなります。Experience Platform Web SDK（推奨）または最新バージョンの at.js にアップグレードしてください。

サイトの各ページの [!DNL Experience Platform Web SDK] または at.js を参照します。例えば、グローバルヘッダーにこれらのライブラリのいずれかを追加できます。または、[Adobe Experience Platform のタグ](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=ja)を使用して [!DNL Target] を実装することを検討してください。

次のリソースには、[!DNL Experience Platform Web SDK] または at.js の実装に役立つ詳細情報が含まれています。

* [[!DNL Adobe Experience Platform Web SDK] 拡張機能](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/sdk/overview.html?lang=ja){target=_blank}
* [ [!DNL Target] を使用した  [!DNL Adobe Experience Platform] の実装](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/deploy-at-js/implement-target-using-adobe-launch.html?lang=ja){target=_blank}

訪問者が [!DNL Target] 用に最適化されたページをリクエストするたびに、リクエストがターゲティングシステムに送信されます。このリクエストは、その訪問者に提供するコンテンツを決定するのに役立ちます。このプロセスはリアルタイムで発生します。ページが読み込まれるたびに、コンテンツへのリクエストが作成され、システムで処理されます。コンテンツは、マーケターが制御するアクティビティおよびエクスペリエンスのルールによって管理され、個々のサイト訪問者がターゲットになります。各サイト訪問者が最も反応する、インタラクションを行う、または最終的に購入する可能性が最も高いコンテンツが提供されます。コンテンツをパーソナライズすることで、応答率、獲得率および売上高を最大化できます。

[!DNL Target] では、ページ上の各要素は、ページ全体に広がる単一のエクスペリエンスの一部です。各エクスペリエンスでは、ページ上に複数の要素を含めることができます。

訪問者に表示されるコンテンツは、作成するアクティビティタイプによって異なります。

### [!UICONTROL A/B Test]

基本的な A/B テストで表示されるコンテンツは、アクティビティに割り当てたエクスペリエンスからランダムに選択されます。各エクスペリエンスにトラフィック配分の割合を割り当てることができます。このランダムなトラフィック分割の結果、トラフィックの割合が均等化するまでの初期のトラフィック量が多くなる場合があります。例えば、2 つのエクスペリエンスを作成した場合、最初のエクスペリエンスはランダムに選択されます。トラフィック量がほとんどない場合は、訪問者の割合が一方のエクスペリエンスに偏っている可能性があります。トラフィックが増えるにしたがって、割合は等しくなります。

エクスペリエンスごとに割合のターゲットを指定できます。この場合、乱数が生成され、その乱数を使用して、表示するエクスペリエンスが選択されます。結果の割合が指定したターゲットと完全に一致しないこともありますが、トラフィックが多いほど、エクスペリエンスがターゲットに近い割合で分割されます。

1. 訪問者が、サーバー上のページをリクエストしてブラウザーに表示します。
1. 訪問者のブラウザー内にファーストパーティ Cookie が設定され、訪問者行動を保存します。
1. ページから、ターゲット設定システムが呼び出されます。
1. アクティビティのルールに基づいてコンテンツが表示されます。

詳細については、「[A/B テストの作成](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)」を参照してください。

### [!UICONTROL Auto-Allocate]

[!UICONTROL Auto-Allocate] は、2 つ以上のエクスペリエンスのうちの勝者を識別します。 [!UICONTROL Auto-Allocate] は、より多くのトラフィックを勝者エクスペリエンスに自動的に再割り当てするので、テストの実行と学習を継続しながらコンバージョンを増やすのに役立ちます。

詳細は、[[!UICONTROL Auto-Allocate]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) を参照してください。

### [!UICONTROL Auto-Target] （時）

[!UICONTROL Auto-Target] では、高度な機械学習を使用して、マーケターが定義した、パフォーマンスの高い複数のエクスペリエンスから選択します。 [!UICONTROL Auto-Target] は、各訪問者に最適なエクスペリエンスを提供します。 エクスペリエンスの配信は、個々の顧客プロファイルと、類似のプロファイルを持つ以前の訪問者の行動に基づきます。[!UICONTROL Auto-Target] を使用してコンテンツをパーソナライズし、コンバージョンを促進します。

詳細については、[自動ターゲット](/help/main/c-activities/auto-target/auto-target-to-optimize.md)を参照してください。

### [!UICONTROL Automated Personalization] （AP）

[!UICONTROL Automated Personalization] （AP）は、オファーやメッセージを組み合わせ、高度な機械学習を使用して各訪問者にマッチするオファーの各種バリエーションを判断します。 個別の顧客プロファイルを基準とするエクスペリエンスの配信により、コンテンツをパーソナライズして販売を促進することが可能です。

詳しくは、[Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9)を参照してください。

### [!UICONTROL Experience Targeting] （XT）

[!UICONTROL Experience Targeting] （XT）では、マーケターが定義した一連のルールや条件を基にして、特定のオーディエンスにコンテンツを配信します。

ジオターゲティングを含む [!UICONTROL Experience Targeting] は、特定のオーディエンスに特定のエクスペリエンスまたはコンテンツをターゲット設定するルールを定義する際に有効です。 アクティビティで複数のルールを定義して、様々なオーディエンスに異なるコンテンツのバリエーションを提供します。訪問者がサイトを表示すると、[!UICONTROL Experience Targeting] （XT）は、その訪問者を評価して、設定した条件を満たしているかどうかを判断します。 条件に一致した場合、その訪問者は該当アクティビティの対象となり、条件が一致したオーディエンス用に設計されたエクスペリエンスが表示されます。単一のアクティビティ内で、複数のオーディエンスに対してエクスペリエンスを作成できます。

詳しくは、[エクスペリエンスのターゲット設定](/help/main/c-activities/t-experience-target/experience-target.md#task_A53DF336CB9F4D7BB87EF2106099EFC4)を参照してください。

### [!UICONTROL Multivariate Test] （MVT）

[!UICONTROL Multivariate Testing] （MVT）はページ上の要素のオファーの組み合わせを比較し、特定のオーディエンスに対して最も効果が高い組み合わせを特定します。 MVT は、アクティビティの成功に最も影響を与える要素を特定するのに役立ちます。

詳しくは、[多変量分析テスト](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md#concept_628695CDC71B449B8DCC2F5654C11499)を参照してください。

### [!UICONTROL Recommendations]

[!UICONTROL Recommendations] のアクティビティは、以前のユーザーアクティビティまたはその他のアルゴリズムを基にして、顧客が興味を持つ可能性のある製品またはコンテンツを自動的に表示します。 Recommendations を使うと、顧客が知らなかったであろう関連商品を紹介するのに役立ちます。

詳細については、[Recommendations](/help/main/c-recommendations/recommendations.md#concept_7556C8A4543942F2A77B13A29339C0C0) を参照してください。

## エッジネットワーク {#concept_0AE2ED8E9DE64288A8B30FCBF1040934}

「エッジ」は、コンテンツをリクエストするエンドユーザーが世界中のどこにいても、最適な応答時間を確保できる、地理的に分散された配信アーキテクチャです。

応答時間を改善するために、[!DNL Target] Edge はアクティビティロジック、キャッシュされたプロファイル、およびオファー情報のみをホストします。

アクティビティおよびコンテンツのデータベース、[!DNL Analytics] データ、API およびマーケター向けのユーザーインターフェイスは、アドビの中央クラスターに格納されます。その後、最新情報が [!DNL Target] Edge に送信されます。中央クラスターとエッジクラスターは自動的に同期され、キャッシュされたアクティビティデータが継続的に更新されます。また、1:1 モデリングがすべて各エッジに保存されるので、複雑なリクエストもエッジ上で処理できます。

各エッジクラスターには、訪問者のコンテンツリクエストに応答し、そのリクエストに関する分析データを追跡するために必要な情報がすべて格納されます。訪問者のリクエストは、最寄りのエッジクラスターに転送されます。

詳しくは、『[Adobe Target セキュリティの概要](https://www.adobe.com/content/dam/cc/en/security/pdfs/AdobeTargetSecurityOverview.pdf)』ホワイトペーパーを参照してください。

[!DNL Target] ソリューションは、世界中のアドビが所有するデータセンターおよびアドビがリース契約を結んでいるデータセンターでホストされています。

管理サーバー拠点には、データ収集センターとデータ処理センターの両方が設置されています。エッジクラスター拠点には、データ収集センターのみが設置されています。個々のレポートスイートは特定のデータ処理センターに割り当てられています。

顧客サイトのアクティビティデータは、最も近い 7 か所のエッジクラスターによって収集されます。このデータは、顧客が事前に決定した中央クラスター（オレゴン、ダブリン、シンガポールのいずれか）に送られ、処理されます。訪問者プロファイルデータは、サイト訪問者に最も近いエッジクラスターに保存されます。エッジクラスター拠点には、中央クラスター拠点と、バージニア、ムンバイ、シドニー、東京が含まれます。

1 か所ですべてのターゲティングリクエストに応答するのではなく、訪問者に最も近いエッジクラスターでリクエストを処理します。このプロセスにより、ネットワークやインターネットでの通信時間の影響を緩和できます。

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
>[!DNL Adobe Target] では現在、中国にエッジクラスターはありません。中国における [!DNL Target] のお客様への訪問者パフォーマンスは引き続き制限されます。中国内のファイアウォールおよびエッジクラスター不足により、[!DNL Target] がデプロイされたサイトのエクスペリエンスに影響が及ぶ可能性があります。エクスペリエンスのレンダリング速度が低下し、ページの読み込みに影響する可能性があります。また、マーケターが、[!DNL Target] のオーサリング UI を使用する際に遅延が発生することがあります。

必要に応じて、[!DNL Target] のエッジクラスターを許可リストに追加できます。詳しくは、[Target のエッジノードを許可リストに加える](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/privacy/allowlist-edges.html?lang=ja){target=_blank}を参照してください。

## ユーザーエクスペリエンスの保護 {#concept_40A5E781D90A41E4955F80EA9E5F8F96}

[!DNL Adobe] は、ターゲット設定インフラストラクチャの可用性とパフォーマンスの可能な限りの安定を確保しています。ただし、訪問者のブラウザーと [!DNL Adobe] サーバー間の通信が切断されると、コンテンツ配信が中断される可能性があります。

サービスの中断や接続の問題を防ぐために、すべての場所は、デフォルトコンテンツ（クライアントが定義）を含めるように設定されています。このデフォルトコンテンツは、ユーザーのブラウザーが [!DNL Target] に接続できない場合に表示されます。

ユーザーのブラウザーが、定義されたタイムアウト時間（デフォルトは 15 秒）以内に接続できない場合は、ページは変更されません。このタイムアウトのしきい値に達した場合、デフォルトの場所のコンテンツが表示されます。

[!DNL Adobe] は、パフォーマンスを最適化し、安全性を保つことで、ユーザーエクスペリエンスを保護します。

* [!DNL Adobe] は、アドビのサービスレベル契約で保証された業界標準に基づくパフォーマンスベンチマークを保証します。
* エッジネットワークによって、タイムリーなデータ配信を実現しています。
* [!UICONTROL Adobe] では、アプリケーションをセキュリティ保護するための多層型アプローチを使用し、お客様に対して最高レベルの可用性と信頼性を確保しています。
* [!DNL Target] コンサルティングは、導入支援と継続的な製品サポートを行っています。

## 検索エンジン最適化（SEO）対応テスト {#concept_C0C865663CAB4251B66A1F250FD25E6A}

[!DNL Adobe Target] はテストのための検索エンジンガイドラインに従っています。

Google はユーザーに対し、テストを推奨しています。Googleはドキュメントの中で、A/B テストおよび [!UICONTROL Multivariate Testing] テストが、特定のガイドラインに従っていれば、オーガニック検索エンジンのランキングは損なわれないと述べています。

詳しくは、次の Google のリソースを参照してください。

* [ウェブテストが Google 検索に与える影響](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html)
* [ウェブテストとクローキング](https://support.google.com/analytics/answer/2576845?hl=ja&amp;ref_topic=1745207)

ガイドラインは[Google ウェブマスター向け公式ブログ](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html)の投稿として公表されています。この投稿は 2012 年のものですが、この問題に関する Google からの最新の発言であり、ガイドラインは現在でも通用します。

* **クロークなし**：クロークとは、ユーザーに対して特定のコンテンツを表示し、検索エンジンボットには別のコンテンツを表示することです。クロークは、ボットを特別に識別し、異なるコンテンツを意図的にフィードすることで実行されます。

  [!DNL Target] は、プラットフォームとしては検索エンジンボットを他のユーザーと同様に扱うよう設定されています。その結果、ボットがランダムに選択され、テストのバリエーションを「確認」した場合、そのボットをアクティビティに含めることができます。

* **rel=&quot;canonical&quot; を使用する**：バリエーションを付けるために、異なる URL を使用して A/B テストを設定する必要が出ることがあります。これらの場合、元来の（コントロール）URL を参照する `rel="canonical"` タグをすべてのバリエーションに追加する必要があります。例えば、[!DNL Adobe] がバリエーションごとに異なる URL を使用してホームページをテストするとします。ホームページの次の canonical タグは、各バリエーションの `<head>` タグ内に配置されます。

  `<link rel="canonical" href="https://www.adobe.com" />`

* **302（一時的な）リダイレクトを使う**：テストでバリエーションのページに異なる URL を使用する場合、Google では、302 リダイレクトを使用してトラフィックを直接テストバリエーションにリダイレクトすることを勧めています。302リダイレクトは、リダイレクトが一時的であり、テストが実行中の間のみアクティブとなることを検索エンジンに通知します。

  302 リダイレクトは、サーバーサイドのリダイレクトであり、[!DNL Target] は他の大多数の最適化プロバイダーと同様、クライアントサイドの機能を使用します。このため、リダイレクトは [!DNL Target] が Google のレコメンデーションに完全に準拠していない領域になります。ただし、これが影響するのは、ほんの一部のテストのみです。[!DNL Target] でテストを実行するための標準的なアプローチでは、1 つの URL 内でコンテンツの変更を呼び出すため、リダイレクトの必要はありません。クライアントのテストバリエーションを表すように複数の URL を使う必要が出ることもあります。この場合、[!DNL Target]は JavaScript `window.location` コマンドを使用します。このコマンドは、テストのバリエーションをユーザーに指示します。テストのバリエーションは、リダイレクトが 301 と 302 のどちらであるかを明示的に示しません。

  [!DNL Adobe] では、検索エンジンのガイドラインに完全に合致する実行可能なソリューションを引き続き探しています。テストに別々の URL を使用する必要があるクライアントの場合、[!DNL Adobe] は、正規タグを適切に実装することで、このアプローチに伴うリスクが軽減されると確信しています。

* **実験を必要な期間のみ実行する**：[!DNL Adobe] では、「必要な期間」を統計的優位差が達成されるまでの期間と考えます。[!DNL Target] には、テストがこの時点に到達したかどうかを判断するためのベストプラクティスと [!DNL Adobe Target] [サンプルサイズ計算ツール](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6)が用意されています。[!DNL Adobe] では、勝者テストのハードコード実装をテストワークフローに組み込み、適切なリソースを割り当てることをお勧めします。

  [!DNL Target] プラットフォームを使用して勝者テストを「公開」することは、恒久的なソリューションとしては推奨されません。勝者テストが 100％ のユーザーに対して 100％ の時間公開されている場合、このアプローチは、勝者テストをハードコーディングするプロセスが完了している間使用できます。

  テストが変更した点に留意することも大切です。単純にページ上のボタンの色や、その他の文字ベースでない小さなアイテムを更新しても、オーガニックランキングには大きな影響はありません。ただし、文字の変更はハードコードする必要があります。

  テストしているページへのアクセスのしやすさに留意することも大切です。検索エンジンからアクセスできず、オーガニック検索でランク付けするように設計されていないページの場合は、上記の考慮事項は一切適用されません。例えば、メールキャンペーン専用のランディングページがあります。

Google によると、これらのガイドラインに従えば、「テストがサイトの検索結果に及ぼす影響はほとんどあるいはまったくない。」とのことです。

これらのガイドラインに加えて、Google はまた、Content Experiments ツールのドキュメンテーションでもう 1 つのガイドラインを提供しています。

* 「バリエーションの各ページは、元来のページ内容の主旨を保持する必要があります。こういったバリエーションは、元来の内容に対しユーザーが持つ全般的イメージを変えてはいけません。」

Google は例として、「ユーザーに表示される組み合わせに関連しないキーワードでサイトの元来のページが読み込まれる場合、そのサイトを Google のインデックスから外すことがあります」と記述しています。

テストのバリエーション内 [!UICONTROL Adobe] 意図せず元のコンテンツの意味を変更するのは難しいと感じています。 [!UICONTROL Adobe] だし、ページのキーワードテーマに注意して、それらのテーマを維持することをお勧めします。 ページ内容を変更、特に関連のあるキーワードを追加したり削除したりすると、オーガニック検索でのその URL のランキングが変わってしまう場合があります。[!DNL Adobe] では、テストプロセスの一環として、SEO パートナーに協力を仰ぐことをお勧めします。

## ボット {#bots}

Adobe [!DNL Target] は、[DeviceAtlas](https://deviceatlas.com/device-data/user-agent-tester/) 指標「isRobot」を使用し、リクエストヘッダーで渡されたユーザーエージェント文字列に基づいて既知のボットを検出します。

>[!NOTE]
>
> [!DNL Server-Side] リクエストの場合、[リクエストの「コンテキスト」ノード](https://developers.adobetarget.com/api/delivery-api/#tag/Delivery-API)に渡された値は、ボット検出用のユーザーエージェント文字列よりも優先されます。

ボットによって生成されたと識別されたトラフィックには、引き続きコンテンツが提供されます。ボットは通常のユーザーと同様に扱われ、[!DNL Target] が SEO ガイドラインに従っていることを確認します。ボットトラフィックの使用は、通常のユーザーのように扱われると、A/B テストやパーソナライゼーションアルゴリズムをゆがめる可能性があります。したがって、[!DNL Target] アクティビティで既知のボットが検出されると、そのトラフィックの処理はわずかに異なります。ボットトラフィックを削除することで、ユーザーアクティビティをより正確に測定できます。

特に、既知のボットトラフィックの場合、[!DNL Target] は以下をおこないません。

* 訪問者プロファイルの作成または取得
* プロファイル属性の記録またはプロファイルスクリプトの実行
* [!DNL Adobe Audience Manager]（AAM）セグメントの検索（該当する場合）
* [!UICONTROL Recommendations]、[!UICONTROL Auto-Target]、[!UICONTROL Automated Personalization]、[!UICONTROL Auto-Allocate] の各アクティビティにおけるパーソナライズされたコンテンツのモデリングおよび提供時のボットトラフィックの使用
* レポート用のアクティビティ訪問の記録
* [!DNL Adobe Experience Cloud] プラットフォームに送信されたログデータ

既知のボットトラフィックに [!UICONTROL Analytics for Target] （A4T）を使用する場合、[!DNL Target] は次を実行しません。

* [!DNL Analytics] にイベントを送信

既知のボットトラフィックに client_side ログを使用する場合は、[!DNL Target] は次を返しません。

* tnta ペイロード
