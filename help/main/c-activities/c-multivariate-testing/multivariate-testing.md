---
keywords: 多変量分析テスト、mvt、full 因子、mvt または a/b、multivariate a/b、トラフィック見積もり、mvt を使用する場合、mvt considerations、multivariate、partial-factorial、partial-factorial、full-factorial
description: AdobeでのMultivariate Testing(MVT) の使用方法を説明します [!DNL Target] ページ上の要素内のオファーの組み合わせを比較し、どの組み合わせが最も効果が高いかを判断します。
title: 多変量分析テストとは
feature: Multivariate Tests
exl-id: c8b60011-cb3a-4e28-b84f-06910687b14b
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1460'
ht-degree: 88%

---

# 多変量分析テストの概要

[!DNL Adobe Target] の[!UICONTROL 多変量分析テスト]（MVT）では、ページ上の要素内のオファーの組み合わせを比較し、特定のオーディエンスに対して最も効果が高い組み合わせと、アクティビティの成功に最も効果が高い要素を特定します。

## MVT の概要 {#section_C73A2D1409EC42C9B0EDD4B976651C5E}

多変量分析テストは、特定の要素をページ上の他の要素と比較して、コンバージョンに対する相対的な影響を明らかにするために役立ちます。また、効果的であることが証明された要素の組み合わせを調節するためにも役立ちます。

A/B テストと比較した多変量分析テストのメリットの 1 つとして、最もコンバージョンに効果のあるページ上の要素を示すことができます。これは、「主効果」とも呼ばれます。この情報は、例えば、最も注目を集めたいコンテンツを配置する場所を決定する場合などに役立ちます。

また、多変量分析テストでは、ページ上の 2 つ以上の要素の複合的な効果を測定することもできます。例えば、特定の広告は、特定のバナーやメイン画像と組み合わせると、より多くのコンバージョンを生み出す場合があります。これは、「交互作用効果」とも呼ばれます。

[!DNL Target] では、コンテンツの最適化に役立つように、全因子多変量分析テストが使用されます。全因子多変量分析テストでは、コンテンツのすべての可能な組み合わせを、同じ確率でテストします。例えば、それぞれ 3 つのオファーが組み込まれたページ要素が 2 つある場合は、9 つの組み合わせ（3 x 3）になります。3 つの要素があり、そのうちの 2 つの要素に 3 つのオファーが、1 つの要素に 2 つのオファーが組み込まれている場合は、組み合わせは 18（3 x 3 x 2）になります。

Target では、各組み合わせが 1 つのエクスペリエンスになります。多変量分析テストでは、各エクスペリエンスを比較して、どの組み合わせが最も効果が高いかを判断できます。同時に、データを収集および分析して、各場所およびオファーが成功指標にどのような影響を与えているかを把握できます。

![](assets/multivariate.png)

多変量分析テストでは、生成される組み合わせの数が多くなる場合があるので、A/B テストよりも多くの時間とトラフィックが必要になります。各エクスペリエンスに対して統計的に有意な結果を得るためには、ページに十分なトラフィックが必要です。有用な結果を得るには、ページで発生するトラフィック量を把握して、必要な結果を得るのに適した時間にわたって最適な数の組み合わせをテストする必要があります。Target の[トラフィック見積もり](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714)を使用すると、サイトのトラフィックに適したテストを設計できます。トラフィック見積もりを使用する前に、サイトで通常発生するインプレッションおよびコンバージョンの数を示す、優れた統計が必要です。1 日あたりのトラフィックレベルを考慮します。アクティビティにおけるエクスペリエンスの数が多いほど、そのアクティビティにはより多くのトラフィックが必要になり、またそのアクティビティを長い時間実行する必要があります。トラフィックがあまり多くない場合は、少数の組み合わせをテストする必要があります。組み合わせの数を少なくしないと、有意なテスト結果を得るために必要な時間があまりに長くなってしまう場合があります。

## MVT の用語 {#section_DF475CA7F34B4CFDB7BE7363761D64AE}

いくつかの基本的な用語を理解しておくと、多変量分析テストを設定する場合に役立ちます。

業界全体で様々な意味で使用されている用語がいくつかあります。ここでは、[!DNL Target] で使用される用語を定義します。

**組み合わせ：**&#x200B;複数の場所で複数のコンテンツオプションをテストする場合に作成するコンテンツのバリエーション。例えば、3 つの場所でそれぞれ 3 つのコンテンツオプションをテストする場合、可能な組み合わせは 27（3 x 3 x 3）になります。サイトの訪問者には、そのうちの 1 つの組み合わせが表示されます。これは「エクスペリエンス」とも呼ばれます。

**コンテンツ：**&#x200B;ある場所でのテストのバリエーションを構成するテキストまたは画像。多変量分析テストでは、複数の場所にある複数のコンテンツオプションが比較されます。MVT 手法では、コンテンツは「*レベル*」と呼ばれる場合があります。

**要素：** MVT テストでテストするコンテンツのバリエーションを含む DOM 要素。*場所*&#x200B;も参照してください。

**場所：**&#x200B;ページ上の特定のコンテンツ領域。多くの場合、単一の DOM 要素に含まれています。MVT の方法論においては、場所は「*因子*」と呼ばれることもあります。全因子多変量分析テストでは、場所におけるすべての可能なオファーの組み合わせが比較されます。

## MVT と A/B を使用するタイミング {#section_3D2B966B6671406C861A1843EA41D28C}

多変量分析テストは、A/B テストと併用して、ページを最適化することができます。これらのテストは、次のような場合に併用します。

