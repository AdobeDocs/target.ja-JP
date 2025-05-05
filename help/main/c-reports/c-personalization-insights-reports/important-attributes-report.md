---
keywords: ターゲット設定;AP レポート;Automated Personalizationレポート;自動ターゲット;自動的なターゲット;自動ターゲットレポート;自動的なターゲットのレポート;パーソナライゼーション;インサイト;FAQ;よくある質問;重要な属性
description: パーソナライゼーションモデルに影響を与えた上位の属性とその相対的な重要度を示す [!UICONTROL Important Attributes] レポートの使用方法を説明します。
title: 重要な属性レポートとは
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Reports
exl-id: c1069ca7-e221-4865-a82e-6cff5b4c0055
source-git-commit: c1a71d1fb6fa9b5c14e22fa3199358a4594bb4a1
workflow-type: tm+mt
source-wordcount: '1773'
ht-degree: 56%

---

# 重要な属性レポート

[!UICONTROL Automated Personalization] （AP）および [!UICONTROL Auto-Target] （AT）アクティビティのユーザーが使用できる 2 つの特殊なレポートの 1 つである [!UICONTROL Important Attributes] レポートに関する情報です。

>[!NOTE]
>
>[!UICONTROL Personalization Insights] レポートを使用する場合は、次の点を考慮してください。
>
>* AP および AT アクティビティは、[!DNL Target Premium] ソリューションの一部です。これらは、[!DNL Target Premium] ライセンスのない [!DNL Target Standard] には付属していません。
>
>* [!UICONTROL Personalization Insights] レポートは、コンバージョン最適化目標を使用する AP アクティビティと AT アクティビティでのみ使用できます。 アクティビティがライブになった後で最適化目標が売上高からコンバージョンに変更されたアクティビティもサポートされません。
>
>* [!UICONTROL Personalization Insights] のレポートは、「[!UICONTROL Report Metric]」ドロップダウンリストから [!UICONTROL Primary Goal] が選択されている場合にのみ使用できます。
>
>* [!UICONTROL Personalization Insights] レポートは、[ デフォルト環境 ](/help/main/administrating-target/hosts.md) でのみサポートされます。
>
>* [!UICONTROL Personalization Insights] レポートは、[!UICONTROL Live] ステータスのアクティビティのうち、アクティブ化され、トラフィックの受信が 15 日以上行われたものについてのみ生成されます。

異なるアクティビティでは、モデルによるパーソナライゼーションの決定にとって重要な属性も多かれ少なかれ異なります。このレポートは、モデルに影響を及ぼした上位の属性とそれら属性の相対的重要性を示します。

## [!UICONTROL Important Attributes] レポートへのアクセス {#section_8E8F997AAAF44A1B9EE06EB6FB652801}

1. 「**[!UICONTROL Activities]**」をクリックし、目的の [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9) または [ 自動ターゲット ](/help/main/c-activities/auto-target/auto-target-to-optimize.md) アクティビティをリストからクリックします。

   アクティビティが多数ある場合は、フィルター（![ フィルターアイコン ](/help/main/assets/icons/Filter.svg)）アイコンをクリックし、「[!UICONTROL Type]」、「[!UICONTROL Status]」、「[!UICONTROL Reporting Source]」、「[!UICONTROL Experience Composer]」、「[!UICONTROL Metrics Type]」、「[!UICONTROL Activity Source]」の各ドロップダウンリストからオプションを選択してリストをフィルタリングします。

