---
keywords: FAQ;よくある質問;analytics for target;A4T;アクティビティの設定
description: Analytics for  [!DNL Target]  （A4T）使用時のアクティビティ設定に関する質問への回答を示します。 A4T では、 [!DNL Target]  アクティビティに Analytics のレポート機能を使用できます。
title: A4T のアクティビティ設定に関する FAQ はどこで見つけることができますか？
feature: Analytics for Target (A4T)
exl-id: 8a8cdbb9-89f6-4e4a-a53e-8f33adab4d61
source-git-commit: 981cff428d9e8849b9bbcbf7bef389dad0fbb32a
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 13%

---

# アクティビティの設定 - A4T FAQ

このトピックには、アクティビティの設定と、[!DNL Analytics] を [!DNL Target] （A4T）のレポートソースとして使用する方法に関するよくある質問に対する回答が含まれています。

## レポートソース（A4T）として [!DNL Analytics] サポートされているアクティビティタイプは何ですか？ {#section_5E4F58CD25A5424E869E6FE0803968EF}

+++回答
完全なリストについては、[Adobe Target for Source レポート （A4T）としてのAdobe Analyticsの「サポートされているアクティビティタイプ」を参照してください ](/help/main/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE)

+++

## A4T レポートを使用する際に、別々のワークスペースから 2 つのアクティビティに同じアクティビティ名を使用できますか？

+++回答

A4T レポートを使用している、別の [ ワークスペース ](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) からの 2 つのアクティビティに同じアクティビティ名を使用しないでください。

[!DNL Target] をレポートソースとして使用する場合はサポートされますが、[!UICONTROL Analytics for Target] をレポートソースとして使用する場合、2 つのアクティビティに同じアクティビティ名を使用することはできません。

+++

## 目標指標を設定する際に、詳細設定オプションにアクセスできないのはなぜですか？

+++回答
[!DNL Analytics] をレポートソースとして使用するアクティビティ（A4T）の場合、目標指標は「[!UICONTROL Increment Count & Keep User in Activity]」設定と「[!UICONTROL On Every Impression]」設定を使用します。 これらの設定は、*変更できません*。

詳しくは、「目標指標を設定する際に、詳細設定オプションにアクセスできないのはなぜですか？」（[指標の定義 - A4T FAQ](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-metric-definition.md)）を参照してください。

+++

## アクティビティを作成しました。データが表示されないのはなぜですか？ {#section_9F8092BE4225442896F926540292F221}


+++回答
アクティビティを作成すると、[!DNL Target] は分類ファイルを [!DNL Analytics] に送信します。 [!DNL Analytics] はデータをキャプチャして処理していますが、分類ファイルが更新されるまで、レポートにそのことが表示されません。 この処理が完了するまでに 24～72 時間かかる場合があります。 72 時間経ってもデータが表示されない場合は、[Client Care にお問い合わせください ](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)。 または、アクティビティを起動したことが分かっている場合は、数日前にそのアクティビティを作成しておくと、アクティビティを保存したときに分類が送信されます。 こうすることで、開始時にレポートにデータが表示されます。データが [!DNL Analytics] で処理されるまでに 45～90 分かかることに注意してください。

+++

## アクティビティを作成する際に、レポートソースとして Analytics を選択できないのはなぜですか？ {#section_9F4F69C3085F4C2480AF439127EB27CD}

+++回答
[!UICONTROL Reporting Settings] のオプションは [!UICONTROL Administration] で変更できます。

1. [!DNL Target] で、「**[!UICONTROL Administration]**」をクリックします。
1. 「**[!UICONTROL Experience Cloud solution used for reporting]**」ドロップダウンリストで、「**[!UICONTROL Select per Activity]**」をクリックします。

![ アクティビティごとの選択画像 ](assets/select-per-activity.png)

アクティビティの作成と編集を行う **[!UICONTROL Goal & Settings]** 画面で、「**[!UICONTROL Reporting Source]**」ドロップダウンリストが有効になります。

[!DNL Analytics] を常にレポートソースとして使用するには、[!UICONTROL Administration] のドロップダウンリストから「**[!UICONTROL Adobe Analytics]**」を選択します。

+++

## 訪問者は、A4T を使用する自動ターゲットアクティビティの異なる訪問で、ターゲット設定されたエクスペリエンスと制御されたエクスペリエンスを切り替えることができますか？

+++回答
次に示すのは、訪問者の visitorId が訪問から次の訪問までの間に変化しない場合です。

トラフィック配分の割合がアクティビティの半ばで調整されると、訪問者がターゲットエクスペリエンスとコントロールエクスペリエンスの間を移動する可能性があります。

アクティビティの途中で割合が調整されない場合、最初にコントロールを表示した訪問者は常にコントロールに送信されます。 ターゲット設定されたエクスペリエンスに送信された訪問者は、常にターゲット設定されたエクスペリエンスに送信されます。

* ターゲット設定された「バケット」に入った訪問者は、機械学習モデルが別のエクスペリエンスが新しい訪問に関連していると判断した場合に、訪問から訪問へと別のエクスペリエンスに送信されます。
* エクスペリエンスの割り当ては訪問者の visitorId の決定論的擬似ランダムハッシュに基づいているので、トラフィックのコントロール「バケット」に割り当てられた後、訪問者には常に同じエクスペリエンスが表示されます。

+++

## セグメントを最適化目標として適用した 2 項 [!DNL Analytics] 指標を [!UICONTROL Auto-Allocate] アクティビティで使用することはできますか？ {#binomial}

+++回答
セグメントを最適化目標として適用した [!DNL Analytics] 指標は [!UICONTROL Auto-Allocate] アクティビティでは使用できません。 回避策として、同じ目的を達成するカスタムイベントを定義し、それを最適化目標指標として使用できます。

+++