* A/B テストを使用してページレイアウトを最適化し、その後に MVT テストを実行してページの各要素に表示する最適なコンテンツを決定します。 

   A/B テストでは、レイアウトについての重要なフィードバックが提供されます。他方、MVT テストは、ページデザインの要素内のコンテンツのテストに優れています。複数のコンテンツオプションをテストする前に、レイアウトに対して A/B テストを実行することで、最適なレイアウトを決定したうえで、最も効果的なコンテンツを決定できます。

* MVT テストを使用してどの要素が最も重要かを判断し、その後その要素に絞って A/B テストを実行します。

   異なるエクスペリエンスの数が 5 を超え、2 つ以上の要素にまたがる場合は、A/B テストを実行する前に MVT テストを検討することをお勧めします。 MVT テストによって、コンバージョンが向上する可能性が最も高そうなページ領域を判定できます。マーケティング担当者は、これらの要素に重点を置いてテストをおこなうことができます。例えば、MVT テストによって、目標を達成するための最も重要な要素がコールトゥアクションであることがわかります。目標を達成するために最も有用な要素およびコンテンツを特定したら、A/B テストを実行して、さらに結果を絞り込むことができます。例えば、2 つの異なる画像を比較してテストしたり、コールトゥアクションの言葉遣いや色を比較したりできます。MVT テストの後に 1 つ以上の A/B テストをおこなうことで、目的の結果を得るための最良のコンテンツを判断できます。

## 注意点 {#section_979FE3F398654C1EA1C86E7DBC9A8DAD}

* MVT テストは、テストする要素が 3 つ以上ある場合に使用します。3 つ未満の場合は、一連の A/B テストを実行します。
* 結果に最も影響を与えるページ要素を選択します。
* 1 つのテストに組み込む要素や場所の数が多くなりすぎないようにします。数が多くなるほど、テストにかかる時間が長くなります。
* 事前にテスト設計を計画しておきます。運用が開始され、データの収集と分析が開始された後は、テストを編集しないことをお勧めします。
* 要素は互いに独立したものであることをお勧めします。

   例えば、同じテスト内でレイアウトとコンテンツをテストしないでください。

* エクスペリエンスの数が多くなるので、計画段階でテストに十分な時間を割り当て、品質を確保します。また、部分因子テストを使用して、多変量分析テストに必要なトラフィック量を減らすこともできます。 詳しくは、以下の「部分因子テスト」を参照してください。

## 部分因子テスト

[!DNL Target] では、全因子多変量分析テストがビルトインアクティビティオプションとして用意されています。統計において、実験計画法は、どの因子が結果に影響を与えるかを判断するためのアプローチまたはデザインを数多く提供します。その一つが、 [田口メソッド](https://en.wikipedia.org/wiki/Taguchi_methods) 部分因子テスト用の 田口メソッドにより、マーケティング担当者は一連の前提を作成して、テストする必要があるエクスペリエンスの順列の数を減らすことができます。その結果、多変量テストのトラフィック要件が小さくなります。この機能とテストのアプローチは、この[オフラインスプレッドシート](/help/main/assets/MVT-Taguchi-Partial-Factorial-Design-02102017.xlsx)を使用することで [!DNL Target] で利用できます。

チームで他の実験計画法アプローチを使用している場合は、この計算スプレッドシートをカスタム実験デザインのリファレンス実装として使用できます。

オフライン計算スプレッドシートを使用する際は、次のヒントを考慮してください。

* 変更する要素と各要素のバージョン数（3x2、4x3 など）を選択します。
* 番号付けの方法には一貫性を持たせます。例えば、ボタンが要素 1 で、オプションが青、緑、黄の場合、青色のボタンを 1-1、緑色のボタンを 1-2、黄色のボタンを 1-3 とします。
* オフラインスプレッドシートには、必要になるエクスペリエンスの数が示されています（例えば、3x2 の場合は 4 つ、4x3 の場合は 9 つ）。
* [Visual Experience Composer（VEC）](/help/main/c-experiences/experiences.md)を使用して A/B ワークフローのエクスペリエンスを構築します。カスタムコードの使用、HTML の編集、WYSIWYG または任意の組み合わせを使用できます。
* （サンプルサイズ計算ツールに基づいて）アクティビティが終了したら、スプレッドシートで結果を処理して、他の詳細を取得します。

その他の考慮事項およびベストプラクティスについては [、多変量分析テストのベストプラクティス](/help/main/c-activities/c-multivariate-testing/best-practices.md#reference_53635817FFB741EF8C4E56CC70688EDD) を参照してください。

## トレーニングビデオ

以下のビデオは、この記事で説明する概念についてさらに詳しく説明しています。

### アクティビティタイプ（9:03）![概要バッジ](/help/main/assets/overview.png)

この概要ビデオでは、Target Standard/Premium で利用できるアクティビティのタイプについて説明します。 多変量分析テストに関する説明は 4:20 から始まります。

* [!DNL Adobe Target] に含まれるアクティビティのタイプの説明
* 目標達成に適したアクティビティタイプの選択
* すべてのアクティビティタイプに適用される 3 ステップのガイドによるワークフローについての説明

>[!VIDEO](https://video.tv.adobe.com/v/17386)

### 多変量分析テストの作成(9:25) ![チュートリアルバッジ](/help/main/assets/tutorial.png)

このビデオでは、Target の 3 ステップのガイドによるワークフローを使用して、多変量分析テストを理解、計画、作成する方法について説明しています。

* 多変量分析テストの定義と設計
* 多変量分析テストの作成

>[!VIDEO](https://video.tv.adobe.com/v/17395)