1. **[!UICONTROL Reports]** をクリックします。

   アクティビティのパフォーマンスに関する情報を提供する [&#128279;](/help/main/c-reports/personalization-reports/reports-ap.md)0&rbrace;Automated Personalizationの概要 [ 自動ターゲットの概要 ](/help/main/c-reports/personalization-reports/auto-target-summary-report.md) レポートが、最初の画面アイコンで表示されます。 2 つの追加のアイコンは、2 つの [!UICONTROL Personalization Insights] レポートを表しています。**[!UICONTROL Automated Segments]** （![ 自動セグメントレポート ](/help/main/assets/icons/AutomatedSegment.svg)）と **[!UICONTROL Important Attributes]** （![ 重要な属性アイコン ](/help/main/assets/icons/ViewList.svg)）です。


   [!UICONTROL Auto-Target] には、[!UICONTROL Summary] レポートをグラフィカルに表示するための追加のグラフアイコンがあります。

   >[!IMPORTANT]
   >
   >[!UICONTROL Important Attributes] レポートは、アクティビティをアクティブ化してから少なくとも 15 日後までは使用できません。 この最初の期間は、このレポートにアクセスしたり、[!UICONTROL Important Attributes] のアイコンをクリックしたりすることはできません。 15 日が経過すると、アクティビティに十分なパーソナライズされたトラフィックがあると仮定して、[!UICONTROL Important Attributes] レポートを使用できるようになります。

1. アクティビティをアクティブ化してから 15 日後に、**[!UICONTROL Important Attributes]** 定（![ 重要な属性アイコン ](/help/main/assets/icons/ViewList.svg)）アイコンをクリックします。

1. 目的の日付範囲を選択します。

   [!UICONTROL Summary] レポート（パフォーマンスレポート）とは異なり、[!UICONTROL Important Attributes] を含む [!UICONTROL Personalization Insights] は、15 日、30 日および 60 日の固定日付範囲でのみ使用できます。

   これらの固定日付範囲を使用 [!UICONTROL Personalization Insights] ると、十分な範囲のデータを使用して、アクティビティの短時間のみ有効なパターンからインサイトを導き出す可能性を低くすることができます。 日付範囲について決定できるのは、「終了日」と「期間」の 2 つです。「開始日」はグレー表示になっています。開始日は、選択した終了日と期間に基づいて自動的に変わります。

   使用可能な固定日付範囲には、「[!UICONTROL Preset Date Range]」ドロップダウンリストからアクセスできます。

1. [!UICONTROL Important Attributes] レポートデータを確認します。

1. （任意）「ダウンロード」（![ ダウンロードアイコン ](/help/main/assets/icons/Download.svg)）アイコンをクリックして [ レポートを CSV 形式でダウンロード ](/help/main/c-reports/c-report-settings/report-settings.md#section_77E65C50BAAF4AB79242DB3A8778ADEF) し、Excel やその他のツールで分析します。

   >[!NOTE]
   >
   >パーソナライゼーションインサイトの UI レポートには、限定された情報のみ含まれています。重要な属性レポートの CSV ダウンロードには、さらに詳細な情報が含まれています。重要な属性レポートのダウンロードには、上位 100 個の属性の完全なリストが含まれていますが、UI レポートには上位 10 個の属性のみ含まれています。レポートで特定の属性を探しても見つからない場合は、その属性がアクティビティに影響を及ぼさなかったわけではなく、ただ上位 100 個の属性のリストに含まれなかっただけです。

## 重要な属性レポートの解釈

レポートの要素と解釈方法について、次の表で説明します。

| 要素 | 詳細 |
|--- |--- |
| 棒グラフ | 画面上部にある多色の横向き棒グラフでは、これらの相対的重要度スコアを視覚化し、表内の各属性の横にあるドットの色にマッピングさせることができます。棒グラフの特定の色にマウスポインターを置くと、その色で表される属性が表示されます。上位 100 個の属性の重要度スコアを加算すると 100% になります。Target のパーソナライゼーションモデルで使用できる属性をさらに追加する方法について詳しくは、[Target のPersonalization アルゴリズム用のデータのアップロード ](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md) を参照してください。 |
| モデル属性ランキンググラフ | モデル属性ランキングには、各訪問者にどのようなコンテンツを表示するかを Target のパーソナライゼーションモデルで決定するうえで最も重要であった上位 10 個の属性が含まれています。重要度スコアは、このアクティビティにおける Target のパーソナライゼーションモデルにとって特定の属性がどの程度重要であったかを、上位 100 個の属性を基準にして示します。 |

## 重要な属性に関する FAQ {#section_740910A52FA646B4AC9452F98C2F5719}

[!UICONTROL Important Attributes] レポートの使用に関するよくある質問への回答については、次の FAQ を参照してください。

### Personalization Insights レポートは、まだアクティビティで使用できません。 なぜでしょう？

[!UICONTROL Personalization Insights] のレポートがアクティビティでまだ使用できない可能性がある理由はいくつかあります。

* アクティビティをアクティブ化してからまだ 15 日経過していません。アクティビティを開始してから 15 日以上経過するまで、自動セグメントレポートと重要な属性レポートは使用できません。この初期期間中は、これらのレポートにアクセスできません。また、自動セグメントアイコンと重要な属性アイコンをクリックすることもできません。
* 指定した期間中、アクティビティに十分なトラフィックがありませんでした。15 日が経過したら、パーソナライゼーションモデルを構築できるだけの[パーソナライズされた十分なトラフィック](/help/main/c-activities/auto-target/auto-target-to-optimize.md#section_BA4D83BE40F14A96BE7CBC7C7CF2A8FB)がアクティビティにあると仮定して、自動セグメントレポートと重要な属性レポートを使用できるようになります。
* お客様のアクティビティに売上高最適化目標があります。現時点では、[!UICONTROL Personalization Insights] はコンバージョンの最適化目標アクティビティでのみ使用できます。 今後のリリースで、売上高最適化目標のアクティビティもサポートする予定です。

### 属性とは

属性は、訪問者または訪問者の特定の訪問に関する情報で、トラフィックのパーソナライズ方法を知るためにパーソナライゼーションアルゴリズムで使用されます。例えば、ブラウザータイプ、場所、訪問時刻などが属性になります。

[!DNL Target] でパーソナライゼーションモデルで使用される属性について詳しくは、[Target のパーソナライゼーションアルゴリズムのデータ収集](/help/main/c-activities/t-automated-personalization/ap-data.md)を参照してください。Target のパーソナライゼーションモデルで使用する新しい属性を Target にアップロードする方法について詳しくは、[Target にデータを取得する方法 ](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=ja){target=_blank} を参照してください。

### モデルでトレーニングに使用する必要がない属性が 1 つ以上表示されます。これらの属性をトレーニングモデルから削除できますか？ {#models-api}

この [!UICONTROL Models API] はブロックリスト API とも呼ばれ、[!UICONTROL Automated Personalization] （AP）および [!UICONTROL Auto-Target] （AT） アクティビティの機械学習モデルで使用される属性（機能とも呼ばれます）のリストを表示および管理できます。 モデルが AP または AT アクティビティに使用する 1 つ以上の属性を除外する場合は、Models API を使用して、それらの属性を「ブロックリスト」に追加できます。

詳しくは、*Adobe Target開発者ガイド [&#128279;](https://experienceleague.adobe.com/docs/target-dev/developer/api/models-api/models-api.html?lang=ja){target=_blank} の Models API の概要* を参照してください。 API を使用して属性をブロックするには、[Models API](https://experienceleague.adobe.com/docs/target-dev/developer/api/models-api/models-api-overview.html?lang=ja){target=_blank} を参照してください。

### [!UICONTROL Automated Segments] および [!UICONTROL Important Attributes] レポートの情報は、CSV ダウンロードの情報と同じですか？

いいえ、UI レポートには、限定された情報のみ含まれています。CSV ダウンロードには、追加の詳細情報が含まれています。自動セグメントインサイトレポートのダウンロードには、UI に含まれている上位セグメント以外のセグメントのほか、オファーやエクスペリエンスに対するこれらのセグメントのパフォーマンスが含まれています。重要な属性レポートには、上位 100 個の訪問者属性とそれらの相対的重要度が含まれていますが、UI には上位 10 個の訪問者属性のみ含まれます。

### カスタムの日付範囲でPersonalization Insights を表示できますか？

Personalization Insights レポート（[!UICONTROL Automated Segments] と [!UICONTROL Important Attributes] の両方）は、15 日、30 日、45 日、60 日および 90 日の固定日付範囲でのみ使用できます。 これらの固定日付範囲を使用 [!UICONTROL Personalization Insights] ると、十分な範囲のデータを使用して、アクティビティの短時間のみ有効なパターンからインサイトを導き出す可能性を低くすることができます。 これらの期間は任意の終了日に対して選択できます（期間を満たすのに十分なデータがアクティビティにある場合）。

### [!UICONTROL Personalization Insights] はどのように作成されますか？

[!UICONTROL Personalization Insights] は、MAGIX （Model Agnostic Globally Interpretable Explanations）と呼ばれるAdobe特許出願中の手法を使用して作成されます。 MAGIX の詳細については、[arXiv.org web サイト ](https://arxiv.org/abs/1706.07160) に公開されているAdobe研究チームの論文を参照してください。

### 収益ベースのモデリング目標/メイン目標に [!UICONTROL Personalization Insights] を使用できますか。

現時点では、[!UICONTROL Personalization Insights] はコンバージョンの最適化目標アクティビティでのみ使用できます。 今後のリリースで、売上高最適化目標のアクティビティもサポートする予定です。

### 重要属性レポートの属性重要度スコアとは

レポートの「属性重要度ランキング」の重要度スコアを見れば、すべての訪問者を識別済みのセグメントに分類する方法をアルゴリズムで決定したとき、学習に使用された変数のうち最も重要であったものがわかります。モデルで使用された上位 100 個の属性には、パーセントスコアが割り当てられています。

### 特定の自動セグメントで、コンバージョン率の低い一部のオファー/エクスペリエンスが他のオファー/エクスペリエンスに比べて大量のトラフィックを受信するのはなぜですか？

自動セグメント内のコンバージョン率の低いオファーやエクスペリエンスの方が訪問数が多い場合、考えられる理由は、以下のようにいくつかあります。

* 特定の自動セグメントのオファー／エクスペリエンスの一部またはすべてについて、ビュー数が少ない。
* 特定のオファーやエクスペリエンスでモデルを作成しない、ボリュームの小さいアクティビティ。
* 一部のオファーやエクスペリエンスに対して、他よりも早くモデルが作成された、ボリュームの小さいアクティビティ。例えば、追加のモデル が 22 日目に作成され、10 ～ 24 日のデータを調べる場合があります。
* どの訪問者にどのオファー／エクスペリエンスが表示されるかを制限する特定のオファーにターゲットルールが設定されている。
* インサイトレポートに信頼区間がない。ただし、コンバージョン率が十分に近い場合、モデルはトラフィックを提供する可能性があるので、ポイント量は多くなりますが、数値が「統計的に異なる」わけではありません。

トラフィックを提供するモデルがどのように機能するかを知ることは有用です。各個人は、それぞれの合計プロファイルに基づいて提供されます。ただし、インサイトレポートは、この動作を一般化して、人間が解釈しやすいものにします。結果として、セグメントは相互に排他的ではありません。同一人物が複数のセグメントに現れる可能性があるので、個々のセグメントでこのタイプの動作が表示されることになる可能性があります。

### Personalization Insights で情報を活用する様々な方法を教えてください。

* ターゲットとなる新しいオーディエンスを発見します。パフォーマンスが特に良い特定の自動セグメントが見つかったら、そのセグメントを他のレポートで再利用できるようにオーディエンスを作成することを検討するとよいでしょう。
* どのようなタイプの訪問者がどのエクスペリエンスに反応するかについての仮説を検証します。
* どのようなコンテンツがどのような種類の訪問者に対して機能したか、どのようなオファーがどの訪問者に効果的であったかについてのインサイトを得ます。
* パフォーマンスの悪いコンテンツを特定します。
* モデルの学習に最も重要であった属性を把握します。
* パーソナライゼーションモデルで使用される属性と、それらの重要度を確認します。
* Target に追加のデータポイントを渡して、パーソナライゼーションに役立つ情報を拡充する機会を特定します。

## 既知の問題

次の問題は、現在、[!DNL Target] エンジニアリングチームによって調査中です。

* セグメント名 [!DNL Adobe Experience Platform]、[!UICONTROL Automated Personalization] （AP）および [!UICONTROL Auto-Target] （AT）アクティビティの [!UICONTROL Important Attributes] レポートに表示されません。 （上位 3813 項目）
