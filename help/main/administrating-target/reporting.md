---
keywords: レポート；レポート；レポート；experience cloud ソリューション；タイムゾーン；タイムゾーン；通貨；IP を除外；推定される収益向上；収益；収益向上；詳細な優先度；詳細な設定
description: 使用方法 [!DNL Target], [!DNL Adobe Analytics], or [!DNL Adobe Customer Journey Analytics] レポートソースとして、デフォルトのタイムゾーンと通貨形式の指定、レポートから除外する IP アドレスの追加などを行います。
title: でのレポートの設定方法 [!DNL Target]?
feature: Administration & Configuration
role: Admin
exl-id: fd83e60e-64a6-4d0e-909f-480d13bac32b
source-git-commit: ea9513c4310d13e1e7899aa7e228b4d7ecdf0748
workflow-type: tm+mt
source-wordcount: '761'
ht-degree: 22%

---

# でのレポートの設定 [!DNL Target]

で使用する一般設定を指定する [!DNL Adobe Target] 全体に適用されるレポート [!DNL Target] アカウント。

にアクセスするには [!UICONTROL Reporting] 設定ページ、 **[!UICONTROL Administration]** > **[!UICONTROL Reporting].**

このページでは、次の設定を指定できます。

* レポートに使用するAdobe Experience Cloud ソリューション
* レポートに使用するタイムゾーン
* レポートに使用する通貨
* レポートから除外する IP アドレス
* レポートで収益向上の見込みを表示するかどうか
* 詳細な優先度を有効にするかどうか

>[!NOTE]
>
>設定を除外するタイムゾーン、通貨、IP アドレスは、を使用するアクティビティに適用されます。 [!DNL Target] レポート。 これらの設定は、を使用するアクティビティには適用されません [Analytics for Target （A4T）](/help/main/c-integrating-target-with-mac/a4t/a4t.md) または [!DNL Customer Journey Analytics] をレポートソースとして使用します。

![レポートページ](/help/main/administrating-target/assets/reporting.png)

## レポートクラウドソリューション {#solution}

結果およびレポートで使用されるデータを決定するオプションを設定します。

次のいずれかの方法で、アクティビティのレポートソースを選択します [!DNL Target], [!DNL Adobe Analytics]、または [!DNL Adobe Customer Journey Analytics]. アクティビティの作成時に、3 つのパートから成るガイド付きワークフローの一部として、アクティビティごとにレポートソースを選択することもできます。

レポートソースを選択する際には、次の点に注意してください。

* **[!DNL Adobe Target]**：レポートソースがに設定されている場合 **[!DNL Target]** ここでは、を使用するアクティビティを作成またはアクティブ化することはできません [!DNL Analytics] または [!DNL Customer Journey Analytics] をレポートソースとして使用します。 レポートソースをに変更する必要があります **[!UICONTROL Select per activity]**.
* **[!DNL Adobe Analytics]**：レポートソースがに設定されている場合 **[!DNL Analytics]** ここでは、を使用するアクティビティを作成またはアクティブ化することはできません [!DNL Target] または [!DNL Customer Journey Analytics] をレポートソースとして使用します。 レポートソースをに変更する必要があります **[!UICONTROL Select per activity]**.
* **[!DNL Adobe Customer Journey Analytics]**：レポートソースがに設定されている場合 **[!DNL Customer Journey Analytics]** ここでは、を使用するアクティビティを作成またはアクティブ化することはできません [!DNL Target] または [!DNL Analytics] をレポートソースとして使用します。 レポートソースをに変更する必要があります **[!UICONTROL Select per activity]**.
* **アクティビティごとに選択**：レポートソースがに設定されている場合 **[!UICONTROL Select per activity]** ここでは、選択したレポートソースでサポートされているアクティビティを作成してアクティブ化できます。

レポートソースを決定する際は、次の情報を考慮してください。

* **[!DNL Analytics]**：を使用したサポート対象アクティビティのマトリックス用 [!DNL Analytics] レポートソース（A4T）については、を参照してください。 [サポートされるアクティビティタイプ](/help/main/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) 。対象： *Adobe TargetのレポートソースとしてのAdobe Analytics（A4t）*.

  [!UICONTROL Automated Personalization] （AP）アクティビティの作成とアクティブ化は、選択したレポートソースに関係なく許可されます。 [!UICONTROL Automated Personalization] を選択した場合、アクティビティはサポートされません [Adobe TargetのレポートソースとしてのAdobe Analytics（A4T）](/help/main/c-integrating-target-with-mac/a4t/a4t.md).

  指定しても [!DNL Analytics] レポートソースとして、 [!DNL Target] は、のレポートソースとして使用されます。 [!DNL Automated Personalization] アクティビティ。

* **[!DNL Customer Journey Analytics]**：を使用したサポート対象アクティビティのマトリックス用 [!DNL Target] でのレポート [!DNL Customer Journey Analytics]を参照してください [サポートされるアクティビティタイプ](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md#supported-activities) 。対象： *[!DNL Target]でのレポート[!DNL Adobe Customer Journey Analytics]*.

  [!UICONTROL Automated Personalization] （AP）、 [!UICONTROL Auto-Allocate]、および [!UICONTROL Auto-Target] アクティビティの作成とアクティブ化は、選択したレポートソースに関係なく許可されます。 これらのアクティビティは、を選択した場合はサポートされません [レポートソースとしてのAdobe Customer Journey Analytics](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md).

  指定しても [!DNL Customer Journey Analytics] レポートソースとして、 [!DNL Target] は、のレポートソースとして使用されます。 [!DNL Automated Personalization] アクティビティ。

  を指定する場合 [!DNL Customer Journey Analytics] のレポートソースとして [!UICONTROL Auto-Allocate] または [!UICONTROL Auto-Target] アクティビティ、 [!DNL Target] または [!DNL Analytics] をレポートソースとして使用できます。

## レポートのタイムゾーン

レポートに使用するタイムゾーンを指定

## レポートの通貨

レポートに使用する通貨を指定します。

## 除外する IP [!DNL Target] レポートデータ

レポートデータから除外する IP アドレスを指定します。 例えば、内部会社アドレスを除外することは、レポートデータが web サイトでの顧客インタラクションを反映していることを確認するための優れた方法です。

新しい行に各 IP アドレスを入力します。

## 収益の推定上昇率を表示

目標に対する金額を入力した場合の、売上高の推定上昇率を表示するように選択できます。 [!DNL Target] では、すべてのユーザーが勝者エクスペリエンスを表示する場合に到達する売上高上昇を予測できます。デフォルトでは、上昇予測機能は無効になっています。

のみ [!DNL Experience Cloud] 管理者ユーザーは、この機能を有効または無効にできます。 上昇予測機能が無効になっている場合、対応するフィールドはインターフェイスに表示されません。この機能を無効にしても、独自の予測に使用したデータをはじめ、データを失うことはありません。予測は、この機能が有効であるかどうかにかかわらず、収集したデータに基づいて計算されます。

詳しくは、[収益の上昇率の予測](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md)を参照してください。

## 詳細な優先度の有効化

0~999 の優先度の数値エントリを許可します。

設定によって、優先度の UI とオプションは異なります。 従来の「低」、「中」、「高」の各設定も使用できますが、0 から 999 の値を入力して詳細な優先度を設定することもできます。

優先度は、同じロケーションの同じオーディエンスに複数のアクティビティが割り当てられた場合に使用されます。ロケーションに 2 つ以上のアクティビティが割り当てられている場合、優先度の最も高いものが表示されます。
