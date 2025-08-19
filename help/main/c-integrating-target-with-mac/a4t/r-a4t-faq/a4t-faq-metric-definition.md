---
keywords: FAQ;よくある質問;analytics for target;A4T;指標;指標の定義
description: 指標の定義と Analytics for [!DNL Target]  （A4T）の使用に関する質問への回答を示します。 A4T では、Adobe アクティビティで Analytics のレポート機能を使用  [!DNL Target]  きます。
title: A4T での指標の定義に関する情報はどこで入手できますか？
feature: Analytics for Target (A4T)
exl-id: 97442622-ba6d-46f8-bfac-72638875d889
source-git-commit: aff96eca1380f4274dba0c1567f6e41d42f4b5ab
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 38%

---

# 指標の定義 - A4T FAQ

このトピックには、指標の定義と、[!DNL Adobe Analytics] を [!DNL Adobe Target] （A4T）のレポートソースとして使用する方法に関するよくある質問に対する回答が含まれています。

## アクティビティメンバーシップの期限切れとは何ですか？訪問者がアクティビティに入ってから、そのアクティビティが再び表示されない場合、そのアクションはどのくらいの間カウントされますか？ {#section_41B4958F33534E4B96DEE0C981227A79}

+++回答
アクティビティのデフォルトの有効期限は、訪問者のアクティビティでの最後のインタラクションの後、90 日です。この設定は、必要に応じて、ClientCare で調整できます。 この設定は、すべてのアクティビティでグローバルなので、1 つの事例のために調整することはしないでください。

+++

## 目標指標を設定する際に、「詳細設定」オプションにアクセスできないのはなぜですか？ {#adv-settings}

+++回答
[!UICONTROL Advanced Settings] のオプションは、[!DNL Analytics] をレポートソースとして使用する（A4T）アクティビティでは使用できません。

A4T を使用するアクティビティの場合、目標指標は常に「[!UICONTROL Increment Count & Keep User in Activity]」と「[!UICONTROL On Every Impression]」の設定を使用します。 これらの設定は、*変更できません*。

A4T 以外のアクティビティの場合は、[ 詳細設定オプション ](/help/main/c-activities/r-success-metrics/success-metrics.md#section_7CE95A2FA8F5438E936C365A6D43BC5B) を使用して、成功の測定方法を管理できます。 依存関係の追加、アクティビティでユーザーを保持するか削除するかの選択、参加者ごとに 1 回指標をカウントするか、すべてのインプレッションで指標をカウントするかの選択などのオプションがあります。 以下に示すように、縦並びの省略記号/[!UICONTROL Advanced Settings] をクリックして、A4T 以外のアクティビティの [!UICONTROL Advanced Settings] のオプションにアクセスします。

![詳細設定](/help/main/c-activities/r-success-metrics/assets/advanced-settings.png)

+++

## 計算指標とは何ですか？また、計算指標を使用すると SiteCatalyst:Event mbox とどのように置き換わりますか？ {#section_D59F4719E6B94758A2187427C17F8EF3}

+++回答
計算指標を使用すると、セグメントまたは数値計算から算出されるカスタム指標を作成できます。従来は、`evar27=shoes` でイベントが `purchase` の `SiteCatlayst:Event` mbox を使用していたかもしれませんが、現在は、`evar27=shoes` のセグメントを作成して、セグメントが適用されたイベントが `purchase` の計算指標を作成できます。これらの指標は、アクティビティの開始後も、いつでも作成できます。 このため、これらの指標を Analytics の任意のレポートで使用できます。

+++

## A4T では、コンバージョンを複数のキャンペーンによるものだと考えますか？ {#section_7F15C727206440CD86B3A8CE77087DF9}

+++回答
はい、「完全割り当て」設定を使用します。

+++
