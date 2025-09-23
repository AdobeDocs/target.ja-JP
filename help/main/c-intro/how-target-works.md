---
keywords: Adobe Experience Platform Web SDK;aep web sdk;aep sdk;検索エンジンの最適化;検索エンジンの最適化;seo;エッジクラスター;セントラルクラスター;at.js;mbox.js;
description: 'JavaScript ライブラリ（AEP Web SDK at.js）、サーバーコールの使用方法、使用方法、Adobe データセンター、SEO テスト、ボットなど、の仕組みを説明します  [!DNL Adobe Target] '
title: ' [!DNL Target]  の仕組み'
feature: Overview
exl-id: 8a93e061-0be7-4ecc-b511-2210094547f2
source-git-commit: 85edad5c3adb3a7b01ee6d1eaf2c30c7596d5f92
workflow-type: tm+mt
source-wordcount: '2214'
ht-degree: 24%

---

# [!DNL Adobe Target] の仕組み

JavaScript ライブラリ（[!DNL Adobe Target] および at.js）の詳細など、[!DNL Adobe Experience Platform Web SDK] の仕組みを説明します。 この記事では、ユーザーが作成できる様々なアクティビティタイプ、[!DNL Target] 用数カウント戦略、[!DNL Target] Edge Network、SEO およびボット検出についても説明します。

主なポイント：

* **JavaScript ライブラリ**: [!DNL Target] JavaScript ライブラリの詳細：[!DNL Adobe Experience Platform Web SDK] および at.js。
* **サーバーコールの使用戦略**：エンドポイント、単一の mbox、バッチ mbox、実行、プリフェッチ、通知の呼び出しなど、様々なサーバーコールの数 [!DNL Target] を把握します。
* **Edge Network**: [!DNL Target] が [!DNL Adobe Experience Platform Edge Network] とどのようにやり取りするかを確認します。
* **保護されたユーザーエクスペリエンス**:[!DNL Adobe] がターゲティングインフラストラクチャの可用性とパフォーマンスを確保する方法について説明します。
* **SEO ガイドライン**:[!DNL Target] アクティビティを SEO ガイドラインに合わせるためのベストプラクティスに従います。
* **ボットトラフィック**：テストやパーソナライゼーションアルゴリズムのゆがみを回避するために Target がボットトラフィックを処理する方法を説明します。

## [!DNL Adobe Target] JavaScript ライブラリ {#libraries}

Target と web サイトの統合（[!DNL Experience Platform Web SDK] または at.js を使用）:

