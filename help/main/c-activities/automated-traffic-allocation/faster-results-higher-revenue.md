---
keywords: 自動トラフィック配分；ターゲティング；自動配分；自動配分
description: '[!DNL Adobe Target]の[!UICONTROL 自動割り当て] アクティビティが、2つ以上のエクスペリエンスの中から勝者を特定し、その勝者に対してより多くのトラフィックを自動的に再割り当てする方法について説明します。'
title: '[!UICONTROL 自動割り当て] アクティビティは、より迅速な結果と高い収益を得ることができますか？'
feature: Auto-Allocate
exl-id: 104ad88f-044b-4c2f-bdaf-f023fd1787a5
TQID: 'https://experienceleague.adobe.com/aSxZ0Zp3cm0x-fVBXHWW4OiXd3Riz-tuhBiw0f8m4lk'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: f2d0aafb-18af-41a0-a32e-2788eafacc2b
    internal-label: Auto-allocate
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 878df20c7fb08c893239135c20f358b5606d0c6f
workflow-type: tm+mt
source-wordcount: '580'
ht-degree: 0%
---
# [!UICONTROL 自動割り当て]が手動テストよりも優れている方法 {#faster-results-higher-revenue}

>[!BEGINSHADEBOX]

**このページ：**&#x200B;では、**[!UICONTROL 自動配分]** アクティビティが、手動A/B テストよりも迅速な結果と高い収益をもたらす理由、その仕組み、手動トラフィック配分が引き続き優れた選択肢である場合について説明します。

>[!ENDSHADEBOX]

手作業によるA/B アクティビティでは、アクティビティが完了するまでオーディエンス全体に優れたエクスペリエンスを提供できないため、コンバージョンが失われる可能性があります。 トラフィックの配分は、いくつかのエクスペリエンスが他のエクスペリエンスよりも優れていることを認識した後も固定されたままになり、勝者に対して行動を起こすには、アクティビティ全体を実行する必要があります。

## トラフィックの自動割り当て {#auto-allocating-traffic}

**[!UICONTROL 自動割り当て]**&#x200B;は、アクティビティの早い段階で勝者エクスペリエンスをより頻繁に提供し、サンプルサイズ、信頼性レベル、およびその他の統計的概念を選択するセットアップおよび計算コストを削除または削減したい場合に最適なオプションです。

## [!UICONTROL 自動割り当て]の仕組み {#how-it-works}

**[!UICONTROL 自動割り当て]**&#x200B;は、マルチアームドバンディットの原則を使用します。 ワンアームドバンディットとは、スロットマシンの俗称です。 トラフィックの自動割り当ては、スロットマシンのセットと考えてください。この場合、テストのバリエーションは、最初はハンドルが同じように引っ張られます。 時間の経過とともに、1つまたは複数のマシン、またはテストのバリエーションが、他のマシンよりも多く支払われる場合があります。 この状況が起こると、ギャンブラーは自然に、より頻繁に勝つ機械のハンドルを引っ張り始めます。 トラフィック配分の観点から、[!DNL Target]はより多くの訪問者に、より多くの成果を上げているエクスペリエンスまたはエクスペリエンスを提供します。

次の図は、2週間のA/B アクティビティを示しています。 **[!UICONTROL 自動割り当て]**&#x200B;では、勝者エクスペリエンスが現れるにつれて、[!DNL Target]はテストの早い段階でその勝者により多くのトラフィックを割り当てます。

![自動配分の図](/help/main/c-activities/automated-traffic-allocation/assets/Auto-Allocate-test.png)

## [!UICONTROL 自動割り当て]では、より高速な結果を得るにはどうすればよいですか？ {#faster-results}

最もパフォーマンスの高いバリエーションを目にする訪問者が増えます。 ひとつのバリエーションが完成するにつれ、テストの実行中にさらに多くの訪問者が勝者エクスペリエンスに振り向けられます。 この方法は、ホリデーシーズン、新製品の発売、ワールドニュースイベントなど、ビジネスの重要な瞬間にA/B アクティビティを実行する場合に特に役立ちます。

## [!UICONTROL 自動割り当て]で高い収益を得るにはどうすればよいですか？ {#higher-revenue}

**[!UICONTROL 自動割り当て]**&#x200B;は、手動A/B分割よりも速く勝者を見つけ、その勝者をすぐに活用し、従来のアプローチや手動アプローチで失われたアップサイドの収益をキャプチャします。 **[!UICONTROL 自動割り当て]**&#x200B;は、コンバージョン率が最も高いエクスペリエンスにトラフィックを集中させます。これにより、アクティビティの実行中および学習中に収益を増やすことができます。

次の例では、**[!UICONTROL 自動割り当て]**&#x200B;は、最も高いコンバージョン率を示したエクスペリエンス Dにより多くのトラフィック（40%）をプッシュすることで、テスト中により多くの収益を得ました。

![自動割り当てにより、より高い収益が得られます](/help/main/c-activities/automated-traffic-allocation/assets/five-experiences.png)

## どのような場合に手作業によるトラフィック配分を継続すればよいですか？ {#manual-allocation}

手動A/B テストは、あらゆるエクスペリエンスが他のエクスペリエンスに対してどのように実行されたかをランク付けする必要がある場合に最も適用可能なオプションです。 **[!UICONTROL 自動割り当て]**&#x200B;は、パフォーマンスの高いユーザーを検索して活用しますが、パフォーマンスの低いエクスペリエンス間での差別化は保証されません。 手動でのトラフィック配分を利用することで、訪問者のトラフィックがどの程度テストの各バリエーションに含まれるかを完全に制御し、自社のビジネスに関連する統計的しきい値をカスタマイズすることができます。

## 基本を学ぶ {#get-started}

最初の&#x200B;**[!UICONTROL 自動配分]** アクティビティを開始する準備ができましたか？ [自動配分アクティビティの作成](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md)および[自動配分の概要](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)を参照してください。
