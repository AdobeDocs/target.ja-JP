---
keywords: Analytics トラッキングサーバー;A4T;Analytics セグメント;レポートスイート;誤ったデータ;親なし;sdid;VisitorAPI.js;mboxMCSDID;ファントム;未指定
description: Analytics を使用して [!DNL Target] (A4T)。
title: Analytics とのトラブルシューティング方法 [!DNL Target] 統合 (A4T)
feature: Analytics for Target (A4T)
exl-id: 7d155cbe-e799-43b5-afc2-1aea43f432ba
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '987'
ht-degree: 39%

---

# Analytics のトラブルシューティングと [!DNL Target] 統合 (A4T)

このトピックでは、 [!DNL Adobe Analytics] レポートソースとして [!DNL Adobe Target] (A4T)。

## Analytics にアクティビティのデータが表示されず、その代わり、「未指定」と表示されます。 {#unspecified}

データが「未指定」と表示される場合がある理由はいくつかあります。

* [!DNL Target] の分類が完全に処理されていない。

   レポートを分類するには、通常、最初の保存から 24 ～ 72 時間かかります。

* レポートスイートにはデータが全く含まれていないが、[!DNL Target] はヒットの分類を試行した。[!DNL Target] は最初のヒットが発生するまで、データの分類をおこなうことができません。

   レポートスイートで、少なくとも 1 つはヒットがあったことを確認してください。

* [!DNL Target] から [!DNL Analytics] への分類呼び出しが失敗した。

   [カスタマーケア](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)までお問い合わせください。

「未指定」行を「Analytics for Target」ディメンションで分類し、アクティビティ ID が含まれていない場合は、すべてが正しく分類されています。 アクティビティ ID がリストに表示される場合、分類の問題を示します。

>[!NOTE]
>
>レポートに正しくデータが表示され、分類が完了していない新しいアクティビティが追加されたので、「未指定」に戻ることがあります。 レポートを分類するには、通常、最初の保存から 24 ～ 72 時間かかることに注意してください。
>
>「未指定」と表示されていても、データは失われていません。分類が実行された後、データはアクティビティまたはエクスペリエンスに適切に割り当てられます。

## A4T アクティビティレポートには、多くの「未指定」イベントが含まれる行が含まれています。 {#added_unspecified_events}

「[!UICONTROL 未指定]」個のイベント行が表示されます。

通常、この行は、 [!DNL Target]-specific ( 例： [!UICONTROL ページビュー数], [!UICONTROL 訪問回数], [!UICONTROL 実訪問者数]など ) を含める必要があります。 この場合、 [!UICONTROL &quot;未指定&quot;] 行にすべてを含む [!UICONTROL ページビュー数], [!UICONTROL 訪問回数]、および [!UICONTROL 実訪問者数] それは [!DNL Target] アクティビティ。

