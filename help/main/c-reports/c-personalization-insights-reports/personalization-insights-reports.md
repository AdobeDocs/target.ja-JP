---
keywords: ターゲット設定;AP レポート;Automated Personalization レポート;自動ターゲット;自動的なターゲット;自動ターゲットレポート;自動的なターゲットのレポート;パーソナライゼーション;インサイト;自動セグメント;FAQ;よくある質問;重要な属性
description: Automated Personalization（AP）および自動ターゲット（AT）アクティビティ用の専用レポートである自動セグメントと重要な属性の使用方法を説明します。
title: Personalization Insights レポートの使用方法
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Reports
exl-id: 89295d95-f179-4277-ae63-453350e1bba8
source-git-commit: 6c8f042acb257fc908349c679bf745e477f94af4
workflow-type: tm+mt
source-wordcount: '877'
ht-degree: 29%

---

# [!UICONTROL Personalization Insights] レポート

[!UICONTROL Automated Personalization] （AP）および [!UICONTROL Auto-Target] （AT）アクティビティのユーザーは、[!UICONTROL Automated Segments] レポートと [!UICONTROL Important Attributes] レポートの 2 つの特殊なレポートを使用できます。

## 注意点

[!UICONTROL Personalization Insights] レポートを使用する場合は、次の点を考慮してください。

