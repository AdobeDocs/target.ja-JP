---
keywords: トラブルシューティング；よくある質問；FAQ;FAQ；自動パーソナライゼーション；制御；デフォルトエクスペリエンス；ベストプラクティス
description: '[!UICONTROL Adobe Target]の[!UICONTROL Automated Personalization] （AP）アクティビティに関するよくある質問（FAQ）と回答の一覧を確認します。'
title: '[!UICONTROL Automated Personalization] アクティビティに関するFAQを見つけるにはどうすればよいですか？'
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Automated Personalization
exl-id: 2bf62cc1-1781-4021-a400-2884e0bae893
TQID: 'https://experienceleague.adobe.com/cYdFwvkJDlfGYdcxql9iWGwNiTed4Lb2kC7JdN7xgdo'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: f0055dd2-93f3-4ac8-9abc-d69d4ed2d977
    internal-label: Automated personalization
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
    internal-label: Machine learning
source-git-commit: 44c6bdd4ab818226e76477782d7e4238b49d5cdc
workflow-type: tm+mt
source-wordcount: '2088'
ht-degree: 13%
---
# Automated Personalizationに関するFAQ {#ap-faq}

>[!BEGINSHADEBOX]

**このページ：** **[!UICONTROL Automated Personalization]** アクティビティに関するよくある質問への回答を表示します。

>[!ENDSHADEBOX]

次の質問と回答では、[!DNL Adobe Target]で&#x200B;**[!UICONTROL Automated Personalization]** アクティビティを設定する方法、パーソナライゼーションモデルの構築方法、トラフィックの割り当て方法、結果の読み取り方法について説明します。

## アクティビティの設定 {#set-up-an-activity}

+++ [!UICONTROL Automated Personalization] アクティビティを設定するためのベストプラクティスを教えてください。

* エクスペリエンスの合計数だけでなく、*アクティビティの形状* （場所×オファーの数）に細心の注意を払います。 場所とオファーのデカルト的な組み合わせは、生のエクスペリエンス数よりもオーサリング時間のパフォーマンスに影響します。 最適なパフォーマンスと管理性を得るには、「**[!UICONTROL Automated Personalization]**&#x200B;および&#x200B;**[!UICONTROL 自動ターゲット]** アクティビティを、1か所あたり4～6件のオファーを含む4～6か所に制限します。詳しくは、「Automated Personalizationの制限事項を教えてください」の質問を参照してください。 このセクションでは。 大きな設定はお勧めせず、**[!UICONTROL Visual Experience Composer]**&#x200B;での読み込みや編集が遅くなる可能性があります。
* トラフィックの少ないページをパーソナライズしたり、パーソナライズ中のエクスペリエンスに構造的な変更を加えたりするには、**[!UICONTROL Automated Personalization]**&#x200B;ではなく[**[!UICONTROL 自動ターゲット &#x200B;]**&#x200B;アクティビティ &#x200B;](/help/main/c-activities/auto-target/auto-target-to-optimize.md)を使用することを検討してください。
* **[!UICONTROL Automated Personalization]** アクティビティで使用するオファーと場所の間で&#x200B;**[!UICONTROL A/B テスト]** アクティビティを実行して、場所と場所が最適化目標に影響を与えていることを確認することを検討してください。 **[!UICONTROL A/B テスト]** アクティビティが有意な違いを示さない場合、**[!UICONTROL Automated Personalization]**&#x200B;も上昇率を生成できない可能性があります。

  A/B...N テストで、エクスペリエンス間に統計的に有意な差が見られない場合、次の状況のうち1つ以上が原因であると考えられます。

  * オファーが互いに十分に異なっていない可能性があります。
  * 選択した場所は、成功指標には影響しません。
  * 最適化の目標がコンバージョン funnel内にあまりにも遠いため、選択したオファーの影響を受けません。

