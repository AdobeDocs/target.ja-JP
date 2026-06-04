---
keywords: FAQ;よくある質問;analytics for target;A4T;指標;指標の定義
description: 指標の定義と [!DNL Target]  （A4T）のAnalyticsの使用に関する質問への回答を検索します。 A4Tを使用すると、Analytics レポートをAdobe [!DNL Target]  アクティビティで使用できます。
title: A4Tを使用した指標定義に関する情報はどこで入手できますか？
feature: Analytics for Target (A4T)
exl-id: 97442622-ba6d-46f8-bfac-72638875d889
TQID: https://experienceleague.adobe.com/CLUm25T-5PCOzdXVL94kCgvqM-OL3dZzWXkG1qmN8IE
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 367
ht-degree: 44%

---

# 指標の定義 - A4T FAQ

このトピックには、指標の定義に関してよく寄せられる質問に対する回答と、[!DNL Adobe Analytics]を[!DNL Adobe Target] （A4T）のレポートソースとして使用する回答が含まれています。

## アクティビティメンバーシップの期限切れとは何ですか？ 訪問者がアクティビティにエントリしてから、アクティビティでアクションがカウントされるまでにどのくらいの時間が経過しても、再び表示されないのですか？ {#section_41B4958F33534E4B96DEE0C981227A79}

+++回答
アクティビティのデフォルトの有効期限は、訪問者のアクティビティでの最後のインタラクションの後、90 日です。 この設定は、必要に応じてClientCareで調整できます。 この設定は、すべてのアクティビティでグローバルなので、1 つの事例のために調整することはしないでください。

+++

## 目標の指標を設定する際に、詳細設定オプションにアクセスできないのはなぜですか？ {#adv-settings}

+++回答
[!UICONTROL 詳細設定] オプションは、[!DNL Analytics]をレポートソース （A4T）として使用するアクティビティでは使用できません。

A4Tを使用するアクティビティの場合、目標指標は常に「[!UICONTROL 増分数とアクティビティ内のユーザーを保持]」と「[!UICONTROL すべてのインプレッション &#x200B;]」の設定を使用します。 これらの設定は、*変更できません*。

A4T以外のアクティビティの場合は、[詳細設定オプション &#x200B;](/help/main/c-activities/r-success-metrics/success-metrics.md#section_7CE95A2FA8F5438E936C365A6D43BC5B)を使用して、成功の測定方法を管理できます。 依存関係の追加、アクティビティでユーザーを保持するか削除するかの選択、参加者ごとに 1 回指標をカウントするか、すべてのインプレッションで指標をカウントするかの選択などのオプションがあります。 以下に示すように、A4T以外のアクティビティで[!UICONTROL 詳細設定] オプションにアクセスするには、垂直省略記号> [!UICONTROL 詳細設定]をクリックします。

![詳細設定](/help/main/c-activities/r-success-metrics/assets/advanced-settings.png)

+++

## 計算指標とは何ですか。また、私が使用していたSiteCatalyst:Event mboxをどのように置き換えますか？ {#section_D59F4719E6B94758A2187427C17F8EF3}

+++回答
計算指標を使用すると、セグメントまたは数値計算から算出されるカスタム指標を作成できます。 従来は、`evar27=shoes` でイベントが `purchase` の `SiteCatlayst:Event` mbox を使用していたかもしれませんが、現在は、`evar27=shoes` のセグメントを作成して、セグメントが適用されたイベントが `purchase` の計算指標を作成できます。 これらの指標は、アクティビティの開始後でも、いつでも作成できます。 このため、これらの指標を Analytics の任意のレポートで使用できます。

+++

## A4T では、コンバージョンを複数のキャンペーンによるものだと考えますか？ {#section_7F15C727206440CD86B3A8CE77087DF9}

+++回答
はい、「完全配分」設定を使用します。

+++
