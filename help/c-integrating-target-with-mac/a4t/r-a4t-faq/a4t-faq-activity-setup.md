---
keywords: faq;frequently asked questions;analytics for target;a4T;activity setup
description: このトピックには、アクティビティの設定と、Analytics を Target のレポートソースとして使用すること（A4T）に関するよくある質問に対する回答が含まれています。
title: アクティビティの設定 - A4T FAQ
feature: a4t troubleshooting
translation-type: tm+mt
source-git-commit: a12eea60aa3e66cdb54ab284fa3f942be4d56178
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 36%

---


# アクティビティの設定 - A4T FAQ

This topic contains answers to questions that are frequently asked about activity setup and using [!DNL Analytics] as the reporting source for [!DNL Target] (A4T).

## レポートソースとしての Analytics（A4T）がサポートされるのは、どのアクティビティタイプですか？{#section_5E4F58CD25A5424E869E6FE0803968EF}

完全なリストについては、「[Adobe Target のレポートソースとしての Adobe Analytics（A4T）](/help/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE)」の「サポートされているアクティビティのタイプ」を参照してください。

## 目標指標を設定する際に、詳細設定にアクセスできないのはなぜですか。

レポートソース [!DNL Analytics] としてを使用するアクティビティ(A4T)の場合、目標指標では常に「カウントを[!UICONTROL 増分、アクティビティでユーザーを保持]」および「すべてのインプレッションで」設定が使用されます。 この設定は *変更できません* 。

詳しくは、「目標指標を設定する際に、詳細設定オプションにアクセスできない理由」を参照してください。 in [Metric definitions - A4T FAQ](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-metric-definition.md).

## アクティビティを作成しました。データが表示されないのはなぜですか？{#section_9F8092BE4225442896F926540292F221}

When an activity is created, [!DNL Target] sends a classification file to [!DNL Analytics]. Although [!DNL Analytics] is capturing the and processing the data, it does not show in the reports until the classification file has been updated. これには、最大 24 時間かかることがあります。48 時間経過してもデータが表示されない場合は、[カスタマーケアにお問い合わせ](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)ください。または、アクティビティを開始することがわかっている場合は、数日前にあらかじめアクティビティを作成して、アクティビティを保存する際に分類が送信されるようにしておきます。こうすることで、開始時にレポートにデータが表示されます。Please note that it takes 45-90 minutes for data to be processed in [!DNL Analytics].

## 新しいアクティビティを作成する際に、Analytics をレポートソースとして選択できないのはなぜですか？{#section_9F4F69C3085F4C2480AF439127EB27CD}

You can change your [!UICONTROL Reporting Settings] options in [!UICONTROL Administration].

1. で、「 [!DNL Target]管理 ****」をクリックします。
1. 「**[!UICONTROL レポートに使用する Experience Cloud ソリューション]**」ドロップダウンリストで、「**[!UICONTROL アクティビティごとに選択]**」を選択します。

![](assets/select-per-activity.png)

アクティビティを作成および編集する&#x200B;**[!UICONTROL 目標と設定]**&#x200B;画面で、**[!UICONTROL レポートソース]**&#x200B;ドロップダウンリストが有効になります。

To always use [!DNL Analytics] as the reporting source, select **[!UICONTROL Adobe Analytics]** from the drop-down list in [!UICONTROL Administration].

## A4Tを使用する自動ターゲットアクティビティで、訪問者は異なる訪問でのターゲットエクスペリエンスと制御されたエクスペリエンスを切り替えることができますか。

訪問間の訪問者に対してvisitorIdが変化しない場合、次のようになります。

トラフィック配分の割合をアクティビティ中に調整すると、訪問者がターゲットエクスペリエンスとコントロールエクスペリエンスの間を移動する可能性があります。

パーセント値がアクティビティの中間値に調整されていない場合、最初にコントロールを見た訪問者が常にコントロールに送信されます。 ターゲット設定されたエクスペリエンスに送信される訪問者は、常にターゲット設定されたエクスペリエンスに送信されます。

* トラフィックの対象となる「グループ」に入った後、機械学習モデルが別のエクスペリエンスが新しい訪問に関連していると判断した場合、訪問者を訪問とは異なるエクスペリエンスに送信できます。
* トラフィックのコントロール「バケット」に割り当てられた後は、エクスペリエンスの割り当ては、訪問者のvisitorIdの決定論的な擬似ランダムハッシュに基づくので、訪問者には常に同じエクスペリエンスが表示されます。