* [Traffic Estimator](/help/main/c-activities/t-automated-personalization/ap-traffic-estimator.md#use-traffic-estimator)を使用して、パーソナライゼーションモデルが&#x200B;**[!UICONTROL Automated Personalization]** アクティビティで構築するのにかかる時間を把握します。
* 目標をもとに、アクティビティを開始する前に、コントロールとターゲットとなるトラフィックの間の割り当てを決定します。 次の表に、アクティビティの目標と選択したコントロールのタイプに基づいて、考慮すべき3つのシナリオを示します。

  | 制御とアクティビティの目標 | コントロールへの推奨される配分 | 詳細 |
  | --- | --- | --- |
  | コントロールとして&#x200B;**[!UICONTROL ランダム エクスペリエンス]**&#x200B;を使用し、目標はパーソナライゼーション アルゴリズムの有効性をテストすることです | 50% | この目標を達成するには、リフトをより正確に把握する必要があります。 また、エクスペリエンスやオファーのコンバージョン率と、単純な&#x200B;**[!UICONTROL A/B テスト]** （ランダムに提供されるコントロール）が提供するコンバージョン率を比較する必要があります。 |
  | コントロールとして&#x200B;**[!UICONTROL ランダム エクスペリエンス]**&#x200B;を使用し、パーソナライズされたトラフィックを最大化することを目標としています | 10%から30% | アルゴリズムに慣れており、トラフィックの最大量をパーソナライズしたい場合は、このオプションを使用します。 トレードオフは、リフト情報の精度です。コントロールトラフィックの信頼区間は、トラフィックの流れが少ないため大きくなります。 |
  | **[!UICONTROL 特定のエクスペリエンス]**&#x200B;をコントロールとして使用し、どちらかの目標を設定します | 10%から30% | このオプションを使用して、特定のマーケター主導のエクスペリエンスをパーソナライゼーションモデルと比較します。 コントロールとして1つのエクスペリエンスのみを選択すると、そのトラフィックがアクティビティ内のすべてのオファーまたはエクスペリエンスに分散するわけではありません。 |

* ターゲティングルールは、モデルが最適化する能力を妨げる可能性があるため、できるだけ控えめに使用します。 詳しくは、[Target のAutomated Personalizationオファー](/help/main/c-activities/t-automated-personalization/ap-target-offers.md)を参照してください。
* レポートグループは&#x200B;**[!UICONTROL Automated Personalization]** アクティビティの成功を制限できるので、特定の条件でのみ使用できます。 詳しくは、[Automated Personalizationのオファーレポートグループ &#x200B;](/help/main/c-activities/t-automated-personalization/offer-reporting-groups-in-automated-personalization.md)を参照してください。

  * 次のすべての条件を満たす場合にのみ、レポートグループを使用します。

    * アクティビティの実行中にオファーを置き換えたり、追加したりすることを計画しています。
    * レポートグループのオファーは、同じ訪問者にアピールします。
    * レポートグループのオファーは、全体的な応答率がほぼ同じです。

  * レポートグループ内のオファー間にパーソナライゼーションがありません。 パーソナライゼーションモデルでは、すべてのオファーが同じように扱われます。
  * アクティビティ内のすべてのオファーを、1 つのレポートグループに入れるのは避けてください。 これにより、すべてのオファーがアクティビティ内のすべての訪問者にランダムに提供されます。

+++

+++ [!UICONTROL Automated Personalization]の制限事項は何ですか？

[!DNL Target]には30,000件のエクスペリエンスのハードリミットがありますが、作成されたエクスペリエンス数が10,000件に満たない場合は、最高の状態で機能します。 アクティビティで「**[!UICONTROL 重複を許可しない]**」オプションが有効になっている場合も、同じ制限が適用されます。

**[!UICONTROL Automated Personalization]**&#x200B;および&#x200B;**[!UICONTROL 自動ターゲット]** アクティビティは、多数のエクスペリエンスをサポートできますが、オーサリングのパフォーマンスは、*アクティビティの形状* （場所×オファー数）に大きく依存します。 特定の設定では、負荷と編集のパフォーマンスに大きな影響を与える大きなデカルトの組み合わせが作成され、文書化されたエクスペリエンス制限を下回る場合でも使用できます。

最適なパフォーマンスと管理性を得るには、1か所につき4 ～ 6件のオファーを含む&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;および&#x200B;**[!UICONTROL 自動ターゲット]** アクティビティを4 ～ 6か所に制限してください。 大きな設定は推奨されず、[!DNL Target] UIで制限される場合があります。

現在の[!DNL Target] UIでは、**[!UICONTROL Automated Personalization]**&#x200B;および&#x200B;**[!UICONTROL 自動ターゲット]** アクティビティが&#x200B;**[!UICONTROL エクスペリエンス]** ステップで直接設定されています。 [!DNL Target]は、設定がサポートされているしきい値を超えると、インライン警告を表示したり、アクティビティの保存を妨げたりする可能性があります。また、**[!UICONTROL 次]**、**[!UICONTROL 保存]**、**[!UICONTROL 公開]**&#x200B;にアクティビティの形状が再検証されます。

[!DNL Target]のアクティビティやその他の要素に影響を与える文字制限およびその他の制限（オファーサイズ、オーディエンス、プロファイル、値、パラメーターなど）について詳しくは、[制限](/help/main/r-troubleshooting-target/target-limits.md)を参照してください。

+++

+++ [!UICONTROL Automated Personalization] アクティビティでコントロールとして使用する特定のエクスペリエンスを指定できますか？

[**[!UICONTROL Automated Personalization]**](/help/main/c-activities/t-automated-personalization/automated-personalization.md#automated-personalization-overview) （AP）または[**[!UICONTROL 自動ターゲット &#x200B;]**](/help/main/c-activities/auto-target/auto-target-to-optimize.md) （AT）アクティビティの作成中に、コントロールとして使用する特定のエクスペリエンスを選択できます。

この機能を使用すると、アクティビティで設定されたトラフィック割り当て率に基づいて、制御トラフィック全体をそのエクスペリエンスにルーティングできます。 その後、パーソナライズされたトラフィックのパフォーマンスレポートを、その1つのエクスペリエンスに対する制御トラフィックと評価できます。

詳しくは、[&#x200B; コントロールエクスペリエンスの選択](/help/main/c-activities/t-automated-personalization/experience-as-control.md)を参照してください。

+++

+++ オファーレベルのターゲット設定は、どのような仕組みになっていますか。

各訪問者が訪問すると、オファーレベルのターゲティングルールによって、訪問者が閲覧できるオファーのセットが決まります。 アルゴリズムは、そのオファーの中から、予測モデルが収益やコンバージョンの可能性が最も高いオファーを選択します。 オファーのターゲティングは、[!DNL Target]機械学習アルゴリズムの有効性に影響を与えるので、できるだけ控えめに使用してください。 詳しくは、[Target のAutomated Personalizationオファー](/help/main/c-activities/t-automated-personalization/ap-target-offers.md)を参照してください。

+++

## モデル構築とトラフィック配分 {#models-and-traffic}

+++ アクティビティのトラフィックを[!UICONTROL Automated Personalization]がどのように割り当てますか？

**[!UICONTROL Automated Personalization]**&#x200B;は、最新の[&#x200B; ランダムフォレスト &#x200B;](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) モデルに基づいて、最も高い予測成功指標を持つエクスペリエンスに訪問者をルーティングします。 この予測は、訪問者の具体的な情報と訪問コンテキストに基づいています。

例えば、**[!UICONTROL Automated Personalization]** アクティビティに、それぞれ2つのオファーを含む2つの場所があるとします。 1 つ目の場所では、特定の訪問者に対するオファー A の推定コンバージョン率が 3％、オファー B の推定コンバージョン率が 1％です。 2 つ目の場所では、同一の訪問者に対するオファー C の推定コンバージョン率が 2％、オファー D の推定コンバージョン率が 5％です。 したがって、**[!UICONTROL Automated Personalization]**&#x200B;は、この訪問者にオファーAとオファーDのエクスペリエンスを提供します。

+++

+++ 環境に関して、[!UICONTROL Automated Personalization]はどのようにモデルを構築しますか？

1 つのモデルを使用して、パーソナライズされた戦略、ランダムに提供されるトラフィック、そしてすべてのトラフィックを勝者エクスペリエンス全体に送信する場合のパフォーマンスを比較します。 このモデルでは、ヒットとコンバージョンはデフォルト環境でのみ考慮されます。

各レポートグループ （**[!UICONTROL Automated Personalization]**）またはエクスペリエンス （**[!UICONTROL 自動ターゲット]**）に対して、2番目のモデルセットが構築されます。 これらのモデルごとに、すべての環境にわたるヒットおよびコンバージョンが考慮されます。

したがって、リクエストは、環境に関係なく、同じモデルで提供されます。 ただし、特定された総合的な勝者エクスペリエンスが実際の行動と一致するように、大多数のトラフィックをデフォルト環境から提供する必要があります。

+++

+++ モデルが構築されるまでに、どの程度待てばよいですか。

通常、モデルがアクティビティを構築するのにかかる時間は、選択したアクティビティの場所へのトラフィックとアクティビティの成功指標によって異なります。 [Traffic Estimator](/help/main/c-activities/t-automated-personalization/ap-traffic-estimator.md#use-traffic-estimator)を使用して、モデルがアクティビティを構築するのにかかる予想期間を決定します。

+++

+++ [!UICONTROL Automated Personalization] アクティビティでモデルを構築するのに必要な時間を短縮するにはどうすればよいですか？

アクティビティの設定を確認して、モデルの構築スピードを向上させる変更を確認します。 たとえば、RPVの成功指標を「コンバージョン」に変更したり、セールスfunnelのアクティビティエクスペリエンスに近い成功指標を選択したり、アクティビティからエクスペリエンスを削除したり、トラフィックの高いページを使用したりできます。 詳しくは、[Automated Personalizationのトラブルシューティング &#x200B;](/help/main/c-activities/t-automated-personalization/ap-trouble.md)を参照してください。

+++

+++ 1つのモデルが[!UICONTROL Automated Personalization] アクティビティ内に構築されています。 そのエクスペリエンスへの訪問に対して、パーソナライゼーションはおこなわれますか。

いいえ。 パーソナライゼーションを開始するには、アクティビティ内に少なくとも2つのモデルを構築する必要があります。

+++

## 成果と上昇率 {#results-and-lift}

+++ [!UICONTROL Automated Personalization] アクティビティの結果はいつ確認できますか？

少なくとも2つのエクスペリエンスがモデルを構築した後（緑のチェックマークで示されます）、**[!UICONTROL Automated Personalization]** アクティビティの結果を確認できます。

+++

+++ [!UICONTROL Automated Personalization] アクティビティで上昇率が表示されないのはなぜですか？

**[!UICONTROL Automated Personalization]** アクティビティで上昇率を生成するには、次の4つの要素が必要です。

* 各地域のオファーは、訪問者に影響を与えるのに十分なほど異なっている必要があります。
* 場所は、最適化の目標に違いをもたらす場所である必要があります。
* 上昇率を検出するために、アクティビティに十分なトラフィックと統計的検出力が必要です。
* パーソナライゼーションアルゴリズムが適切に機能する必要があります。

アクションの最善の方法は、まず、シンプルでパーソナライズされていない&#x200B;**[!UICONTROL A/B テスト]** アクティビティを使用して、アクティビティのエクスペリエンスを構成するコンテンツと場所が、全体的な応答率に真に違いをもたらすことを確認することです。 完全な手順については、[Automated Personalizationのトラブルシューティング &#x200B;](/help/main/c-activities/t-automated-personalization/ap-trouble.md)を参照してください。

+++

+++ [!UICONTROL Automated Personalization]をデフォルトエクスペリエンスと比較するにはどうすればよいですか？

**[!UICONTROL Automated Personalization]**&#x200B;をデフォルトのエクスペリエンスと比較するターンキーオプションはありません。 回避策として、アクティビティの一部としてデフォルトのオファーまたはエクスペリエンスが存在する場合は、レポートで&#x200B;**[!UICONTROL Control]** セグメントをクリックし、結果として得られるオファーレベル レポートでそのオファーを見つけます。 このオファーに記録されたコンバージョン率は、「ランダムフォレスト」セグメント全体のコンバージョン率と比較できます。 この比較は、モデルのパフォーマンスをデフォルトのオファーと比較して示します。

+++

## ライブアクティビティの管理 {#manage-live-activity}

+++ [!UICONTROL Automated Personalization] アクティビティはいつ停止すべきですか？

**[!UICONTROL Automated Personalization]**&#x200B;は、常に最適化される「常時稼動」のパーソナライゼーションとして使用できます。 特に常緑コンテンツの場合、**[!UICONTROL Automated Personalization]** アクティビティを停止する必要はありません。 現在のアクティビティのオファーと類似していないコンテンツに実質的な変更を加える場合は、新しいアクティビティを開始することをお勧めします。 新しいアクティビティを開始することで、レポートを確認する他のユーザーは、過去の結果を異なるコンテンツと混同したり関連付けたりすることを避けることができます。

+++

+++ [!UICONTROL Automated Personalization] アクティビティの途中で目標指標を変更できますか？

[!DNL Adobe] では、アクティビティの途中で目標指標を変更することはお勧めしません。 アクティビティ中に[!DNL Target] UIを使用して目標指標を変更することは可能ですが、代わりに常に新しいアクティビティを開始してください。 [!DNL Adobe] は、実行後にアクティビティの目標指標を変更した場合の動作を保証しません。

このレコメンデーションは、**[!UICONTROL 自動配分]**、**[!UICONTROL 自動ターゲット]**、**[!UICONTROL Automated Personalization]** の各アクティビティで、レポートソースとして [!DNL Target] または [!DNL Analytics]（A4T）を使用します。

+++

+++ [!UICONTROL Automated Personalization] アクティビティの実行中に「[!UICONTROL &#x200B; レポート データをリセット &#x200B;]」オプションを使用できますか？

[!DNL Adobe]は、**[!UICONTROL Automated Personalization]** アクティビティに&#x200B;**[!UICONTROL レポート データのリセット]** オプションを使用することを推奨しません。 表示されているレポートデータは削除されますが、このオプションを使用しても、**[!UICONTROL Automated Personalization]** モデルからすべてのトレーニングレコードが削除されるわけではありません。 「**[!UICONTROL レポートデータをリセット]**」オプションを使用する代わりに、新しいアクティビティを作成し、元のアクティビティを無効にします。 このガイダンスは、**[!UICONTROL 自動配分]**&#x200B;および&#x200B;**[!UICONTROL 自動ターゲット]**&#x200B;活動にも適用されます。

+++

+++ [!UICONTROL Automated Personalization]のアクティビティに関する体験を見た訪問者が、見るべきではない体験を見るのはなぜですか？

**[!UICONTROL Automated Personalization]**&#x200B;のアクティビティは、セッションごとに1回評価されます。 特定のエクスペリエンスに適格なアクティブなセッションがあり、その後に新しいオファーが追加された場合、訪問者には、新しいコンテンツと以前に表示されたオファーが表示されます。 このような訪問者は、以前はこのような体験に適格であったため、セッション中にそのような体験を確認します。 ページ訪問時ごとにアクティビティを評価するには、**[!UICONTROL エクスペリエンスのターゲット設定]** （XT）アクティビティタイプに変更します。

+++
