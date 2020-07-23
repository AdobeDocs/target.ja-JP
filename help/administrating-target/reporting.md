---
keywords: report;reports;reporting;experience cloud solution;timezone;time zone;currency;exclude IPs;estimated lift in revenue;revenue;lift in revenue;fine-grained priorities;fine-grained
description: 一般的な設定、モバイルAdobe Target設定、CSSセレクターを指定して、Visual Experience Composer(VEC)を設定します。
title: Adobe Targetでのレポートの設定
topic: Standard
translation-type: tm+mt
source-git-commit: 3edb13b196240bb1918fc66edcc653936e32d3ef
workflow-type: tm+mt
source-wordcount: '666'
ht-degree: 32%

---


# Targetでのレポートの設定

アカウント全体に適用する [!DNL Adobe Target] レポートで使用する一般設定を設定し [!DNL Target] ます。

[!UICONTROL レポート設定ページにアクセスするには、] 管理 **[!UICONTROL /]** レポートをクリックします **。**

このページでは、次の設定を指定できます。

* レポートに使用するAdobe Experience Cloudソリューション
* レポートに使用するタイムゾーン
* レポートに使用する通貨
* レポートから除外するIPアドレス
* レポートの売上高の予測上昇を表示するかどうか
* 優先度の細かい設定を有効にするかどうか

>[!NOTE]
>
>除外するタイムゾーン、通貨およびIPアドレスは、 [!DNL Target] レポートを使用するアクティビティに適用されることに注意してください。 これらの設定は、レポートソース(/help/c-integrating-target-with-mac/a4t/a4t.md)として [AnalyticsをTarget(A4T)] に使用するアクティビティには適用されません。

![レポートページ](/help/administrating-target/assets/reporting.png)

## レポートクラウドソリューション

結果およびレポートで使用されるデータを決定するオプションを設定します。

Select the reporting source for your activities, either [!DNL Target] or [!DNL Adobe Analytics]. アクティビティごとにレポートソースを選択することもできます。

レポートソースを選択する際には、次の点に注意してください。

* ここでレポートソースを **[!DNL Target]** に設定した場合、 をレポートソースとして使用するアクティビティをアクティブ化することはできません。[!DNL Analytics]You must change the reporting source to [!DNL Target] in your activity or change the reporting source to **[!UICONTROL Select per activity]** in **[!UICONTROL Administration]>[!UICONTROL Reporting]**.
* If the reporting source is set to **[!DNL Analytics]** here, you are not allowed to activate an activity that uses [!DNL Target] as the reporting source (the reporting source is specified as **[!UICONTROL Target per activity])**. You must change the reporting source to[!DNL Analytics]in your activity or change the reporting engine to**[!UICONTROL Select per activity ]**in**[!UICONTROL Administration]>[!UICONTROL Reporting ]**.
* If the reporting source is set to **[!UICONTROL Select per activity]** here, you can create, activate, and deactivate activities that are supported by the selected reporting source. For a matrix of supported activities, see [Supported activity types](/help/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) in *Adobe Analytics as the reporting source for Adobe Target (A4t)*.
* [!UICONTROL 自動パーソナライゼーション] (AP)アクティビティの作成、アクティベーションおよび非アクティブ化は、選択したレポートソースに関係なく許可されます。 Automated Personalization activities are not supported when you choose [Adobe Analytics as the reporting source for Adobe Target (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md). Even if you specify [!DNL Analytics] as your reporting source, [!DNL Target] is used as the reporting source for Automated Personalization activities. For more information, see [Supported activity types](/help/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) in *Adobe Analytics as the reporting source for Adobe Target (A4t)*.

## レポートのタイムゾーン

レポートに使用するタイムゾーンを指定します。

## レポートの通貨

レポートに使用する通貨を指定します。

## Targetレポートデータから除外するIP

レポートデータから除外するIPアドレスを指定します。 例えば、内部会社アドレスを除外すると、レポートデータがWebサイトでの顧客の操作を反映するのに適した方法です。

新しい行に各IPアドレスを入力します。

## 収益の推定上昇率を表示

目標に金額を入力した場合は、売上高の予測上昇を表示できます。 [!DNL Target] では、すべてのユーザーが勝者エクスペリエンスを表示する場合に到達する売上高上昇を予測できます。デフォルトでは、上昇予測機能は無効になっています。

Only [!DNL Experience Cloud] Admin users can enable or disable this feature. 上昇予測機能が無効になっている場合、対応するフィールドはインターフェイスに表示されません。この機能を無効にしても、独自の予測に使用したデータをはじめ、データを失うことはありません。予測は、この機能が有効であるかどうかにかかわらず、収集したデータに基づいて計算されます。

詳しくは、[収益の上昇率の予測](/help/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md)を参照してください。

## 詳細な優先度の有効化

0~999 の優先度の数値エントリを許可します。

優先度の UI とオプションは、設定によって変わります。従来の「低」、「中」、「高」の各設定も使用できますが、0 から 999 の値を入力して詳細な優先度を設定することもできます。

優先度は、同じロケーションの同じオーディエンスに複数のアクティビティが割り当てられた場合に使用されます。ロケーションに 2 つ以上のアクティビティが割り当てられている場合、優先度の最も高いものが表示されます。
