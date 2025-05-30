---
keywords: レポート；レポート；レポート；experience cloud ソリューション；タイムゾーン；タイムゾーン；通貨；IP を除外；推定される収益向上；収益；収益向上；詳細な優先度；詳細な設定
description: レポ  [!DNL Target], [!DNL Adobe Analytics], or [!DNL Adobe Customer Journey Analytics]  トソースとして、デフォルトのタイムゾーンと通貨形式の指定、レポートから除外する IP アドレスの追加などを使用します。
title: ' [!DNL Target] でのレポートの設定方法'
feature: Administration & Configuration
role: Admin
exl-id: fd83e60e-64a6-4d0e-909f-480d13bac32b
source-git-commit: 3e2682acdf8c7be86285c901ddcdae0f43b647f2
workflow-type: tm+mt
source-wordcount: '761'
ht-degree: 22%

---

# [!DNL Target] でのレポートの設定

[!DNL Target] アカウント全体に適用される [!DNL Adobe Target] レポートで使用する一般設定を構成します。

{{permissions-update}}

[!UICONTROL Reporting] 設定ページにアクセスするには、**[!UICONTROL Administration]**/**[!UICONTROL Reporting]をクリックします。**

このページでは、次の設定を指定できます。

* レポートに使用するAdobe Experience Cloud ソリューション
* レポートに使用するタイムゾーン
* レポートに使用する通貨
* レポートから除外する IP アドレス
* レポートで収益向上の見込みを表示するかどうか
* 詳細な優先度を有効にするかどうか

>[!NOTE]
>
>設定を除外するタイムゾーン、通貨、IP アドレスは、[!DNL Target] レポートを使用するアクティビティに適用されることに注意してください。 これらの設定は、[Analytics for Target （A4T）または [!DNL Customer Journey Analytics] をレポートソースとして使用するアクティビティには適用されません ](/help/main/c-integrating-target-with-mac/a4t/a4t.md)

![ レポートページ ](/help/main/administrating-target/assets/reporting.png)

## レポートクラウドソリューション {#solution}

結果およびレポートで使用されるデータを決定するオプションを設定します。

アクティビティのレポートソース（[!DNL Target]、[!DNL Adobe Analytics]、[!DNL Adobe Customer Journey Analytics]）を選択します。 アクティビティの作成時に、3 つのパートから成るガイド付きワークフローの一部として、アクティビティごとにレポートソースを選択することもできます。

レポートソースを選択する際には、次の点に注意してください。

* **[!DNL Adobe Target]**: レポートソースが **[!DNL Target]** に設定されている場合、[!DNL Analytics] または [!DNL Customer Journey Analytics] をレポートソースとして使用するアクティビティを作成またはアクティブ化することはできません。 レポートソースを **[!UICONTROL Select per activity]** に変更する必要があります。
* **[!DNL Adobe Analytics]**: レポートソースが **[!DNL Analytics]** に設定されている場合、[!DNL Target] または [!DNL Customer Journey Analytics] をレポートソースとして使用するアクティビティを作成またはアクティブ化することはできません。 レポートソースを **[!UICONTROL Select per activity]** に変更する必要があります。
* **[!DNL Adobe Customer Journey Analytics]**: レポートソースが **[!DNL Customer Journey Analytics]** に設定されている場合、[!DNL Target] または [!DNL Analytics] をレポートソースとして使用するアクティビティを作成またはアクティブ化することはできません。 レポートソースを **[!UICONTROL Select per activity]** に変更する必要があります。
* **アクティビティごとに選択**：ここでレポートソースを **[!UICONTROL Select per activity]** に設定している場合、選択したレポートソースでサポートされるアクティビティを作成してアクティブにできます。

レポートソースを決定する際は、次の情報を考慮してください。

* **[!DNL Analytics]**: [!DNL Analytics] をレポートソースとして使用する（A4T）サポートされているアクティビティのマトリックスについては、*Adobe TargetのレポートソースとしてのAdobe Analytics（A4T）の [ サポートされているアクティビティタイプ ](/help/main/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) を参照してください*

  [!UICONTROL Automated Personalization] （AP）アクティビティの作成とアクティブ化は、選択したレポートソースに関係なく許可されます。 [Adobe AnalyticsをAdobe Target（A4T）のレポートソースとして選択した場合、[!UICONTROL Automated Personalization] アクティビティはサポートされません ](/help/main/c-integrating-target-with-mac/a4t/a4t.md)。

  レポートソースとして [!DNL Analytics] を指定した場合でも、[!DNL Target] は [!DNL Automated Personalization] アクティビティのレポートソースとして使用されます。

* **[!DNL Customer Journey Analytics]**: [!DNL Customer Journey Analytics] の [!DNL Target] レポートを使用したサポートされるアクティビティのマトリックスについては、[!DNL Adobe Customer Journey Analytics]*のレポートの [ サポートされるアクティビティタイプ ](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md#supported-activities)*[!DNL Target] 参照してください。

  [!UICONTROL Automated Personalization] （AP）、[!UICONTROL Auto-Allocate]、[!UICONTROL Auto-Target] アクティビティの作成とアクティブ化は、選択したレポートソースに関係なく許可されます。 これらのアクティビティは、[Adobe Customer Journey Analyticsをレポートソースとして選択した場合はサポートされ ](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md) せん。

  レポートソースとして [!DNL Customer Journey Analytics] を指定した場合でも、[!DNL Target] は [!DNL Automated Personalization] アクティビティのレポートソースとして使用されます。

  [!UICONTROL Auto-Allocate] または [!UICONTROL Auto-Target] アクティビティのレポートソースとして [!DNL Customer Journey Analytics] を指定した場合は、[!DNL Target] または [!DNL Analytics] をレポートソースとして使用できます。

## レポートのタイムゾーン

レポートに使用するタイムゾーンを指定

## レポートの通貨

レポートに使用する通貨を指定します。

## [!DNL Target] レポートデータから除外する IP

レポートデータから除外する IP アドレスを指定します。 例えば、内部会社アドレスを除外することは、レポートデータが web サイトでの顧客インタラクションを反映していることを確認するための優れた方法です。

新しい行に各 IP アドレスを入力します。

## 収益の推定上昇率を表示

目標に対する金額を入力した場合の、売上高の推定上昇率を表示するように選択できます。 [!DNL Target] では、すべてのユーザーが勝者エクスペリエンスを表示する場合に到達する売上高上昇を予測できます。デフォルトでは、上昇予測機能は無効になっています。

[!DNL Experience Cloud] 管理者ユーザーのみがこの機能を有効または無効にできます。 上昇予測機能が無効になっている場合、対応するフィールドはインターフェイスに表示されません。この機能を無効にしても、独自の予測に使用したデータをはじめ、データを失うことはありません。予測は、この機能が有効であるかどうかにかかわらず、収集したデータに基づいて計算されます。

詳しくは、[収益の上昇率の予測](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md)を参照してください。

## 詳細な優先度の有効化

0~999 の優先度の数値エントリを許可します。

設定によって、優先度の UI とオプションは異なります。 従来の「低」、「中」、「高」の各設定も使用できますが、0 から 999 の値を入力して詳細な優先度を設定することもできます。

優先度は、同じロケーションの同じオーディエンスに複数のアクティビティが割り当てられた場合に使用されます。ロケーションに 2 つ以上のアクティビティが割り当てられている場合、優先度の最も高いものが表示されます。
