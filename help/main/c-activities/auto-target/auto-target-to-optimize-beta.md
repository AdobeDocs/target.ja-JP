---
keywords: 自動ターゲット;ターゲティング;トラフィック配分;よくある質問;faq;トラブルシューティング
description: '[!UICONTROL Auto-Target] アクティビティが、顧客プロファイルと類似の訪問者の行動に基づいて、各訪問者に最適なエクスペリエンスをどのように提供するかを説明します。'
title: '[!UICONTROL Auto-Target] アクティビティとは'
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Auto-Target
hide: true
hidefromtoc: true
exl-id: 3e55e032-3a70-4023-b705-2e489aa60277
source-git-commit: 5846e567cffda70ecd75f2975b0891f9a3f423a5
workflow-type: tm+mt
source-wordcount: '1828'
ht-degree: 39%

---

# [!UICONTROL Auto-Target] の概要

[!DNL Adobe Target] の [!UICONTROL Auto-Target] アクティビティでは、高度な機械学習を使用して、パフォーマンスが高くマーケターが定義した複数のエクスペリエンスから選択して、コンテンツをパーソナライズし、コンバージョンを促進します。 [!UICONTROL Auto-Target] は、個々の顧客プロファイルと類似のプロファイルを持つ以前の訪問者の行動に基づいて、各訪問者に最適なエクスペリエンスを提供します。

>[!NOTE]
>
>* [!UICONTROL Auto-Target] は、[!DNL Target Premium] ソリューションの一部として利用できます。 この機能は、[!DNL Target Premium] ライセンスのない [!DNL Target Standard] では使用できません。このライセンスで提供される高度な機能について詳しくは、[Target Premium](/help/main/c-intro/intro.md) を参照してください。
>
>* [!UICONTROL Analytics for Target] （A4T）は、[!UICONTROL Auto-Target] アクティビティをサポートします。 詳しくは、[A4T での自動配分および自動ターゲットアクティビティのサポート](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md)を参照してください。

## 自動ターゲットを使用した実際のユーザー事例 {#success}

ある大手衣料品小売業者は最近、10 個の製品カテゴリベースのエクスペリエンス（およびランダム化されたコントロール）を含む [!UICONTROL Auto-Target] アクティビティを使用して、各訪問者に適切なコンテンツを配信しました。 「[!UICONTROL Add to Cart]」がプライマリ最適化指標として選択されました。 ターゲットエクスペリエンスの平均上昇率は 29.09％でした。[!UICONTROL Auto-Target] モデルを作成した後、アクティビティは 90% のパーソナライズされたエクスペリエンスに設定されました。

わずか 10 日で、1,700,000 ドル以上の上昇率を達成しました。

[!UICONTROL Auto-Target] を使用して組織の上昇率と売上高を増やす方法については、読み続けてください。

## 概要 {#section_972257739A2648AFA7E7556B693079C9}

[A/B アクティビティの作成 ](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)3 ステップのガイド付きワークフローの使用中に、**[!UICONTROL Targeting]** ページで「**[!UICONTROL Auto-Target for personalized experiences]**」オプションを選択します（手順 2）。

![ トラフィック配分方法の設定 ](/help/main/c-activities/automated-traffic-allocation/assets/auto-target.png)

A/B アクティビティフローの [!UICONTROL Auto-Target] オプションを使用すると、マーケターが定義した一連のエクスペリエンスに基づいて、ワンクリックで機械学習を活用してパーソナライズできます。 [!UICONTROL Auto-Target] は、従来の A/B テストや [!UICONTROL Auto Allocate] と比較して、各訪問者に表示するエクスペリエンスを決定することで、最大限の最適化を実現するように設計されています。 単一の勝者を見つけることを目的とする A/B アクティビティとは異なり、[!UICONTROL Auto-Target] は特定の訪問者に最適なエクスペリエンスを自動的に決定します。 最適なエクスペリエンスは、訪問者のプロファイルやその他のコンテキスト情報に基づいて、高度にパーソナライズされたエクスペリエンスを提供します。

