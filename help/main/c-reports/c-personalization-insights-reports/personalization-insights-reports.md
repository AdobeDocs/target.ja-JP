---
keywords: ターゲティング;AP レポート;Automated Personalization レポート;自動ターゲット;自動的なターゲット;自動ターゲットレポート;自動的なターゲットのレポート;パーソナライゼーション;インサイト;自動セグメント;FAQ;よくある質問;重要な属性
description: Automated Personalization（AP）および自動ターゲット（AT）アクティビティの専用レポートの使用方法（自動セグメントと重要な属性）を説明します。
title: Personalization インサイトレポートの使用方法を教えてください。
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Reports
exl-id: 89295d95-f179-4277-ae63-453350e1bba8
TQID: https://experienceleague.adobe.com/qDaIhyfV-m3oHJArqg8TKMAe-k5QwjEUjGzhZrPSTEI
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: adee20bd-51f4-461d-b9db-d215f8756eeb
subfeature_v2: id: fff07a91-d479-45f4-ae95-9762e79b1b7c
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1id: d3cdead0-685a-4489-9250-4bb709942f66id: e0eb8757-182f-49f3-94a4-1587d16f5094id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 948
ht-degree: 28%

---

# [!UICONTROL Personalization Insights] レポート

[!UICONTROL Automated Personalization] （AP）および[!UICONTROL Auto-Target] （AT）アクティビティのユーザーは、次の2つの専用レポートを利用できます：[!UICONTROL Automated Segments]および[!UICONTROL Important Attributes] レポート。

## 注意点

[!UICONTROL Personalization Insights]件のレポートを使用する場合は、次の点を考慮してください。

