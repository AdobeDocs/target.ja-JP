---
keywords: ターゲティング;AP レポート;Automated Personalizationレポート;自動ターゲット;自動的なターゲット;自動ターゲットレポート;自動的なターゲットのレポート;パーソナライゼーション;インサイト;FAQ;よくある質問;重要な属性
description: パーソナライゼーションモデルに影響を与えた上位の属性とその相対的な重要度を示す[!UICONTROL Important Attributes] レポートの使用方法について説明します。
title: 重要な属性レポートとは何ですか？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Reports
exl-id: c1069ca7-e221-4865-a82e-6cff5b4c0055
TQID: https://experienceleague.adobe.com/4G8mYap2O5RW5wr9YvXEaHm2k-oNQVVCHyKv4ltaNHo
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: adee20bd-51f4-461d-b9db-d215f8756eebid: c93393a4-e558-47e1-992e-c91ed4d480ce
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1id: d3cdead0-685a-4489-9250-4bb709942f66id: e0eb8757-182f-49f3-94a4-1587d16f5094id: e1e0219c-f879-479f-8427-888ed2a6e9c2id: eb30f47f-d87a-400f-8f78-63ce7979ff56
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 1835
ht-degree: 58%

---

# 重要な属性レポート

[!UICONTROL Important Attributes] レポートに関する情報。これは、[!UICONTROL Automated Personalization] （AP）および[!UICONTROL Auto-Target] （AT）アクティビティのユーザーが利用できる2つの専用レポートのうちの1つです。

>[!NOTE]
>
>[!UICONTROL Personalization Insights]件のレポートを使用する場合は、次の点を考慮してください。
>
>* AP および AT アクティビティは、[!DNL Target Premium] ソリューションの一部です。 これらは、[!DNL Target Premium] ライセンスのない [!DNL Target Standard] には付属していません。
>
>* [!UICONTROL Personalization Insights]件のレポートは、コンバージョンの最適化目標を使用するAPおよびAT アクティビティでのみ使用できます。 アクティビティがライブになった後で最適化目標が売上高からコンバージョンに変更されたアクティビティもサポートされません。
>
>* [!UICONTROL Personalization Insights] レポートは、[!UICONTROL Report Metric] ドロップダウンリストから[!UICONTROL Primary Goal]が選択されている場合にのみ使用できます。
>
>* [!UICONTROL Personalization Insights]件のレポートは、[既定の環境](/help/main/administrating-target/hosts.md)でのみサポートされています。
>
>* [!UICONTROL Personalization Insights] レポートは、[!UICONTROL Live] ステータスで、少なくとも15日間アクティブ化され、トラフィックを受信しているアクティビティに対してのみ生成されます。

異なるアクティビティでは、モデルによるパーソナライゼーションの決定にとって重要な属性も多かれ少なかれ異なります。 このレポートは、モデルに影響を及ぼした上位の属性とそれら属性の相対的重要性を示します。

## [!UICONTROL Important Attributes] レポートにアクセス {#section_8E8F997AAAF44A1B9EE06EB6FB652801}

1. **[!UICONTROL Activities]**&#x200B;をクリックし、リストから目的の[Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9)または[自動ターゲット ](/help/main/c-activities/auto-target/auto-target-to-optimize.md) アクティビティをクリックします。

   アクティビティが多い場合は、フィルター（![ フィルターアイコン ](/help/main/assets/icons/Filter.svg)）アイコンをクリックして、[!UICONTROL Type]、[!UICONTROL Status]、[!UICONTROL Reporting Source]、[!UICONTROL Experience Composer]、[!UICONTROL Metrics Type]、および[!UICONTROL Activity Source] ドロップダウンリストからオプションを選択してリストをフィルタリングします。