* **[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/aep/aep-web-sdk-overview){target=_blank}**：このクライアントサイド JavaScript ライブラリを使用すると、[!DNL Adobe Experience Cloud] のお客様は [!DNL Experience Platform Edge Network] を通じて様々なサービスを操作できます。 [!DNL Adobe] では、新規の [!DNL Target] ユーザーに [!DNL Experience Platform Web SDK] を実装することをお勧めします。
* **[at.js](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/at-js-implementation/deploy-at-js/how-to-deployatjs){target=_blank}**:[!DNL Target] 用のこの実装ライブラリは、web 実装のページ読み込み時間を改善し、単一ページアプリケーション向けのより優れたオプションを提供します。 新機能を使用して頻繁に更新される [!DNL Adobe]、すべての [at.js ユーザーを最新バージョンにアップデート ](https://experienceleague-review.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} することをお勧めします。

>[!NOTE]
>
>mbox.js ライブラリは [!DNL Target] のレガシー実装で、2021 年 3 月 31 日（PT）以降はサポートされなくなります。 [!UICONTROL Experience Platform Web SDK] （推奨）または at.js の最新バージョンへのアップグレード。

サイトの各ページの [!UICONTROL Experience Platform Web SDK] または at.js を参照します。 例えば、グローバルヘッダーにこれらのライブラリのいずれかを追加します。 または、[Adobe Experience Platformのタグ ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/home){target=_blank} を使用して [!DNL Target] を実装します。

次のリソースには、[!DNL Experience Platform Web SDK] または at.js の実装に役立つ詳細情報が含まれています。

* [[!DNL Adobe Experience Platform Web SDK] 拡張機能](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/sdk/overview.html?lang=ja){target=_blank}
* [ [!DNL Adobe Experience Platform]を使用した  [!DNL Target]  の実装](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/at-js-implementation/deploy-at-js/implement-target-using-adobe-launch){target=_blank}

訪問者が [!DNL Target] 用に最適化されたページをリクエストするたびに、ターゲティングシステムにリアルタイムリクエストが送信され、提供するコンテンツが決定されます。 このリクエストは、マーケターが制御するアクティビティやエクスペリエンスの管理の下で、ページが読み込まれるたびに行われ、実行されます。 コンテンツは、個々のサイト訪問者をターゲットにし、応答率、獲得率、売上高を最大化します。 パーソナライズされたコンテンツは、訪問者の反応、インタラクション、購入を保証するのに役立ちます。

ま [!DNL Target]、ページ上の各要素は、複数の要素を含めることができる単一のエクスペリエンスの一部です。

表示されるコンテンツは、作成するアクティビティのタイプによって異なります。

### [!UICONTROL A/B Test]

基本的な A/B テストでは、コンテンツは割り当てられたエクスペリエンスからランダムに選択されます。 各エクスペリエンスにトラフィック配分の割合を設定できます。 最初は、ランダムな分割によってトラフィックが不均等に分散される可能性がありますが、トラフィックが増加するとイコライズされます。 例えば、2 つのエクスペリエンスを使用する場合、開始エクスペリエンスはランダムに選択されます。 低トラフィックは 1 つのエクスペリエンスに対して訪問者の割合をゆがめる可能性がありますが、この状況は多トラフィックでバランスします。

各エクスペリエンスの割合のターゲットを指定します。 表示するエクスペリエンスを選択する乱数が生成されます。 結果の割合は、ターゲットと完全には一致しない場合がありますが、トラフィックが多いほど、ターゲット目標に対する割合が近くなります。

1. 顧客が、サーバーからページをリクエストして、ブラウザーに表示します。
1. ファーストパーティ cookie は、顧客のブラウザーに設定され、行動を保存します。
1. ページから、ターゲティングシステムが呼び出されます。
1. コンテンツは、アクティビティルールに基づいて表示されます。

詳細については、「[A/B テストの作成](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)」を参照してください。

### [!UICONTROL Auto-Allocate]

[!UICONTROL Auto-Allocate] は、2 つ以上のオプションの中から勝者エクスペリエンスを識別します。 その後、より多くのトラフィックを勝者に自動的に再割り当てし、テストの実行と学習を継続しながらコンバージョンを増やします。

詳細は、[[!UICONTROL Auto-Allocate]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) を参照してください。

### [!UICONTROL Auto-Target] （時）

[!UICONTROL Auto-Target] は、高度な機械学習を活用して、パフォーマンスの高い複数のマーケターが定義したエクスペリエンスから選択します。 [!UICONTROL Auto-Target] は、個々の顧客プロファイルと類似のプロファイルを持つ以前の訪問者の行動に基づいて、各訪問者に最適なエクスペリエンスを提供します。 [!UICONTROL Auto-Target] を使用してコンテンツをパーソナライズし、コンバージョンを促進します。

詳細については、[自動ターゲット](/help/main/c-activities/auto-target/auto-target-to-optimize.md)を参照してください。

### [!UICONTROL Automated Personalization] （AP）

[!UICONTROL Automated Personalization] （AP）は、オファーやメッセージを組み合わせ、高度な機械学習を使用して各訪問者にマッチする様々なバリエーションを提供します。 AP は、個人の顧客プロファイルに基づいてコンテンツをパーソナライズし、上昇率を高めます。

詳しくは、[Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9)を参照してください。

### [!UICONTROL Experience Targeting] （XT）

[!UICONTROL Experience Targeting] （XT）では、マーケターが定義したルールや条件を基にして、特定のオーディエンスにコンテンツを配信します。 ジオターゲティングを含め、XT は、特定のオーディエンスに特定のエクスペリエンスやコンテンツをターゲット設定するルールを定義する際に役立ちます。 アクティビティで複数のルールを設定して、様々なオーディエンスに異なるコンテンツのバリエーションを提供します。 訪問者がサイトを表示すると、XT は訪問者を評価して、条件を満たしているかどうかを判断します。 選定されると、アクティビティにエントリし、向けに設計されたエクスペリエンスを確認します。 単一のアクティビティ内で、複数のオーディエンスに対してエクスペリエンスを作成できます。

詳しくは、[エクスペリエンスのターゲット設定](/help/main/c-activities/t-experience-target/experience-target.md#task_A53DF336CB9F4D7BB87EF2106099EFC4)を参照してください。

### [!UICONTROL Multivariate Test] （MVT）

[!UICONTROL Multivariate Testing] （MVT）はページ要素内のオファーの組み合わせを比較し、特定のオーディエンスに対して最も効果が高い組み合わせを特定します。 MVT は、アクティビティの成功に最も影響を与える要素を特定するのに役立ちます。

詳しくは、[多変量分析テスト](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md#concept_628695CDC71B449B8DCC2F5654C11499)を参照してください。

### [!UICONTROL Recommendations]

[!UICONTROL Recommendations] のアクティビティは、以前のアクティビティやその他のアルゴリズムを基にして、顧客が興味を持つ可能性のある製品やコンテンツを自動的に表示します。 Recommendations により、顧客が関心を持つ商品を積極的に紹介することが可能になります。

詳細については、[Recommendations](/help/main/c-recommendations/recommendations.md#concept_7556C8A4543942F2A77B13A29339C0C0) を参照してください。

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

「Edge」は、コンテンツをリクエストする訪問者の場所に関係なく、最適な応答時間を確保する、地理的に分散された配信アーキテクチャです。

応答時間を改善するために、[!DNL Target] Edge はアクティビティロジック、キャッシュされたプロファイル、およびオファー情報のみをホストします。

アクティビティおよびコンテンツのデータベース、[!DNL Analytics] データ、API およびマーケター向けのユーザーインターフェイスは、[!DNL Adobe] 中央クラスターに格納されます。 アップデートは [!DNL Target] Edge に送信され、中央クラスターと自動的に同期されて、キャッシュされたアクティビティデータが継続的に更新されます。 また、すべての 1:1 モデリングが各エッジに保存されるので、複雑なリクエストをローカルで処理できます。

各Edge クラスターには、訪問者のコンテンツリクエストに対応し、分析データを追跡するために必要なすべての情報が含まれています。 訪問者のリクエストは、最寄りのエッジクラスターに転送されます。

詳しくは、『[Adobe Target セキュリティの概要](https://www.adobe.com/content/dam/cc/en/security/pdfs/AdobeTargetSecurityOverview.pdf)』ホワイトペーパーを参照してください。

[!DNL Target] は、世界中のAdobeが所有するデータセンターおよびAdobeがリース契約を結んでいるデータセンターでホストされています。

中央クラスターの場所には、データ収集センターとデータ処理センターの両方が格納されています。 Edge クラスターの場所には、データ収集センターのみが含まれています。 個々のレポートスイートは特定のデータ処理センターに割り当てられています。

お客様のサイトのアクティビティデータは、最も近い 7 つのEdge クラスターによって収集されます。 その後、このデータは、事前に決定された中央クラスター（オレゴン、ダブリンまたはシンガポール）に送られ、処理されます。 訪問者プロファイルデータは、サイト訪問者に最も近いエッジクラスターに保存されます。Edgeクラスター拠点には、中央クラスター拠点のほか、バージニア、ムンバイ、シドニー、東京が含まれます。

すべてのターゲティングリクエストを 1 か所で処理する代わりに、訪問者に最も近いEdge クラスターでリクエストを処理します。 このアプローチは、ネットワークとインターネットの移動時間の影響を軽減します。

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
>現在、[!DNL Target] には中国にEdge クラスターがないため、同地域の [!DNL Target] のお客様は訪問者パフォーマンスに制限を感じています。 ファイアウォールが存在せず、Edge クラスターが存在しない場合は、サイトエクスペリエンスに影響を与え、レンダリングやページの読み込み時間が遅くなる可能性があります。 また、マーケターが、[!DNL Target] オーサリング UI を使用する際に遅延が発生することがあります。

必要に応じて、[!DNL Target] のエッジクラスターを許可リストに追加できます。詳しくは、[Target のエッジノードを許可リストに登録する](https://experienceleague.adobe.com/ja/docs/target-dev/developer/implementation/privacy/allowlist-edges){target=_blank}を参照してください。

## ユーザーエクスペリエンスの保護 {#concept_40A5E781D90A41E4955F80EA9E5F8F96}

[!DNL Adobe] は、ターゲット設定インフラストラクチャの可用性とパフォーマンスの可能な限りの安定を確保しています。 ただし、訪問者のブラウザーと [!DNL Adobe] サーバー間の通信が切断されると、コンテンツ配信が中断される可能性があります。

サービスの中断や接続の問題を防ぐために、すべての場所は、デフォルトコンテンツ（クライアントが定義）を含めるように設定されています。このデフォルトコンテンツは、訪問者のブラウザーが [!DNL Target] に接続できない場合に表示されます。

訪問者のブラウザーが、定義されたタイムアウト期間（デフォルト：15 秒）以内に接続できない場合は、ページは変更されません。 このタイムアウトのしきい値に達した場合、デフォルトの場所のコンテンツが表示されます。

[!DNL Adobe] は、パフォーマンスを最適化し、安全性を保つことで、ユーザーエクスペリエンスを保護します。

* [!DNL Adobe] は、[!UICONTROL Adobe Service Level Agreement] が保証する業界標準に基づくパフォーマンスベンチマークを保証します。
* エッジネットワークによって、タイムリーなデータ配信を実現しています。
* [!UICONTROL Adobe] では、アプリケーションを保護するための多層型アプローチを採用し、お客様に対して最高レベルの可用性と信頼性を提供しています。
* [!DNL Target] コンサルティングは、導入支援と継続的な製品サポートを行っています。

## 検索エンジン最適化（SEO）対応テスト {#concept_C0C865663CAB4251B66A1F250FD25E6A}

[!DNL Adobe Target] はテストのための検索エンジンガイドラインに従っています。 [!DNL Google] は、ユーザーのテストを推奨し、特定のガイドラインに従っている場合は、A/B および [!UICONTROL Multivariate Testing] がオーガニック検索エンジンのランキングに悪影響を与えないことを宣言します。

[!DNL Adobe Target] はテストのための検索エンジンガイドラインに従っています。

詳しくは、次の Google のリソースを参照してください。

* [ウェブテストが Google 検索に与える影響](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html)
* [ウェブテストとクローキング](https://support.google.com/analytics/answer/12979939?hl)


ガイドラインは[Google ウェブマスター向け公式ブログ](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html)の投稿として公表されています。この投稿は 2012 年のものですが、この問題に関する [!DNL Google] の最新の発言であり、ガイドラインはまだ関連性があります。

* **クロークなし**：クロークでは、ユーザーに対して一連のコンテンツを表示し、ボットを特別に識別して異なるコンテンツをフィードすることで、検索エンジンボットに異なるコンテンツを表示します。

  [!DNL Target] は、検索エンジンボットを他のユーザーと同様に扱うよう設定されています。 その結果、ボットがランダムに選択され、テストのバリエーションを「確認」した場合、アクティビティに含めることができます。

* **rel=&quot;canonical&quot;を使用する**：バリエーションを付けるために、A/B テストに異なる URL が必要な場合があります。 この場合、元の（コントロール） URL を参照する rel=&quot;canonical&quot; タグをすべてのバリエーションに含める必要があります。 例え [!DNL Adobe]、各バリエーションに異なる URL を持つホームページをテストする場合、ホームページの次の正規タグを各バリエーションの `<head>` タグに配置する必要があります。

  `<link rel="canonical" href="https://www.adobe.com" />`

* **302 （一時的な）リダイレクトを使う**：テストでバリエーションのページに異なる URL を使用する場合、302 リダイレクトを使用してトラフィックを直接テストバリエーションにリダイレクトすることを [!DNL Google] 勧めします。 302 リダイレクトは、リダイレクトが一時的で、テストの実行中にのみアクティブになることを検索エンジンに通知します。

  302 リダイレクトはサーバーサイドのリダイレクトですが、[!DNL Target] とんどの最適化プロバイダーはクライアントサイドの機能を使用しています。 したがって、[!DNL Target] は、リダイレクトに関する [!DNL Google] の推奨事項に完全に準拠していません。 ただし、影響を受けるのはテストのごく一部に限られます。 [!DNL Target] でテストを実行するための標準的なアプローチでは、1 つの URL 内でコンテンツを変更するので、リダイレクトの必要がなくなります。 テストバリエーションに複数の URL が必要な場合、[!DNL Target] はJavaScript `window.location` コマンドを使用します。リダイレクトが 301 か 302 かを示すものではありません。

  [!DNL Adobe] は、検索エンジンガイドラインに完全に準拠するソリューションを積極的に探しています。 テスト用に別々の URL を必要とするクライアントの場合、[!DNL Adobe] では、正規タグを正しく実装することで、関連するリスクを軽減できると考えています。

* **実験を必要な期間のみ実行**:[!DNL Adobe] では、「必要な期間」を統計的有意性に到達するために必要な時間として定義します。 [!DNL Target] には、テストがこの時点に到達したかどうかを判断するためのベストプラクティスと [!DNL Adobe Target] [ サンプルサイズ計算ツール ](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6) が用意されています。 [!DNL Adobe] では、勝者テストのハードコード実装をテストワークフローに組み込み、適切なリソースを割り当てることをお勧めします。

  [!DNL Target] を使用して勝者テストを「公開」することは、恒久的なソリューションとしては推奨されません。 勝者テストが常に 100% のユーザーに対して公開されている場合、このアプローチを一時的に使用して、勝者テストをハードコーディングできます。

  テストが変更した点を考慮します。 ボタンの色などの小規模な更新も、オーガニックのランキングには影響しません。 ただし、テキストの変更はハードコードする必要があります。

  また、テストするページのアクセシビリティも考慮してください。 検索エンジンからアクセスできず、オーガニック検索でランク付けすることを意図していないページの場合、これらの考慮事項は適用されません。 例えば、メールキャンペーン専用のランディングページがあります。

Google によると、これらのガイドラインに従えば、「テストがサイトの検索結果に及ぼす影響はほとんどあるいはまったくない。」とのことです。

これらのガイドラインに加えて、Google はまた、Content Experiments ツールのドキュメンテーションでもう 1 つのガイドラインを提供しています。

* 「バリエーションの各ページは、元来のページ内容の主旨を保持する必要があります。こういったバリエーションは、元来の内容に対しユーザーが持つ全般的イメージを変えてはいけません。」

Google は例として、「ユーザーに表示される組み合わせに関連しないキーワードでサイトの元来のページが読み込まれる場合、そのサイトを Google のインデックスから外すことがあります」と記述しています。

テストのバリエーション内 [!UICONTROL Adobe] 意図せず元のコンテンツの意味を変更するのは難しいと感じています。 [!UICONTROL Adobe] だし、ページのキーワードテーマに注意して、それらのテーマを維持することをお勧めします。 ページ内容を変更、特に関連のあるキーワードを追加したり削除したりすると、オーガニック検索でのその URL のランキングが変わってしまう場合があります。[!DNL Adobe] では、テストプロセスの一環として、SEO パートナーに協力を仰ぐことをお勧めします。

## ボット {#bots}

[!DNL Target] は、[DeviceAtlas](https://deviceatlas.com/device-data/user-agent-tester/) 指標「isRobot」を使用し、リクエストヘッダーで渡されたユーザーエージェント文字列に基づいて既知のボットを検出します。

>[!NOTE]
>
> [!DNL Server-Side] リクエストの場合、[リクエストの「コンテキスト」ノード](https://developers.adobetarget.com/api/delivery-api/#tag/Delivery-API)に渡された値は、ボット検出用のユーザーエージェント文字列よりも優先されます。

ボット生成と識別されたトラフィックには、引き続きコンテンツが提供されます。 ボットは通常のユーザーと同様に扱われ、[!DNL Target] が SEO ガイドラインに従っていることを確認します。 ただし、ボットトラフィックは、通常のユーザーのように扱われると、A/B テストやパーソナライゼーションアルゴリズムをゆがめる可能性があります。 したがって、[!DNL Target] アクティビティにおける既知のボットトラフィックの扱いは異なります。 ボットトラフィックを削除すると、ユーザーアクティビティをより正確に測定できます。

既知のボットトラフィックの場合、[!DNL Target] は次を行いません。

* 訪問者プロファイルの作成または取得
* プロファイル属性のログまたはプロファイルスクリプトの実行
* [!DNL Adobe Audience Manager]（AAM）セグメントの検索（該当する場合）
* [!UICONTROL Recommendations]、[!UICONTROL Auto-Target]、[!UICONTROL Automated Personalization]、[!UICONTROL Auto-Allocate] の各アクティビティにおけるパーソナライズされたコンテンツのモデリングまたは提供時のボットトラフィックの使用
* レポート用のアクティビティ訪問の記録
* [!DNL Adobe Experience Cloud] プラットフォームに送信されたログデータ

既知のボットトラフィックの場合、[!UICONTROL Analytics for Target] （A4T）を使用すると、[!DNL Target] は次を実行しません。

* [!DNL Analytics] にイベントを送信

既知のボットトラフィックに `client_side` ログを使用する場合は、[!DNL Target] は次を返しません。

* `tnta payload`
