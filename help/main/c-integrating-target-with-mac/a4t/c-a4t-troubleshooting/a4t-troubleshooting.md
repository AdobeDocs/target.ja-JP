---
keywords: Analytics トラッキングサーバー;A4T;Analytics セグメント;レポートスイート;誤ったデータ;親なし;sdid;VisitorAPI.js;mboxMCSDID;ファントム;未指定
description: Analytics for  [!DNL Target] （A4T）使用時の一般的な問題について説明します。
title: Analytics と  [!DNL Target]  の統合（A4T）のトラブルシューティング方法
feature: Analytics for Target (A4T)
exl-id: 7d155cbe-e799-43b5-afc2-1aea43f432ba
source-git-commit: 0be54d82e25eb919102f6098c1b1db76ab291675
workflow-type: tm+mt
source-wordcount: '926'
ht-degree: 88%

---

# Analytics と [!DNL Target] の統合（A4T）のトラブルシューティング

このトピックでは、[!DNL Adobe Analytics] を [!DNL Adobe Target] のレポートソースとして使用する場合（A4T）に発生する一般的な問題について説明します。

## Analytics にアクティビティのデータが表示されず、その代わり、「未指定」と表示されます。 {#unspecified}

データが「未指定」と表示される場合がある理由はいくつかあります。

* [!DNL Target] の分類が完全に処理されていない。

  レポートを分類するには、通常、最初の保存から 24 ～ 72 時間かかります。

* レポートスイートにはデータが全く含まれていないが、[!DNL Target] はヒットの分類を試行した。[!DNL Target] は最初のヒットが発生するまで、データの分類をおこなうことができません。

  レポートスイートで、少なくとも 1 つはヒットがあったことを確認してください。

* [!DNL Target] から [!DNL Analytics] への分類呼び出しが失敗した。

  [カスタマーケア](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)までお問い合わせください。

「未指定」行を「Analytics for Target」ディメンションで分類し、アクティビティ ID が含まれていない場合は、すべてが正しく分類されています。アクティビティ ID がリストに表示される場合は、分類の問題が存在していることを示します。

>[!NOTE]
>
>新しいアクティビティが追加され、その分類が完了していないために、レポートに正しくデータが表示された後に「未指定」に戻ることがあります。レポートを分類するには、通常、最初の保存から 24 ～ 72 時間かかりることに注意してください。
>
>「未指定」と表示されていても、データは失われていません。分類が実行された後、データはアクティビティまたはエクスペリエンスに適切に割り当てられます。

## A4T アクティビティレポートに、多くの「未指定」イベントが含まれる行が含まれています。 {#added_unspecified_events}

データとともに表示する指標に応じて、レポートに「[!UICONTROL Unspecified]」イベント行が表示されることがあります。

通常、この行は、[!DNL Target] 固有ではない（[!UICONTROL Page Views]、[!UICONTROL Visits]、[!UICONTROL Unique Visitors] など）、レポートの一般的な指標を選択した場合に表示されます。 この場合、[!UICONTROL "Unspecified"] の行には、[!UICONTROL Page Views] のアクティビティに関連付けられていない、すべての [!UICONTROL Visits]、[!UICONTROL Unique Visitors]、[!DNL Target] が含まれます。

その行には [!DNL Target] 関連情報（訪問者数、訪問数、インプレッション数など）が含まれることはありません。詳しくは、*Analytics テクニカルノート*&#x200B;にある レポートにある[「未指定」、「なし」、「その他」、「不明」をご覧ください](https://experienceleague.adobe.com/docs/analytics/technotes/unspecified.html?lang=ja)。

レポート内で [!DNL Target] 固有の指標を選択した場合、そ [!UICONTROL "Unspecified"] 行は表示されません。 レポート全体がこの特性を持つことを回避する唯一の方法は、そのページから送信されるすべてのリクエストで、一般的でも必要でもない、[!DNL Target] 呼び出しを設定することです。

## 売上高指標の推定上昇率に正しいデータが表示されません。 {#section_35D766E5E4D347C39E15D08AA883FBB0}

上昇率と信頼性の詳細は、Analytics では利用できません。ただし、これらの詳細は Target レポートで利用できます。

## Analytics レポートにアクティビティが表示されません。 {#section_F7001EB4670F4B3497CC7DA60BBDA6D5}