* AP アクティビティと AT アクティビティは、[[!DNL Target Premium]  ソリューション ](/help/main/c-intro/intro.md#premium) の一部です。 これらは、[!DNL Target Premium] ライセンスのない [!DNL Target Standard] には付属していません。

* [!UICONTROL Personalization Insights] レポートは、次のように設定された AP アクティビティおよび AT アクティビティに対してのみ使用できます。

   * [!DNL Target] レポート/[!UICONTROL Conversion]

     次に例を示します。

     ![ ターゲットレポート/コンバージョン ](/help/main/c-reports/assets/conversion.png)

   * [!DNL Analytics] レポート/[!DNL Conversion]

     次に例を示します。

     ![ 分析レポート/コンバージョン ](/help/main/c-reports/assets/analytics-reporting-conversion.png)

   * [!DNL Analytics] レポート/[!UICONTROL Use an Analytics metric]/[!UICONTROL Maximize Visit Conversion Rate]

     次に例を示します。

     ![Analytics 指標を使用/訪問のコンバージョン率を最大化 ](/help/main/c-reports/assets/maximize-visit-conversion-rate.png)

* アクティビティがライブになった後で最適化目標が売上高からコンバージョンに変更されたアクティビティもサポートされません。

* [!UICONTROL Personalization Insights] のレポートは、「[!UICONTROL Report Metric]」ドロップダウンリストから [!UICONTROL Primary Goal] が選択されている場合にのみ使用できます。

* [!UICONTROL Personalization Insights] レポートは、[ デフォルト環境 ](/help/main/administrating-target/hosts.md) でのみサポートされます。

* [!UICONTROL Personalization Insights] レポートは、[!UICONTROL Live] ステータスのアクティビティのうち、アクティブ化され、トラフィックの受信が 15 日以上行われたものについてのみ生成されます。

## Personalization Insights レポートの概要 {#section_B47CD4A50FEB43D587F9FACD9FFD6D9D}

[!UICONTROL Personalization Insights] レポートの目的は、AP と AT アクティビティの背後にある [!UICONTROL Target] パーソナライゼーションモデルが訪問者トラフィックをどのようにパーソナライズするかについての詳細を提供することです。 [ ランダムフォレストアルゴリズム ](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) は、[!DNL Target] パーソナライゼーションモデルの基礎です。

[!UICONTROL Personalization Insights] レポートの目的は、[!DNL Target] のパーソナライゼーションモデルが、どの訪問者をコンテンツに送信するかを決定した方法を理解することです。そのため、[!UICONTROL Personalization Insights] レポートには、AP または AT アクティビティから提供されるすべてのトラフィックのサブセグメントのみが反映されます。 具体的に言うと、これら 2 つのレポートは、パーソナライゼーションモデルを使用したすべてのトラフィックを反映します。つまり、[!UICONTROL Personalization Insights] レポートでは、制御トラフィックや、全体的な勝者モデルによって提供されるトラフィックは考慮されません。

次の 2 つの [!UICONTROL Personalization Insights] レポートを使用できます。

| レポート | 詳細 |
|--- |--- |
| [!UICONTROL Automated Segments] | AP／AT アクティビティでのオファーやエクスペリエンスへの反応は、訪問者によって異なります。このレポートでは、[!DNL Target] パーソナライゼーションモデルで定義された様々な自動セグメントがアクティビティのオファー/エクスペリエンスにどのように応答したかを示します。 |
| [!UICONTROL Important Attributes] | 異なるアクティビティでは、モデルによるパーソナライゼーションの決定にとって重要な属性も多かれ少なかれ異なります。このレポートは、モデルに影響を及ぼした上位の属性とそれら属性の相対的重要性を示します。 |

## Personalization Insights での属性の解釈 {#section_B5C45E723EC941BDA2A7A642EEB30E4D}

AP または自動ターゲット モデルで使用される [!UICONTROL Personalization Insights] レポートには、次の 2 種類の属性が表示されます。

* **Target によって自動的に収集される属性：** [!DNL Target] は、ベースデータセットを使用して、Personalization Insights に反映される AP アクティビティと AT アクティビティでパーソナライゼーションアルゴリズムを構築します。 属性などのデータ型とその [!UICONTROL Personalization Insights] しい命名規則については、[Target のPersonalization アルゴリズムのデータ収集 ](/help/main/c-activities/t-automated-personalization/ap-data.md) を参照してください。 これらの属性は考慮されますが、個々のアクティビティのモデルは、最終的なモデルでこれらの属性のすべてを使用しない場合があります。
* **Target に渡される属性：** Target Personalization アルゴリズムのデータのアップロード [ を参照してください ](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md)。

[!DNL Target] では、追加のデータを [!DNL Target] に渡して、AP および AT アクティビティでパーソナライゼーションアルゴリズムを構築するために使用されるベースデータセットを強化する多くの方法を提供しています。

| データタイプ | 説明 | データタイプの命名規則 |
|--- |--- |--- |
| プロファイル属性（プロファイルスクリプト、プロファイル更新 API、ページ内プロファイル属性など） | Target のユーザープロファイルに追加したすべての情報。<br>この情報は、プロファイルスクリプトや、プロファイル更新 API を使用してアップロードされた情報、「profile」というプレフィックスが付いた in-mbox プロファイルパラメーターから取得できます。 | `Custom - Profile - [parameter name]` |
| ページパラメーター（「mbox パラメーター」とも呼ばれます） | ページコードを介して直接渡される名前と値のペアで、今後の使用のために訪問者のプロファイルに保管されることはありません。 | `Custom - Mbox Parameter - [parameter name]` |
| 顧客属性 | 顧客属性を利用すると、FTP を介して訪問者のプロファイルデータを Experience Cloud にアップロードできます。アップロード後は、データを Adobe Analytics と Adobe Target で利用できます。 | `Custom - Customer Attributes - [parameter name]` |
| 共有オーディエンス（Adobe Audience Manager または Adobe Analytics） | Adobe Audience Manager または Adobe Analytics で作成され、Target と共有されているオーディエンス。 | `Custom - Experience Cloud Segment - [segment name]` |
| 共有オーディエンス（Adobe Experience Platform/リアルタイム CDP） | Adobe Experience Platform/Real-time CDP を通じて作成され、宛先を介して Target と共有されるオーディエンス。 | `Custom - Adobe Experience Platform Segment - [segment name]` |
| 共有属性（Adobe Experience Platform/Real-Time CDP） | Adobe Experience Platform/Real-time CDP を通じて作成され、宛先を介して Target と共有される属性。 この機能は、現在Betaにあります。 | `Custom - Adobe Experience Platform Attribute - [attribute name]]` |
| アクティビティ内レポート用オーディエンス／セグメント | 「目標と指標」での設定時に、AP アクティビティまたは自動ターゲットアクティビティで定義されたオーディエンス。 | `Custom - Reporting Segment - [segment name]` |

## よくある質問

[!UICONTROL Automated Personalization] （AP）と [!UICONTROL Auto-Target] [!UICONTROL Insights] レポートに関するよくある質問のリストです。

### [!UICONTROL Automated Personalization] （AP）および [!UICONTROL Auto-Target] モデルのデータは、どのくらいの期間保持されますか？

[!UICONTROL Automated Personalization] （AP）および [!UICONTROL Auto-Target] モデルは、アクティビティのユーザー行動（ユーザープロファイル、インプレッションイベント、コンバージョンイベント）の過去 45 日間にトレーニングされます。

[!UICONTROL Automated Personalization] （AP）および [!UICONTROL Auto-Target] モデルでは、ユーザーの行動、トレーニングレコード、モデル決定データが 90 日間保持され、[!UICONTROL Insights] しいレポートが作成されます。 90 日が経過すると、トレーニングレコードとモデル決定は破棄されます。 [!UICONTROL Automated Personalization] （AP）および [!UICONTROL Auto-Target] モデルでは、集計されたエクスペリエンス/オファーレベルのインプレッションとコンバージョンデータも、レポート目的で 2 年間保持します。 このデータは集計レベルのデータのみであり、個々のレベルのプロファイルデータは含まれていません。

## トレーニングビデオ：Personalization Insights レポートの使用 ![ チュートリアルバッジ ](/help/main/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/25601/)

詳しくは、[Adobe TargetでのPersonalization Insights レポートの使用 ](https://helpx.adobe.com/target/kt/using/personalization-insights-report-feature-video-use.html) を参照してください。

## Adobe ブログ

* 第 1 部 [AI 駆動Personalizationの魔法から謎を解き放つ ](https://theblog.adobe.com/taking-mystery-magic-ai-driven-personalization-part-1/)
* 第 2 部 [Adobe TargetのPersonalizationで AI の幕裏を覗く ](https://theblog.adobe.com/a-peek-behind-the-curtain-of-ai-for-personalization-in-adobe-target/)
* 第 3 回 [MAGIX — AI 駆動型Personalizationのブラックボックス問題に対するソリューション ](https://theblog.adobe.com/magix-the-solution-to-the-black-box-issue-of-ai-driven-personalization/)