* AP アクティビティとAT アクティビティは、[[!DNL Target Premium] solution](/help/main/c-intro/intro.md#premium)の一部として利用できます。 これらは、[!DNL Target Premium] ライセンスのない [!DNL Target Standard] には付属していません。

* [!UICONTROL Personalization Insights]件のレポートは、次のように設定されたAPおよびAT アクティビティでのみ使用できます。

   * [!DNL Target] レポート > [!UICONTROL Conversion]

     次に例を示します。

     ![ ターゲットレポート > コンバージョン ](/help/main/c-reports/assets/conversion.png)

   * [!DNL Analytics] レポート > [!DNL Conversion]

     次に例を示します。

     ![分析レポート > コンバージョン ](/help/main/c-reports/assets/analytics-reporting-conversion.png)

   * [!DNL Analytics] レポート > [!UICONTROL Use an Analytics metric] > [!UICONTROL Maximize Visit Conversion Rate]

     次に例を示します。

     ![Analytics指標を使用する/訪問コンバージョン率を最大化](/help/main/c-reports/assets/maximize-visit-conversion-rate.png)

* アクティビティがライブになった後で最適化目標が売上高からコンバージョンに変更されたアクティビティもサポートされません。

* [!UICONTROL Personalization Insights] レポートは、[!UICONTROL Report Metric] ドロップダウンリストから[!UICONTROL Primary Goal]が選択されている場合にのみ使用できます。

* [!UICONTROL Personalization Insights]件のレポートは、[既定の環境](/help/main/administrating-target/hosts.md)でのみサポートされています。

* [!UICONTROL Personalization Insights] レポートは、[!UICONTROL Live] ステータスで、少なくとも15日間アクティブ化され、トラフィックを受信しているアクティビティに対してのみ生成されます。

## Personalization インサイトレポートの概要 {#section_B47CD4A50FEB43D587F9FACD9FFD6D9D}

[!UICONTROL Personalization Insights] レポートの目的は、APおよびAT アクティビティの背後にある[!UICONTROL Target] パーソナライゼーションモデルが訪問者のトラフィックをどのようにパーソナライズするかについての詳細を提供することです。 [ ランダムフォレスト アルゴリズム ](/help/main/c-activities/t-automated-personalization/algo-random-forest.md)は、[!DNL Target]のパーソナライゼーションモデルの基本です。

[!UICONTROL Personalization Insights] レポートの目的は、[!DNL Target]のパーソナライゼーションモデルが、どの訪問者をコンテンツのどの部分に送信するかを決定する方法を理解することであるため、[!UICONTROL Personalization Insights] レポートは、APまたはAT アクティビティが提供するすべてのトラフィックのサブセグメントのみを反映します。 具体的に言うと、これら 2 つのレポートは、パーソナライゼーションモデルを使用したすべてのトラフィックを反映します。 つまり、[!UICONTROL Personalization Insights]件のレポートでは、勝者モデル全体で提供される制御トラフィックまたはトラフィックは考慮されません。

次の2つの[!UICONTROL Personalization Insights] レポートを使用できます。

| レポート | 詳細 |
|--- |--- |
| [!UICONTROL Automated Segments] | AP／AT アクティビティでのオファーやエクスペリエンスへの反応は、訪問者によって異なります。 このレポートでは、[!DNL Target]個のパーソナライゼーションモデルによって定義されたさまざまな自動セグメントが、アクティビティ内のオファー/エクスペリエンスに対してどのように応答したかを示します。 |
| [!UICONTROL Important Attributes] | 異なるアクティビティでは、モデルによるパーソナライゼーションの決定にとって重要な属性も多かれ少なかれ異なります。 このレポートは、モデルに影響を及ぼした上位の属性とそれら属性の相対的重要性を示します。 |

## Personalization Insightsの属性の解釈 {#section_B5C45E723EC941BDA2A7A642EEB30E4D}

AP モデルまたは自動ターゲット モデルで使用される[!UICONTROL Personalization Insights] レポートで表される属性には、次の2種類があります。

* Target:**[!DNL Target]によって自動的に収集された**&#x200B;属性は、基本データセットを使用して、APおよびAT アクティビティでパーソナライゼーションアルゴリズムを構築し、Personalization インサイトに反映されます。 データ型、属性の例、および[!UICONTROL Personalization Insights]の命名規則については、[Target Personalization Algorithms](/help/main/c-activities/t-automated-personalization/ap-data.md)のデータ収集を参照してください。 これらの属性は考慮されますが、個々のアクティビティのモデルでは、最終的なモデルでこれらの属性のすべてを使用しない場合があります。
* **Targetに渡された属性：** 「[Target Personalization アルゴリズムのデータのアップロード ](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md)」を参照してください。

[!DNL Target]は、APおよびAT アクティビティでパーソナライゼーション アルゴリズムを構築するために使用される基本データセットを強化するために、追加のデータを[!DNL Target]に渡すための多くの方法を提供します。

| データタイプ | 説明 | データタイプの命名規則 |
|--- |--- |--- |
| プロファイル属性（プロファイルスクリプト、プロファイル更新 API、ページ内プロファイル属性など） | Target のユーザープロファイルに追加したすべての情報。<br>この情報は、プロファイルスクリプトや、プロファイル更新 API を使用してアップロードされた情報、「profile」という接頭辞が付いた in-mbox プロファイルパラメーターから取得できます。 | `Custom - Profile - [parameter name]` |
| ページパラメーター（「mbox パラメーター」とも呼ばれます） | ページコードを介して直接渡される名前と値のペアで、今後の使用のために訪問者のプロファイルに保管されることはありません。 | `Custom - Mbox Parameter - [parameter name]` |
| 顧客属性 | 顧客属性を利用すると、FTP を介して訪問者のプロファイルデータを Experience Cloud にアップロードできます。 アップロード後は、データを Adobe Analytics と Adobe Target で利用できます。 | `Custom - Customer Attributes - [parameter name]` |
| 共有オーディエンス（Adobe Audience Manager または Adobe Analytics） | Adobe Audience Manager または Adobe Analytics で作成され、Target と共有されているオーディエンス。 | `Custom - Experience Cloud Segment - [segment name]` |
| 共有オーディエンス（Adobe Experience Platform/Real-Time CDP） | Adobe Experience Platform/Real-time CDPで作成され、宛先経由でTargetと共有されるオーディエンス。 | `Custom - Adobe Experience Platform Segment - [segment name]` |
| 共有属性（Adobe Experience Platform/Real-Time CDP） | Adobe Experience Platform/Real-time CDPを通じて作成され、宛先経由でTargetと共有される属性。 この機能は現在Betaにあります。 | `Custom - Adobe Experience Platform Attribute - [attribute name]]` |
| アクティビティ内レポート用オーディエンス／セグメント | 「目標と指標」の設定中に、APまたは自動ターゲットアクティビティで定義されたオーディエンス。 | `Custom - Reporting Segment - [segment name]` |

## よくある質問

[!UICONTROL Automated Personalization] （AP）および[!UICONTROL Auto-Target] [!UICONTROL Insights]件のレポートに関するよくある質問の一覧。

### [!UICONTROL Automated Personalization] （AP）および[!UICONTROL Auto-Target] モデルのデータはどのくらいの期間保持されますか？

[!UICONTROL Automated Personalization] （AP）および[!UICONTROL Auto-Target] モデルは、アクティビティのユーザー行動（ユーザープロファイル、インプレッションイベント、コンバージョンイベント）の過去45日間にトレーニングされます。

[!UICONTROL Automated Personalization] （AP）および[!UICONTROL Auto-Target] モデルは、ユーザーの行動、トレーニング レコード、モデル決定データを90日間保持して、[!UICONTROL Insights] レポートを作成します。 90日が経過すると、トレーニング記録とモデル決定は破棄されます。[!UICONTROL Automated Personalization] （AP）および[!UICONTROL Auto-Target] モデルでは、レポート用に集計されたエクスペリエンス/オファーレベルのインプレッションおよびコンバージョンデータも2年間保持します。 このデータは集計レベルのデータのみであり、個人レベルのプロファイルデータは含まれていません。

## トレーニングビデオ：Personalization インサイトレポートの使用![ チュートリアルバッジ ](/help/main/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/25601/)

詳しくは、[Adobe TargetでのPersonalization インサイトレポートの使用](https://helpx.adobe.com/target/kt/using/personalization-insights-report-feature-video-use.html)を参照してください。

## Adobeのブログ

* パート 1: [AI主導のPersonalizationの魔法を解き放つ](https://theblog.adobe.com/taking-mystery-magic-ai-driven-personalization-part-1/)
* パート 2: [Adobe TargetのPersonalization向けAIのカーテンの裏を覗く](https://theblog.adobe.com/a-peek-behind-the-curtain-of-ai-for-personalization-in-adobe-target/)
* パート 3: [MAGIX — AI ドリブン型Personalizationのブラックボックス問題の解決策](https://theblog.adobe.com/magix-the-solution-to-the-black-box-issue-of-ai-driven-personalization/)
