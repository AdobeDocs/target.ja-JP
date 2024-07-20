---
keywords: FAQ;よくある質問;analytics for target;A4T;水増し;訪問;訪問者;部分的なヒット;親なし;親なし;部分ヒット
description: Analytics for  [!DNL Target]  （A4T）を使用する場合の水増しされた訪問と訪問者カウントに関する質問への回答を示します。 「部分的なデータ」を最小化する方法を説明します。
title: A4T での訪問と訪問者のカウントの水増しに関する FAQ はどこで見つけることができますか？
feature: Analytics for Target (A4T)
exl-id: e936b1f6-dc72-4ab2-9bb5-169d1710edbe
source-git-commit: 0be54d82e25eb919102f6098c1b1db76ab291675
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 45%

---

# 水増しされた訪問および訪問者のカウント - A4T FAQ

このトピックには、Analytics を Target のレポートソースとして使用する（A4T）場合の水増しされた訪問および訪問者のカウントに関するよくある質問に対する回答が含まれています。

## 訪問のスパイクがあります。これらの訪問が部分的なデータヒットによって発生したかどうかを確認する方法 {#section_28506672C6224ED18AC74F6A02F6F811}

+++回答
部分的なデータレポートを取得するには、[Adobeカスタマーケア ](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) にお問い合わせください。 この情報は、[!DNL Analytics] UI で直接入手することはできません。

+++

## 部分的なデータヒットの潜在的な原因は何ですか？ {#section_C4BB9925CE6444BE8CB9FBEFE5085546}

+++回答
部分的なデータヒットは、多くの場合、レポートスイート ID のアラインメントの誤りなど、不適切な実装が原因で発生します。 また、遅いページ、ページエラー、アクティビティのリダイレクトオファー、古いライブラリバージョンなど、論理的な原因もあります。

+++

## 部分的なデータヒットを引き起こす可能性の高い特定のタイプの [!DNL Target] アクティビティはありますか？ {#section_69837442A9B84366BEFDA4588B31E574}

+++回答
リダイレクトオファーでは、ユーザーが直ちに別のページに送信されます。つまり、[!DNL Analytics] 呼び出しは最初のページでは実行されません。

+++