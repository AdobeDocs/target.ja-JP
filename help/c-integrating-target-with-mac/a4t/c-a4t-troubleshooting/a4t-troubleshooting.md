---
keywords: Analytics トラッキングサーバー;A4T;Analytics セグメント;レポートスイート;誤ったデータ;親なし;sdid;VisitorAPI.js;mboxMCSDID;ファントム;未指定
description: Analytics for [!DNL Target] (A4T)を使用する際に発生している一般的な問題を調べます。
title: Analyticsと [!DNL Target] 統合(A4T)のトラブルシューティング方法を教えてください。
feature: Analytics for Target（A4T）
exl-id: 7d155cbe-e799-43b5-afc2-1aea43f432ba
source-git-commit: 3c79b2ce70e456275ddf6774a35ae5c36f0ae99d
workflow-type: tm+mt
source-wordcount: '992'
ht-degree: 39%

---

# Analyticsと[!DNL Target]統合(A4T)のトラブルシューティング

このトピックでは、[!DNL Adobe Target]のレポートソースとして[!DNL Adobe Analytics]を使用する(A4T)際に発生する一般的な問題について説明します。

## Analytics にアクティビティのデータが表示されず、その代わり、「未指定」と表示されます。 {#unspecified}

データが「未指定」と表示される理由はいくつかあります。

* [!DNL Target] の分類が完全に処理されていない。

   レポートを分類するには、通常、最初の保存から24 ～ 72時間かかります。

* レポートスイートにはデータが全く含まれていないが、[!DNL Target] はヒットの分類を試行した。[!DNL Target] は最初のヒットが発生するまで、データの分類をおこなうことができません。

   レポートスイートで、少なくとも 1 つはヒットがあったことを確認してください。

* [!DNL Target] から [!DNL Analytics] への分類呼び出しが失敗した。

   [カスタマーケア](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)までお問い合わせください。

「未指定」行を「Analytics for Target」ディメンションで分類し、アクティビティIDがない場合は、すべてが正しく分類されています。 アクティビティIDがここに表示されている場合は、分類の問題を示します。

>[!NOTE]
>
>新しいアクティビティが追加され、分類が完了していない場合、レポートに正しくデータが表示され、「未指定」に戻ることがあります。 レポートを分類するには、通常、最初の保存から24 ～ 72時間かかります。
>
>「未指定」と表示されていても、データは失われていません。分類が実行された後、データはアクティビティまたはエクスペリエンスに適切に割り当てられます。

## A4Tアクティビティレポートには、多くの「未指定」イベントを含む行が含まれます。 {#added_unspecified_events}

データの表示に使用する指標に応じて、レポートに「[!UICONTROL 未指定]」イベント行が表示される場合があります。

通常、この行は、[!DNL Target]固有ではない一般的な指標をレポートで選択した場合に表示されます（例：[!UICONTROL ページビュー]、[!UICONTROL 訪問回数]、[!UICONTROL 個別訪問者数]など）。 この場合、[!UICONTROL &quot;Unspecified&quot;]行には、[!DNL Target]アクティビティに関連付けられていない[!UICONTROL ページビュー]、[!UICONTROL 訪問回数]、[!UICONTROL 実訪問者数]がすべて含まれます。

その行には[!DNL Target]に関連する情報は含まれません（例えば、訪問者、訪問、インプレッションがありません）。 詳しくは、*Analyticsのテクニカルノート*&#x200B;のレポート](https://experienceleague.adobe.com/docs/analytics/technotes/unspecified.html?lang=en)の「[」（未指定）、「なし」、「その他」、「不明」（不明）を参照してください。

レポートで[!DNL Target]固有の指標を選択した場合、[!UICONTROL &quot;Unspecified&quot;]行は表示されません。 レポート全体でこれを回避する唯一の方法は、そのページから送信されるすべてのリクエストに対して[!DNL Target]呼び出しを設定することです。これは、一般的でも必要でもありません。

## Analytics データにて、A4T を開始してから訪問または訪問カウントが水増しされています。 {#section_4BE374E573D44FB7918611699B74F58E}

詳しくは、[A4T での水増しされた訪問と訪問者カウントの最小化](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235)を参照してください。

## 売上高指標の推定上昇率に正しいデータが表示されません。 {#section_35D766E5E4D347C39E15D08AA883FBB0}

上昇率と信頼性の詳細は、Analytics では利用できません。ただし、これらの詳細は Target レポートで利用できます。

## Analytics レポートにアクティビティが表示されません。 {#section_F7001EB4670F4B3497CC7DA60BBDA6D5}

