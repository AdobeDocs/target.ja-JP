---
keywords: faq;frequently asked questions;analytics for target;a4T;metric;metric definitions
description: このトピックには、指標の定義と、Analytics を Target のレポートソースとして使用すること（A4T）に関するよくある質問に対する回答が含まれています。
title: 指標の定義 - A4T FAQ
feature: a4t troubleshooting
topic: Standard
uuid: 41d41665-9057-479d-b0a8-7cffb90ca843
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 100%

---


# 指標の定義 - A4T FAQ{#metric-definitions-a-t-faq}

このトピックには、指標の定義と、Analytics を Target のレポートソースとして使用すること（A4T）に関するよくある質問に対する回答が含まれています。

## アクティビティメンバーシップの期限切れとは何ですか？訪問者にアクティビティが再度表示されない場合、アクティビティのアクションがカウントされるのは、訪問者がアクティビティに参加してからどのくらいの期間ですか？ {#section_41B4958F33534E4B96DEE0C981227A79}

アクティビティのデフォルトの有効期限は、訪問者のアクティビティでの最後のインタラクションの後、90 日です。これは、必要に応じて ClientCare に依頼することで調整できます。この設定は、すべてのアクティビティでグローバルなので、1 つの事例のために調整することはしないでください。

## Target の成功指標の高度なオプションは A4T で機能しますか？ {#section_F060E3438F4144258BB95813EDEABDAA}

これらのオプションは、現在、A4T では機能しません。

## 計算指標とは何ですか？ 以前使用していた SiteCatalyst:Event mbox をどのように置き換えるものですか？ {#section_D59F4719E6B94758A2187427C17F8EF3}

計算指標を使用すると、セグメントまたは数値計算から算出されるカスタム指標を作成できます。従来は、`evar27=shoes` でイベントが `purchase` の `SiteCatlayst:Event` mbox を使用していたかもしれませんが、現在は、`evar27=shoes` のセグメントを作成して、セグメントが適用されたイベントが `purchase` の計算指標を作成できます。このメリットは、これらの指標が、たとえアクティビティが進行中でも、いつでも作成できるということです。このため、これらの指標を Analytics の任意のレポートで使用できます。

## A4T では、コンバージョンを複数のキャンペーンによるものだと考えますか？ {#section_7F15C727206440CD86B3A8CE77087DF9}

はい。これは、配分設定をフルにすることでおこなわれます。
