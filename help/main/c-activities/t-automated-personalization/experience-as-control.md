---
keywords: エクスペリエンス;コントロール;Automated Personalization;自動ターゲット
description: コントロールとして使用するエクスペリエンスを選択する方法を説明します。 [!UICONTROL Automated Personalization] (AP) または [!UICONTROL 自動ターゲット] アクティビティ [!DNL Adobe Target].
title: 特定のエクスペリエンスをコントロールとして [!UICONTROL Automated Personalization] 活動？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Automated Personalization, Auto-Target
solution: Target,Analytics
exl-id: a0a36ace-3cba-4d8d-9bbd-e35204ff6453
source-git-commit: a9508c4bc454faeb8d6763677cce17a264a4a70f
workflow-type: tm+mt
source-wordcount: '783'
ht-degree: 45%

---

# のコントロールを選択します。 [!UICONTROL Automated Personalization] または [!UICONTROL 自動ターゲット] アクティビティ

ランダムに提供されるエクスペリエンスまたは特定のエクスペリエンスを選択して、 [[!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) または [[!UICONTROL 自動ターゲット]](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT) アクティビティ

この機能を使用すると、アクティビティで設定されたトラフィック配分率に基づいて、コントロールトラフィックを関連性のあるエクスペリエンスにルーティングできます。その後、そのコントロールへのコントロールトラフィックに対するパーソナライズされたトラフィックのパフォーマンスレポートを評価できます。

でコントロールを設定するためのオプション [!UICONTROL Automated Personalization] および [!UICONTROL 自動ターゲット] アクティビティは、他のアクティビティタイプとは少し異なります。 マニュアル [!UICONTROL A/B テスト]を使用すると、レポートでコントロールとして表示する内容を変更でき、そのコントロールエクスペリエンスのコンバージョン率に基づいて上昇率が計算されます。 最初に設定されていたコントロールにかかわらず、トラフィックはアクティビティに含めた各エクスペリエンスにランダムに提供されるので、この変更を簡単におこなえます。つまり、コントロールの選択は、トラフィックの提供方法に影響しません。 In [!UICONTROL Automated Personalization] および [!UICONTROL 自動ターゲット] アクティビティと同様に、何をコントロールとして選択するかの決定は、訪問者トラフィックの提供方法に影響します。 その結果、決定についてより慎重に考える必要があります。

のコントロールで使用できるオプションは 2 つあります。 [!UICONTROL Automated Personalization] および [!UICONTROL 自動ターゲット] アクティビティ：

* **ランダムに提供される**：ランダムコントロールの場合、トラフィックのコントロールの割合は、その訪問者のプロファイルを考慮せずに、アクティビティのすべてのエクスペリエンスをランダムに提供します。 コントロールは、「訪問者に対してランダムにエクスペリエンス（またはオファー）を提供し、プロファイルを考慮しない場合、そのエクスペリエンス（またはオファー）のコンバージョン率はどれくらいですか？」という質問への回答に役立ちます。 このコントロールは、 [!UICONTROL A/B テスト] を設定します。 各エクスペリエンスやオファーに関するパーソナライズされていないコンバージョン率のこの情報を持つことは、アクティビティ結果を分析するタイミングを把握するのに役立ちます。

* **特定のエクスペリエンス**：特定のエクスペリエンスコントロールを使用すると、 [!DNL Target] パーソナライゼーションモデルを、マーケターが定義した特定のエクスペリエンス（デフォルトのホームページなど）に追加できます。 このオプションでは、トラフィックのコントロールの割合は、その 1 つのエクスペリエンスに対してトラフィックをランダムに提供します。

## 特定のエクスペリエンスのコントロールとしての指定

1. を作成する際に、 [[!UICONTROL Automated Personalization] アクティビティ](/help/main/c-activities/t-automated-personalization/create-ap-activity.md) または [[!UICONTROL 自動ターゲット] アクティビティ](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md)、必要に応じてエクスペリエンスを設定します。
1. [!UICONTROL ターゲット設定]ページ（3 ステップのガイドによるワークフローの手順 2）で、目的のエクスペリエンスをコントロールとして選択します。
1. コントロールエクスペリエンスおよび他のエクスペリエンスの目的のトラフィック配分を指定します。

   特定のエクスペリエンスコントロールの場合、10％～ 30％をお勧めします。

1. [!UICONTROL 目標と設定]ページに進みます。

## 既知の制限と考慮事項

特定のエクスペリエンスをコントロールとして使用する際は、次の点に注意してください。

* 既にライブ状態のアクティビティでコントロールエクスペリエンスを変更しないでください。選択された最新のコントロールエクスペリエンスは、レポートで名前が指定されています（以前のレポートが別のエクスペリエンスに基づいている場合でも）。
* コントロールエクスペリエンスを削除しないでください。
* 特定のエクスペリエンスをコントロールとして使用するライブアクティビティに多数の新しいオファーやエクスペリエンスを追加しないでください。
* In [!UICONTROL Automated Personalization] アクティビティ（そのエクスペリエンスを表示できるユーザーがさらに制限される可能性のあるコントロールエクスペリエンスのターゲット設定を含む）はお勧めしません。
* In [!UICONTROL Automated Personalization] アクティビティ、上昇率および信頼性の情報は次のとおりです。 *NOT* 特定のエクスペリエンスが選択されている場合に、オファーレベルのレポートで使用できます。 上昇率および信頼性情報は、 [!UICONTROL Automated Personalization] アクティビティ。 上昇率および信頼性情報は、コントロールとして「ランダム」が選択されている場合に使用できます。この違いは、特定のエクスペリエンスのコンバージョン率とオファーのコンバージョン率の比較が単位が違うので論理的でないことによります。次の場所で使用できる情報： [!UICONTROL 自動ターゲット] どのタイプのコントロールが選択されていても、アクティビティは同じです。
* エクスペリエンスをコントロールとして選択すると、すべてのコントロールトラフィックは 1 つのエクスペリエンスまたはオファーのセットに向かうので、（コントロールトラフィック量がアクティビティのエクスペリエンスやオファーの数だけ分割されるランダムに比べて）通常、それほどトラフィックをコントロールに流す必要はありません。10％が開始するのに適しています。
* 特定のエクスペリエンスをコントロールとして含むライブアクティビティに対して以下のいずれかをおこなう場合、コントロールは、（以前選択していた特定のエクスペリエンスではなく）ランダムに提供されるエクスペリエンスに自動的にリセットされます。

   * エクスペリエンスを削除する
   * 場所またはオファー ([!UICONTROL Automated Personalization] のみ )
   * 重複するオファーを削除するか、除外グループ ([!UICONTROL Automated Personalization] のみ )