A4T アクティビティには Analytics トラッキングサーバーの指定が必要です。Analytics トラッキングサーバーが正しく設定されていることを確認するには、[Analytics トラッキングサーバーの使用 &#x200B;](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823) を参照してください。

>[!NOTE]
>
>at.js バージョン 0.9.1 （またはそれ以降）を使用している場合は、アクティビティの作成中にトラッキングサーバーを指定する必要はありません。at.js ライブラリは、トラッキングサーバーの値を自動的に [!DNL Target] へ送信します。アクティビティの作成時には、[!UICONTROL Tracking Server] のページの「[!UICONTROL Goals & Settings]」フィールドを空白にできます。

## Analytics セグメントが Target に表示されません。 {#section_DEE87F1557834F448E99381D3D02EEEF}

A4T アクティビティの作成を始める前に、適切な権限があることを確認してください。

* Analytics を Target のレポートソースとして使用できるようにするには、Adobe Analytics の Web サービスアクセスグループに所属している必要があります
* 1 つ以上の Experience Cloud グループのメンバーであり、Analytics と Target へのアクセス権を持っている必要があります。
* 左側のナビゲーションの「マーケティングアプリ」セクションに Analytics と Target が表示されていることを確認してください。

## バウンス率、バウンスおよび出口の指標がレポートで肯定的なものとして表示されます。 {#section_B5C3D56EF0344407AE67ABEB93037F5A}

これらの指標がレポートで肯定的なものとして表示されるのは、既知の問題です。

これらの指標は否定的な意味を持っていますが、Target レポートでは、これらの指標の上昇が肯定的な現象であるかのように表示されます。例えば、バウンス率を低く抑えたい場合であっても、最も高いバウンス率を持つものが勝者として表示されます。このような指標の取り扱いには注意が必要です。ポートに基づいて判断を行う場合には、数値が低下した方が好ましいのか、上昇した方が好ましいのかを確認してください。

## 必要なレポートスイートが表示されません。 {#section_BD8F956E41D6475B98B7BF0C74CC387C}

[!DNL Target Standard/Premium] に表示されるレポートスイートのリストは、[!DNL Target] のレポートソースとして [!DNL Analytics]に設定されている（A4T）レポートスイートのリストです。存在するすべてのレポートスイートが表示されるわけではありません。

複数のレポートソースを使用している場合、レポートスイートは [!DNL Target] で設定したデフォルトのレポートソースにも表示されますす。レポートスイートがデフォルトのレポートソースにない場合、レポートスイートは表示されません。

必要なレポートスイートが見つからない場合は、[Client Care](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) に問い合わせて有効にしてもらってください。

## 期待した量のレポートのデータが表示されません。 {#section_75002584FA63456D8D9086172925DD8D}

（特に訪問者にエクスペリエンスの資格を与えるページについて）実装を確認して、追加のデータ ID が [!DNL Target] と [!DNL Analytics] の呼び出しで一致していることを確認してください。

* **at.js 1.x**：[!DNL Target] 呼び出しでは、追加の ID は `mboxMCSDID` パラメーターに含まれます。[!DNL Analytics] 呼び出しでは、追加の ID は `sdid` パラメーターに含まれます。
* **at.js 2.x**：[!DNL Target] 呼び出しで、HTTP ヘッダーの `experienceCloud.analytics.supplementalDataId` の値として追加の ID が返されます。[!DNL Analytics] 呼び出しでは、追加の ID は `sdid` パラメーターに含まれます。

追加の ID を調べる最も簡単な方法は、 Adobe Experience Platform Debugger を使用することです。

デバッガーをまだインストールしていない場合は、[Adobe Experience Platform Debugger の概要](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/web-sdk/introduction-to-the-experience-platform-debugger.html?lang=ja)を参照してください。

![デバッガー](/help/main/c-integrating-target-with-mac/a4t/assets/debugger.png)

[!DNL Target] 呼び出しに追加のデータ ID がない場合は、[!DNL VisitorAPI.js] ファイルが [!DNL at.js] より先に読み込まれていることを確認してください。[!DNL Analytics] 呼び出しに追加のデータ ID がない場合は、[!DNL Target] 呼び出しが [!DNL Analytics] 呼び出しより先に実行されていることを確認してください。

詳細については、「[Analytics for Target の実装](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md#concept_CE78750AC2A4487D8ACD9369B3EAC85A)」を参照してください。または、[カスタマーケア](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)までお問い合わせください。
