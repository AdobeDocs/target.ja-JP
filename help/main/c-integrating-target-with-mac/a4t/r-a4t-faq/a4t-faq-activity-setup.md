---
keywords: FAQ;よくある質問;analytics for target;A4T;アクティビティの設定
description: Analytics を使用した場合のアクティビティの設定に関する質問への回答を見つけます。 [!DNL Target] (A4T)。 A4T では、 [!DNL Target]  アクティビティに Analytics のレポート機能を使用できます。
title: A4T を使用したアクティビティ設定に関する FAQ はどこで確認できますか？
feature: Analytics for Target (A4T)
exl-id: 8a8cdbb9-89f6-4e4a-a53e-8f33adab4d61
source-git-commit: 981cff428d9e8849b9bbcbf7bef389dad0fbb32a
workflow-type: tm+mt
source-wordcount: '630'
ht-degree: 18%

---

# アクティビティの設定 - A4T FAQ

このトピックには、アクティビティの設定と使用に関するよくある質問に対する回答が含まれています。 [!DNL Analytics] レポートソースとして [!DNL Target] (A4T)。

## サポートされるアクティビティのタイプ [!DNL Analytics] レポートソース (A4T) として使用する場合は、 {#section_5E4F58CD25A5424E869E6FE0803968EF}

+++回答完全なリストについては、 [Adobe TargetのレポートソースとしてのAdobe Analytics(A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE).

+++

## A4T レポートを使用する際に、別々のワークスペースから 2 つのアクティビティに同じアクティビティ名を使用できますか？

+++回答

別々の [workspaces](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) A4T レポートを使用している

これは [!DNL Target] レポートソースとして、2 つのアクティビティに同じアクティビティ名を使用することは、 [!UICONTROL Analytics for Target] を使用します。

+++

## 目標指標を設定する際に、詳細設定オプションにアクセスできないのはなぜですか？

+++次を使用するアクティビティに対する回答： [!DNL Analytics] レポートソースとして (A4T)、目標指標は「[!UICONTROL カウントを増分、アクティビティでユーザーを保持]&quot;および&quot;[!UICONTROL すべてのインプレッション]」設定を使用します。 これらの設定は、*変更できません*。

詳しくは、「目標指標を設定する際に、詳細設定オプションにアクセスできないのはなぜですか？」（[指標の定義 - A4T FAQ](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-metric-definition.md)）を参照してください。

+++

## アクティビティを作成しました。データが表示されないのはなぜですか？ {#section_9F8092BE4225442896F926540292F221}


+++回答アクティビティが作成されると、 [!DNL Target] は分類ファイルをに送信します。 [!DNL Analytics]. ただし [!DNL Analytics] は、データを取得して処理する際に、分類ファイルが更新されるまで、レポートには表示されません。 この処理が完了するまでに 24 ～ 72 時間かかる場合があります。 72 時間後にデータが表示されない場合、 [ClientCare にお問い合わせください。](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C). または、アクティビティを開始したことがわかっている場合は、数日前に事前にアクティビティを作成して、アクティビティを保存する際に分類が送信されるようにしておきます。 こうすることで、開始時にレポートにデータが表示されます。でデータが処理されるまでに 45 ～ 90 分かかることに注意してください。 [!DNL Analytics].

+++

## アクティビティを作成する際に Analytics をレポートソースとして選択できないのはなぜですか？ {#section_9F4F69C3085F4C2480AF439127EB27CD}

+++回答： [!UICONTROL レポート設定] のオプション [!UICONTROL 管理].

1. In [!DNL Target]をクリックし、 **[!UICONTROL 管理]**.
1. **[!UICONTROL レポートに使用する Experience Cloud ソリューション]**&#x200B;ドロップダウンリストで、「**[!UICONTROL アクティビティごとに選択]**」を選択します。

![アクティビティごとに選択画像](assets/select-per-activity.png)

アクティビティを作成および編集する&#x200B;**[!UICONTROL 目標と設定]**&#x200B;画面で、**[!UICONTROL レポートソース]**&#x200B;ドロップダウンリストが有効になります。

常に [!DNL Analytics] レポートソースとして、 **[!UICONTROL Adobe Analytics]** を、 [!UICONTROL 管理].

+++

## 訪問者は、A4T を使用する自動ターゲットアクティビティで、異なる訪問でのターゲットエクスペリエンスと制御されたエクスペリエンスを切り替えることができますか？

+++回答次は、訪問の間に訪問者の visitorId が変更されないと仮定して当てはまります。

トラフィック配分の割合をアクティビティ中に調整した場合、訪問者は、ターゲットエクスペリエンスとコントロールエクスペリエンスの間を移動できる可能性があります。

割合がアクティビティ中に調整されない場合、最初にコントロールを表示した訪問者は常にコントロールに送信されます。 ターゲット設定されたエクスペリエンスに送信された訪問者は、常にターゲット設定されたエクスペリエンスに送信されます。

* トラフィックのターゲット「バケット」に入った後、機械学習モデルが新しい訪問に関連すると判断した場合は、訪問者を訪問とは別のエクスペリエンスに送信して、その訪問を訪問できます。
* エクスペリエンスの割り当ては、訪問者の visitorId の決定論的な擬似ランダムハッシュに基づいているので、トラフィックのコントロール「バケット」に割り当てられた後、常に同じエクスペリエンスが表示されます。

+++

## 二項式を使用できますか？ [!DNL Analytics] 指標の最適化目標として [!UICONTROL 自動配分] アクティビティ？ {#binomial}

+++回答： [!DNL Analytics] 指標の最適化目標として [!UICONTROL 自動配分] アクティビティ。 回避策として、同じ目標を達成し、それを最適化目標指標として使用するカスタムイベントを定義できます。

+++