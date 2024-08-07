---
keywords: mvt;多変量分析テスト;多変量分析テストのベストプラクティス;mvtベストプラクティス;mvtの組み合わせ;mvt レポート
description: ' [!DNL Adobe Target] でアクティビティを作成および実行する際の、パフォーマンスの向上、問題の回避、発生する可能性がある既知の問題の修正 [!UICONTROL Multivariate Test] 方法について説明します。'
title: '[!UICONTROL Multivariate Test] アクティビティのベストプラクティスは？'
feature: Multivariate Tests
exl-id: bcd15517-1b5f-4425-9404-1d7dd0689e28
source-git-commit: 0d73a062f70080057c3323f5150af067e3a2e27e
workflow-type: tm+mt
source-wordcount: '610'
ht-degree: 57%

---

# [!UICONTROL Multivariate Test] ベストプラクティス

[!DNL Adobe Target] で [!UICONTROL Multivariate Test] （MVT）アクティビティを作成および実行する際のパフォーマンスの向上、問題の回避、発生する可能性がある既知の問題の修正に役立つヒントです。

## 計画 {#section_4D4A1F6226F042379BF48DB753608579}

* 有意な結果をもたらす可能性があるページの場所に注目します。

  例えば、バナーやメイン画像は、フッターを変更するよりも多くのコンバージョンにつながる可能性があります。テストに効果の低い場所を組み込むと、ページ上のより効果の高い場所をテストするのに必要なトラフィック量や時間が増えることになります。
* 事前にページのバリエーションを準備します。

  各オファーのコンテンツの差異を把握し、MVT テストで使用する画像、テキストおよび HTML オファーを作成します。

## 作成 {#section_C59C722CA82E48ABA58A4A7FA758F193}

* テストに必要となる以上の組み合わせを組み込まないでください。

  テストする組み合わせの数が増えると、期待に添った結果を実現するために必要なトラフィック量および時間が大幅に増加します。例えば、それぞれ 3 つのオファーが組み込まれた場所が 3 つある場合、27 の組み合わせ（3 x 3 x 3）になります。3 つの場所があり、そのうちの 2 つの場所に 3 つのオファーが、1 つの場所に 2 つのオファーが組み込まれている場合、組み合わせは 18（3 x 3 x 2）になります。場所やオファーの数が増えると、組み合わせの数は大きく増加します。

* 場所およびオファーに名前を付けます。

  テスト内のそれぞれの場所およびオファーを、わかりやすい名前に変更できます。それぞれの場所におけるオファーの数が、場所のヘッダーに表示されます。役に立つ名前は、レポートを調べる際にオファーを識別するのに役立ちます。

* 望ましくないコンテンツの組み合わせを避けるためにプレビュー機能を利用します。

  テストを開始する前に、テストによって生成されるすべてのエクスペリエンスを確認します。相反する主張（例えば、同じエクスペリエンスで 20% オフや 19$オフなど）や、同じ色の背景やフォントを持つなど、互換性のないデザインとの組み合わせがないことを確認してください。

* [トラフィック見積もり](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md)を使用して、ページで予想されるトラフィック量に合ったテストをおこないます。

  希望する結果を得ることができるように、トラフィック見積もりでテスト設定の信号が緑になっていることを確認します。

* 各要素の代替値は、互いに大きく異なる必要があります。

## 分析 {#section_9A2118CF1039451681C13D9AE79A58AB}

* [ 場所の貢献度レポート ](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md) を頻繁に使用して、各ロケーションとオファーのパフォーマンスを監視します。
* [ エクスペリエンスパフォーマンスレポート ](/help/main/c-reports/multivariate-test-reports/experience-performance-report.md) では、[!UICONTROL Best 5] フィルターと [!UICONTROL Worst 5] フィルターを使用して表示されるデータに基づいて決定を下します。

  [!UICONTROL All] フィルターを使用すると、目的の情報の抽出が困難になり、すべてのエクスペリエンスがグラフに表示できるわけではありません。 [!UICONTROL All] フィルターを使用するのは、特定のエクスペリエンスが最良または最悪の 5 つではない場合です。

## フォローアップ {#section_1C44A767F6AB4441A3EAA8AC995F46B0}

* [!DNL Target] ではライブアクティビティを編集できますが、進行中のアクティビティを編集するとテストがリセットされる場合があります。 レポートで、一部の変更が認識されない場合があります。 オファーライブラリに含まれている HTML オファーに変更を加えることは安全です。

  エクスペリエンス名およびレポートをリセットする具体的なアクションを次に示します。

   * 新しい場所の追加
   * 場所の削除
   * 新しいオファーの追加、または既存の場所からのオファーの削除
   * リッチテキストオファーの編集
   * 背景色オファーの編集

* MVT テストの後に 1 つ以上の A/B テストをおこなうことで、目的の結果を得るための最良のコンテンツを判断できます。

  目標を達成するために最も有用な場所およびコンテンツを特定したら、A/B テストを実行して、さらに結果を絞り込むことができます。例えば、最も重要な場所がわかっている場合は、2 つの特定の画像を相互にテストしたり、コールトゥアクションの表現や色を比較したりします。
