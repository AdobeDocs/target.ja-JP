---
keywords: A/B;アクティビティ指標;指標;指標の設定;目標の指標;アクティビティ設定;成功指標;コンバージョン;収益;エンゲージメント
description: A/B テスト、エクスペリエンスのターゲット設定、または多変量テスト アクティビティで指標を設定して、訪問の成功を判断する方法（[!UICONTROL &#x200B; コンバージョン &#x200B;]、[!UICONTROL 収益]、[!UICONTROL &#x200B; エンゲージメント &#x200B;]など）を説明します。
title: A/B アクティビティで目標指標を設定するにはどうすればよいですか？
feature: A/B Tests
exl-id: 9e9e8787-c0cd-4aab-bd2d-0e9591e0a07d
TQID: 'https://experienceleague.adobe.com/WE27AidwrwYLn-ZlnpxKNfOG2jT07iPYztdrovRl0Qk'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ab2570eb-4844-49aa-8334-e91a345525e5
    internal-label: A/B Tests
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: c87804d95464cc31658be23bc7de051c6e1bc12e
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 27%
---
# 指標の設定 {#ab-set-metrics}

>[!BEGINSHADEBOX]

**このページ：**&#x200B;では、A/B、エクスペリエンスのターゲット設定（XT）、または多変量テスト（MVT）アクティビティの目標指標と追加指標を設定する方法と、指標の名前に使用できない文字について説明します。

>[!ENDSHADEBOX]

[!DNL Adobe Target]A/B、[!UICONTROL &#x200B; エクスペリエンスターゲティング &#x200B;] （XT）、[!UICONTROL 多変量テスト &#x200B;] （MVT）アクティビティの指標を使用して、訪問が成功したタイミングを判断します。 成功指標について詳しくは、[成功指標](/help/main/c-activities/r-success-metrics/success-metrics.md#overview)を参照してください。

>[!NOTE]
>
>このページは、[!DNL Adobe Target]がレポートソースである場合に適用されます。 その他のレポートソースについては、 [!DNL Adobe Customer Journey Analytics]&#x200B;[&#128279;](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md)の [!DNL Target]&#x200B;[&#128279;](/help/main/c-integrating-target-with-mac/a4t/a4t.md) and [!DNL Target]  レポートのレポートソースとして[!DNL Adobe Analytics] を参照してください。

## 指標の設定 {#set-a-metric}

1. **[!UICONTROL 目標と設定]** ページの&#x200B;**[!UICONTROL レポート設定]** セクションで、[成功指標](/help/main/c-activities/r-success-metrics/success-metrics.md#overview)を選択します。

   「**[!UICONTROL 指標を選択]**」オプションには、アクティビティに選択できる成功指標が一覧表示されます。 成功指標は次のカテゴリに分類されます。

   * **[!UICONTROL コンバージョン]**
   * **[!UICONTROL 売上高]**
   * **[!UICONTROL エンゲージメント]**

   あらかじめ用意されている成功指標を使用することも、カスタム成功指標を作成することもできます。 成功指標を主要指標としてマークすることもできます。 Reports カードおよび Experience Cloud カードは、主要指標が設定されている場合はデフォルトで主要指標を表示します。

   ![](../../assets/metric-1.png)

1. 指標の設定を指定します。 使用可能な設定は、使用している成功指標によって異なります。

1. 有効にした場合、「**[!UICONTROL コンバージョンの見積もり値]**」フィールドには、目標の値が表示されます。

   * この値を使用すると、[!DNL Target]は売上増加の推定値を計算できます。
   * このフィールドはオプションですが、収益以外の指標の増分収益は、このフィールドなしでは計算できません。
   * このフィールドは、**[!UICONTROL ページスコア]**&#x200B;指標では使用できません。
   * データタイプは通貨です。
   * このフィールドは、ユーザーが目標を達成するために実行されたアクションを示した後、段階的に表示されます。

   詳しくは、「[売上高情報の予測](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md)」を参照してください。 成功指標の適切な設定は、期待するデータを確実に取得するために不可欠です。

   ![](../../assets/metric-2.png)

1. （オプション）目標指標を超える指標を追跡するには、**[!UICONTROL 新しい指標を追加]**&#x200B;をクリックし、前の手順で説明したように、各追加指標を選択して設定します。

1. 指標の設定が完了したら、XT アクティビティで&#x200B;**[!UICONTROL 続行]**&#x200B;をクリックするか、MVT アクティビティで&#x200B;**[!UICONTROL 保存して閉じる]**&#x200B;をクリックします。

## メトリック名に使用できない文字 {#metric-name-rules}

![](../../assets/metric-3.png)

指標に名前を付けたり、名前を変更したりする場合、次の文字は使用できません。


| 文字 | 説明 |
|--- |--- |
| `/` | フォワードスラッシュ |
| `?` | 疑問符 |
| `#` | 番号記号 |
| `:` | コロン |
| `=` | イコール |
| `+` | プラス |
| `-` | マイナス |
| `@` | アットマーク |
