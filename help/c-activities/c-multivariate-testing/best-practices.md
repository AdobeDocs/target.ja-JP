---
description: Adobe Targetで多変量分析テストアクティビティを作成および実行する際に発生する可能性のある、パフォーマンスの向上、問題の回避、既知の問題の修正に役立つヒントです。
keywords: mvt、多変量分析テスト、多変量分析テストのベストプラクティスmvtベストプラクティス、mvtの組み合わせ、mvtレポート
seo-description: Adobe Targetで多変量分析テストアクティビティを作成および実行する際に発生する可能性のある、パフォーマンスの向上、問題の回避、既知の問題の修正に役立つヒントです。
seo-title: 多変量分析テストにおけるAdobe Targetを使用したベストプラクティス
solution: 'Target '
title: 多変量分析テストのベストプラクティス
topic: Standard
uuid: 4468a2eb-3fc1-4bc5-85ac-90cc02db4fbb
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# 多変量分析テストのベストプラクティス{#multivariate-test-best-practices}

Tips to help you improve performance, avoid issues, and correct known issues that might occur when creating and running Multivariate Test (MVT) activities in [!DNL Adobe Target].

## 計画 {#section_4D4A1F6226F042379BF48DB753608579}

* 有意な結果をもたらす可能性があるページの場所に注目します。

   例えば、バナーやヒーロー画像は、フッターの変更よりも多くのコンバージョンにつながる可能性があります。テストに効果の低い場所を組み込むと、ページ上のより効果の高い場所をテストするのに必要なトラフィック量や時間が増えることになります。
* 事前にページのバリエーションを準備します。

   各オファーのコンテンツの差異を把握し、MVT テストで使用する画像、テキストおよび HTML オファーを作成します。

## 作成 {#section_C59C722CA82E48ABA58A4A7FA758F193}

* テストに必要となる以上の組み合わせを組み込まないでください。

   テストする組み合わせの数が増えると、期待に添った結果を実現するために必要なトラフィック量および時間が大幅に増加します。例えば、それぞれ3つのオファーのある3つの場所がある場合、27の組み合わせ（3x3x3）があります。3つの場所に3つの場所があり、3つの場所に3つのオファーがあり、1つの場所に2つのオファーがあります（3x3x2）。場所やオファーの数が増えると、組み合わせの数は大きく増加します。

* 場所およびオファーに名前を付けます。

   テスト内のそれぞれの場所およびオファーを、わかりやすい名前に変更できます。それぞれの場所におけるオファーの数が、場所のヘッダーに表示されます。わかりやすい名前を付けると、レポートを調査するときにオファーを特定しやすくなります。

* 望ましくないコンテンツの組み合わせを避けるためにプレビュー機能を利用します。

   テストを開始する前に、テストによって生成されるすべてのエクスペリエンスを確認します。矛盾する内容を謳う組み合わせ（同じエクスペリエンスで 20％オフと 19 ドルオフを謳うなど）がないかや、同じ色を背景色と前景色で使用するなどの不適切なデザインがないかを確認します。

* [トラフィック見積もり](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md) を使用して、ページが受け取るトラフィック量をテストします。

   望ましい結果を得ることができるように、トラフィック見積もりでテスト設定が適切であることを確認します。
* 各要素の代替オプションの内容を大幅に変えることをお勧めします。

## 分析 {#section_9A2118CF1039451681C13D9AE79A58AB}

* [場所の貢献度レポート](/help/c-reports/location-contribution-report.md) を頻繁に使用して、各場所および各オファーのパフォーマンスを監視します。
* [エクスペリエンスのパフォーマンスレポート](/help/c-reports/experience-performance-report.md)で、上位5件と下位5件のフィルターを使用して表示されるデータに基づいて決定を行います。

   [!UICONTROL すべて] のフィルターにより、必要な情報を抽出するのが困難になり、すべてのエクスペリエンスがグラフに表示できるわけではありません。Use the [!UICONTROL All] filter if you want to look at a specific experience that is not in the best or worst five.

## フォローアップ {#section_1C44A767F6AB4441A3EAA8AC995F46B0}

* Although [!DNL Target] allows you to edit a live activity, be aware that editing an activity that is in progress could reset the test. そのため、レポートで一部の変更が認識されない場合があります。オファーライブラリに含まれている HTML オファーに変更を加えることは安全です。

   エクスペリエンス名やレポートがリセットされるアクションには、次のものがあります。

   * 新しい場所の追加
   * 場所の削除
   * 新しいオファーの追加、または既存の場所からのオファーの削除
   * リッチテキストオファーの編集
   * 背景色オファーの編集

* MVT テストの後に 1 つ以上の A/B テストをおこなうことで、目的の結果を得るための最良のコンテンツを判断できます。

   目標を達成するために最も有用な場所およびコンテンツを特定したら、A/B テストを実行して、さらに結果を絞り込むことができます。例えば、最も重要な場所を特定したら、2 つの異なる画像を比較してテストしたり、コールトゥアクションの言葉遣いや色を比較したりできます。