1. **[!UICONTROL Reports]** をクリックします。

   [Automated Personalizationの概要](/help/main/c-reports/personalization-reports/reports-ap.md)または[自動ターゲットの概要](/help/main/c-reports/personalization-reports/auto-target-summary-report.md) レポートが表示され、アクティビティのパフォーマンスに関する情報が最初の画面アイコンで表示されます。 追加された2つのアイコンは、2つの[!UICONTROL Personalization Insights] レポートを表します：**[!UICONTROL Automated Segments]** （![自動セグメントレポート ](/help/main/assets/icons/AutomatedSegment.svg)）と&#x200B;**[!UICONTROL Important Attributes]** （![重要な属性アイコン ](/help/main/assets/icons/ViewList.svg)）。


   [!UICONTROL Auto-Target]には、[!UICONTROL Summary] レポートのグラフィック表示に追加のグラフアイコンがあります。

   >[!IMPORTANT]
   >
   >アクティビティをアクティブ化してから少なくとも15日後まで、[!UICONTROL Important Attributes] レポートは利用できません。 この初期の期間では、このレポートにアクセスしたり、[!UICONTROL Important Attributes] アイコンをクリックしたりすることはできません。 アクティビティに十分なパーソナライズされたトラフィックがあると仮定して、15日が経過すると、[!UICONTROL Important Attributes] レポートが使用可能になります。

1. アクティビティをアクティブ化してから15日後に、**[!UICONTROL Important Attributes]** （![重要な属性アイコン ](/help/main/assets/icons/ViewList.svg)）アイコンをクリックします。

1. 目的の日付範囲を選択します。

   [!UICONTROL Summary] レポート （パフォーマンス レポート）とは異なり、[!UICONTROL Important Attributes]を含む[!UICONTROL Personalization Insights]は、15日、30日、60日の固定日付範囲でのみ使用できます。

   これらの固定日付範囲を使用すると、[!UICONTROL Personalization Insights]は十分な範囲のデータを使用して、アクティビティの短期的なパターンからインサイトを導き出す可能性を減らすことができます。 日付範囲について決定できるのは、「終了日」と「期間」の 2 つです。 「開始日」はグレー表示になっています。 開始日は、選択した終了日と期間に基づいて自動的に変わります。

   使用可能な固定日付範囲には、[!UICONTROL Preset Date Range] ドロップダウンリストからアクセスできます。

1. [!UICONTROL Important Attributes] レポートデータを確認します。

