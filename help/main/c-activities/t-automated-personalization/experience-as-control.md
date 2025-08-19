---
keywords: エクスペリエンス;コントロール;Automated Personalization;自動ターゲット
description: '[!UICONTROL Automated Personalization] で [!UICONTROL Auto-Target] （AP）または  [!DNL Adobe Target] のアクティビティを作成する際に、コントロールとして使用するエクスペリエンスを選択する方法を説明します。'
title: 特定のエクスペリエンスを [!UICONTROL Automated Personalization] アクティビティのコントロールとして使用するにはどうすればよいですか？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Automated Personalization, Auto-Target
solution: Target,Analytics
exl-id: a0a36ace-3cba-4d8d-9bbd-e35204ff6453
source-git-commit: 3a44c05bea24c622292dd0b774f88f0c93be1d88
workflow-type: tm+mt
source-wordcount: '768'
ht-degree: 40%

---

# [!UICONTROL Automated Personalization] または [!UICONTROL Auto-Target] アクティビティ用のコントロールの選択

[[!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/automated-personalization.md) （AP）または [[!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/auto-target-to-optimize.md) （AT）アクティビティを作成する際に、コントロールとして使用する、ランダムに提供されるエクスペリエンスまたは特定のエクスペリエンスを選択できます。

この機能を使用すると、アクティビティで設定されたトラフィック配分率に基づいて、コントロールトラフィックを関連性のあるエクスペリエンスにルーティングできます。その後、そのコントロールへのコントロールトラフィックに対するパーソナライズされたトラフィックのパフォーマンスレポートを評価できます。

[!UICONTROL Automated Personalization] および [!UICONTROL Auto-Target] アクティビティでコントロールを設定するオプションは、他のアクティビティタイプとは少し異なります。 手動 [!UICONTROL A/B Test] では、レポートがコントロールとして表示する内容を変更でき、上昇率はそのコントロールエクスペリエンスのコンバージョン率に基づいて計算されます。 最初に設定されていたコントロールにかかわらず、トラフィックはアクティビティに含めた各エクスペリエンスにランダムに提供されるので、この変更を簡単におこなえます。つまり、コントロールを選択しても、トラフィックの提供方法には影響しません。 [!UICONTROL Automated Personalization] アクティビティと [!UICONTROL Auto-Target] アクティビティでは、コントロールとして選択するものに関する決定は、訪問者トラフィックの提供方法に影響を与えます。 その結果、決定についてより慎重に考える必要があります。

[!UICONTROL Automated Personalization] アクティビティと [!UICONTROL Auto-Target] アクティビティでは、2 つのオプションを使用して制御できます。

* **ランダムに提供**：ランダムなコントロールの場合、トラフィックのコントロール割合は、訪問者のプロファイルを考慮せずに、アクティビティ内のすべてのエクスペリエンスをランダムに提供します。 コントロールは、「訪問者にランダムにエクスペリエンス（またはオファー）を提供し、訪問者のプロファイルを考慮しない場合、そのエクスペリエンス（またはオファー）のコンバージョン率は何ですか？」という質問に対する回答に役立つと考えることができます。 コントロールは、AI アクティビティ内の [!UICONTROL A/B Test] のようなものです。 各エクスペリエンスやオファーに関するパーソナライズされていないコンバージョン率のこの情報を持つことは、アクティビティ結果を分析するタイミングを把握するのに役立ちます。

* **特定のエクスペリエンス**：特定のエクスペリエンスコントロールを使用すると、パーソナライゼーションモデルから提供され [!DNL Target] トラフィックを特定のマーケターが定義したエクスペリエンス（デフォルトのホームページなど）と比較できます。 このオプションでは、トラフィックのコントロールの割合は、その 1 つのエクスペリエンスに対してトラフィックをランダムに提供します。

## 特定のエクスペリエンスのコントロールとしての指定

1. [[!UICONTROL Automated Personalization] アクティビティまたは ](/help/main/c-activities/t-automated-personalization/create-ap-activity.md) のアクティビティを作成または編集する際に [[!UICONTROL Auto-Target] 必要に応じ ](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) エクスペリエンスを設定します。
1. [!UICONTROL Targeting] ページ（3 つのパートから成るガイド付きワークフローのステップ 2）で、コントロールエクスペリエンスをクリックすると、右側のパネルに [!UICONTROL Control] のオプションが表示されます。

   ![ コントロールペイン ](/help/main/c-activities/t-automated-personalization/assets/control.png)

1. [!UICONTROL Control] ドロップダウンリストから「[!UICONTROL Random Experience]」を選択するか、コントロールに使用するエクスペリエンスを選択します。

1. [!UICONTROL Traffic Allocation] コントロールをクリックし、コントロールエクスペリエンスと他のエクスペリエンスに必要なトラフィックの配分を指定します。

   ![ トラフィック配分レール ](/help/main/c-activities/t-automated-personalization/assets/traffic-allocation.png)

   特定のエクスペリエンスコントロールの場合、10％～ 30％をお勧めします。

1. [!UICONTROL Goals & Settings] ページに進みます。

## 既知の制限と考慮事項

特定のエクスペリエンスをコントロールとして使用する場合は、次の点に注意してください。

* 既にライブ状態のアクティビティでコントロールエクスペリエンスを変更しないでください。選択された最新のコントロールエクスペリエンスは、レポートで名前が指定されています（以前のレポートが別のエクスペリエンスに基づいている場合でも）。
* コントロールエクスペリエンスを削除しないでください。
* コントロールは推奨されないので、特定のエクスペリエンスを持つライブアクティビティに新しいオファーやエクスペリエンスを多数追加します。
* [!UICONTROL Automated Personalization] のアクティビティ（コントロールエクスペリエンスのターゲティングを含む）では、そのエクスペリエンスを表示できるユーザーをさらに制限することは推奨されません。
* 特定のエクスペリエンスが選択されている場合、[!UICONTROL Automated Personalization] のアクティビティでは、上昇率と信頼性に関する情報は、オファーレベルのレポートで *利用できません*。 上昇率と信頼性の情報は、[!UICONTROL Automated Personalization] アクティビティの全体的な「ターゲット」トラフィックレベルと「コントロール」トラフィックレベルで利用できます。 上昇率および信頼性情報は、コントロールとして「ランダム」が選択されている場合に使用できます。この違いは、特定のエクスペリエンスのコンバージョン率とオファーのコンバージョン率の比較が単位が違うので論理的でないことによります。[!UICONTROL Auto-Target] アクティビティで使用できる情報は、選択したコントロールの種類に関係なく同じです。
* エクスペリエンスをコントロールとして選択すると、すべてのコントロールトラフィックは 1 つのエクスペリエンスまたはオファーのセットに向かうので、（コントロールトラフィック量がアクティビティのエクスペリエンスやオファーの数だけ分割されるランダムに比べて）通常、それほどトラフィックをコントロールに流す必要はありません。10％が開始するのに適しています。
* 特定のエクスペリエンスをコントロールとして含むライブアクティビティに対して以下のいずれかをおこなう場合、コントロールは、（以前選択していた特定のエクスペリエンスではなく）ランダムに提供されるエクスペリエンスに自動的にリセットされます。

   * エクスペリエンスを削除する
   * 場所またはオファーの削除（[!UICONTROL Automated Personalization] のみ）
   * 重複するオファーの削除または除外グループを使用して、エクスペリエンスを手動で除外する（[!UICONTROL Automated Personalization] のみ）
