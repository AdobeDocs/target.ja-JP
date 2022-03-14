---
keywords: 部分的なデータ;部分的なデータ;A4T; 矛盾;Analytics for Target;親なし;仮想レポートスイート;ファントム;トラブルシューティング;未関連付け;水増し;未指定
description: Analytics を [!DNL Target] (A4t) を参照してください。 「部分的なデータ」とは何かと、それを減らす方法について説明します。
title: A4T での水増しされた訪問と訪問者カウントを最小限に抑える方法を教えてください。
feature: Analytics for Target (A4T)
exl-id: 308711f7-e630-4f6b-8a6d-a1f36ed7902d
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1341'
ht-degree: 47%

---

# A4T での水増しされた訪問と訪問者カウントの最小化

を使用する際に、水増しされた訪問および訪問者カウントの影響を最小限に抑える方法について説明します。 [!DNL Adobe Analytics] レポートソースとして [!DNL Adobe Target] (A4T)。

>[!IMPORTANT]
>2016 年 11 月 15 日に、Adobe Analytics では、Target で Analytics レポートを使用（A4T）しているお客様のために、一部のデータの処理方法を変更しました。この変更により、Adobe Target データと Adobe Analytics のデータモデルとの整合性が向上しています。この変更は、A4T をご利用のすべてのお客様にロールアウトされています。具体的には、この変更では、一部の顧客から指摘のあった、Target アクティビティが実行されているときに訪問者カウントが水増しされる問題を解決します。
>
>この変更はさかのぼっては適用されません。履歴レポートに水増しされたカウントが表示され、レポートからそれらのカウントを除外したい場合は、下で説明されているように、仮想レポートスイートを作成できます。
>
>また、いくつかの JavaScript ライブラリが更新され、水増しされたカウントを最小限に抑えることができます。 Adobeでは、次のバージョン以降のライブラリにアップグレードすることをお勧めします。
>
>* Experience Cloud 訪問者 ID サービス：visitorAPI.js バージョン 2.3.0 以降。
>* Adobe Analytics：appMeasurement.js バージョン 2.1。
>* Adobe Target：at.js バージョン 0.9.6 以降（A4T でリダイレクトオファーを使用している場合はバージョン 1.1.0 を除く）。


## 変更内容  {#section_9CCF45F5D66D48EBA88F3A178B27D986}

条件 [!DNL Adobe Analytics] は、 [!DNL Target] アクティビティ（A4T と呼ばれる） [!DNL Analytics] がない場合に利用できない追加のデータを収集します [!DNL Target] アクティビティを選択します。 この [!DNL Target] 「 」アクティビティは、ページ上部に呼び出しを実行しますが、 [!DNL Analytics] は、通常、ページの下部でデータ収集呼び出しを実行します。 これまでの A4T の実装では、Adobeには、 [!DNL Target] アクティビティがアクティブでした。 今後、Adobeには、この追加データが含まれるのは、 [!DNL Target] および [!DNL Analytics] タグが実行されました。

## この変更をおこなった理由 {#section_92380A4BD69E4B8886692DD27540C92A}

アドビはデータの正確性と品質に自信を持っています。次の場合に [!DNL Target] タグが実行され、 [!DNL Analytics] タグに含まれていない場合、Analytics は、「部分的なデータ」（「未関連付けヒット」とも呼ばれます）を記録します。 これらの未関連付けヒットは、 [!DNL Analytics] もし [!DNL Target] アクティビティ。 ただし、 [!DNL Analytics] レポートは追加情報を提供しますが、まだ情報がなかった期間の履歴データとの矛盾も生じます [!DNL Target] アクティビティの実行中。 この状況は、 [!DNL Analytics] 経時的なトレンドの分析をおこなうユーザー。 でのデータの一貫性を確保するために [!DNL Analytics]の場合、Adobeはすべての部分的なデータを除外します。

## 部分的なデータが生じる原因 {#section_C9C906BEAA7D44DAB9D3C03932A2FEB8}

Adobeで、 [!DNL Analytics]. 部分的なデータの割合が高いと、不適切な実装が原因で生じる可能性がありますが、正当な原因もあります。

部分的なデータが生じる原因として特定されているものは次のとおりです。

