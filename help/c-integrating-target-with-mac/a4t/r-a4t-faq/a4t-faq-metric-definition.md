---
keywords: FAQ;よくある質問;analytics for target;A4T;指標;指標の定義
description: 指標の定義とAnalyticsによるターゲット(A4T)に関する質問への回答を検索します。 A4Tを使用すると、Adobe TargetアクティビティでAnalyticsレポートを使用できます。
title: A4Tを使用した指標定義に関する情報はどこで入手できますか。
feature: Analytics for Target（A4T）
translation-type: tm+mt
source-git-commit: e45f0d2d2370f9c7aba2c2bd26afdd4c0e401db8
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 39%

---


# 指標の定義 - A4T FAQ

このトピックでは、指標の定義に関してよくある質問と、[!DNL Adobe Analytics]を[!DNL Adobe Target]のレポートソースとして使用する(A4T)質問に対する回答を記載します。

## アクティビティメンバーシップの期限切れとは何ですか？訪問者がアクティビティに入ってからどのくらい経つと、再び表示されない場合にアクティビティでのアクションがカウントされますか。{#section_41B4958F33534E4B96DEE0C981227A79}

アクティビティのデフォルトの有効期限は、訪問者のアクティビティでの最後のインタラクションの後、90 日です。この設定は、必要に応じてClientCareによって調整できます。 この設定は、すべてのアクティビティでグローバルなので、1 つの事例のために調整することはしないでください。

## 目標指標を設定する際に、詳細設定オプションにアクセスできないのはなぜですか。{#adv-settings}

[!UICONTROL 詳細設定]オプションは、[!DNL Analytics]をレポートソースとして使用するアクティビティ(A4T)では使用できません。

A4Tを使用するアクティビティの場合、目標指標では常に「[!UICONTROL カウントを増分、ユーザーをアクティビティに保持]」および「[!UICONTROL すべてのインプレッション]」の設定が使用されます。 これらの設定は&#x200B;*設定できません*。

A4T以外のアクティビティの場合は、[詳細設定オプション](/help/c-activities/r-success-metrics/success-metrics.md#section_7CE95A2FA8F5438E936C365A6D43BC5B)を使用して、成功の測定方法を管理できます。 依存関係の追加、アクティビティにユーザーを保持するか、ユーザーを削除するかの選択、参加者ごとに1回カウントするか、すべてのインプレッションでカウントするかを選択するオプションが含まれます。 次に示すように、A4T以外のアクティビティの[!UICONTROL 詳細設定]オプションには、垂直楕円/[!UICONTROL 詳細設定]をクリックしてアクセスします。

![詳細設定](/help/c-activities/r-success-metrics/assets/advanced-settings.png)

## 計算指標とは何ですか？ 以前使用していた SiteCatalyst:Event mbox をどのように置き換えるものですか？{#section_D59F4719E6B94758A2187427C17F8EF3}

計算指標を使用すると、セグメントまたは数値計算から算出されるカスタム指標を作成できます。従来は、`evar27=shoes` でイベントが `purchase` の `SiteCatlayst:Event` mbox を使用していたかもしれませんが、現在は、`evar27=shoes` のセグメントを作成して、セグメントが適用されたイベントが `purchase` の計算指標を作成できます。これらの指標は、アクティビティ中でも、いつでも作成できます。 このため、これらの指標を Analytics の任意のレポートで使用できます。

## A4T では、コンバージョンを複数のキャンペーンによるものだと考えますか？ {#section_7F15C727206440CD86B3A8CE77087DF9}

はい、「フル配分」設定を使用します。
