---
keywords: エクスペリエンス;コントロール;Automated Personalization;自動ターゲット
description: '[!DNL Adobe Target]で[!UICONTROL Automated Personalization] （AP）または[!UICONTROL 自動ターゲット ] アクティビティを作成する際に、コントロールとして使用するエクスペリエンスを選択する方法について説明します。'
title: '[!UICONTROL Automated Personalization] アクティビティで特定のエクスペリエンスをコントロールとして使用するにはどうすればよいですか？'
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Automated Personalization, Auto-Target
solution: Target,Analytics
exl-id: a0a36ace-3cba-4d8d-9bbd-e35204ff6453
TQID: 'https://experienceleague.adobe.com/a-lIVDWxeAi-VCp7-lLD-zaClCDCKJGfa25XMKF0vZA'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: f0055dd2-93f3-4ac8-9abc-d69d4ed2d977
    internal-label: Automated personalization
  - id: db15a02f-03cd-46fe-a53e-02064cdeadfa
    internal-label: Auto target
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 44c6bdd4ab818226e76477782d7e4238b49d5cdc
workflow-type: tm+mt
source-wordcount: '801'
ht-degree: 6%
---
# コントロールエクスペリエンスの選択 {#experience-as-control}

>[!BEGINSHADEBOX]

**このページ：**&#x200B;では、**[!UICONTROL Automated Personalization]**&#x200B;または&#x200B;**[!UICONTROL 自動ターゲット]** アクティビティのコントロールを選択する方法と、特定のエクスペリエンスをコントロールとして使用する際に考慮すべき点について説明します。

>[!ENDSHADEBOX]

