---
keywords: FAQ;よくある質問;analytics for target;A4T;指標;指標の定義
description: 指標の定義と、Analytics を使用した [!DNL Target] (A4T)。 A4T では、Analytics レポートをAdobeと共に使用できます [!DNL Target] アクティビティ。
title: A4T を使用した指標の定義に関する情報はどこで確認できますか？
feature: Analytics for Target (A4T)
exl-id: 97442622-ba6d-46f8-bfac-72638875d889
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 39%

---

# 指標の定義 - A4T FAQ

このトピックには、指標の定義と使用に関するよくある質問に対する回答が含まれています [!DNL Adobe Analytics] レポートソースとして [!DNL Adobe Target] (A4T)。

## アクティビティメンバーシップの期限切れとは何ですか？訪問者がアクティビティに再度表示されない場合、訪問者のアクションがアクティビティにカウントされるのは、その後どのくらいの期間ですか？ {#section_41B4958F33534E4B96DEE0C981227A79}

アクティビティのデフォルトの有効期限は、訪問者のアクティビティでの最後のインタラクションの後、90 日です。この設定は、必要に応じて ClientCare が調整できます。 この設定は、すべてのアクティビティでグローバルなので、1 つの事例のために調整することはしないでください。

## 目標指標を設定する際に「詳細設定」オプションにアクセスできないのはなぜですか？ {#adv-settings}

この [!UICONTROL 詳細設定] オプションは、 [!DNL Analytics] を使用します (A4T)。

A4T を使用するアクティビティの場合、目標指標は常に「[!UICONTROL カウントを増分、アクティビティでユーザーを保持]&quot;および&quot;[!UICONTROL すべてのインプレッション]」設定を使用します。 これらの設定は、*変更できません*。

A4T 以外のアクティビティの場合、 [詳細設定オプション](/help/main/c-activities/r-success-metrics/success-metrics.md#section_7CE95A2FA8F5438E936C365A6D43BC5B) 成功の測定方法を管理する。 依存関係の追加、アクティビティでユーザーを保持するか削除するかの選択、参加者ごとに 1 回指標をカウントするか、すべてのインプレッションで指標をカウントするかの選択などのオプションがあります。 次にアクセスする [!UICONTROL 詳細設定] 縦並びの省略記号/ [!UICONTROL 詳細設定]、以下に示すように。

![詳細設定](/help/main/c-activities/r-success-metrics/assets/advanced-settings.png)

## 計算指標とは何ですか？ 以前使用していた SiteCatalyst:Event mbox をどのように置き換えるものですか？ {#section_D59F4719E6B94758A2187427C17F8EF3}

計算指標を使用すると、セグメントまたは数値計算から算出されるカスタム指標を作成できます。従来は、`evar27=shoes` でイベントが `purchase` の `SiteCatlayst:Event` mbox を使用していたかもしれませんが、現在は、`evar27=shoes` のセグメントを作成して、セグメントが適用されたイベントが `purchase` の計算指標を作成できます。これらの指標は、アクティビティが進行中の場合でも、いつでも作成できます。 このため、これらの指標を Analytics の任意のレポートで使用できます。

## A4T では、コンバージョンを複数のキャンペーンによるものだと考えますか？ {#section_7F15C727206440CD86B3A8CE77087DF9}

はい、「完全配分」設定を使用します。
