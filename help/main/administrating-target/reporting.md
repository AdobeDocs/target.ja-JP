---
keywords: レポート；レポート；レポート；experience cloud ソリューション；タイムゾーン；タイムゾーン；通貨；IPの除外；収益の推定上昇率；収益の上昇率；収益の増加；きめ細かい優先順位；きめ細かい設定
description: ' [!DNL Target], [!DNL Adobe Analytics], or [!DNL Adobe Customer Journey Analytics] をレポートソースとして使用し、デフォルトのタイムゾーンと通貨形式を指定し、レポートから除外するIP アドレスを追加します。'
title: ' [!DNL Target]でレポートを設定するにはどうすればよいですか？'
feature: Administration & Configuration
role: Admin
exl-id: fd83e60e-64a6-4d0e-909f-480d13bac32b
TQID: https://experienceleague.adobe.com/Vdi1o6bvCbgrhWUrJfCOyxqN3JkhEe3Rd9J-3NmLVyY
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: e0eb8757-182f-49f3-94a4-1587d16f5094id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 795
ht-degree: 22%

---

# [!DNL Target]でのレポートの設定

[!DNL Target] アカウント全体に適用される[!DNL Adobe Target] レポートで使用する一般設定を構成します。

{{permissions-update}}

[!UICONTROL  レポート ]設定ページにアクセスするには、**[!UICONTROL 管理]** > **[!UICONTROL レポート ].**&#x200B;をクリックします

このページでは、次の設定を指定できます。

* レポートに使用するAdobe Experience Cloud ソリューション
* レポートに使用するタイムゾーン
* レポートに使用する通貨
* レポートから除外するIP アドレス
* レポートで売上増加の予測を表示するかどうか
* きめ細かな優先度を有効にするかどうか

>[!NOTE]
>
>設定を除外するタイムゾーン、通貨、およびIP アドレスは、[!DNL Target] レポートを使用するアクティビティに適用されることに注意してください。 これらの設定は、[Analytics for Target （A4T） ](/help/main/c-integrating-target-with-mac/a4t/a4t.md)または[!DNL Customer Journey Analytics]をレポートソースとして使用するアクティビティには適用されません。

![ レポートページ ](/help/main/administrating-target/assets/reporting.png)

## Reporting Cloud ソリューション {#solution}

結果およびレポートで使用されるデータを決定するオプションを設定します。

アクティビティのレポートソース（[!DNL Target]、[!DNL Adobe Analytics]、または[!DNL Adobe Customer Journey Analytics]）を選択します。 アクティビティの作成時に、3つの部分で構成されるガイド付きワークフローの一部として、アクティビティごとにレポートソースを選択することもできます。

レポートソースを選択する際には、次の点に注意してください。

* **[!DNL Adobe Target]**: レポートソースがここで&#x200B;**[!DNL Target]**&#x200B;に設定されている場合、[!DNL Analytics]または[!DNL Customer Journey Analytics]をレポートソースとして使用するアクティビティを作成またはアクティブ化することはできません。 レポート ソースを&#x200B;**[!UICONTROL アクティビティごとに選択]**&#x200B;に変更する必要があります。
* **[!DNL Adobe Analytics]**: レポートソースがここで&#x200B;**[!DNL Analytics]**&#x200B;に設定されている場合、[!DNL Target]または[!DNL Customer Journey Analytics]をレポートソースとして使用するアクティビティを作成またはアクティブ化することはできません。 レポート ソースを&#x200B;**[!UICONTROL アクティビティごとに選択]**&#x200B;に変更する必要があります。
* **[!DNL Adobe Customer Journey Analytics]**: レポートソースがここで&#x200B;**[!DNL Customer Journey Analytics]**&#x200B;に設定されている場合、[!DNL Target]または[!DNL Analytics]をレポートソースとして使用するアクティビティを作成またはアクティブ化することはできません。 レポート ソースを&#x200B;**[!UICONTROL アクティビティごとに選択]**&#x200B;に変更する必要があります。
* **アクティビティごとに選択**：ここでレポートソースが&#x200B;**[!UICONTROL アクティビティごとに選択]**&#x200B;に設定されている場合、選択したレポートソースでサポートされているアクティビティを作成してアクティブ化できます。