A4T アクティビティには Analytics トラッキングサーバーの指定が必要です。詳しくは、  [Analyticsトラッキングサーバーを使](/help/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823) 用して、Analyticsトラッキングサーバーが正しく設定されていることを確認します。

>[!NOTE]
>
>at.jsバージョン0.9.1（またはそれ以降）を使用している場合、アクティビティ作成時にトラッキングサーバーを指定する必要はありません。 at.jsライブラリは、トラッキングサーバーの値を自動的に[!DNL Target]に送信します。 アクティビティの作成時には、[!UICONTROL 目標および設定]ページの「[!UICONTROL トラッキングサーバー]」フィールドを空白にできます。

## Analytics セグメントが Target に表示されません。 {#section_DEE87F1557834F448E99381D3D02EEEF}

A4T アクティビティの作成を始める前に、適切な権限があることを確認してください。

* Adobe AnalyticsのWebサービスアクセスグループに属し、AnalyticsをTargetのレポートソースとして使用できる
* AnalyticsとTargetへのアクセス権を持つ1つ以上のExperience Cloudグループのメンバーである。
* 左側のナビゲーションの「マーケティングアプリ」セクションに Analytics と Target が表示されていることを確認してください。

## バウンス率、バウンスおよび出口の指標がレポートで肯定的なものとして表示されます。 {#section_B5C3D56EF0344407AE67ABEB93037F5A}

これらの指標がレポートで肯定的なものとして表示されるのは、既知の問題です。

これらの指標は否定的な意味を持っていますが、Target レポートでは、これらの指標の上昇が肯定的な現象であるかのように表示されます。例えば、バウンス率を低く抑えたい場合であっても、最も高いバウンス率を持つものが勝者として表示されます。このような指標の取り扱いには注意が必要です。ポートに基づいて判断をおこなう場合には、数値が低下した方が好ましいのか、上昇した方が好ましいのかを確認してください。

## 必要なレポートスイートが表示されません。 {#section_BD8F956E41D6475B98B7BF0C74CC387C}

[!DNL Target Standard/Premium]に表示されるレポートスイートのリストは、[!DNL Target](A4T)のレポートソースとして[!DNL Analytics]用に設定されたレポートスイートのリストです。 存在するすべてのレポートスイートが表示されるわけではありません。

複数のレポートソースを使用する場合は、[!DNL Target]のデフォルトのレポートソースセットにもレポートスイートが存在する必要があります。 レポートスイートがデフォルトのレポートソースにない場合、レポートスイートは表示されません。

まだ探しているレポートスイートが表示されない場合は、[ClientCare](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)に連絡して有効にしてください。

## 期待した量のレポートのデータが表示されません。 {#section_75002584FA63456D8D9086172925DD8D}

（特に訪問者にエクスペリエンスの資格を与えるページについて）実装を確認して、追加のデータ ID が [!DNL Target] と [!DNL Analytics] の呼び出しで一致していることを確認してください。

* **at.js 1.x**&#x200B;の場合：呼び出しで [!DNL Target] は、追加のIDはパラメーターに含ま `mboxMCSDID` れます。[!DNL Analytics] 呼び出しでは、追加の ID は `sdid` パラメーターに含まれます。
* **at.js 2.x**:呼び出し [!DNL Target] では、追加のIDがの値としてHTTPヘッダーに返され `experienceCloud.analytics.supplementalDataId`ます。[!DNL Analytics] 呼び出しでは、追加の ID は `sdid` パラメーターに含まれます。

追加のIDを調べる最も簡単な方法は、 Adobe Experience Platform Debuggerを使用することです。

Debuggerをまだインストールしていない場合は、「[Adobe Experience Platform Debuggerの概要](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/web-sdk/introduction-to-the-experience-platform-debugger.html)」を参照してください。

![デバッガー](/help/c-integrating-target-with-mac/a4t/assets/debugger.png)

[!DNL Target]呼び出しに追加のデータIDがない場合は、[!DNL at.js]の前に[!DNL VisitorAPI.js]ファイルが読み込まれていることを確認します。 [!DNL Analytics] 呼び出しに追加のデータ ID がない場合は、[!DNL Target] 呼び出しが [!DNL Analytics] 呼び出しより先に実行されていることを確認してください。

詳細については、「[Analytics for Target の実装](/help/c-integrating-target-with-mac/a4t/a4timplementation.md#concept_CE78750AC2A4487D8ACD9369B3EAC85A)」を参照してください。または、[カスタマーケア](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)までお問い合わせください。
