---
keywords: 自動ターゲット;ターゲティング;トラフィック配分;よくある質問;faq;トラブルシューティング
description: 顧客プロファイルと類似した訪問者の行動に基づいて、各訪問者に最もカスタマイズされたエクスペリエンスを[!UICONTROL Auto-Target] アクティビティがどのように提供するかを説明します。
title: '[!UICONTROL Auto-Target] アクティビティとは'
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Auto-Target
exl-id: 59ca30dc-45a0-4129-b832-84e1132d3b69
TQID: https://experienceleague.adobe.com/uKmfIlOcT-tZgOjuvERXuif-Y5-2Jw3prtPbuBjv1is
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: adee20bd-51f4-461d-b9db-d215f8756eeb
subfeature_v2: id: fff07a91-d479-45f4-ae95-9762e79b1b7c
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: c1579802-ddd4-4214-8a91-97b2066abe11id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1id: d3cdead0-685a-4489-9250-4bb709942f66id: e0eb8757-182f-49f3-94a4-1587d16f5094id: eb30f47f-d87a-400f-8f78-63ce7979ff56id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
source-git-commit: 16fb7a1902ea76cab56a93fa141a32a3c6bc4467
workflow-type: tm+mt
source-wordcount: 1882
ht-degree: 41%

---

# [!UICONTROL Auto-Target] の概要

[!DNL Adobe Target]の[!UICONTROL Auto-Target]のアクティビティでは、高度な機械学習を使用して、複数のパフォーマンスの高いマーケター定義エクスペリエンスから選択し、コンテンツをパーソナライズしてコンバージョンを促進します。 [!UICONTROL Auto-Target]は、個々の顧客プロファイルと、類似したプロファイルを持つ以前の訪問者の行動に基づいて、各訪問者に最もカスタマイズされたエクスペリエンスを提供します。

>[!NOTE]
>
>* [!UICONTROL Auto-Target]は[!DNL Target Premium] ソリューションの一部として利用できます。 この機能は、[!DNL Target Premium] ライセンスのない [!DNL Target Standard] では使用できません。 このライセンスで提供される高度な機能について詳しくは、[Target Premium](/help/main/c-intro/intro.md) を参照してください。
>
>* [!UICONTROL Analytics for Target] （A4T）は[!UICONTROL Auto-Target] アクティビティをサポートしています。 詳しくは、[A4T での自動配分および自動ターゲットアクティビティのサポート](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md)を参照してください。

## 自動ターゲットを使用した実際のユーザー事例 {#success}

大手アパレル企業のretailerは、最近[!UICONTROL Auto-Target] アクティビティを利用して、10種類の商品カテゴリーベースのエクスペリエンス（さらにランダム化されたコントロール）を提供し、各訪問者に適切なコンテンツを提供しています。 &quot;[!UICONTROL Add to Cart]&quot;が主な最適化指標として選択されました。 ターゲットエクスペリエンスの平均上昇率は 29.09％でした。 [!UICONTROL Auto-Target] モデルの構築後、アクティビティは90%のパーソナライズされたエクスペリエンスに設定されました。

わずか 10 日で、1,700,000 ドル以上の上昇率を達成しました。

[!UICONTROL Auto-Target]を使用して組織の上昇率と収益を増加させる方法については、引き続きご覧ください。

## 概要 {#section_972257739A2648AFA7E7556B693079C9}

3 ステップのガイドによるワークフローを使用して [A/B アクティビティを作成](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)するときは、**[!UICONTROL Targeting]** ページ（ステップ 2）で **[!UICONTROL Auto-Target for personalized experiences]** オプションを選択します。

![ トラフィック配分メソッドの設定](/help/main/c-activities/automated-traffic-allocation/assets/auto-target.png)

