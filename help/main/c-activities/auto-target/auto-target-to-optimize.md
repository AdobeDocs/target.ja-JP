---
keywords: 自動ターゲット;ターゲティング;トラフィック配分;よくある質問;faq;トラブルシューティング
description: '[!UICONTROL 自動ターゲット]アクティビティが顧客プロファイルや類似する訪問者の行動に基づいて、各訪問者に最適なエクスペリエンスを提供する仕組みを説明します。'
title: '[!UICONTROL 自動ターゲット]アクティビティとは'
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Auto-Target
exl-id: 59ca30dc-45a0-4129-b832-84e1132d3b69
TQID: 'https://experienceleague.adobe.com/uKmfIlOcT-tZgOjuvERXuif-Y5-2Jw3prtPbuBjv1is'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: fff07a91-d479-45f4-ae95-9762e79b1b7c
    internal-label: Shared audiences
  - id: db15a02f-03cd-46fe-a53e-02064cdeadfa
    internal-label: Auto target
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
    internal-label: Machine learning
  - id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
    internal-label: Customer profiles
source-git-commit: de439134b0ee5aa795ae255bba852b9b6f10da12
workflow-type: tm+mt
source-wordcount: '2072'
ht-degree: 40%
---
# [!UICONTROL 自動ターゲット ]の基本を学ぶ {#auto-target-overview}

>[!BEGINSHADEBOX]

**このページ：**&#x200B;では、**[!UICONTROL 自動ターゲット]** アクティビティが、各訪問者に最もカスタマイズされたエクスペリエンスをどのように提供するか、どのように機能するか、トラフィック配分の選択方法、**[!UICONTROL Automated Personalization]**&#x200B;との比較について説明します。

>[!ENDSHADEBOX]

[!DNL Adobe Target] の&#x200B;**[!UICONTROL 自動ターゲット]**&#x200B;アクティビティは、高度な機械学習を活用して、マーケターが定義した複数の高パフォーマンスエクスペリエンスから選択し、コンテンツのパーソナライズとコンバージョンの促進を行います。 **[!UICONTROL 自動ターゲット]**&#x200B;は、個々の顧客プロファイルや同様のプロファイルを持つ過去の訪問者の行動に基づいて、各訪問者に合わせた最適なエクスペリエンスを提供します。

>[!NOTE]
>
>* **[!UICONTROL 自動ターゲット]**&#x200B;は、この [!DNL Target Premium] ソリューションの一部として使用できます。 この機能は、[!DNL Target Premium] ライセンスのない [!DNL Target Standard] では使用できません。 このライセンスで提供される高度な機能について詳しくは、[Target Premium](/help/main/c-intro/intro.md) を参照してください。
>
>* **[!UICONTROL Analytics for Target]**（A4T）は、**[!UICONTROL 自動ターゲット]**&#x200B;アクティビティをサポートします。 詳しくは、[A4T での自動割り当ておよび自動ターゲットアクティビティのサポート](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md)を参照してください。

