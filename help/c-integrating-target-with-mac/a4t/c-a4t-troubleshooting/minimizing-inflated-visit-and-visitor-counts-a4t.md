---
keywords: 部分的なデータ;部分的なデータ;A4T; 矛盾;Analytics for Target;親なし;仮想レポートスイート;ファントム;トラブルシューティング;未関連付け;水増し;未指定
description: Analytics for [!DNL Target] (A4t)を使用する場合に、水増しされた訪問と訪問者カウントの影響を最小限に抑える方法を説明します。 「部分的なデータ」とは何かと、データを減らす方法について説明します。
title: A4Tでの水増しされた訪問と訪問者カウントを最小限に抑える方法を教えてください。
feature: Analytics for Target（A4T）
exl-id: 308711f7-e630-4f6b-8a6d-a1f36ed7902d
source-git-commit: 3c79b2ce70e456275ddf6774a35ae5c36f0ae99d
workflow-type: tm+mt
source-wordcount: '1346'
ht-degree: 47%

---

# A4T での水増しされた訪問と訪問者カウントの最小化

[!DNL Adobe Target](A4T)のレポートソースとして[!DNL Adobe Analytics]を使用する場合に、水増しされた訪問と訪問者カウントの影響を最小限に抑える方法について説明します。

>[!IMPORTANT]
>2016 年 11 月 15 日に、Adobe Analytics では、Target で Analytics レポートを使用（A4T）しているお客様のために、一部のデータの処理方法を変更しました。この変更により、Adobe Target データと Adobe Analytics のデータモデルとの整合性が向上しています。この変更は、A4T をご利用のすべてのお客様にロールアウトされています。具体的には、この変更では、一部の顧客から指摘のあった、Target アクティビティが実行されているときに訪問者カウントが水増しされる問題を解決します。
>
>この変更はさかのぼっては適用されません。履歴レポートに水増しされたカウントが表示され、レポートからそれらのカウントを除外したい場合は、下で説明されているように、仮想レポートスイートを作成できます。
>
>また、水増しカウントを最小限に抑えるために、いくつかのJavaScriptライブラリが更新されました。 Adobeでは、次のバージョン以降のライブラリにアップグレードすることをお勧めします。
>
>* Experience Cloud 訪問者 ID サービス：visitorAPI.js バージョン 2.3.0 以降。
>* Adobe Analytics：appMeasurement.js バージョン 2.1。
>* Adobe Target：at.js バージョン 0.9.6 以降（A4T でリダイレクトオファーを使用している場合はバージョン 1.1.0 を除く）。


## 変更内容  {#section_9CCF45F5D66D48EBA88F3A178B27D986}

[!DNL Adobe Analytics]を使用して[!DNL Target]アクティビティを測定すると（A4Tと呼ばれます）、[!DNL Analytics]は、ページに[!DNL Target]アクティビティがない場合に利用できない追加データを収集します。 [!DNL Target]アクティビティは、ページの上部にある呼び出しを実行しますが、[!DNL Analytics]は通常、ページの下部にあるデータ収集呼び出しを実行します。 これまでのA4Tの実装では、[!DNL Target]アクティビティがアクティブな場合は必ずこの追加データがAdobeに含まれます。 今後、Adobeには、[!DNL Target]タグと[!DNL Analytics]タグの両方が実行された場合にのみ、この追加データが含まれます。

## この変更をおこなった理由 {#section_92380A4BD69E4B8886692DD27540C92A}

アドビはデータの正確性と品質に自信を持っています。[!DNL Target]タグは実行され、[!DNL Analytics]タグは実行されない場合、Analyticsは「部分的なデータ」（「未関連付けヒット」とも呼ばれます）を記録します。 [!DNL Target]アクティビティがない場合、これらの未関連付けヒットは[!DNL Analytics]によってキャプチャされません。 [!DNL Analytics]レポートにこの部分的なデータを含めると追加情報が得られますが、[!DNL Target]アクティビティが実行されなかった期間の履歴データとの矛盾も生じます。 この状況は、[!DNL Analytics]ユーザーが経時的にトレンドを分析している場合に問題を引き起こす可能性があります。 [!DNL Analytics]でのデータの一貫性を確保するために、Adobeは部分的なデータをすべて除外します。

