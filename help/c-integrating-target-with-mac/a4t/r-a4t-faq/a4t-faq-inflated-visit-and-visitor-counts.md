---
description: このトピックには、Analytics を Target のレポートソースとして使用する（A4T）場合の水増しされた訪問および訪問者のカウントに関するよくある質問に対する回答が含まれています。
keywords: FAQ;よくある質問;analytics for target;A4T;水増し;訪問;訪問者;部分的なヒット;親なし;親なし;部分ヒット
seo-description: このトピックには、Analytics を Target のレポートソースとして使用する（A4T）場合の水増しされた訪問および訪問者のカウントに関するよくある質問に対する回答が含まれています。
seo-title: 水増しされた訪問および訪問者のカウント - A4T FAQ
solution: 'Target '
title: 水増しされた訪問および訪問者のカウント - A4T FAQ
topic: Standard
uuid: 5d1b77bb-9053-4533-bd01-d6f53f0751e9
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# 水増しされた訪問および訪問者のカウント - A4T FAQ{#inflated-visit-and-visitor-counts-a-t-faq}

このトピックには、Analytics を Target のレポートソースとして使用する（A4T）場合の水増しされた訪問および訪問者のカウントに関するよくある質問に対する回答が含まれています。

## Analytics データに、ページビュー数などの変数値のない訪問数が表示されるのはなぜですか？{#section_4D8C2C2D766842E6B12F3ECC774A64D5}

[!DNL Adobe Analytics] を使用して [!DNL Target] アクティビティを測定すると（A4T と呼ばれます）、[!DNL Analytics] により、ページに [!DNL Target] アクティビティがない場合に利用できない追加データが収集されます。これは、[!DNL Target] アクティビティではページの上部にある呼び出しが実行されますが、[!DNL Analytics] では通常、ページの下部にあるデータ収集呼び出しが実行されるためです。これまでの A4T の実装では、[!DNL Target] アクティビティがアクティブな場合は必ずこの追加データを含めていました。

詳しくは、[A4T での水増しされた訪問と訪問者カウントの最小化](../../../c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235)を参照してください。

## 部分的なデータヒットとは何ですか？{#section_59A203E289564576BF6821F96B0B9E11}

部分的なデータヒットは、ページの上部にある [!DNL Target] タグは実行されたが、ページの下部にある [!DNL Analytics] タグは実行されなかった場合に生じます。こうなる理由はいくつか考えられます。これまでの [!DNL A4T] の実装では、[!DNL Target] アクティビティがアクティブな場合は必ずこれらのヒットに関する部分的なデータを含めていました。今後、この追加データは、[!DNL Target] タグと [!DNL Analytics] タグの両方が実行された場合にのみ追加されます。

詳しくは、[A4T での水増しされた訪問と訪問者カウントの最小化](../../../c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235)を参照してください。

## 訪問のスパイクがあります。この原因が部分的なデータヒットかどうかはどうしたらわかりますか？ {#section_28506672C6224ED18AC74F6A02F6F811}

お客様は[アドビカスタマーケア](../../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)に連絡して、部分的なデータレポートを取得できます。この情報は、[!DNL Analytics] UI で直接入手することはできません。

## 部分的なデータヒットの潜在的な原因は何ですか？{#section_C4BB9925CE6444BE8CB9FBEFE5085546}

部分的なデータヒットは、多くの場合、不適切な実装（レポートスイート ID の不一致など）の結果です。また、遅いページ、ページエラー、アクティビティのリダイレクトオファー、古いライブラリバージョンなど、論理的な原因もあります。

詳細については、「[A4T での水増しされた訪問と訪問者カウントの最小化](../../../c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235)」の「部分的なデータが生じる原因」を参照してください。

## 部分的なデータヒットがあります。データをクリーンアップするにはどうすればよいですか？ {#section_CBE778A9D07A469E8FF98F68BACC7124}

仮想レポートスイートを作成して、履歴の部分的なデータをレポートから除外できます。

詳しくは、「部分的なデータを除外して履歴トレンドを表示する方法」（[A4T での水増しされた訪問と訪問者カウントの最小化](../../../c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## ページで部分的なデータヒットが生成されるのを防ぐためにできることはありますか？{#section_4B00E7E618444BE98A0798DE98F08B21}

2016 年 11 月 14 日以降は、[!DNL Target] タグと [!DNL Analytics] タグの両方が実行された場合にのみ、データが含まれます。この変更はさかのぼっては適用されません。履歴レポートに水増しされたカウントが表示され、レポートからそれらのカウントを除外したい場合は、「部分的なデータを除外して履歴トレンドを表示する方法」（[A4T での水増しされた訪問と訪問者カウントの最小化](../../../c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

部分的なデータヒットを最小限に抑えるために実行できる手順もあります。詳細については、「[A4T での水増しされた訪問と訪問者カウントの最小化](../../../c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235)」の「部分的なデータを減らすためのベストプラクティス」を参照してください。

## 部分的なデータヒットデータがレポートから削除された場合、Target または Analytics の重要なデータが失われることはありませんか？{#section_EBC39E8A0F6A40E58F51E776936F7D9E}

[!DNL Analytics] レポートに部分的なデータを含めることで追加情報が得られますが、[!DNL Target] アクティビティが実行されなかった期間の履歴データとの矛盾も生じます。[!DNL Analytics] ユーザーが長期間のトレンドを分析している場合、これが原因で問題が起こる可能性があります。

部分的なデータヒットを最小限に抑えるために実行できる手順があります。詳細は、[A4T での水増しされた訪問と訪問者カウントの最小化](../../../c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235)の「部分的なデータを減らすためのベストプラクティス」を参照してください。

## 部分的なデータヒットが生成される可能性の高い特定のタイプの Target アクティビティはありますか？{#section_69837442A9B84366BEFDA4588B31E574}

リダイレクトオファーでは、すぐにユーザーを別のページに送信するので、最初のページで [!DNL Analytics] の呼び出しが実行されません。
