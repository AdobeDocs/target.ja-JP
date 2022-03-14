---
keywords: FAQ;よくある質問;analytics for target;A4T;水増し;訪問;訪問者;部分的なヒット;親なし;親なし;部分ヒット
description: Analytics を [!DNL Target] (A4T)。 「部分的なデータ」を最小限に抑える方法を説明します。
title: A4T での水増しされた訪問と訪問者カウントに関する FAQ はどこで確認できますか？
feature: Analytics for Target (A4T)
exl-id: e936b1f6-dc72-4ab2-9bb5-169d1710edbe
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '653'
ht-degree: 61%

---

# 水増しされた訪問および訪問者のカウント - A4T FAQ

このトピックには、Analytics を Target のレポートソースとして使用する（A4T）場合の水増しされた訪問および訪問者のカウントに関するよくある質問に対する回答が含まれています。

## Analytics データに、ページビュー数などの変数値のない訪問数が表示されるのはなぜですか？ {#section_4D8C2C2D766842E6B12F3ECC774A64D5}

条件 [!DNL Adobe Analytics] は、 [!DNL Target] アクティビティ（A4T と呼ばれる） [!DNL Analytics] がない場合に利用できないデータを収集します [!DNL Target] アクティビティを選択します。 これは、[!DNL Target] アクティビティではページの上部にある呼び出しが実行されますが、[!DNL Analytics] では通常、ページの下部にあるデータ収集呼び出しが実行されるためです。これまでの A4T の実装では、Adobeには、 [!DNL Target] アクティビティがアクティブでした。

詳しくは、[A4T での水増しされた訪問と訪問者カウントの最小化](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235)を参照してください。

## 部分的なデータヒットとは何ですか？ {#section_59A203E289564576BF6821F96B0B9E11}

部分的なデータヒットは、ページの上部にある [!DNL Target] タグは実行されたが、ページの下部にある [!DNL Analytics] タグは実行されなかった場合に生じます。この状況が起こる理由は様々です。 内 [!DNL A4T] これまでの実装では、Adobeには、常にこれらのヒットに関する部分的なデータが含まれます [!DNL Target] アクティビティがアクティブでした。 今後、Adobeは、この追加データを含めるのは、 [!DNL Target] および [!DNL Analytics] タグが実行されました。

詳しくは、[A4T での水増しされた訪問と訪問者カウントの最小化](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235)を参照してください。

## 訪問のスパイクがあります。これらの訪問が部分的なデータヒットが原因であるかどうかは、どうすればわかりますか？ {#section_28506672C6224ED18AC74F6A02F6F811}

お客様は[アドビカスタマーケア](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)に連絡して、部分的なデータレポートを取得できます。この情報は、[!DNL Analytics] UI で直接入手することはできません。

## 部分的なデータヒットの潜在的な原因は何ですか？ {#section_C4BB9925CE6444BE8CB9FBEFE5085546}

部分的なデータヒットは、多くの場合、不適切な実装（レポートスイート ID の不一致など）の結果です。また、遅いページ、ページエラー、アクティビティのリダイレクトオファー、古いライブラリバージョンなど、論理的な原因もあります。

詳細については、「[A4T での水増しされた訪問と訪問者カウントの最小化](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235)」の「部分的なデータが生じる原因」を参照してください。

## 部分的なデータヒットがあります。データをクリーンアップするにはどうすればよいですか？ {#section_CBE778A9D07A469E8FF98F68BACC7124}

仮想レポートスイートを作成して、履歴の部分的なデータをレポートから除外できます。

詳しくは、「部分的なデータを除外して履歴トレンドを表示する方法」（[A4T での水増しされた訪問と訪問者カウントの最小化](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

## ページで部分的なデータヒットが生成されるのを防ぐためにできることはありますか？ {#section_4B00E7E618444BE98A0798DE98F08B21}

2016 年 11 月 14 日以降、Adobeには、 [!DNL Target] および [!DNL Analytics] タグが実行されました。 この変更はさかのぼっては適用されません。履歴レポートに水増しされたカウントが表示される場合は、仮想レポートスイートを作成することで、それらのカウントをレポートから除外できます。 「部分的なデータを含まない履歴トレンドを表示するにはどうすればよいですか？」を参照してください。 in [A4T での水増しされた訪問と訪問者カウントの最小化](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235).

部分的なデータヒットを最小限に抑えるために実行できる手順もあります。詳細は、[A4T での水増しされた訪問と訪問者カウントの最小化](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235)の「部分的なデータを減らすためのベストプラクティス」を参照してください。

## 部分的なデータヒットデータがレポートから削除された場合、重要なデータが失われることはありません [!DNL Target] Analytics データのどちらが該当しますか。 {#section_EBC39E8A0F6A40E58F51E776936F7D9E}

部分的なデータを [!DNL Analytics] レポートは追加情報を提供しますが、また、まだ情報がなかった期間の履歴データとの矛盾も生じます [!DNL Target] アクティビティの実行中。 部分ヒットデータを含めると、 [!DNL Analytics] 経時的なトレンドの分析をおこなうユーザー。

部分的なデータヒットを最小限に抑えるために実行できる手順があります。詳細は、[A4T での水増しされた訪問と訪問者カウントの最小化](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235)の「部分的なデータを減らすためのベストプラクティス」を参照してください。

## 特定のタイプの [!DNL Target] アクティビティで部分的なデータヒットが発生する可能性の高いものを示しますか？ {#section_69837442A9B84366BEFDA4588B31E574}

リダイレクトオファーでは、すぐにユーザーを別のページに送信するので、最初のページで [!DNL Analytics] の呼び出しが実行されません。