A/B アクティビティフロー内の[!UICONTROL Auto-Target] オプションを使用すると、マシンラーニングを活用して、マーケターが定義した一連のエクスペリエンスに基づいて、ワンクリックでパーソナライズできます。 [!UICONTROL Auto-Target]は、訪問者ごとに表示するエクスペリエンスを決定することにより、従来のA/B テストまたは[!UICONTROL Auto Allocate]と比較して、最大限の最適化を実現するように設計されています。 目的が単一の勝者を見つけることであるA/B アクティビティとは異なり、[!UICONTROL Auto-Target]は、特定の訪問者に対する最適なエクスペリエンスを自動的に決定します。 優れた体験は、訪問者のプロファイルやその他のコンテクスト情報にもとづいて構築され、詳細にパーソナライズされた体験を提供します。

[!UICONTROL Automated Personalization]と同様に、[!UICONTROL Auto-Target]は[ ランダムフォレスト アルゴリズム ](/help/main/c-activities/t-automated-personalization/algo-random-forest.md)を使用して、訪問者に表示する最適なエクスペリエンスを決定します。 [!UICONTROL Auto-Target]は訪問者の行動の変化に適応できるため、永続的に実行して上昇率を提供できます。 この方法は、「常時オン」モードと呼ばれることもあります。

特定の訪問者に対するエクスペリエンスの割り当てが固定されるA/B アクティビティとは異なり、[!UICONTROL Auto-Target]は各訪問に対して指定されたビジネス目標を最適化します。 [!UICONTROL Auto Personalization]と同様、[!UICONTROL Auto-Target]は、デフォルトでは、アクティビティのトラフィックの一部をコントロールグループとして予約し、上昇率を測定します。 コントロールグループの訪問者には、アクティビティのランダムエクスペリエンスが配信されます。

## 注意点

[!UICONTROL Auto-Target]を使用する際は、いくつかの重要な考慮事項に注意する必要があります。

* 特定のアクティビティを[!UICONTROL Auto-Target]から[!UICONTROL Automated Personalization]に切り替えることはできません。その逆の方法です。
* アクティビティがドラフトとして保存された後、トラフィックの割り当て（従来の[!UICONTROL A/B Test]）を[!UICONTROL Auto-Target]に[!UICONTROL Manual]から切り替えることはできません。
* ひとつのモデルは、パーソナライズされた戦略のパフォーマンスを特定するように構築されており、ランダムにトラフィックを提供するか、全体的な勝者エクスペリエンスにすべてのトラフィックを送信するかを決定します。 このモデルでは、ヒットとコンバージョンはデフォルト環境でのみ考慮されます。

  2 番目のモデルセットからのトラフィックは、モデリンググループ（AP）またはエクスペリエンス（AT）ごとに作成されます。 これらのモデルごとに、すべての環境にわたるヒットおよびコンバージョンが考慮されます。

  リクエストは、環境に関係なく、同じモデルで提供されます。 ただし、識別された全体的な勝者エクスペリエンスが実際の動作と一致するように、複数のトラフィックをデフォルト環境から取得する必要があります。

* 2 つ以上のエクスペリエンスを使用します。

## 用語 {#section_A309B7E0B258467789A5CACDC1D923F3}

[!UICONTROL Auto-Target] について説明するときに役立つ用語を次に示します。

