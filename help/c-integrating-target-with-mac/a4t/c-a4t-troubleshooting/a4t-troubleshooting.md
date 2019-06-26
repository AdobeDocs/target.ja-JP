---
description: このトピックでは、Analytics を Target のレポートソースとして使用する場合（A4T）に発生する一般的な問題について説明します。
keywords: Analytics トラッキングサーバー;A4T;Analytics セグメント;レポートスイート;誤ったデータ;親なし;sdid;VisitorAPI.js;mboxMCSDID;ファントム;未指定
seo-description: このトピックでは、Analytics を Target のレポートソースとして使用する場合（A4T）に発生する一般的な問題について説明します。
seo-title: Analytics と Target の統合（A4T）のトラブルシューティング
solution: 'Target '
subtopic: 多変量分析テスト
title: Analytics と Target の統合（A4T）のトラブルシューティング
topic: Standard
uuid: a5aa3be5-68a2-4f12-8226-f32a76136bbd
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Analytics と Target の統合（A4T）のトラブルシューティング{#troubleshoot-the-analytics-and-target-integration-a-t}

このトピックでは、Analytics を Target のレポートソースとして使用する場合（A4T）に発生する一般的な問題について説明します。

## Analytics にアクティビティのデータが表示されず、その代わり、「未指定」と表示されます。{#section_EB97F0499B0E40E69A21C30DC539BF67}

こうなる理由はいくつか考えられます。

* [!DNL Target] の分類が完全に処理されていない。

   分類の処理には、アクティビティが最初に保存されてから 24 時間もかかることがあります。

* レポートスイートにはデータが全く含まれていないが、[!DNL Target] はヒットの分類を試行した。[!DNL Target] は最初のヒットが発生するまで、データの分類をおこなうことができません。

   レポートスイートで、少なくとも 1 つはヒットがあったことを確認してください。

* [!DNL Target] から [!DNL Analytics] への分類呼び出しが失敗した。

   [カスタマーケア](../../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)までお問い合わせください。

新しいアクティビティが追加され、その分類が完了していないために、レポートに正しくデータが表示された後に「未指定」に戻ることがあります。レポートを分類するには、最初の保存から 24 時間もかかることがあります。

>[!NOTE]
>
>「未指定」と表示されていても、データは失われていません。分類が実行された後、データはアクティビティまたはエクスペリエンスに適切に割り当てられます。

## Analytics データにて、A4T を開始してから訪問または訪問カウントが水増しされています。 {#section_4BE374E573D44FB7918611699B74F58E}

詳しくは、[A4T での水増しされた訪問と訪問者カウントの最小化](../../../c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/minimizing-inflated-visit-and-visitor-counts-a4t.md#concept_A515C2DE126E44B6AD97754C2C6D5235)を参照してください。

## 売上高指標の推定上昇率に正しいデータが表示されません。{#section_35D766E5E4D347C39E15D08AA883FBB0}

上昇率と信頼性の詳細は、Analytics では利用できません。ただし、これらの詳細は Target レポートで利用できます。

## Analytics レポートにアクティビティが表示されません。 {#section_F7001EB4670F4B3497CC7DA60BBDA6D5}

A4T アクティビティには Analytics トラッキングサーバーの指定が必要です。詳しくは、[Analytics トラッキングサーバーの使用](../../../c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823)を参照し、Analytics トラッキングサーバーが正しく設定されていることを確認してください。

>[!NOTE]
>
>Adobe Analytics をアクティビティのレポートソースとして使用する場合、 mbox.js バージョン 61 （またはそれ以降）または at.js バージョン 0.9.1 （またはそれ以降）を使用しているのであれば、アクティビティを作成する際にトラッキングサーバーを指定する必要はありません。mbox.js または at.js ライブラリは、トラッキングサーバーの値を自動的に [!DNL Target] へ送信します。アクティビティの作成時には、[!UICONTROL 目標および設定]ページの「[!UICONTROL トラッキングサーバー]」フィールドを空白にできます。

## Analytics セグメントが Target に表示されません。 {#section_DEE87F1557834F448E99381D3D02EEEF}

A4T アクティビティの作成を始める前に、適切な権限があることを確認してください。

* Analytics を Target のレポートソースとして使用できるようにするには、ユーザーが Adobe Analytics の Web サービスアクセスグループに所属している必要があります。
* ユーザーは、1 つ以上の Experience Cloud グループのメンバーであり、Analytics と Target へのアクセス権を持っている必要があります。
* 左側のナビゲーションの「マーケティングアプリ」セクションに Analytics と Target が表示されていることを確認してください。

## バウンス率、バウンスおよび出口の指標がレポートで肯定的なものとして表示されます。 {#section_B5C3D56EF0344407AE67ABEB93037F5A}

これは既知の問題です。

これらの指標は否定的な意味を持っていますが、Target レポートでは、これらの指標の上昇が肯定的な現象であるかのように表示されます。例えば、バウンス率を低く抑えたい場合であっても、最も高いバウンス率を持つものが勝者として表示されます。このような指標の取り扱いには注意が必要です。ポートに基づいて判断をおこなう場合には、数値が低下した方が好ましいのか、上昇した方が好ましいのかを確認してください。

## 必要なレポートスイートが表示されません。 {#section_BD8F956E41D6475B98B7BF0C74CC387C}

Target Standard/Premium に表示されるレポートスイートのリストは、Target のレポートソースとして Analytics に設定されているレポートスイートのリストです。つまり、存在するすべてのレポートスイートが表示されるわけではありません。必要なレポートスイートが見つからない場合は、ClientCare に問い合わせて有効にしてください。

## 期待した量のレポートのデータが表示されません。{#section_75002584FA63456D8D9086172925DD8D}

（特に訪問者にエクスペリエンスの資格を与えるページについて）実装を確認して、追加のデータ ID が [!DNL Target] と [!DNL Analytics] の呼び出しで一致していることを確認してください。[!DNL Target] 呼び出しでは、追加の ID は `mboxMCSDID` パラメーターに含まれます。[!DNL Analytics] 呼び出しでは、追加の ID は `sdid` パラメーターに含まれます。

[!DNL Target] 呼び出しに追加のデータ ID がない場合は、[!DNL VisitorAPI.js] ファイルが [!DNL at.js] や [!DNL mbox.js] より先に読み込まれていることを確認してください。[!DNL Analytics] 呼び出しに追加のデータ ID がない場合は、[!DNL Target] 呼び出しが [!DNL Analytics] 呼び出しより先に実行されていることを確認してください。

詳細については、「[Analytics for Target の実装](../../../c-integrating-target-with-mac/a4t/a4timplementation.md#concept_CE78750AC2A4487D8ACD9369B3EAC85A)」を参照してください。または、[カスタマーケア](../../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)までお問い合わせください。