[!UICONTROL Automated Personalization] と同様に、[!UICONTROL Auto-Target] は先進のデータサイエンスアンサンブル手法である [ ランダムフォレストアルゴリズム ](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) を使用して、訪問者に表示する最適なエクスペリエンスを決定します。 訪問者の行動の変化に適応で [!UICONTROL Auto-Target] るので、上昇率を提供するために永続的に実行できます。 この方法は、「常時稼動」モードと呼ばれることがあります。

特定の訪問者のエクスペリエンスの割り当てが固定される A/B アクティビティとは異なり、[!UICONTROL Auto-Target] では、各訪問で指定されたビジネス目標が最適化されます。 [!UICONTROL Auto Personalization] と同様に、[!UICONTROL Auto-Target] はデフォルトで、アクティビティのトラフィックの一部をコントロール母集団として予約して、上昇率を測定します。 コントロールグループの訪問者には、アクティビティのランダムエクスペリエンスが配信されます。

## 注意点

[!UICONTROL Auto-Target] を使用する際は、次の点に注意してください。

* 特定のアクティビティを [!UICONTROL Auto-Target] から [!UICONTROL Automated Personalization] に切り替えることはできません。逆も同様です。
* アクティビティ [!UICONTROL Manual] ドラフトとして保存した後で、トラフィックの割り当て（従来の [!UICONTROL A/B Test]）から [!UICONTROL Auto-Target] に切り替えることはできません。逆も同様です。
* 1 つのモデルは、パーソナライズされた戦略とランダムに提供されたトラフィックのパフォーマンスを識別し、すべてのトラフィックを勝者エクスペリエンス全体に送信するように構築されています。 このモデルでは、ヒットとコンバージョンはデフォルト環境でのみ考慮されます。

  2 番目のモデルセットからのトラフィックは、モデリンググループ（AP）またはエクスペリエンス（AT）ごとに作成されます。これらのモデルごとに、すべての環境にわたるヒットおよびコンバージョンが考慮されます。

  リクエストは、環境に関係なく、同じモデルで提供されます。 ただし、識別された全体的な勝者エクスペリエンスが実際の行動と一致していることを確認するために、複数のトラフィックはデフォルト環境から取得する必要があります。

* 2 つ以上のエクスペリエンスを使用します。

## 用語 {#section_A309B7E0B258467789A5CACDC1D923F3}

[!UICONTROL Auto-Target] について説明する際には、次の用語が役立ちます。