* **レポートスイート ID（実装）の不一致：**&#x200B;アクティビティの設定中に指定されたレポートスイートが、テストが配信されるページのレポートスイートと一致していません。データを調整できません [!DNL Analytics] サーバー上に存在するので、部分的なデータのように見えます。
* **遅いページ：** [!DNL Target] 呼び出しはページの上部にあり、 [!DNL Analytics] 呼び出しは通常、ページの下部にあります。 ページの読み込みに時間がかかると、訪問者が [!DNL Target] 呼び出しが実行される前、が [!DNL Analytics] 呼び出し。 低速なページは、接続速度が頻繁に低下するモバイル Web サイトでは特に問題になる場合があります。
* **ページエラー：** JavaScript エラーがある場合や、各タッチポイントが実行されないシナリオ (Experience CloudID サービス、Target および Analytics) の場合、データの一部が返されます。
* **でのリダイレクトオファー [!DNL Target] アクティビティ：** A4T を使用してアクティビティでリダイレクトオファーを使用する場合、実装が特定の最小要件を満たす必要があります。 また、知っておくべき重要な情報もあります。 詳しくは、[リダイレクトオファー - A4T に関する FAQ](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#section_FA9384C2AA9D41EDBCE263FFFD1D9B58) を参照してください。
* **ライブラリの古いバージョン：** 過去 1 年間に、Adobeで JavaScript ライブラリ ( [!DNL appMeasurement.js], `at.js`、および `visitorAPI.js`) を使用して、データをできるだけ効率的に送信する必要があります。 導入に必要な条件について詳しくは、[実装する前に](/help/main/c-integrating-target-with-mac/a4t/before-implement.md#concept_046BC89C03044417A30B63CE34C22543)を参照してください。

## 部分的なデータを減らすためのベストプラクティス {#section_065C38501527451C8058278054A1818D}

部分的なデータ収集を減らすには、次の手順を確認します。

| 手順 | タスク |
| --- | --- |
| ![手順 1](assets/step1_icon.png) | レポートスイートが [!DNL Target] は、アクティビティが表示されるページのものと同じです。 |
| ![手順 2](assets/step2_icon.png) | visitorAPI.js、appMeasurement.js および at.js ライブラリが A4T と互換性のあるバージョンにあることを確認します。 導入に必要な条件について詳しくは、[実装する前に](/help/main/c-integrating-target-with-mac/a4t/before-implement.md)を参照してください。 |
| ![手順 3](assets/step3_icon.png) | SDID がすべての [!DNL Target] および [!DNL Analytics] は、ページを離れると一致するを呼び出します。<br/>ネットワークアナライザーまたはデバッグツールを使用して、 `mboxMCSDID` のパラメーター [!DNL Target] の呼び出しは、 [!DNL Analytics] 呼び出し。 |
| ![手順 4](assets/step4_icon.png) | サイトで実装ライブラリが正しい順序で読み込まれることを確認します。詳しくは、[Analytics for Target の実装](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md). |

## 部分的なデータの部分を見るにはどうすればよいですか？ {#section_89B663E2824A4805AB934153508A0F4B}

この情報を [!DNL Analytics] で直接入手することはできませんが、アドビカスタマーケアに連絡して、部分的なデータレポートを取得できます。このレポートは、デバッグを支援するためのものです。

## 部分的なデータを含まない履歴トレンドを表示するにはどうしたらよいですか？ {#section_4C9DED560FAD4428B362DDA2064897C3}

この処理の変更は、リリース日（2016 年 11 月 15 日）以降のデータにのみ影響します。 過去の指標が一致するように調整する場合は、部分的なデータを除外するセグメントを作成することをAdobeにお勧めします。

この変更に関連する次の情報には、セグメントを定義し、仮想レポートスイートに適用して、このセグメントが常に [!DNL Analytics] ビューに適用されるようにするための手順が含まれています。

ほとんどの状況では、 [!DNL Target] ヒットが各ウェブページの [!DNL Analytics] ヒットで結び付けられます。[!DNL Target] および [!DNL Analytics] 呼び出し両方と同じページの [!DNL Analytics] 呼び出しに [!DNL Experience Cloud ID]（MCID） に一貫した SDID がある場合、この関連付けが発生します。[!DNL Target] は通常、MCID も持っていますが、 [!DNL Target] は訪問者 ID が戻る前に発生します。このヒットは、SDID によって関連付けられます。 また、[!DNL Target] を呼び出した後、[!DNL Analytics] を呼び出すまで、ユーザーが同じページにとどまる必要もあります。このシナリオは理想的です。

**部分的なデータヒット:** ユーザーは、呼び出しを [!DNL Analytics] 送信するまでに十分な長さのページにとどまり、適切なMCIDが [!DNL Target] あることがあります。このシナリオでは、部分的なデータヒットが発生します ( [!DNL Analytics] ページビュー )。 ユーザーがサイトに戻ってきて、 [!DNL Analytics] コードで指定された場合、再訪問者として適切にカウントされます。 以下のヒットが失われたのは、 [!DNL Analytics] コードをページに貼り付けます。 このヒットのデータは、一定の指標（訪問数）を水増しし、他の指標（1 訪問あたりのページビュー数、1 訪問あたりの時間など）を下げてしまうため、そういったデータを望まないクライアントもいます。また、ページビューのない訪問も表示されます。 ただし、このデータを保持する正当な理由もあります。

部分的なデータヒットを最小限に抑えるには、ページの読み込みを高速化したり、ライブラリの最新バージョンに更新したり、それらのヒットを除外した[仮想レポートスイート](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-workflow/vrs-create.html)を作成したりします。詳細な手順については、 [仮想レポートスイートの作成](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-workflow/vrs-create.html) 内 *Analytics コンポーネントガイド*.

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

**親なしヒット：** Analytics が呼び出される前にユーザーがページを離れてしまい、Target が適切な MCID を受け取らないこともありえます。これらのヒットは、Adobeが「親なし」ヒットと呼ぶものです。 これらのヒットは、ほとんど戻ってくることのない顧客を表し、訪問数と訪問者数を不適切に水増しします。

こういった「親なし」ヒットを最小限に抑えるには、上で説明しているように、こうしたヒットを除外する[仮想レポートスイート](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-workflow/vrs-create.html)を作成することができます。

## [!DNL Target] レポートの意味は何ですか？ {#section_AAD354C722BE46D4875507F0FCBA5E36}

この変更が発生すると、ライブテストの新規訪問者数と訪問回数が減少する場合があります。 [!DNL Adobe] は受信する部分的なデータを処理しません。 他の [!DNL Analytics] の指標のコンバージョンおよびヒットは変更されません。