[**[!UICONTROL Automated Personalization]**](/help/main/c-activities/t-automated-personalization/automated-personalization.md#automated-personalization-overview) （AP）または[**[!UICONTROL 自動ターゲット ]**](/help/main/c-activities/auto-target/auto-target-to-optimize.md) （AT）アクティビティの作成中に、ランダムに提供されたエクスペリエンスまたは特定のエクスペリエンスをコントロールとして使用できます。 コントロールトラフィックは、アクティビティで設定されたトラフィック割り当て率に基づいて関連するエクスペリエンスにルーティングされるので、パーソナライズされたトラフィックのパフォーマンスレポートをコントロールトラフィックと比較して評価できます。

手動の&#x200B;**[!UICONTROL A/B テスト]**&#x200B;では、制御として表示されるレポートを変更でき、制御が何であれ、トラフィックはすべてのエクスペリエンスにランダムに提供されるので、そのエクスペリエンスから上昇率が計算されます。 **[!UICONTROL Automated Personalization]**&#x200B;および&#x200B;**[!UICONTROL 自動ターゲット]** アクティビティでは、制御は訪問者のトラフィックの提供方法に影響を与えるので、慎重に選択してください。

コントロールには、次の2つのオプションがあります。

* **ランダム サービス：** トラフィックの制御率は、訪問者のプロファイルを考慮せずに、アクティビティ内のすべてのエクスペリエンスをランダムに提供します。 アクティビティ内の&#x200B;**[!UICONTROL A/B テスト]**&#x200B;のように機能し、各エクスペリエンスまたはオファーのパーソナライズされていないコンバージョン率を示します。これは、結果を分析するのに役立ちます。

* **特定のエクスペリエンス：** トラフィックの制御パーセンテージは、ランダムに1つのエクスペリエンスのみを提供します。 このオプションを使用すると、[!DNL Target] パーソナライゼーションモデルによって提供されるトラフィックを、デフォルトのホームページなど、定義した特定のエクスペリエンスと比較できます。

## 注意点 {#considerations}

特定のエクスペリエンスをコントロールとして使用する場合は、次の点に注意してください。

* 既にライブなアクティビティでコントロールエクスペリエンスを変更することは推奨されません。 古いレポートが別のエクスペリエンスに基づいている場合でも、選択した最新のコントロールエクスペリエンスはレポートで名前が付けられます。

* コントロールエクスペリエンスの削除はお勧めしません。

* コントロールは推奨されないので、特定のエクスペリエンスを含むライブアクティビティに多くの新しいオファーまたはエクスペリエンスを追加します。

* **[!UICONTROL Automated Personalization]**&#x200B;のアクティビティで、そのエクスペリエンスを見ることができるユーザーをさらに制限する可能性のあるコントロールエクスペリエンスのターゲティングを含むエクスペリエンスは推奨されません。

* **[!UICONTROL Automated Personalization]**&#x200B;のアクティビティでは、特定のエクスペリエンスが選択されている場合、オファーレベル レポートで上昇率と信頼性に関する情報は&#x200B;*not*&#x200B;利用できます。 これは、特定のエクスペリエンスのコンバージョン率とオファーのコンバージョン率を比較する方法が、ユニットの違いによって論理的ではないためです。 上昇率と信頼度の情報は、アクティビティの「ターゲット」と「コントロール」のトラフィックレベル全体、および「ランダム」がコントロールとして選択されている場合は、すべてのレベルで利用できます。 どの種類のコントロールを選択しても、**[!UICONTROL 自動ターゲット]** アクティビティで使用できる情報は同じです。

* コントロールとして特定のエクスペリエンスを選択すると、すべてのコントロールトラフィックが1つのエクスペリエンスまたは一連のオファーに送信されます。 ランダムコントロールでは、コントロールトラフィックは、アクティビティ内のエクスペリエンスまたはオファーの数に分割されます。 その結果、通常、特定のエクスペリエンスを持つコントロールに流れるために、それほど多くのトラフィックは必要ありません。 10％が開始するのに適しています。

* コントロールとして特定のエクスペリエンスを持つライブアクティビティに対して次のいずれかの操作を行うと、コントロールは（以前に選択した特定のエクスペリエンスではなく）ランダムに提供されたエクスペリエンスに自動的にリセットされます。

  * エクスペリエンスの削除。
  * 場所またはオファーを削除（**[!UICONTROL Automated Personalization]**&#x200B;のみ）。
  * 重複するオファーを削除するか、除外グループ（**[!UICONTROL Automated Personalization]**&#x200B;のみ）を使用して、エクスペリエンスを手動で除外します。


## 特定のエクスペリエンスのコントロールとしての指定 {#specify-control}

コントロールとして特定のエクスペリエンスを指定すると、パーソナライズされたトラフィックは、アクティビティのレポートで現在のデフォルトのエクスペリエンスなど、比較する既知のエクスペリエンスになります。

1. [**[!UICONTROL Automated Personalization ]**アクティビティ ](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#create-ap-activity)または[**[!UICONTROL 自動ターゲット]** アクティビティ ](/help/main/c-activities/auto-target/create-auto-target.md#create-auto-target-activity)を作成または編集する際に、必要に応じてエクスペリエンスを設定します。

1. **[!UICONTROL ターゲティング]** ページ（3部構成のガイド付きワークフローのステップ 2）で、コントロールエクスペリエンスをクリックすると、右側のペインに&#x200B;**[!UICONTROL コントロール]** オプションが表示されます。

   ![ コントロールパネル ](/help/main/c-activities/t-automated-personalization/assets/control.png)

1. **[!UICONTROL コントロール]** ドロップダウンリストから、**[!UICONTROL ランダムエクスペリエンス]**&#x200B;を選択するか、コントロールとして使用するエクスペリエンスを選択します。

1. 「**[!UICONTROL トラフィック配分]**」コントロールをクリックし、コントロールエクスペリエンスおよびその他のエクスペリエンスのトラフィック配分を指定します。

   ![ トラフィック配分レール ](/help/main/c-activities/t-automated-personalization/assets/traffic-allocation.png)

   特定のエクスペリエンスコントロールの場合、10％～ 30％をお勧めします。

1. 「**[!UICONTROL 目標と設定]**」ページに進みます。

アクティビティがライブになると、レポートでは、パーソナライズされたトラフィックと、選択したコントロールエクスペリエンスが比較されます。 ライブアクティビティを変更する前に、[の考慮事項](#considerations)を確認してください。一部の変更では、コントロールが自動的にランダムに提供されたエクスペリエンスにリセットされます。