| 用語 | 定義 |
|---|---|
| [マルチアームバンディット](https://en.wikipedia.org/wiki/Multi-armed_bandit){target=_blank} | マルチアームバンディット最適化アプローチでは、調査学習とその学習の活用のバランスを取ります。 |
| [ランダムフォレスト](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) | ランダムフォレストは、有力な機械学習アプローチです。データサイエンス分野では、訪問者と訪問の属性に基づいて多数の決定ツリーを作成することで機能するアンサンブル分類または回帰手法を指します。[!DNL Target] 内部では、ランダムフォレストを使用して、コンバージョンの可能性が最も高い（または訪問あたりの売上高が最も高い）と予想されるエクスペリエンスを特定の訪問者ごとに決定します。 |
| [トンプソンサンプリング](https://en.wikipedia.org/wiki/Thompson_sampling){target=_blank} | トンプソンサンプリングの目的は、全体的に最良の（パーソナライズされていない）エクスペリエンスを最小限の「コスト」で特定することです。トンプソンサンプリングでは、2 つのエクスペリエンスに統計的な差異がない場合でも、必ず勝者が選定されます。 |

## [!UICONTROL Auto-Target] の仕組み {#section_77240E2DEB7D4CD89F52BE0A85E20136}

[!UICONTROL Auto-Target] と [!UICONTROL Automated Personalization] の基礎となるデータとアルゴリズムについて詳しくは、以下のリンクを参照してください。

| 用語 | 詳細 |
|--- |--- |
| [ランダムフォレストアルゴリズム](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) | [!UICONTROL Auto-Target] と [!UICONTROL Automated Personalization] の両方で使用される [!DNL Target] の主なパーソナライゼーションアルゴリズムは、ランダムフォレストです。 ランダムフォレストなどのアンサンブル手法では、複数の学習アルゴリズムを使用して、構成学習アルゴリズムのいずれかから得られるよりも優れた予測パフォーマンスを得ます。 [!UICONTROL Automated Personalization] および [!UICONTROL Auto-Target] アクティビティのランダムフォレストアルゴリズムは、トレーニング時に多数のデシジョンツリーを構築することで機能する分類または回帰方法です。 |
| [ のPersonalization アルゴリズム  [!DNL Target] データのアップロード ](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) | [!UICONTROL Auto-Target] モデルと [!UICONTROL Automated Personalization] モデルのデータを入力する方法はいくつかあります。 |
| [ のPersonalization アルゴリズム  [!DNL Target] データ収集 ](/help/main/c-activities/t-automated-personalization/ap-data.md) | [!DNL Target] のパーソナライゼーションアルゴリズムは、さまざまなデータを自動的に収集します。 |

## トラフィック配分の決定 {#section_AB3656F71D2D4C67A55A24B38092958F}

アクティビティの目標に合わせて、様々な方法でコントロールとパーソナライズされたエクスペリエンスにトラフィックを配分できます。アクティビティをライブにする前に、アクティビティの目標を決めておくことをお勧めします。

「[!UICONTROL Custom Allocation]」ドロップダウンリストを使用すると、次のオプションから選択できます。

* [!UICONTROL Evaluate Personalization Algorithm (50/50)]
* [!UICONTROL Maximize Personalization Traffic (90/10)]
* [!UICONTROL Custom Allocation]

![配分目標ドロップダウンリスト](/help/main/c-activities/assets/split-new-ui.png)

次の表では、3 つのオプションについて説明します。

| アクティビティの目標 | 推奨のトラフィック配分 | メリットとデメリット |
|--- |--- |--- |
| **[!UICONTROL Evaluate Personalization Algorithm (50/50)]**：アルゴリズムのテストが目標の場合は、コントロールとターゲットアルゴリズムの間で訪問者を 50/50% 分割して使用します。 この配分により、上昇率を最も正確に推定できます。「ランダムエクスペリエンス」をコントロールとして使用する場合にお勧めします。 | 配分はコントロールエクスペリエンスに 50％、パーソナライズされたエクスペリエンスに 50％ | <ul><li>コントロールと比較した場合のパーソナライゼーションの上昇率の精度を最大化できます。</li><li>エクスペリエンスがパーソナライズされる訪問者は比較的少数です。</li></ul> |
| **[!UICONTROL Maximize Personalization Traffic (90/10)]**: 「常時稼動」アクティビティを作成することが目標の場合は、訪問者の 10% をコントロールに配置して、アルゴリズムが時間の経過と共に学習を継続するのに十分なデータがあることを確認します。 ここでのトレードオフは、トラフィックの大部分をパーソナライズする代わりに、正確な上昇率が何であるかについての精度が低くなることです。 これは、目標にかかわらず、特定のエクスペリエンスをコントロールとして使用する場合のお勧めのトラフィック分割です。 | 最適な配分はコントロールエクスペリエンスに 10％から 30％、パーソナライズされたエクスペリエンスに 70％から 90％ | <ul><li>エクスペリエンスをパーソナライズされた訪問者の数を最大化します</li><li>上昇率を最大化できます。</li><li>アクティビティの上昇率の精度が落ちます。</li></ul> |
| **カスタム配分** | 配分の割合を手動で調節します。 | <ul><li>想定どおりの結果が得られない場合もあります。目安がわからない場合は、上述のいずれかのオプションを使用することをお勧めします。</li></ul> |

[!UICONTROL Control] の割合を調整するには、[!UICONTROL Traffic Allocation] のウィンドウ領域の [!UICONTROL Experiences] をクリックし、必要に応じて割合を調整します。 コントロールグループの割合を 10％未満にすることはできません。

[特定のエクスペリエンスを選択してコントロールとして使用](/help/main/c-activities/t-automated-personalization/experience-as-control.md)したり、ランダムエクスペリエンスオプションを使用したりできます。

## あなたはいつ [!UICONTROL Auto-Target] を [!UICONTROL Automated Personalization] より選ぶべきですか？{#section_BBC4871C87944DD7A8B925811A30C633}

[!UICONTROL Automated Personalization] よりも [!UICONTROL Auto-Target] を使用する場合は、いくつかのシナリオがあります。

* 自動的に組み合わされてエクスペリエンスを形成する個々のオファーではなく、エクスペリエンス全体を定義する場合。
* [!UICONTROL Auto Personalization] でサポートされていない [!UICONTROL Visual Experience Composer] （VEC）機能の完全なセット（カスタムコードエディター、複数のエクスペリエンスオーディエンスなど）を使用する場合。
* 様々なエクスペリエンスでページに構造的な変更を加えたい場合。例えば、ホームページの要素の順序を変更する場合、[!UICONTROL Automated Personalization] よりも [!UICONTROL Auto-Target] を使用する方が適切です。

## [!UICONTROL Auto-Target] と [!UICONTROL Automated Personalization] の共通点は何ですか？{#section_2A601F482F9A44E38D4B694668711319}

### 訪問ごとに好ましい結果を得るためにアルゴリズムが最適化されます。

* アルゴリズムが訪問者のコンバージョン傾向（またはコンバージョンによる推定売上高）を予測して、最適なエクスペリエンスを提供します。
* 訪問者は、既存のセッションの終了時に新しいエクスペリエンスに対して適格となります（訪問者がコントロール母集団に属している場合を除き、この場合、最初の訪問に割り当てられたエクスペリエンスは後続の訪問でも同じままです）。
* セッション内では、ビジュアルの一貫性を保つために、予測は変わりません。

### 訪問者の行動の変化にアルゴリズムが対応します。

* マルチアームバンディットでは、モデルは常にトラフィックのごく一部を「消費」して、アクティビティ学習の全期間を通じて学習を継続し、それまでに学習したトレンドの乱用を防止します。
* 基盤となるモデルは、最新の訪問者行動データを使用して 24 時間ごとに再構築され、変化する訪問者の好みを [!DNL Target] が常に利用できるようになっています。
* 個人の勝者エクスペリエンスをアルゴリズムで特定できなかった場合は、パフォーマンスが全体として最も高いエクスペリエンスを表示する方式に自動的に切り替わりますが、パーソナライズされた勝者の特定は続行されます。最もパフォーマンスが高いエクスペリエンスは、[トンプソンサンプリング](https://en.wikipedia.org/wiki/Thompson_sampling)によって割り出されます。

### 単一の目標指標に合わせて、アルゴリズムが絶えず最適化されます。

* この指標は、コンバージョンベースまたは収益ベース（より具体的には [!UICONTROL Revenue per Visit]）の場合があります。

### [!DNL Target] では、訪問者に関する情報を自動的に収集して、パーソナライゼーションモデルを構築します。

* [!UICONTROL Auto-Target] および [!UICONTROL Automated Personalization] で使用されるパラメーターについて詳しくは、[Automated Personalization Data Collection](/help/main/c-activities/t-automated-personalization/ap-data.md) を参照してください。

### [!DNL Target] では、[!DNL Adobe Experience Cloud] のすべての共有オーディエンスを自動的に使用して、パーソナライゼーションモデルを構築します。

* オーディエンスをモデルに追加するために、特別な作業を行う必要はありません。[!DNL Experience Cloud Audiences] と [!DNL Target] を併用する方法について詳しくは、「[Experience Cloud オーディエンス](/help/main/c-integrating-target-with-mac/mmp.md)」を参照してください。

### マーケターは、オフラインデータや傾向スコアなどのカスタムデータをアップロードして、パーソナライゼーションモデルを構築することができます。

* 詳しくは、[[!UICONTROL Auto-Target] および [!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md) 用のデータのアップロードを参照してください。

## [!UICONTROL Auto-Target] と [!UICONTROL Automated Personalization] の違い{#section_BA4D83BE40F14A96BE7CBC7C7CF2A8FB}

### 通常、パーソナライズされたモデルの作成に必要なトラフィックの量は、[!UICONTROL Automated Personalization] よりも [!UICONTROL Auto-Target] のほうが少なくなります。

[!UICONTROL Auto-Target] または [!UICONTROL Auto Personalization] のモデルが構築するために必要なトラフィックの量 *エクスペリエンスあたり* は同じですが、通常、[!UICONTROL Automated Personalization] アクティビティの方が [!UICONTROL Auto-Target] アクティビティよりも多くのエクスペリエンスがあります。

例えば、[!UICONTROL Auto Personalization] アクティビティで、場所ごとに 2 つのオファーを 2 つの場所で作成した場合、アクティビティには合計 4 つのエクスペリエンス（2 = 4）が含まれます（除外なし）。 [!UICONTROL Auto-Target] を使用すると、オファー 1 を場所 1 に、オファー 2 を場所 2 に含めるようにエクスペリエンス 1 を設定し、オファー 1 を場所 1 に、オファー 2 を場所 2 に含めるようにエクスペリエンス 2 を設定できます。 [!UICONTROL Auto-Target] では 1 つのエクスペリエンス内で複数の変更を選択できるので、アクティビティ内の合計エクスペリエンス数を減らすことができます。

[!UICONTROL Auto-Target] しくは、トラフィック要件を理解するための簡単な経験則を使用できます。

* **成功指標が [!UICONTROL Conversion] の場合：エクスペリエンスあたり 1,000 回の訪問と 1 日あたりの少なくとも 50 コンバージョン。さらに、アクティビティには少なくとも 7,000 回の訪問と 350 回のコンバージョンが必要です。**
* **成功指標が [!UICONTROL Revenue per Visit] の場合：エクスペリエンスあたり 1,000 回の訪問と 1 日あたり少なくとも 50 回のコンバージョン。さらに、アクティビティにはエクスペリエンスあたり少なくとも 1,000 回のコンバージョンが必要です**。 訪問あたりの売上高の方が、通常、モデルの構築に多くのデータが必要になります。これは、コンバージョン率と比べて、訪問あたりの売上高の方が一般にデータ分散が大きいことが原因です。

### [!UICONTROL Auto-Target] には本格的なセットアップ機能があります。

* [!UICONTROL Auto-Target] は A/B アクティビティワークフローに埋め込まれ [!UICONTROL Auto-Target] ので、より成熟した本格的な [!UICONTROL Visual Experience Composer] （VEC）のメリットが得られます。 [!UICONTROL Auto-Target] で [QA リンク ](/help/main/c-activities/c-activity-qa/activity-qa.md) を使用することもできます。

### [!UICONTROL Auto-Target] は、広範なオンラインテストフレームワークを提供します。

* マルチアームバンディットは、[!DNL Adobe] のデータサイエンティストや研究者が現実の状況における継続的な改善のメリットを把握できるようにする、より大規模なオンラインテストフレームワークの一部となっています。
* 将来的には、このテストベッドにより、データに詳しいクライアントに [!DNL Adobe] の機械学習プラットフォームを開くことができ、[!DNL Target] しいモデルを強化するために独自のモデルを取り込むことができます。

## レポートと [!UICONTROL Auto-Target] {#section_42EE7F5E65E84F89A872FE9921917F76}

詳しくは、[レポートと自動ターゲット](/help/main/c-activities/auto-target/reporting-and-auto-target.md)を参照してください。