3段階のガイド付きワークフローを使用してA/B アクティビティ ](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)を[作成する場合、**[!UICONTROL ターゲティング]** ページで&#x200B;**[!UICONTROL 自動ターゲティング]** オプションを選択します（ステップ 2）。 手順については、[自動ターゲットアクティビティの作成](/help/main/c-activities/auto-target/create-auto-target.md)を参照してください。

![トラフィック配分方法の設定](/help/main/c-activities/automated-traffic-allocation/assets/auto-target.png)

A/B アクティビティフロー内のこのオプションでは、マシンラーニングを利用して、マーケターが定義した一連のエクスペリエンスに基づいて、ワンクリックでコンテンツをパーソナライズできます。 **[!UICONTROL 自動ターゲット]**&#x200B;は、訪問者ごとに表示するエクスペリエンスを決定することで、従来のA/B テストや&#x200B;**[!UICONTROL 自動割り当て]**&#x200B;と比較して、最大限の最適化を実現するように設計されています。 1人の勝者を見つけることが目的のA/B アクティビティとは異なり、**[!UICONTROL 自動ターゲット]**&#x200B;は、特定の訪問者に対して最適なエクスペリエンスを自動的に決定します。 最適なエクスペリエンスは、訪問者のプロファイルやその他のコンテキスト情報にもとづいています。

**[!UICONTROL Automated Personalization]** と同じように、**[!UICONTROL 自動ターゲット]**&#x200B;では先進のデータサイエンスアンサンブル手法である[ランダムフォレストアルゴリズム](/help/main/c-activities/t-automated-personalization/algo-random-forest.md)を使用して、訪問者に表示する最適なエクスペリエンスを決定します。 **[!UICONTROL 自動ターゲット]**&#x200B;は、訪問者の行動の変化に適応できるため、永続的に実行して上昇率を提供できます。 この手法は、「常時稼働」モードとも呼ばれます。

特定の訪問者に対するエクスペリエンスの割り当てが固定されるA/B アクティビティとは異なり、**[!UICONTROL 自動ターゲット]**&#x200B;は、各訪問に対して指定されたビジネス目標を最適化します。 **[!UICONTROL Automated Personalization]**&#x200B;と同様、**[!UICONTROL 自動ターゲット]**&#x200B;は、デフォルトでアクティビティトラフィックの一部をコントロールグループとして予約し、上昇率を測定します。 コントロールグループの訪問者には、アクティビティのランダムエクスペリエンスが配信されます。

## 注意点 {#considerations}

**[!UICONTROL 自動ターゲット]**&#x200B;を使用する場合は、次の点に注意してください。

* アクティビティの形状に注意を払う。 パフォーマンスは、未加工のエクスペリエンス数よりも × オファーの数に左右されます。 大きなデカルトの組み合わせでは、ドキュメントに記載されているエクスペリエンス制限を下回る場合でも、**[!UICONTROL Visual Experience Composer]**&#x200B;の読み込みや編集が遅くなる可能性があります。

  ベストプラクティスとして、1 か所あたり 4～6 件のオファーを含む&#x200B;**[!UICONTROL 自動ターゲット]**&#x200B;および **[!UICONTROL Automated Personalization]** のアクティビティを 4～6 か所に保存します。 大きな設定は推奨されません。 これらのアクティビティは&#x200B;**[!UICONTROL エクスペリエンス]** ステップで直接構築されるので、[!DNL Target] UIでは、設定がサポートされているしきい値を超えると、インライン警告またはブロック保存が表示される場合があります。

* 特定のアクティビティを&#x200B;**[!UICONTROL 自動ターゲット]**&#x200B;から&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;またはその逆に切り替えることはできません。
* アクティビティをドラフトとして保存した後、トラフィックの割り当て（従来の&#x200B;**[!UICONTROL A/B テスト]**）を&#x200B;**[!UICONTROL 自動ターゲット]**、またはその逆に&#x200B;**[!UICONTROL 手動]**&#x200B;から切り替えることはできません。
* 1 つのモデルを使用して、パーソナライズされた戦略、ランダムに提供されるトラフィック、そしてすべてのトラフィックを勝者エクスペリエンス全体に送信する場合のパフォーマンスを比較します。 このモデルでは、ヒットとコンバージョンはデフォルト環境でのみ考慮されます。

  2つ目のモデリングセットは、各モデリンググループ（AP）またはエクスペリエンス（AT）に対して構築されます。 これらのモデルごとに、すべての環境にわたるヒットおよびコンバージョンが考慮されます。

  リクエストは、環境に関係なく、同じモデルで提供されます。 ただし、特定された総合的な勝者エクスペリエンスが実際の行動と一致するように、大多数のトラフィックをデフォルト環境から提供する必要があります。

* 2 つ以上のエクスペリエンスを使用します。

## 用語 {#section_A309B7E0B258467789A5CACDC1D923F3}

**[!UICONTROL 自動ターゲット]**&#x200B;の重要な用語を次に示します。

| 用語 | 定義 |
|---|---|
| [マルチアームバンディット](https://en.wikipedia.org/wiki/Multi-armed_bandit){target=_blank} | マルチアームバンディット最適化アプローチでは、調査学習とその学習の活用のバランスを取ります。 |
| [ランダムフォレスト](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) | ランダムフォレストは、有力な機械学習アプローチです。 データサイエンス用語では、訪問者と訪問属性に基づいて多くの決定木を構築することで機能するアンサンブル分類または回帰方法です。 [!DNL Target] 内部では、ランダムフォレストを使用して、コンバージョンの可能性が最も高い（または訪問あたりの売上高が最も高い）と予想されるエクスペリエンスを特定の訪問者ごとに決定します。 |
| [トンプソンサンプリング](https://en.wikipedia.org/wiki/Thompson_sampling){target=_blank} | トンプソンサンプリングの目的は、全体的に最良の（パーソナライズされていない）エクスペリエンスを最小限の「コスト」で特定することです。 Thompson Samplingは、2つのエクスペリエンス間に統計的な違いがない場合でも、常に勝者を選びます。 |

## [!UICONTROL 自動ターゲット ]の仕組み {#section_77240E2DEB7D4CD89F52BE0A85E20136}

次のページでは、**[!UICONTROL 自動ターゲット]**&#x200B;と&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;の基礎となるデータとアルゴリズムについて説明します。

| トピック | 詳細 |
|--- |--- |
| [ランダムフォレストアルゴリズム](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) | **[!UICONTROL 自動ターゲット]**&#x200B;と&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;の両方で使用される[!DNL Target]の主なパーソナライゼーションアルゴリズムは、ランダムフォレストです。 ランダムフォレストのようなアンサンブル手法は、複数の学習アルゴリズムを使用して、構成要素となるどの学習アルゴリズムを使用した場合よりも優れた予測パフォーマンスを発揮します。 **[!UICONTROL Automated Personalization]**&#x200B;および&#x200B;**[!UICONTROL 自動ターゲット]** アクティビティのランダムフォレスト アルゴリズムは、学習時に多数の決定木を作成することによって動作する分類または回帰方式です。 |
| [Personalization アルゴリズム ](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md)のデータをアップロード中 [!DNL Target]  | **[!UICONTROL 自動ターゲット]**&#x200B;と **[!UICONTROL Automated Personalization]** モデルのデータを入力する方法は複数あります。 |
| [Personalization アルゴリズム ](/help/main/c-activities/t-automated-personalization/ap-data.md)のデータ収集 [!DNL Target]  | [!DNL Target]のパーソナライゼーションアルゴリズムは、様々なデータを自動的に収集します。 |

## トラフィック配分の決定 {#section_AB3656F71D2D4C67A55A24B38092958F}

アクティビティの目標に応じて、制御エクスペリエンスとパーソナライズされたエクスペリエンスの間で異なるトラフィック配分を選択できます。 アクティビティをライブにする前に、アクティビティの目標を決めておくことをお勧めします。

**[!UICONTROL カスタム配分]**&#x200B;ドロップダウンリストで、以下のオプションを選択できます。

* **[!UICONTROL パーソナライゼーションアルゴリズムを評価（50/50）]**
* **[!UICONTROL パーソナライゼーショントラフィックを最大化（90/10）]**
* **[!UICONTROL カスタム配分]**

![配分目標ドロップダウンリスト](/help/main/c-activities/assets/split-new-ui.png)

次の表では、3 つのオプションについて説明します。

| アクティビティの目標 | 推奨のトラフィック配分 | メリットとデメリット |
|--- |--- |--- |
| **[!UICONTROL パーソナライゼーションアルゴリズムを評価 (50/50)]**：目標がアルゴリズムのテストの場合は、50:50 の比率でコントロールとターゲットアルゴリズムに訪問者を配分します。 この配分により、上昇率を最も正確に推定できます。 「ランダムエクスペリエンス」をコントロールとして使用する場合にお勧めします。 | 配分はコントロールエクスペリエンスに 50％、パーソナライズされたエクスペリエンスに 50％ | <ul><li>コントロールと比較した場合のパーソナライゼーションの上昇率の精度を最大化できます。</li><li>エクスペリエンスがパーソナライズされる訪問者は比較的少数です。</li></ul> |
| **[!UICONTROL パーソナライゼーショントラフィックを最大化 (90/10)]**：「常時稼動」のアクティビティを作成することが目標の場合は、10％の訪問者をコントロールに配分して、アルゴリズムによる学習の長期的な継続に十分なデータを確保します。 この場合は、トラフィックの大部分をパーソナライズ対象にする代わりに、推定上昇率の精度が落ちるというデメリットがあります。 これは、目標にかかわらず、特定のエクスペリエンスをコントロールとして使用する場合のお勧めのトラフィック分割です。 | 最適な配分はコントロールエクスペリエンスに 10％から 30％、パーソナライズされたエクスペリエンスに 70％から 90％ | <ul><li>パーソナライズされたエクスペリエンスを提供する訪問者数を最大化できます。</li><li>上昇率を最大化できます。</li><li>アクティビティの上昇率の精度が落ちます。</li></ul> |
| **[!UICONTROL カスタム配分]** | 配分の割合を手動で調節します。 | <ul><li>想定どおりの結果が得られない場合もあります。 目安がわからない場合は、上述のいずれかのオプションを使用することをお勧めします。</li></ul> |

**[!UICONTROL コントロール]**&#x200B;の割合を調整するには、**[!UICONTROL トラフィック配分]**&#x200B;パネルの「**[!UICONTROL エクスペリエンス]**」をクリックし、必要に応じて割合を調整します。 コントロールグループの割合を 10％未満にすることはできません。

[ コントロール ](/help/main/c-activities/t-automated-personalization/experience-as-control.md)として使用する特定のエクスペリエンスを選択するか、**[!UICONTROL ランダムエクスペリエンス]** オプションを使用できます。

## [!UICONTROL 自動ターゲット ]と[!UICONTROL Automated Personalization]の比較 {#compare-at-ap}

**[!UICONTROL 自動ターゲット]**&#x200B;と&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;は、同じアルゴリズムとデータを共有していますが、エクスペリエンスの構築方法とモデルに必要なトラフィックの量が異なります。

### 2つのアクティビティタイプの共通点 {#section_2A601F482F9A44E38D4B694668711319}

* **各訪問に対する最適化。** このアルゴリズムは、最適なエクスペリエンスを提供するための訪問者のコンバージョン傾向（またはコンバージョンからの推定収益）を予測します。 訪問者は、既存のセッションの終了時に新しいエクスペリエンスの対象となります。 例外は、コントロールグループの訪問者で、初回訪問時に割り当てられたエクスペリエンスを保持します。 セッション内では、視覚的な一貫性を維持するために、予測は変更されません。
* **訪問者の行動の変化への適応。** マルチアームドバンディットは、アクティビティの全期間を通じて学習を続け、以前に学習したトレンドの過度な悪用を防ぐために、常に小さなトラフィックを「費やす」ことになります。 最新の訪問者行動データを使用して、24時間ごとに基本モデルを再構築します。 アルゴリズムが個人に対する勝者エクスペリエンスを判断できない場合は、[ トンプソンサンプリング ](https://en.wikipedia.org/wiki/Thompson_sampling)を使用して見つかった全体的に最もパフォーマンスの高いエクスペリエンスを表示し、パーソナライズされた勝者を引き続き探します。
* **単一の目標指標。** アルゴリズムは、コンバージョンベースまたは収益ベースの指標（具体的には、**[!UICONTROL 訪問あたりの収益]**）を使用して、1つの指標に対して継続的に最適化します。
* **自動データ収集。** [!DNL Target] では、訪問者に関する情報を自動的に収集して、パーソナライゼーションモデルを構築します。 使用されるパラメーターについて詳しくは、[Automated Personalization Data Collection](/help/main/c-activities/t-automated-personalization/ap-data.md)を参照してください。
* **共有オーディエンス。** [!DNL Target] では、[!DNL Adobe Experience Cloud] のすべての共有オーディエンスを自動的に使用して、パーソナライゼーションモデルを構築します。 モデルにオーディエンスを追加するために特別なことをする必要はありません。 [!DNL Experience Cloud Audiences] と [!DNL Target] を併用する方法について詳しくは、「[Experience Cloud オーディエンス](/help/main/c-integrating-target-with-mac/mmp.md)」を参照してください。
* **カスタムデータ。** マーケターは、オフラインデータや傾向スコアなどのカスタムデータをアップロードして、パーソナライゼーションモデルを構築することができます。 自動ターゲットおよびAutomated Personalization](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md)のデータのアップロードについて詳しくは、[を参照してください。

### 2つのアクティビティタイプの違い {#section_BA4D83BE40F14A96BE7CBC7C7CF2A8FB}

エクスペリエンス全体を定義する場合、**[!UICONTROL Visual Experience Composer]** （VEC）機能の完全なセットを使用する場合、またはページに構造的な変更を加える場合は、**[!UICONTROL Automated Personalization]**&#x200B;ではなく&#x200B;**[!UICONTROL 自動ターゲット]**&#x200B;を検討してください。

| | [!UICONTROL 自動ターゲット] | [!UICONTROL Automated Personalization] |
|---|---|---|
| **エクスペリエンス定義** | 複数の変更を含めることができるエクスペリエンス全体を定義します。 | 個々のオファーが自動的に組み合わされて、エクスペリエンスが形成されます。 |
| **[!UICONTROL Visual Experience Composer]の機能** | **[!UICONTROL 自動ターゲット]**&#x200B;はA/B アクティビティワークフローに組み込まれているため、より成熟した本格的なVECからメリットが得られます。 [QA リンク ](/help/main/c-activities/c-activity-qa/activity-qa.md)を使用することもできます。 | カスタムコードエディター、複数のエクスペリエンスオーディエンスなどの機能はサポートされていません。 |
| **ページの構造的な変更** | より適切な。 例えば、ホームページ上の要素を並べ替えることができます。 | あまり適切でない。 |
| **エクスペリエンス数** | 1つのエクスペリエンスに複数の変更が含まれる場合があるため、通常は少なくなります。 | エクスペリエンスは、オファーと場所を組み合わせたものであるため、通常はもっと重要です。 |
| **モデルの構築に必要なトラフィック** | 頻繁に合計より少ない。 | より多い頻度で合計。 |

モデルの構築に必要なエクスペリエンスごとのトラフィック *の量*&#x200B;は、両方のアクティビティタイプで同じです。 **[!UICONTROL 自動ターゲット]**&#x200B;は、通常はエクスペリエンスが少ないため、総トラフィックが少なくなります。

例えば、**[!UICONTROL Automated Personalization]** アクティビティで、1か所につき2つのオファーと2か所の場所で、アクティビティには合計4つの（2 × 2 = 4）エクスペリエンスがあります（除外なし）。 **[!UICONTROL 自動ターゲット]**&#x200B;では、エクスペリエンス 1を場所1にオファー1を、場所2にオファー2を含めるように設定し、エクスペリエンス 2を場所1にオファー2を、場所2にオファー1を含めるように設定できます。 **[!UICONTROL 自動ターゲット]**&#x200B;では、1つのエクスペリエンス内で複数の変更が可能なので、アクティビティ内のエクスペリエンスの合計数を減らすことができます。

### [!UICONTROL 自動ターゲット ]のトラフィック要件 {#traffic-requirements}

次の経験則は、トラフィック要件を理解するのに役立ちます。

* **[!UICONTROL  コンバージョン ]が成功指標の場合：** 1,000回の訪問と、1日あたりのエクスペリエンスあたりのコンバージョン数が少なくとも50回です。 さらに、アクティビティには7,000件以上の訪問と350件のコンバージョンが必要です。
* **1訪問あたりの売上高]が成功指標である場合：** 1,000回の訪問と、1日あたりのエクスペリエンスあたりのコンバージョン数が少なくとも50回である場合。 [!UICONTROL さらに、アクティビティには、エクスペリエンスごとに少なくとも1,000回のコンバージョンが必要です。 **[!UICONTROL 訪問あたりの収益]**&#x200B;は、通常、モデルを構築するためにより多くのデータを必要とします。これは、訪問の収益の分散がコンバージョン率よりも高くなることが原因です。

**[!UICONTROL 自動ターゲット]**&#x200B;は、広範なオンライン テスト フレームワークも提供します。 マルチアームドバンディットは、[!DNL Adobe]人のデータサイエンティストと研究者が現実世界の状況における継続的な改善の利点を理解できるようにする、より大規模なオンラインテストフレームワークの一部です。 将来的には、このテストベッドにより、[!DNL Adobe]はデータに精通した顧客に機械学習プラットフォームを開くことができるようになり、顧客は独自のモデルを取り込んで[!DNL Target] モデルを拡張できるようになります。

レポートについて詳しくは、[ レポートと自動ターゲット ](/help/main/c-activities/auto-target/reporting-and-auto-target.md)を参照してください。