その行には [!DNL Target]関連情報（訪問者数、訪問数、インプレッション数など）。 詳しくは、 [レポートにおける「未指定」、「なし」、「その他」および「不明」](https://experienceleague.adobe.com/docs/analytics/technotes/unspecified.html?lang=en) 内 *Analytics テクニカルノート*.

次を選択した場合、 [!DNL Target] — レポート内の特定の指標 [!UICONTROL &quot;未指定&quot;] 行が表示されません。 レポート全体でこの特性を持つことを回避する唯一の方法は、 [!DNL Target] は、一般的でも必要でもない、そのページから送信されるすべてのリクエストでを呼び出します。

## Analytics データにて、A4T を開始してから訪問または訪問カウントが水増しされています。 {#section_4BE374E573D44FB7918611699B74F58E}

詳しくは、[A4T での水増しされた訪問と訪問者カウントの最小化](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235)を参照してください。

## 売上高指標の推定上昇率に正しいデータが表示されません。 {#section_35D766E5E4D347C39E15D08AA883FBB0}

上昇率と信頼性の詳細は、Analytics では利用できません。ただし、これらの詳細は Target レポートで利用できます。

## Analytics レポートにアクティビティが表示されません。 {#section_F7001EB4670F4B3497CC7DA60BBDA6D5}

A4T アクティビティには Analytics トラッキングサーバーの指定が必要です。詳しくは、 [Analytics トラッキングサーバーの使用](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823) Analytics トラッキングサーバーが正しく設定されていることを確認します。

>[!NOTE]
>
>at.js バージョン 0.9.1 以降を使用している場合は、アクティビティの作成中にトラッキングサーバーを指定する必要はありません。 at.js ライブラリは、トラッキングサーバーの値をに自動的に送信します。 [!DNL Target]. アクティビティの作成時には、[!UICONTROL 目標および設定]ページの「[!UICONTROL トラッキングサーバー]」フィールドを空白にできます。

## Analytics セグメントが Target に表示されません。 {#section_DEE87F1557834F448E99381D3D02EEEF}

A4T アクティビティの作成を始める前に、適切な権限があることを確認してください。

* Adobe Analyticsの Web サービスアクセスグループに属しているので、Analytics を Target のレポートソースとして使用できます
* Analytics および Target へのアクセス権を持つ 1 つ以上のExperience Cloudグループのメンバーである。
* 左側のナビゲーションの「マーケティングアプリ」セクションに Analytics と Target が表示されていることを確認してください。

## バウンス率、バウンスおよび出口の指標がレポートで肯定的なものとして表示されます。 {#section_B5C3D56EF0344407AE67ABEB93037F5A}

これらの指標がレポートで肯定的なものとして表示されるのは、既知の問題です。

これらの指標は否定的な意味を持っていますが、Target レポートでは、これらの指標の上昇が肯定的な現象であるかのように表示されます。例えば、バウンス率を低く抑えたい場合であっても、最も高いバウンス率を持つものが勝者として表示されます。このような指標の取り扱いには注意が必要です。ポートに基づいて判断をおこなう場合には、数値が低下した方が好ましいのか、上昇した方が好ましいのかを確認してください。

## 必要なレポートスイートが表示されません。 {#section_BD8F956E41D6475B98B7BF0C74CC387C}

に表示されるレポートスイートのリスト [!DNL Target Standard/Premium] は、 [!DNL Analytics] レポートソースとして [!DNL Target] (A4T)。 存在するすべてのレポートスイートが表示されるわけではありません。

複数のレポートソースを使用している場合、レポートスイートが [!DNL Target] 同様に。 レポートスイートがデフォルトのレポートソースにない場合、レポートスイートは表示されません。

探しているレポートスイートがまだ表示されない場合は、にお問い合わせください。 [ClientCare](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) 有効にします。

## 期待した量のレポートのデータが表示されません。 {#section_75002584FA63456D8D9086172925DD8D}

（特に訪問者にエクスペリエンスの資格を与えるページについて）実装を確認して、追加のデータ ID が [!DNL Target] と [!DNL Analytics] の呼び出しで一致していることを確認してください。

* **at.js 1.x**:内 [!DNL Target] 呼び出しの場合、追加の ID は `mboxMCSDID` パラメーター。 [!DNL Analytics] 呼び出しでは、追加の ID は `sdid` パラメーターに含まれます。
* **at.js 2.x**:内 [!DNL Target] を呼び出すと、追加の ID が `experienceCloud.analytics.supplementalDataId`. [!DNL Analytics] 呼び出しでは、追加の ID は `sdid` パラメーターに含まれます。

追加の ID を調べる最も簡単な方法は、 Adobe Experience Platform Debugger を使用することです。

デバッガーをまだインストールしていない場合は、 [Adobe Experience Platform Debugger の概要](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/web-sdk/introduction-to-the-experience-platform-debugger.html).

![デバッガー](/help/main/c-integrating-target-with-mac/a4t/assets/debugger.png)

追加のデータ ID が [!DNL Target] を呼び出し、 [!DNL VisitorAPI.js] ファイルは [!DNL at.js]. [!DNL Analytics] 呼び出しに追加のデータ ID がない場合は、[!DNL Target] 呼び出しが [!DNL Analytics] 呼び出しより先に実行されていることを確認してください。

詳細については、「[Analytics for Target の実装](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md#concept_CE78750AC2A4487D8ACD9369B3EAC85A)」を参照してください。または、[カスタマーケア](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)までお問い合わせください。