1. （オプション）ダウンロード（![ ダウンロードアイコン ](/help/main/assets/icons/Download.svg)）アイコンをクリックして、[Excelやその他のツールでの分析用にCSV形式](/help/main/c-reports/c-report-settings/report-settings.md#section_77E65C50BAAF4AB79242DB3A8778ADEF)でレポートをダウンロードします。

   >[!NOTE]
   >
   >パーソナライゼーションインサイトの UI レポートには、限定された情報のみ含まれています。 重要な属性レポートの CSV ダウンロードには、さらに詳細な情報が含まれています。 重要な属性レポートのダウンロードには、上位 100 個の属性の完全なリストが含まれていますが、UI レポートには上位 10 個の属性のみ含まれています。 レポートで特定の属性を探しても見つからない場合は、その属性がアクティビティに影響を及ぼさなかったわけではなく、ただ上位 100 個の属性のリストに含まれなかっただけです。

## 重要な属性レポートの解釈

レポートの要素と解釈方法について、次の表で説明します。

| 要素 | 詳細 |
|--- |--- |
| 棒グラフ | 画面上部にある多色の横向き棒グラフでは、これらの相対的重要度スコアを視覚化し、表内の各属性の横にあるドットの色にマッピングさせることができます。 棒グラフの特定の色にマウスポインターを置くと、その色で表される属性が表示されます。  上位 100 個の属性の重要度スコアを加算すると 100% になります。 Targetのパーソナライゼーションモデルで使用できる属性をさらに追加する方法について詳しくは、[TargetのPersonalization アルゴリズム用のデータのアップロード ](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md)を参照してください。 |
| モデル属性ランキンググラフ | モデル属性ランキングには、各訪問者にどのようなコンテンツを表示するかを Target のパーソナライゼーションモデルで決定するうえで最も重要であった上位 10 個の属性が含まれています。 重要度スコアは、このアクティビティにおける Target のパーソナライゼーションモデルにとって特定の属性がどの程度重要であったかを、上位 100 個の属性を基準にして示します。 |

## 重要な属性に関する FAQ {#section_740910A52FA646B4AC9452F98C2F5719}

[!UICONTROL Important Attributes] レポートの使用に関してよく寄せられる質問に対する回答については、次のFAQを参照してください。

### Personalization インサイトレポートは、まだ自分のアクティビティで使用できません。 なぜでしょうか？

[!UICONTROL Personalization Insights] レポートがまだアクティビティで利用できない理由がいくつかあります。

* アクティビティをアクティブ化してからまだ 15 日経過していません。 アクティビティを開始してから 15 日以上経過するまで、自動セグメントレポートと重要な属性レポートは使用できません。 この初期期間中は、これらのレポートにアクセスできません。また、自動セグメントアイコンと重要な属性アイコンをクリックすることもできません。
* 指定した期間中、アクティビティに十分なトラフィックがありませんでした。 15 日が経過したら、パーソナライゼーションモデルを構築できるだけの[パーソナライズされた十分なトラフィック](/help/main/c-activities/auto-target/auto-target-to-optimize.md#section_BA4D83BE40F14A96BE7CBC7C7CF2A8FB)がアクティビティにあると仮定して、自動セグメントレポートと重要な属性レポートを使用できるようになります。
* お客様のアクティビティに売上高最適化目標があります。 現時点では、[!UICONTROL Personalization Insights]はコンバージョン最適化の目標アクティビティでのみ使用できます。 今後のリリースで、売上高最適化目標のアクティビティもサポートする予定です。

### 属性とは？

属性は、訪問者または訪問者の特定の訪問に関する情報で、トラフィックのパーソナライズ方法を知るためにパーソナライゼーションアルゴリズムで使用されます。 例えば、ブラウザータイプ、場所、訪問時刻などが属性になります。

[!DNL Target] でパーソナライゼーションモデルで使用される属性について詳しくは、[Target のパーソナライゼーションアルゴリズムのデータ収集](/help/main/c-activities/t-automated-personalization/ap-data.md)を参照してください。 新しい属性を Target にアップロードして Target のパーソナライゼーションモデルで使用する方法について詳しくは、[データを Target に送信する方法](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=ja){target=_blank}を参照してください。

### モデルでトレーニングに使用する必要がない属性が 1 つ以上表示されます。 これらの属性をトレーニングモデルから削除できますか？ {#models-api}

[!UICONTROL Models API]は、[!UICONTROL Automated Personalization] （AP）および[!UICONTROL Auto-Target] （AT）アクティビティのマシンラーニングモデルで使用される属性（機能とも呼ばれる）のリストを表示および管理できます。この機能は、ブロックリスト APIとも呼ばれます。 APまたはAT アクティビティのモデルで使用される1つ以上の属性を除外する場合は、Models APIを使用して、これらの属性を「ブロックリスト」に追加できます。

詳しくは、*Adobe Target開発者ガイド*&#x200B;の[ モデル APIの概要](https://experienceleague.adobe.com/docs/target-dev/developer/api/models-api/models-api.html?lang=ja){target=_blank}を参照してください。 APIを使用して属性をブロックするには、[ モデル API](https://experienceleague.adobe.com/docs/target-dev/developer/api/models-api/models-api-overview.html){target=_blank}を参照してください。

### [!UICONTROL Automated Segments]と[!UICONTROL Important Attributes]の情報は、CSV ダウンロードと同じですか？

いいえ、UI レポートには、限定された情報のみ含まれています。 CSV ダウンロードには、追加の詳細情報が含まれています。 自動セグメントインサイトレポートのダウンロードには、UI に含まれている上位セグメント以外のセグメントのほか、オファーやエクスペリエンスに対するこれらのセグメントのパフォーマンスが含まれています。 重要な属性レポートには、上位 100 個の訪問者属性とそれらの相対的重要度が含まれていますが、UI には上位 10 個の訪問者属性のみ含まれます。

### カスタム日付範囲のPersonalization インサイトを表示できますか？

Personalization インサイトレポート（[!UICONTROL Automated Segments]および[!UICONTROL Important Attributes]）は、15日、30日、45日、60日、および90日の固定日付範囲でのみ使用できます。 これらの固定日付範囲を使用すると、[!UICONTROL Personalization Insights]は十分な範囲のデータを使用して、アクティビティの短期的なパターンからインサイトを導き出す可能性を減らすことができます。 これらの期間は任意の終了日に対して選択できます（期間を満たすのに十分なデータがアクティビティにある場合）。

### [!UICONTROL Personalization Insights]はどのように作成されますか？

[!UICONTROL Personalization Insights]は、MAGIX （Model Agnostic Globally Interpretable Explanations）と呼ばれるAdobeの特許保留中の手法を使用して作成されます。 MAGIXについて詳しくは、[arXiv.org web サイト ](https://arxiv.org/abs/1706.07160)に掲載されているAdobeのリサーチチームが公開した論文をご覧ください。

### 収益ベースのモデリング目標/主要目標に[!UICONTROL Personalization Insights]を使用できますか？

現時点では、[!UICONTROL Personalization Insights]はコンバージョン最適化の目標アクティビティでのみ使用できます。 今後のリリースで、売上高最適化目標のアクティビティもサポートする予定です。

### 「重要属性」レポートの属性重要性スコアは何ですか。

レポートの「属性重要度ランキング」の重要度スコアを見れば、すべての訪問者を識別済みのセグメントに分類する方法をアルゴリズムで決定したとき、学習に使用された変数のうち最も重要であったものがわかります。 モデルで使用された上位 100 個の属性には、パーセントスコアが割り当てられています。

### 特定の自動セグメントの他のオファー/エクスペリエンスと比較して、コンバージョン率が低い一部のオファー/エクスペリエンスが多くのトラフィックを受け取るのはなぜですか？

自動セグメント内のコンバージョン率の低いオファーやエクスペリエンスの方が訪問数が多い場合、考えられる理由は、以下のようにいくつかあります。

* 特定の自動セグメントのオファー／エクスペリエンスの一部またはすべてについて、ビュー数が少ない。
* 特定のオファーやエクスペリエンスでモデルを作成しない、ボリュームの小さいアクティビティ。
* 一部のオファーやエクスペリエンスに対して、他よりも早くモデルが作成された、ボリュームの小さいアクティビティ。 例えば、追加のモデル が 22 日目に作成され、10 ～ 24 日のデータを調べる場合があります。
* どの訪問者にどのオファー／エクスペリエンスが表示されるかを制限する特定のオファーにターゲティングルールが設定されている。
* インサイトレポートに信頼区間がない。 ただし、コンバージョン率が十分に近い場合は、ポイント数が多くなるようにモデルがトラフィックに対応する可能性がありますが、「統計的に異なる」数値ではありません。

トラフィックを提供するモデルがどのように機能するかを知ることは有用です。 各個人は、それぞれの合計プロファイルに基づいて提供されます。 ただし、インサイトレポートは、この動作を一般化して、人間が解釈しやすいものにします。 結果として、セグメントは相互に排他的ではありません。 同一人物が複数のセグメントに現れる可能性があるので、個々のセグメントでこのタイプの動作が表示されることになる可能性があります。

### Personalization Insightsの情報を活用する方法は何ですか？

* ターゲットとなる新しいオーディエンスを発見します。パフォーマンスが特に良い特定の自動セグメントが見つかったら、そのセグメントを他のレポートで再利用できるようにオーディエンスを作成することを検討するとよいでしょう。
* どのようなタイプの訪問者がどのエクスペリエンスに反応するかについての仮説を検証します。
* どのようなコンテンツがどのような種類の訪問者に対して機能したか、どのようなオファーがどの訪問者に効果的であったかについてのインサイトを得ます。
* パフォーマンスの悪いコンテンツを特定します。
* モデルの学習に最も重要であった属性を把握します。
* パーソナライゼーションモデルで使用される属性と、それらの重要度を確認します。
* Target に追加のデータポイントを渡して、パーソナライゼーションに役立つ情報を拡充する機会を特定します。

## 既知の問題

次の問題は現在、[!DNL Target] エンジニアリングチームによって調査中です。

* [!UICONTROL Automated Personalization] （AP）および[!UICONTROL Auto-Target] （AT）アクティビティの[!UICONTROL Important Attributes] レポートに[!DNL Adobe Experience Platform]個のセグメント名が表示されません。 （上位 3813 項目）