## 部分的なデータが生じる原因 {#section_C9C906BEAA7D44DAB9D3C03932A2FEB8}

Adobeでは、[!DNL Analytics]内の部分的なデータの割合が高いお客様がいます。 部分的なデータの割合が高いと、不適切な実装が原因で生じる可能性がありますが、正当な原因もあります。

部分的なデータが生じる原因として特定されているものは次のとおりです。

* **レポートスイート ID（実装）の不一致：**&#x200B;アクティビティの設定中に指定されたレポートスイートが、テストが配信されるページのレポートスイートと一致していません。[!DNL Analytics]サーバーでデータを紐付けできないので、部分的なデータのように見えます。
* **遅いページ：** [!DNL Target] 呼び出しはページの上部にあり、呼び出 [!DNL Analytics] しは通常、ページの下部にあります。ページの読み込みに時間がかかると、[!DNL Target]の呼び出しの後、ただし[!DNL Analytics]の呼び出しの前に訪問者がページを離れる可能性が高くなります。 遅いページは、接続速度が頻繁に低下するモバイルWebサイトでは特に問題になる場合があります。
* **ページエラー：** JavaScriptエラーがある場合や、各タッチポイントが実行されないシナリオ(Experience CloudIDサービス、TargetおよびAnalytics)の場合、データの一部が返されます。
* **アクティビティのリダ [!DNL Target] イレクトオファー：** A4Tを使用してアクティビティでリダイレクトオファーを使用する場合、実装が特定の最小要件を満たす必要があります。また、知っておくべき重要な情報もあります。 詳しくは、[リダイレクトオファー - A4T に関する FAQ](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#section_FA9384C2AA9D41EDBCE263FFFD1D9B58) を参照してください。
* **古いバージョンのライブラリ：** データをできるだけ効率的に送信するために、過去1年間にAdobeでJavaScriptライブラリ(  [!DNL appMeasurement.js]、  `at.js`、および `visitorAPI.js` )にいくつかの改善が加えられました。導入に必要な条件について詳しくは、[実装する前に](/help/c-integrating-target-with-mac/a4t/before-implement.md#concept_046BC89C03044417A30B63CE34C22543)を参照してください。

## 部分的なデータを減らすためのベストプラクティス {#section_065C38501527451C8058278054A1818D}

部分的なデータ収集を減らすには、次の手順を確認します。

| 手順 | タスク |
| --- | --- |
| ![手順 1](assets/step1_icon.png) | [!DNL Target]で選択したレポートスイートが、アクティビティが表示されるページのレポートスイートと同じであることを確認します。 |
| ![手順 2](assets/step2_icon.png) | visitorAPI.js、appMeasurement.jsおよびat.jsライブラリがA4Tと互換性のあるバージョンであることを確認します。 導入に必要な条件について詳しくは、[実装する前に](/help/c-integrating-target-with-mac/a4t/before-implement.md)を参照してください。 |
| ![手順 3](assets/step3_icon.png) | ページを離れるすべての[!DNL Target]呼び出しと[!DNL Analytics]呼び出しでSDIDが設定され、それらが一致していることを確認します。<br/>ネットワークアナライザーまたはデバッグツールを使用して、呼び出しのパラメ `mboxMCSDID` ーター [!DNL Target] が呼び出しのSDIDパラメーターと一致することを確 [!DNL Analytics] 認します。 |
| ![手順 4](assets/step4_icon.png) | サイトで実装ライブラリが正しい順序で読み込まれることを確認します。詳しくは、[Analytics for Target の実装](/help/c-integrating-target-with-mac/a4t/a4timplementation.md). |

## 部分的なデータの部分を見るにはどうすればよいですか？ {#section_89B663E2824A4805AB934153508A0F4B}

この情報を [!DNL Analytics] で直接入手することはできませんが、アドビカスタマーケアに連絡して、部分的なデータレポートを取得できます。このレポートは、デバッグを支援するためのものです。

## 部分的なデータを含まない履歴トレンドを表示するにはどうしたらよいですか？ {#section_4C9DED560FAD4428B362DDA2064897C3}

この処理の変更は、リリース日（2016年11月15日）以降のデータにのみ影響します。 履歴指標を一致させるように調整する場合、Adobeでは、部分的なデータを除外するセグメントを作成することをお勧めします。

この変更に関連する次の情報には、セグメントを定義し、仮想レポートスイートに適用して、このセグメントが常に [!DNL Analytics] ビューに適用されるようにするための手順が含まれています。

ほとんどの状況では、 [!DNL Target] ヒットが各ウェブページの [!DNL Analytics] ヒットで結び付けられます。[!DNL Target] および [!DNL Analytics] 呼び出し両方と同じページの [!DNL Analytics] 呼び出しに [!DNL Experience Cloud ID]（MCID） に一貫した SDID がある場合、この関連付けが発生します。[!DNL Target] 通常はMCIDも含まれますが、訪問者IDが戻る前にへの呼び出しが発生した場合で [!DNL Target] も、そのヒットはSDIDによって関連付けられます。また、[!DNL Target] を呼び出した後、[!DNL Analytics] を呼び出すまで、ユーザーが同じページにとどまる必要もあります。このシナリオは理想的です。

**部分的なデータヒット:** ユーザーは、呼び出しを [!DNL Analytics] 送信するまでに十分な長さのページにとどまり、適切なMCIDが [!DNL Target] あることがあります。このシナリオでは、部分的なデータヒットが発生します（ページビューが[!DNL Analytics]でないヒット）。 ユーザーがサイトに戻ってきて、[!DNL Analytics]コードを含むページを表示すると、再訪問者として適切にカウントされます。 ページに[!DNL Analytics]コードしかない場合、これらのヒットは失われていました。 このヒットのデータは、一定の指標（訪問数）を水増しし、他の指標（1 訪問あたりのページビュー数、1 訪問あたりの時間など）を下げてしまうため、そういったデータを望まないクライアントもいます。また、ページビューのない訪問も表示されます。 ただし、このデータを保持する正当な理由もあります。

部分的なデータヒットを最小限に抑えるには、ページの読み込みを高速化したり、ライブラリの最新バージョンに更新したり、それらのヒットを除外した[仮想レポートスイート](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-workflow/vrs-create.html)を作成したりします。詳しい手順については、『*Analyticsコンポーネントガイド*』の「[仮想レポートスイートの作成](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-workflow/vrs-create.html)」を参照してください。

次の図には、仮想レポートスイートのセグメント定義を示しています。

![](assets/ts_a4t.png)

仮想レポートスイートを作成するときは、セグメント定義の次の設定を指定します（上の図を参照）。

* **表示：ヒット**
* Analytics for Target：存在する
* AND
* ページビュー数：存在しない
* AND
* カスタムリンクインスタンス：存在しない
* AND
* ダウンロードリンクインスタンス：存在しない
* AND
* 離脱リンクインスタンス：存在しない

**親なしヒット：** Analytics が呼び出される前にユーザーがページを離れてしまい、Target が適切な MCID を受け取らないこともありえます。これらのヒットは、Adobeが「親なし」ヒットと定義するものです。 これらのヒットは、ほとんど戻ってくることのない顧客を表し、訪問数と訪問者数を不適切に水増しします。

こういった「親なし」ヒットを最小限に抑えるには、上で説明しているように、こうしたヒットを除外する[仮想レポートスイート](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-workflow/vrs-create.html)を作成することができます。

## [!DNL Target] レポートの意味は何ですか？ {#section_AAD354C722BE46D4875507F0FCBA5E36}

この変更が発生すると、[!DNL Adobe]が部分的な受信データを処理しないので、ライブテストの新規訪問者数と訪問回数が減少する場合があります。 他の [!DNL Analytics] の指標のコンバージョンおよびヒットは変更されません。
