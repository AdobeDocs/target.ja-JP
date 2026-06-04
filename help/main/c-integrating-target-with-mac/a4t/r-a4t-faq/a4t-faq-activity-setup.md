---
keywords: FAQ;よくある質問;analytics for target;A4T;アクティビティの設定
description: Analytics for [!DNL Target]  （A4T）を使用する際のアクティビティ設定に関する質問への回答を見つけます。 A4T では、 [!DNL Target]  アクティビティに Analytics のレポート機能を使用できます。
title: A4Tのアクティビティ設定に関するFAQはどこで見つけることができますか？
feature: Analytics for Target (A4T)
exl-id: 8a8cdbb9-89f6-4e4a-a53e-8f33adab4d61
TQID: https://experienceleague.adobe.com/y4pSMxqYoXPMyrkG7ZW9XuJP-R2iVaH2OqhcXn02Vs8
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 642
ht-degree: 21%

---

# アクティビティの設定 - A4T FAQ

このトピックには、アクティビティの設定と[!DNL Analytics]を[!DNL Target] （A4T）のレポートソースとして使用することについてよく寄せられる質問に対する回答が含まれています。

## レポートソース （A4T）として[!DNL Analytics]をサポートしているアクティビティの種類はどれですか？ {#section_5E4F58CD25A5424E869E6FE0803968EF}

+++回答
完全なリストについては、「[Adobe Target のレポートソースとしての Adobe Analytics（A4T）](/help/main/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE)」の「サポートされているアクティビティのタイプ」を参照してください。

+++

## A4T レポートを使用する場合、別々のワークスペースから2つのアクティビティに同じアクティビティ名を使用できますか？

+++回答

A4T レポートを使用している別々の[ ワークスペース ](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)の2つのアクティビティに対して、同じアクティビティ名を使用しないでください。

これは[!DNL Target]をレポートソースとして使用する場合はサポートされますが、2つのアクティビティに同じアクティビティ名を使用することは、レポートソースとして[!UICONTROL Analytics for Target]を使用する場合はサポートされません。

+++

## 目標指標を設定する際に、詳細設定オプションにアクセスできないのはなぜですか？

+++回答
レポートソース（A4T）として[!DNL Analytics]を使用するアクティビティの場合、目標指標は「[!UICONTROL  アクティビティの増分数とユーザーをアクティビティ ]」と「[!UICONTROL すべてのインプレッション ]」の設定を使用します。 これらの設定は、*変更できません*。

詳しくは、「目標指標を設定する際に、詳細設定オプションにアクセスできないのはなぜですか？」 （[指標の定義 - A4T FAQ](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-metric-definition.md)）を参照してください。

+++

## アクティビティを作成しました。 データが表示されないのはなぜですか？ {#section_9F8092BE4225442896F926540292F221}


+++回答
アクティビティが作成されると、[!DNL Target]は分類ファイルを[!DNL Analytics]に送信します。 [!DNL Analytics]はデータを取得および処理していますが、分類ファイルが更新されるまで、レポートにそれが表示されません。 このプロセスが完了するには24～72時間かかる場合があります。 72時間後にデータが表示されない場合は、[ クライアントケアにお問い合わせください](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)。 または、アクティビティを起動したことがわかっている場合は、アクティビティを数日前に作成し、アクティビティの保存時に分類が送信されます。 こうすることで、開始時にレポートにデータが表示されます。 データが[!DNL Analytics]で処理されるまでに45 ～ 90分かかることに注意してください。

+++

## アクティビティの作成時に、Analyticsをレポートソースとして選択できないのはなぜですか？ {#section_9F4F69C3085F4C2480AF439127EB27CD}

+++回答
[!UICONTROL  レポート設定]のオプションは、[!UICONTROL 管理]で変更できます。

1. [!DNL Target]で、**[!UICONTROL 管理]**&#x200B;をクリックします。
1. **[!UICONTROL レポートに使用する Experience Cloud ソリューション]**&#x200B;ドロップダウンリストで、「**[!UICONTROL アクティビティごとに選択]**」を選択します。

![ アクティビティごとの選択画像](assets/select-per-activity.png)

アクティビティを作成および編集する&#x200B;**[!UICONTROL 目標と設定]**&#x200B;画面で、**[!UICONTROL レポートソース]**&#x200B;ドロップダウンリストが有効になります。

常に[!DNL Analytics]をレポートソースとして使用するには、[!UICONTROL 管理]のドロップダウンリストから&#x200B;**[!UICONTROL Adobe Analytics]**&#x200B;を選択します。

+++

## 訪問者は、A4Tを使用する自動ターゲットアクティビティで、異なる訪問のターゲットエクスペリエンスと制御エクスペリエンスを切り替えることができますか？

+++回答
訪問者間で訪問者IDが変更されないと仮定すると、次のようになります。

アクティビティ中にトラフィック配分の割合を調整すると、訪問者は、ターゲットを絞ったエクスペリエンスと制御されたエクスペリエンスの間を移動する可能性があります。

アクティビティ中に割合が調整されない場合、最初にコントロールを見た訪問者は常にコントロールに送信されます。 ターゲティングされたエクスペリエンスに送信された訪問者は、常にターゲティングされたエクスペリエンスに送信されます。

* マシンラーニングモデルが異なるエクスペリエンスが新しい訪問に関連すると判断した場合、訪問者は、ターゲットとするトラフィックの「バケット」に入った後、訪問から訪問まで、異なるエクスペリエンスに送信できます。
* エクスペリエンスの割り当ては、訪問者の訪問者Idの決定論的な疑似ランダムハッシュに基づいているため、訪問者はトラフィックの制御「バケット」に割り当てられた後、常に同じエクスペリエンスを表示します。

+++

## [!UICONTROL 自動配分] アクティビティで、セグメントが最適化目標として適用された二項式[!DNL Analytics]指標を使用できますか？ {#binomial}

+++回答
[!UICONTROL 自動配分] アクティビティで、セグメントが最適化目標として適用された[!DNL Analytics]指標を使用することはできません。 回避策として、同じ目的を達成するカスタムイベントを定義し、それを最適化目標指標として使用できます。

+++
