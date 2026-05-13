---
keywords: エクスペリエンス;コントロール;Automated Personalization;自動ターゲット
description: ' [!DNL Adobe Target]で[!UICONTROL Automated Personalization] （AP）または[!UICONTROL Auto-Target] アクティビティを作成する際に、コントロールとして使用するエクスペリエンスを選択する方法について説明します。'
title: '[!UICONTROL Automated Personalization] アクティビティで特定のエクスペリエンスをコントロールとして使用するにはどうすればよいですか？'
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Automated Personalization, Auto-Target
solution: Target,Analytics
exl-id: a0a36ace-3cba-4d8d-9bbd-e35204ff6453
TQID: https://experienceleague.adobe.com/a-lIVDWxeAi-VCp7-lLD-zaClCDCKJGfa25XMKF0vZA
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3aid: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 783
ht-degree: 41%

---

# [!UICONTROL Automated Personalization]または[!UICONTROL Auto-Target] アクティビティのコントロールを選択します

[[!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/automated-personalization.md) （AP）または[[!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/auto-target-to-optimize.md) （AT）アクティビティの作成時に、コントロールとして使用するランダムに提供されたエクスペリエンスまたは特定のエクスペリエンスを選択できます。

この機能を使用すると、アクティビティで設定されたトラフィック配分率に基づいて、コントロールトラフィックを関連性のあるエクスペリエンスにルーティングできます。 その後、そのコントロールへのコントロールトラフィックに対するパーソナライズされたトラフィックのパフォーマンスレポートを評価できます。

[!UICONTROL Automated Personalization]および[!UICONTROL Auto-Target] アクティビティでコントロールを設定するオプションは、他のアクティビティタイプとは少し異なります。 手動[!UICONTROL A/B Test]では、コントロールとして表示されるレポートを変更でき、そのコントロール エクスペリエンスのコンバージョン率に基づいて上昇率が計算されます。 最初に設定されていたコントロールにかかわらず、トラフィックはアクティビティに含めた各エクスペリエンスにランダムに提供されるので、この変更を簡単におこなえます。 つまり、コントロールを選択しても、トラフィックの提供方法には影響しません。 [!UICONTROL Automated Personalization]および[!UICONTROL Auto-Target]のアクティビティでは、コントロールとして選択する項目に関する決定が、訪問者のトラフィックの提供方法に影響します。 その結果、あなたはあなたの決定についてもっと慎重に考えなければなりません。

[!UICONTROL Automated Personalization]および[!UICONTROL Auto-Target] アクティビティでは、コントロールに使用できる2つのオプションがあります。

* **ランダムサービス**：ランダムコントロールの場合、トラフィックの制御率は、訪問者のプロファイルを考慮せずに、アクティビティ内のすべてのエクスペリエンスをランダムに提供します。 コントロールは、「ランダムにエクスペリエンス（またはオファー）を訪問者に提供し、そのプロファイルを考慮しない場合、そのエクスペリエンス（またはオファー）のコンバージョン率は何ですか？」という質問に対する回答を助けるものとみなすことができます。 コントロールは、AI アクティビティ内の[!UICONTROL A/B Test]のようなものです。 各エクスペリエンスやオファーに関するパーソナライズされていないコンバージョン率のこの情報を持つことは、アクティビティ結果を分析するタイミングを把握するのに役立ちます。

* **特定のエクスペリエンス**：特定のエクスペリエンス コントロールを使用すると、[!DNL Target]個のパーソナライゼーションモデルによって提供されるトラフィックを、特定のマーケター定義のエクスペリエンス（デフォルトのホームページなど）と比較できます。 このオプションでは、トラフィックのコントロールの割合は、その 1 つのエクスペリエンスに対してトラフィックをランダムに提供します。

## 特定のエクスペリエンスのコントロールとしての指定

1. [[!UICONTROL Automated Personalization] アクティビティ ](/help/main/c-activities/t-automated-personalization/create-ap-activity.md)または[[!UICONTROL Auto-Target] アクティビティ ](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md)の作成または編集中に、必要に応じてエクスペリエンスを設定します。
1. [!UICONTROL Targeting] ページ （3部構成のガイド付きワークフローのステップ 2）で、コントロールエクスペリエンスをクリックすると、右側のパネルに[!UICONTROL Control] オプションが表示されます。

   ![ コントロールパネル ](/help/main/c-activities/t-automated-personalization/assets/control.png)

1. [!UICONTROL Control] ドロップダウンリストから、[!UICONTROL Random Experience]を選択するか、コントロールに使用するエクスペリエンスを選択します。

1. 「[!UICONTROL Traffic Allocation]」コントロールをクリックし、コントロールエクスペリエンスおよびその他のエクスペリエンスに対する目的のトラフィック割り当てを指定します。

   ![ トラフィック配分レール ](/help/main/c-activities/t-automated-personalization/assets/traffic-allocation.png)

   特定のエクスペリエンスコントロールの場合、10％～ 30％をお勧めします。

1. [!UICONTROL Goals & Settings] ページで続行します。

## 既知の制限と考慮事項

特定のエクスペリエンスをコントロールとして使用する場合は、次の点に注意してください。

* 既にライブ状態のアクティビティでコントロールエクスペリエンスを変更しないでください。 選択された最新のコントロールエクスペリエンスは、レポートで名前が指定されています（以前のレポートが別のエクスペリエンスに基づいている場合でも）。
* コントロールエクスペリエンスを削除しないでください。
* コントロールは推奨されないので、特定のエクスペリエンスを含むライブアクティビティに多くの新しいオファーまたはエクスペリエンスを追加します。
* [!UICONTROL Automated Personalization]のアクティビティで、そのエクスペリエンスが推奨されないユーザーをさらに制限する可能性のあるコントロール エクスペリエンスのターゲティングを含む。
* [!UICONTROL Automated Personalization]のアクティビティでは、特定のエクスペリエンスが選択されている場合、オファーレベル レポートで上昇率と信頼度の情報は&#x200B;*NOT*&#x200B;利用できます。 上昇率と信頼度の情報は、[!UICONTROL Automated Personalization] アクティビティの「ターゲットされた」トラフィックレベルと「コントロール」トラフィックレベルの両方で利用できます。 上昇率および信頼性情報は、コントロールとして「ランダム」が選択されている場合に使用できます。 この違いは、特定のエクスペリエンスのコンバージョン率とオファーのコンバージョン率の比較が単位が違うので論理的でないことによります。 どの種類のコントロールを選択しても、[!UICONTROL Auto-Target] アクティビティで使用できる情報は同じです。
* エクスペリエンスをコントロールとして選択すると、すべてのコントロールトラフィックは 1 つのエクスペリエンスまたはオファーのセットに向かうので、（コントロールトラフィック量がアクティビティのエクスペリエンスやオファーの数だけ分割されるランダムに比べて）通常、それほどトラフィックをコントロールに流す必要はありません。 10％が開始するのに適しています。
* 特定のエクスペリエンスをコントロールとして含むライブアクティビティに対して以下のいずれかをおこなう場合、コントロールは、（以前選択していた特定のエクスペリエンスではなく）ランダムに提供されるエクスペリエンスに自動的にリセットされます。

   * エクスペリエンスを削除する
   * 場所またはオファーの削除（[!UICONTROL Automated Personalization]のみ）
   * 重複するオファーを削除するか、除外グループを使用して、エクスペリエンスを手動で除外します（[!UICONTROL Automated Personalization]のみ）