| 用語 | 定義 |
|---|---|
| [ マルチアームドバンディット ](https://en.wikipedia.org/wiki/Multi-armed_bandit){target=_blank} | マルチアームバンディット最適化アプローチでは、調査学習とその学習の活用のバランスを取ります。 |
| [ランダムフォレスト](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) | ランダムフォレストは、有力な機械学習アプローチです。 データサイエンス分野では、訪問者と訪問の属性に基づいて多数の決定ツリーを作成することで機能するアンサンブル分類または回帰手法を指します。 [!DNL Target] 内部では、ランダムフォレストを使用して、コンバージョンの可能性が最も高い（または訪問あたりの売上高が最も高い）と予想されるエクスペリエンスを特定の訪問者ごとに決定します。 |
| [ トンプソンサンプリング ](https://en.wikipedia.org/wiki/Thompson_sampling){target=_blank} | トンプソンサンプリングの目的は、全体的に最良の（パーソナライズされていない）エクスペリエンスを最小限の「コスト」で特定することです。 トンプソンサンプリングでは、2 つのエクスペリエンスに統計的な差異がない場合でも、必ず勝者が選定されます。 |

## [!UICONTROL Auto-Target]の仕組み {#section_77240E2DEB7D4CD89F52BE0A85E20136}

[!UICONTROL Auto-Target]と[!UICONTROL Automated Personalization]の基礎となるデータとアルゴリズムについて詳しくは、以下のリンクを参照してください。

| 用語 | 詳細 |
|--- |--- |
| [ランダムフォレストアルゴリズム](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) | [!UICONTROL Auto-Target]と[!UICONTROL Automated Personalization]の両方で使用される[!DNL Target]の主なパーソナライゼーションアルゴリズムは、ランダム フォレストです。 ランダムフォレストなどのアンサンブル手法では、複数の学習アルゴリズムを使用して、任意の構成学習アルゴリズムから得られるよりも優れた予測性能を得ることができます。 [!UICONTROL Automated Personalization]および[!UICONTROL Auto-Target] アクティビティのランダムフォレスト アルゴリズムは分類または回帰方法であり、学習時に多数の決定木を構築することによって動作します。 |
| [の [!DNL Target]のPersonalization アルゴリズム ](/help/main/c-activities/t-automated-personalization/algo-random-forest.md)のデータをアップロードしています | [!UICONTROL Auto-Target]および[!UICONTROL Automated Personalization] モデルのデータを入力するには、いくつかの方法があります。 |
|  [!DNL Target]のPersonalization アルゴリズム ](/help/main/c-activities/t-automated-personalization/ap-data.md)の[ データ収集 | [!DNL Target]のパーソナライゼーションアルゴリズムは、様々なデータを自動的に収集します。 |

## トラフィック配分の決定 {#section_AB3656F71D2D4C67A55A24B38092958F}

アクティビティの目標に合わせて、様々な方法でコントロールとパーソナライズされたエクスペリエンスにトラフィックを配分できます。 アクティビティをライブにする前に、アクティビティの目標を決めておくことをお勧めします。

[!UICONTROL Custom Allocation] ドロップダウンリストでは、次のオプションから選択できます。

* [!UICONTROL Evaluate Personalization Algorithm (50/50)]
* [!UICONTROL Maximize Personalization Traffic (90/10)]
* [!UICONTROL Custom Allocation]

![配分目標ドロップダウンリスト](/help/main/c-activities/assets/split-new-ui.png)

次の表では、3つのオプションについて説明します。

| アクティビティの目標 | 推奨のトラフィック配分 | メリットとデメリット |
|--- |--- |--- |
| **[!UICONTROL Evaluate Personalization Algorithm (50/50)]**：目標がアルゴリズムをテストする場合は、コントロールとターゲット アルゴリズムの間で訪問者を50/50%分割します。 この配分により、上昇率を最も正確に推定できます。 「ランダムエクスペリエンス」をコントロールとして使用する場合にお勧めします。 | 配分はコントロールエクスペリエンスに 50％、パーソナライズされたエクスペリエンスに 50％ | <ul><li>コントロールと比較した場合のパーソナライゼーションの上昇率の精度を最大化できます。</li><li>エクスペリエンスがパーソナライズされる訪問者は比較的少数です。</li></ul> |
| **[!UICONTROL Maximize Personalization Traffic (90/10)]**：目標が「常時稼動」アクティビティを作成する場合は、訪問者の10%をコントロールに入れて、アルゴリズムが時間の経過とともに学習を継続するのに十分なデータを確保します。 ここでのトレードオフは、より多くのトラフィックをパーソナライズする見返りとして、正確な上昇率を把握する精度が低くなることです。 これは、目標にかかわらず、特定のエクスペリエンスをコントロールとして使用する場合のお勧めのトラフィック分割です。 | 最適な配分はコントロールエクスペリエンスに 10％から 30％、パーソナライズされたエクスペリエンスに 70％から 90％ | <ul><li>パーソナライズされた体験を提供した訪問者の数を最大化したい</li><li>上昇率を最大化できます。</li><li>アクティビティの上昇率の精度が落ちます。</li></ul> |
| **カスタム配分** | 配分の割合を手動で調節します。 | <ul><li>想定どおりの結果が得られない場合もあります。 目安がわからない場合は、上述のいずれかのオプションを使用することをお勧めします。</li></ul> |

[!UICONTROL Control]の割合を調整するには、[!UICONTROL Traffic Allocation] ペインの[!UICONTROL Experiences]をクリックし、必要に応じて割合を調整します。 コントロールグループの割合を 10％未満にすることはできません。

[特定のエクスペリエンスを選択してコントロールとして使用](/help/main/c-activities/t-automated-personalization/experience-as-control.md)したり、ランダムエクスペリエンスオプションを使用したりできます。

## [!UICONTROL Automated Personalization]よりも[!UICONTROL Auto-Target]を選択するタイミング {#section_BBC4871C87944DD7A8B925811A30C633}

[!UICONTROL Automated Personalization]よりも[!UICONTROL Auto-Target]を使用するシナリオがいくつかあります。

* エクスペリエンスを形成するために自動的に組み合わされる個々のオファーではなく、エクスペリエンス全体を定義する場合。
* [!UICONTROL Auto Personalization]でサポートされていない[!UICONTROL Visual Experience Composer] （VEC）機能の完全なセットを使用する場合：カスタムコードエディター、複数のエクスペリエンスオーディエンスなど。
* 様々なエクスペリエンスでページに構造的な変更を加えたい場合。 例えば、ホームページ上の要素を並べ替えたい場合、[!UICONTROL Auto-Target]は[!UICONTROL Automated Personalization]よりも適切です。

## [!UICONTROL Auto-Target]と[!UICONTROL Automated Personalization]の共通点は何ですか？ {#section_2A601F482F9A44E38D4B694668711319}

### 訪問ごとに好ましい結果を得るためにアルゴリズムが最適化されます。

* アルゴリズムが訪問者のコンバージョン傾向（またはコンバージョンによる推定売上高）を予測して、最適なエクスペリエンスを提供します。
* 訪問者は、既存のセッションの終了時に新しいエクスペリエンスを利用できます（訪問者がコントロールグループに属していない場合、最初の訪問で割り当てられたエクスペリエンスは、その後の訪問でも同じままです）。
* セッション内では、ビジュアルの一貫性を保つために、予測は変わりません。

### 訪問者の行動の変化にアルゴリズムが対応します。

* マルチアームバンディットでは、モデルは常にトラフィックのごく一部を「消費」して、アクティビティ学習の全期間を通じて学習を継続し、それまでに学習したトレンドの乱用を防止します。
* 基盤となるモデルは、最新の訪問者行動データを使用して 24 時間ごとに再構築され、変化する訪問者の好みを [!DNL Target] が常に利用できるようになっています。
* 個人の勝者エクスペリエンスをアルゴリズムで特定できなかった場合は、パフォーマンスが全体として最も高いエクスペリエンスを表示する方式に自動的に切り替わりますが、パーソナライズされた勝者の特定は続行されます。 最もパフォーマンスが高いエクスペリエンスは、[トンプソンサンプリング](https://en.wikipedia.org/wiki/Thompson_sampling)によって割り出されます。

### 単一の目標指標に合わせて、アルゴリズムが絶えず最適化されます。

* この指標は、コンバージョンベースまたは収益ベース（より具体的には[!UICONTROL Revenue per Visit]）です。

### [!DNL Target] では、訪問者に関する情報を自動的に収集して、パーソナライゼーションモデルを構築します。

* [!UICONTROL Auto-Target]および[!UICONTROL Automated Personalization]で使用されるパラメーターについて詳しくは、[Automated Personalization Data Collection](/help/main/c-activities/t-automated-personalization/ap-data.md)を参照してください。

### [!DNL Target] では、[!DNL Adobe Experience Cloud] のすべての共有オーディエンスを自動的に使用して、パーソナライゼーションモデルを構築します。

* オーディエンスをモデルに追加するために、特別な作業を行う必要はありません。 [!DNL Experience Cloud Audiences] と [!DNL Target] を併用する方法について詳しくは、「[Experience Cloud オーディエンス](/help/main/c-integrating-target-with-mac/mmp.md)」を参照してください。

### マーケターは、オフラインデータや傾向スコアなどのカスタムデータをアップロードして、パーソナライゼーションモデルを構築することができます。

* [!UICONTROL Auto-Target]と[!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md)のデータのアップロードについて詳しくは、[を参照してください。

## [!UICONTROL Auto-Target]と[!UICONTROL Automated Personalization]の違いとは？ {#section_BA4D83BE40F14A96BE7CBC7C7CF2A8FB}

### [!UICONTROL Auto-Target]では、パーソナライズされたモデルを構築するために[!UICONTROL Automated Personalization]よりも少ないトラフィックが必要になることがよくあります。

[!UICONTROL Auto-Target]または[!UICONTROL Auto Personalization] モデルを構築するために必要なエクスペリエンスごとのトラフィック *数*&#x200B;は同じですが、通常、[!UICONTROL Automated Personalization] アクティビティには[!UICONTROL Auto-Target] アクティビティよりも多くのエクスペリエンスがあります。

例えば、2つの場所を持つ場所ごとに2つのオファーを作成した[!UICONTROL Auto Personalization] アクティビティがある場合、アクティビティに含まれる合計エクスペリエンスは4つ（2 = 4）になります（除外なし）。 [!UICONTROL Auto-Target]を使用すると、エクスペリエンス 1を設定して場所1にオファー1を含め、場所2にオファー2を含め、エクスペリエンス 2を場所1にオファー1を含め、場所2にオファー2を含めることができます。 [!UICONTROL Auto-Target]では、1つのエクスペリエンス内で複数の変更を選択できるので、アクティビティ内のエクスペリエンスの合計数を減らすことができます。

[!UICONTROL Auto-Target]では、経験則を使用してトラフィック要件を理解できます。

* **成功指標が[!UICONTROL Conversion]の場合：** 1,000回の訪問と1日あたりのコンバージョン数が50件以上で、さらにアクティビティには7,000回以上の訪問と350回のコンバージョンが必要です。
* **成功指標が[!UICONTROL Revenue per Visit]の場合：** 1 エクスペリエンスあたりの1日あたりの訪問数が1,000回、コンバージョン数が50以上で、さらにアクティビティには1 エクスペリエンスあたりのコンバージョン数が1,000回以上である必要があります。 訪問あたりの売上高の方が、通常、モデルの構築に多くのデータが必要になります。これは、コンバージョン率と比べて、訪問あたりの売上高の方が一般にデータ分散が大きいことが原因です。

### [!UICONTROL Auto-Target]には完全なセットアップ機能があります。

* [!UICONTROL Auto-Target]はA/B アクティビティワークフローに組み込まれているため、[!UICONTROL Auto-Target]はより成熟した本格的な[!UICONTROL Visual Experience Composer] （VEC）から恩恵を受けます。 [QA リンク ](/help/main/c-activities/c-activity-qa/activity-qa.md)を[!UICONTROL Auto-Target]と共に使用することもできます。

### [!UICONTROL Auto-Target]は、広範なオンライン テスト フレームワークを提供します。

* マルチアームバンディットは、[!DNL Adobe] のデータサイエンティストや研究者が現実の状況における継続的な改善のメリットを把握できるようにする、より大規模なオンラインテストフレームワークの一部となっています。
* 将来的には、このテストベッドにより、[!DNL Adobe] マシンラーニングプラットフォームをデータに精通した顧客に対してオープンし、顧客が独自のモデルを取り込んで[!DNL Target] モデルを拡張できるようにします。

## レポートと[!UICONTROL Auto-Target] {#section_42EE7F5E65E84F89A872FE9921917F76}

詳しくは、[レポートと自動ターゲット](/help/main/c-activities/auto-target/reporting-and-auto-target.md)を参照してください。

