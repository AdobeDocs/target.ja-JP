---
keywords: レポート；レポート；レポート；experience cloud ソリューション；タイムゾーン；タイムゾーン；通貨；IP の除外；売上高の推定上昇率；売上高の上昇；詳細な優先度；詳細設定
description: 用途 [!DNL Target] または、Adobe Analyticsをレポートソースとして指定し、デフォルトのタイムゾーンと通貨の形式を指定し、レポートから除外する IP アドレスを追加するなどをおこないます。
title: Target でレポートを設定する方法を教えてください。
feature: Administration & Configuration
role: Admin
exl-id: fd83e60e-64a6-4d0e-909f-480d13bac32b
source-git-commit: d414f1554e1875e873f1ce557a7edf86b88ee79e
workflow-type: tm+mt
source-wordcount: '690'
ht-degree: 31%

---

# Target でのレポートの設定

で使用する一般設定を指定します。 [!DNL Adobe Target] レポートを作成し、 [!DNL Target] アカウント。

次の手順で [!UICONTROL レポート] 設定ページで、「 **[!UICONTROL 管理]** > **[!UICONTROL レポート].**

このページでは、次の設定を指定できます。

* レポートに使用するAdobe Experience Cloudソリューション
* レポートに使用するタイムゾーン。
* レポートに使用する通貨
* レポートから除外する IP アドレス
* レポートで売上高の推定上昇率を表示するかどうか
* 詳細な優先度を有効にするかどうか

>[!NOTE]
>
>除外するタイムゾーン、通貨および IP アドレスは、 [!DNL Target] レポート。 これらの設定は、 [Analytics for Target(A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md) を使用します。

![レポートページ](/help/main/administrating-target/assets/reporting.png)

## Reporting Cloud ソリューション {#solution}

結果およびレポートで使用されるデータを決定するオプションを設定します。

アクティビティのレポートソースを選択します（次のいずれか）。 [!DNL Target] または [!DNL Adobe Analytics]. アクティビティごとにレポートソースを選択することもできます。

レポートソースを選択する際には、次の点に注意してください。

* ここでレポートソースを **[!DNL Target]** に設定した場合、 をレポートソースとして使用するアクティビティをアクティブ化することはできません。[!DNL Analytics]レポートソースをに変更する必要があります。 [!DNL Target] 」をクリックします。または、レポートソースを **[!UICONTROL アクティビティごとに選択]** in **[!UICONTROL 管理] > [!UICONTROL レポート]**.
* レポートソースが **[!DNL Analytics]** ここでは、 [!DNL Target] をレポートソースとして ( レポートソースは **[!UICONTROL アクティビティごとのターゲット])**. レポートソースをに変更する必要があります。 [!DNL Analytics] 」をクリックします。または、レポートエンジンを **[!UICONTROL アクティビティごとに選択]** in **[!UICONTROL 管理] > [!UICONTROL レポート]**.
* レポートソースが **[!UICONTROL アクティビティごとに選択]** ここでは、選択したレポートソースでサポートされるアクティビティを作成、アクティブ化および非アクティブ化できます。 サポートされているアクティビティのマトリックスについては、 [サポートされるアクティビティのタイプ](/help/main/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) in *Adobe TargetのレポートソースとしてのAdobe Analytics(A4t)*.
* [!UICONTROL Automated Personalization] (AP) アクティビティの作成、アクティブ化および非アクティブ化は、選択したレポートソースに関係なく許可されます。 Automated Personalizationアクティビティは、 [Adobe TargetのレポートソースとしてのAdobe Analytics(A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md). 次を指定した場合でも、 [!DNL Analytics] をレポートソースとして使用する場合 [!DNL Target] は、 Automated Personalizationアクティビティのレポートソースとして使用されます。 詳しくは、 [サポートされるアクティビティのタイプ](/help/main/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) in *Adobe TargetのレポートソースとしてのAdobe Analytics(A4t)*.

## レポートのタイムゾーン

レポートに使用するタイムゾーンを指定します。

## レポート用の通貨

レポートに使用する通貨を指定します。

## 除外する IP [!DNL Target] レポートデータ

レポートデータから除外する IP アドレスを指定します。 例えば、社内の住所を除外することは、レポートデータが Web サイトでの顧客のインタラクションを反映する良い方法です。

各 IP アドレスを新しい行に入力します。

## 収益の推定上昇率を表示

目標の金額を入力する場合は、売上高の推定上昇率を表示するように選択できます。 [!DNL Target] では、すべてのユーザーが勝者エクスペリエンスを表示する場合に到達する売上高上昇を予測できます。デフォルトでは、上昇予測機能は無効になっています。

のみ [!DNL Experience Cloud] 管理者ユーザーは、この機能を有効または無効にできます。 上昇予測機能が無効になっている場合、対応するフィールドはインターフェイスに表示されません。この機能を無効にしても、独自の予測に使用したデータをはじめ、データを失うことはありません。予測は、この機能が有効であるかどうかにかかわらず、収集したデータに基づいて計算されます。

詳しくは、[収益の上昇率の予測](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md)を参照してください。

## 詳細な優先度の有効化

0~999 の優先度の数値エントリを許可します。

優先度の UI とオプションは、設定によって変わります。従来の「低」、「中」、「高」の各設定も使用できますが、0 から 999 の値を入力して詳細な優先度を設定することもできます。

優先度は、同じロケーションの同じオーディエンスに複数のアクティビティが割り当てられた場合に使用されます。ロケーションに 2 つ以上のアクティビティが割り当てられている場合、優先度の最も高いものが表示されます。
