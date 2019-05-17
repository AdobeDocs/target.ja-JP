---
description: Analytics を Target のレポートソースとして使用すると（A4T）、Target アクティビティに関する Analytics レポートを利用できるようになります。
keywords: analytics for target;A4T;レポートソースとしての analytics
seo-description: Analytics を Target のレポートソースとして使用すると（A4T）、Target アクティビティに関する Analytics レポートを利用できるようになります。
seo-title: A4T レポート
solution: 'Target '
subtopic: 多変量分析テスト
title: A4T レポート
topic: Standard
uuid: bd3a7fa4-ba45-4ea3-81b6-fc2584831ce4
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# A4T レポート{#a-t-reporting}

Analytics を Target のレポートソースとして使用すると（A4T）、Target アクティビティに関する Analytics レポートを利用できるようになります。

Analytics および Target Standard/Premium の両方でアクティビティのレポートを表示できます。

Analytics for Target を使用したレポート作成のベストプラクティスについては、[こちらの Adobe Spark ページ](https://spark.adobe.com/page/Lo3Spm4oBOvwF/)を参照してください。

## 概要 {#section_035A62D65608423285D8A5A54731E2C5}

Analytics および Target の両方のレポートでは、サイトへの訪問者ではなく、参加者（テストに参加したユーザー）が測定されます。

訪問者がページ上のアクティビティコンテンツを見ると、そのたびに Target が直接 Analytics に対して、訪問者がどのアクティビティやエクスペリエンスを見たかの情報を含むサーバー間コールを送ります。また、Target はコンバージョンがおこなわれるたびに Analytics を呼び出します。Analytics はコンバージョンを「アクティビティのコンバージョン」という Analytics の新しいイベントとして追加し、Analytics が収集する他のデータとともに追跡します。

選択の操作を使用して、*参加者*で並べ替えをおこなうと、選択した期間中に参加者を獲得したエクスペリエンスのみがレポートに表示されます。

>[!NOTE]
>
>Target が生成するレポートには、4 分の遅延があります。A4T が生成するアクティビティについては、Target と Analytics の両方のレポートで、アクティビティが最初に保存されてから、エクスペリエンスによってレポートデータを分類できるようになるまでに、最大で 24 時間かかる場合があります。最初の 24 時間に収集されたデータも正確であり、適切なエクスペリエンスに割り当てられます。

## Analytics のレポート {#section_F6884872DC864AE7913587FAED4CD11C}

Analytics の左側のメニューで、**[!UICONTROL ターゲット]**／**[!UICONTROL ターゲットアクティビティ]**をクリックします。Target では、アクティビティのレポートに自動的に Analytics のデータ、指標およびセグメントが表示されます。これらのレポートでは、データがサイトから収集された約 1 時間後にデータが表示されます。レポート内のすべての指標、オーディエンスおよび値は、アクティビティを設定したときに選択したレポートスイートから収集されます。

Analytics で Target アクティビティの結果を表示するには、ターゲットアクティビティレポートを使用します。Test&amp;Target（従来の）レポートは、以前の Test&amp;Target プラグインスタイルのページ統合についての情報を提供しますが、Analytics for Target データは含まれません。アクティビティレポートで Target のエクスペリエンスについての情報を表示します。「**[!UICONTROL 指標]**」をクリックして、「**Target[!UICONTROL 」指標タイプを選択します。]**レポートでは、2 つの指標を利用できます。

* **アクティビティのエントリ：** Target レポートの参加者数に対応します。
* **アクティビティのコンバージョン：** Target レポートのカスタムコンバージョン数に対応します。

>[!NOTE]
>
>Target の上昇率と信頼性の詳細は、Analytics でも利用できます。詳しくは、Adobe Analytics 製品ドキュメントの [Target の上昇率と信頼性レポートのタイプ](https://marketing.adobe.com/resources/help/en_US/reference/report_target_lift_confidence.html)を参照してください。

>[!IMPORTANT]
>
>Analytics のターゲットアクティビティレポートに、アクティビティのリストの代わりに「未指定」とリストされる場合は、プロビジョニングされているアカウントの更新が必要です。カスタマーケアに連絡して、この問題を解決してください。

## Target のレポート {#section_C0D1F17F88374B6690BF904D7B83B42E}

レポートソースとして Analytics を使用する場合、Target Standard のレポートでは、Analytics から収集されたデータが表示されます。このレポートは他の Target Standard のレポートと少し異なります。

* オーディエンスリストには Analytics レポートスイートから利用できるオーディエンスが表示されます。
* 指標リストには Analytics を通じて利用できるすべての指標が表示されます。

   カスタム指標や Analytics に組み込まれている計算指標を含む、すべての指標を利用できます。を参照してください。

   このレポートでは、実際には数値の上昇が好ましくない状況であっても、数値の上昇が肯定的な現象として表示されることに注意してください。例えば、バウンス率を低く抑えたい場合であっても、最も高いバウンス率を持つものが勝者として表示されます。このような指標の取り扱いには注意が必要です。ポートに基づいて判断をおこなう場合には、数値が低下した方が好ましいのか、上昇した方が好ましいのかを確認してください。

テスト開始後、またはテストが完了した後でも、Target のレポートに指標やオーディエンスを適用できます。測定する内容を事前に正確に知っておく必要はありません。

アクティビティレポートページから直接完全な Analytics レポートをクリックして表示します。

## Analysis Workspaceのレポート {#reports-in-analysis-workspace}

データをより深く分析したり、表面の下に隠れているインサイトを目立たないようにする [!DNL Adobe Analysis Workspace] ことができます。

詳しくは [、Analytics&amp; Targetを開きます。分析のベストプラクティス」を](https://spark.adobe.com/page/Lo3Spm4oBOvwF/)参照してください。

## アクティビティの作成 {#section_311586E3FF5541E7A91D1A3CE5F9ACE3}

アクティビティを作成する場合は、[!UICONTROL 設定]ページでアクティビティの目標を指定する必要があります。この目標は、レポートのデフォルトの指標となり、指標セレクターで常に先頭に表示されます。通常の Target アクティビティとは異なり、レポート用のセグメントを自由に選択できません。Analytics でのテストでは、Target Standard オーディエンスではなく Adobe Analytics セグメントが使用されます。

## Analytics for Target（A4T）でのオフライン計算の実行{#section_33A97A691F3A45D497DAF57A844388F0}

A4T でオフライン計算を実行することはできますが、[!DNL Analytics] でのデータエクスポートを含む手順が必要になります。

詳しくは、[Analytics for Target（A4T）でのオフライン計算の実行](../../c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B)を参照してください。
