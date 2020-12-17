---
keywords: report;reports;reporting;experience cloud solution;timezone;time zone;currency;exclude IPs;estimated lift in revenue;revenue;lift in revenue;fine-grained priorities;fine-grained
description: 一般的な設定、モバイルビューポート設定、CSSセレクターを指定して、Adobe TargetVisual Experience Composer(VEC)を設定します。
title: Adobe Targetでのレポートの設定
feature: Administration & Configuration
translation-type: tm+mt
source-git-commit: 9b57d5554884b06d278c3baef3b2c1d5f37bdeb5
workflow-type: tm+mt
source-wordcount: '666'
ht-degree: 32%

---


# ターゲットでのレポートの設定

[!DNL Target]アカウント全体に適用する[!DNL Adobe Target]レポートで使用する一般設定を構成します。

[!UICONTROL レポート]設定ページにアクセスするには、**[!UICONTROL 管理]**/**[!UICONTROL レポート]をクリックします。**

このページでは、次の設定を指定できます。

* レポートに使用するAdobe Experience Cloudソリューション
* レポートに使用するタイムゾーン
* レポートに使用する通貨
* レポートから除外するIPアドレス
* レポートの売上高の予測上昇を表示するかどうか
* 優先度の細かい設定を有効にするかどうか

>[!NOTE]
>
>除外するタイムゾーン、通貨およびIPアドレスは、[!DNL Target]レポートを使用するアクティビティに適用されることに注意してください。 これらの設定は、[ターゲット用のAnalytics(A4T)]をレポートソース(/help/c-integrating-target-with-mac/a4t/a4t.md)として使用するアクティビティには適用されません。

![レポートページ](/help/administrating-target/assets/reporting.png)

## レポートクラウドソリューション

結果およびレポートで使用されるデータを決定するオプションを設定します。

アクティビティのレポートソースを[!DNL Target]または[!DNL Adobe Analytics]から選択します。 アクティビティごとにレポートソースを選択することもできます。

レポートソースを選択する際には、次の点に注意してください。

* ここでレポートソースを **[!DNL Target]** に設定した場合、 をレポートソースとして使用するアクティビティをアクティブ化することはできません。[!DNL Analytics]アクティビティーでレポートソースを[!DNL Target]に変更するか、レポートソースを&#x200B;**[!UICONTROL **[!UICONTROL &#x200B;管理]/[!UICONTROL レポート&#x200B;]**のアクティビティごとに選択]**&#x200B;に変更する必要があります。
* レポートソースが&#x200B;**[!DNL Analytics]**&#x200B;に設定されている場合、[!DNL Target]をレポートソースとして使用するアクティビティをアクティブにすることはできません(レポートソースは、アクティビティごとの]ターゲット&#x200B;**として指定されます)。**[!UICONTROL &#x200B;アクティビティーでレポートソースを[!DNL Analytics]に変更するか、レポートエンジンを&#x200B;**[!UICONTROL アクティビティ]/[!UICONTROL レポート]**&#x200B;の&#x200B;**[!UICONTROL 「管理者ごとに選択]**」に変更する必要があります。
* レポートソースが「**[!UICONTROL アクティビティごとに選択]**」に設定されている場合は、選択したレポートソースでサポートされているアクティビティを作成、アクティブ化および非アクティブ化できます。 サポートされるアクティビティのマトリックスについては、*Adobe Analyticsの[サポートされるアクティビティタイプ](/help/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA)を参照してください。Adobe Targetのレポートソースは&lt;A4t)*&#x200B;です。
* [!UICONTROL Automated Personalization] (AP)アクティビティの作成、アクティベーション、非アクティブ化は、選択したレポートソースに関係なく許可されます。Automated Personalizationアクティビティは、Adobe Target(A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md)のレポートソースとして[Adobe Analyticsを選択した場合はサポートされません。 レポートソースとして[!DNL Analytics]を指定した場合でも、Automated Personalizationアクティビティのレポートソースとして[!DNL Target]が使用されます。 詳しくは、*Adobe Analyticsの[サポートされているアクティビティタイプ](/help/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA)を、Adobe Targetのレポートソースとして参照してください(A4t)*。

## レポートのタイムゾーン

レポートに使用するタイムゾーンを指定します。

## レポートの通貨

レポートに使用する通貨を指定します。

## ターゲットレポートデータから除外するIP

レポートデータから除外するIPアドレスを指定します。 例えば、内部会社アドレスを除外すると、レポートデータがWebサイトでの顧客の操作を反映するのに適した方法です。

新しい行に各IPアドレスを入力します。

## 収益の推定上昇率を表示

目標に金額を入力した場合は、売上高の予測上昇を表示できます。 [!DNL Target] では、すべてのユーザーが勝者エクスペリエンスを表示する場合に到達する売上高上昇を予測できます。デフォルトでは、上昇予測機能は無効になっています。

[!DNL Experience Cloud]管理者ユーザーのみがこの機能を有効または無効にできます。 上昇予測機能が無効になっている場合、対応するフィールドはインターフェイスに表示されません。この機能を無効にしても、独自の予測に使用したデータをはじめ、データを失うことはありません。予測は、この機能が有効であるかどうかにかかわらず、収集したデータに基づいて計算されます。

詳しくは、[収益の上昇率の予測](/help/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md)を参照してください。

## 詳細な優先度の有効化

0~999 の優先度の数値エントリを許可します。

優先度の UI とオプションは、設定によって変わります。従来の「低」、「中」、「高」の各設定も使用できますが、0 から 999 の値を入力して詳細な優先度を設定することもできます。

優先度は、同じロケーションの同じオーディエンスに複数のアクティビティが割り当てられた場合に使用されます。ロケーションに 2 つ以上のアクティビティが割り当てられている場合、優先度の最も高いものが表示されます。