レポートソースを決定する際には、次の情報を考慮してください。

* **[!DNL Analytics]**: [!DNL Analytics]をレポートソース （A4T）として使用するサポートされているアクティビティのマトリックスについては、*Adobe Analyticsの[ サポートされているアクティビティタイプ ](/help/main/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA)をAdobe Target （A4t）*&#x200B;のレポートソースとして参照してください。

  [!UICONTROL Automated Personalization] （AP） アクティビティの作成とアクティブ化は、選択したレポートソースに関係なく許可されます。 [!UICONTROL Automated Personalization] アクティビティは、Adobe Target （A4T） ](/help/main/c-integrating-target-with-mac/a4t/a4t.md)のレポートソースとして[Adobe Analyticsを選択した場合はサポートされません。

  レポートソースとして[!DNL Analytics]を指定した場合でも、[!DNL Target]は[!DNL Automated Personalization] アクティビティのレポートソースとして使用されます。

* **[!DNL Customer Journey Analytics]**: [!DNL Customer Journey Analytics]の[!DNL Target]のレポートを使用してサポートされているアクティビティのマトリックスについては、[!DNL Adobe Customer Journey Analytics]*の*[!DNL Target]&#x200B;のレポートの[ サポートされているアクティビティタイプ ](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md#supported-activities)を参照してください。

  [!UICONTROL Automated Personalization] （AP）、[!UICONTROL 自動配分]、[!UICONTROL 自動ターゲット ] アクティビティの作成とアクティブ化は、選択したレポートソースに関係なく許可されます。 これらのアクティビティは、[Adobe Customer Journey Analyticsをレポートソース ](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md)として選択した場合はサポートされません。

  レポートソースとして[!DNL Customer Journey Analytics]を指定した場合でも、[!DNL Target]は[!DNL Automated Personalization] アクティビティのレポートソースとして使用されます。

  [!DNL Customer Journey Analytics]を[!UICONTROL 自動配分]または[!UICONTROL 自動ターゲット ] アクティビティのレポートソースとして指定すると、[!DNL Target]または[!DNL Analytics]をレポートソースとして使用できます。

## レポートのタイムゾーン

レポートに使用するタイムゾーンを指定します。

## レポート用の通貨

レポートに使用する通貨を指定します。

## [!DNL Target]件のレポート データから除外するIP

レポートデータから除外するIP アドレスを指定します。 例えば、内部企業のアドレスを除外することは、レポートデータがweb サイトでの顧客とのやり取りを反映していることを確認する優れた方法です。

新しい行に各IP アドレスを入力します。

## 収益の推定上昇率を表示

目標に金銭的な価値を入力した場合、予測される売上向上を表示することができます。 [!DNL Target] では、すべてのユーザーが勝者エクスペリエンスを表示する場合に到達する売上高上昇を予測できます。 デフォルトでは、上昇予測機能は無効になっています。

この機能を有効または無効にできるのは[!DNL Experience Cloud]人の管理者ユーザーのみです。 上昇予測機能が無効になっている場合、対応するフィールドはインターフェイスに表示されません。 この機能を無効にしても、独自の予測に使用したデータをはじめ、データを失うことはありません。 予測は、この機能が有効であるかどうかにかかわらず、収集したデータに基づいて計算されます。

詳しくは、[収益の上昇率の予測](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md)を参照してください。

## 詳細な優先度の有効化

0~999 の優先度の数値エントリを許可します。

設定に応じて、UIと優先度のオプションが異なります。 従来の「低」、「中」、「高」の各設定も使用できますが、0 から 999 の値を入力して詳細な優先度を設定することもできます。

優先度は、同じロケーションの同じオーディエンスに複数のアクティビティが割り当てられた場合に使用されます。 ロケーションに 2 つ以上のアクティビティが割り当てられている場合、優先度の最も高いものが表示されます。
