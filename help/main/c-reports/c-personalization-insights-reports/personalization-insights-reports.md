---
keywords: ターゲット設定;AP レポート;Automated Personalization レポート;自動ターゲット;自動的なターゲット;自動ターゲットレポート;自動的なターゲットのレポート;パーソナライゼーション;インサイト;自動セグメント;FAQ;よくある質問;重要な属性
description: Automated Personalization(AP) および自動ターゲット (AT) アクティビティ用の特殊なレポートの使用方法 — 自動セグメントと重要な属性。
title: パーソナライゼーションインサイトレポートの使用方法
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Reports
exl-id: 89295d95-f179-4277-ae63-453350e1bba8
source-git-commit: 6c8f042acb257fc908349c679bf745e477f94af4
workflow-type: tm+mt
source-wordcount: '877'
ht-degree: 29%

---

# [!UICONTROL Personalization Insights] レポート

のユーザーは、次の 2 つの特殊なレポートを使用できます。 [!UICONTROL Automated Personalization] (AP) および [!UICONTROL Auto-Target] (AT) アクティビティ： [!UICONTROL Automated Segments] および [!UICONTROL Important Attributes] レポート。

## 注意点

を使用する際は、次の点を考慮してください。 [!UICONTROL Personalization Insights] レポート：

* AP および AT アクティビティは、 [[!DNL Target Premium] ソリューション](/help/main/c-intro/intro.md#premium). これらは、[!DNL Target Premium] ライセンスのない [!DNL Target Standard] には付属していません。

* [!UICONTROL Personalization Insights] レポートは、次のように設定された AP および AT アクティビティでのみ使用できます。

   * [!DNL Target] レポート > [!UICONTROL Conversion]

     次に例を示します。

     ![Target レポート/コンバージョン](/help/main/c-reports/assets/conversion.png)

   * [!DNL Analytics] レポート > [!DNL Conversion]

     次に例を示します。

     ![分析レポート/コンバージョン](/help/main/c-reports/assets/analytics-reporting-conversion.png)

   * [!DNL Analytics] レポート > [!UICONTROL Use an Analytics metric] > [!UICONTROL Maximize Visit Conversion Rate]

     次に例を示します。

     ![Analytics 指標を使用/訪問コンバージョン率を最大化](/help/main/c-reports/assets/maximize-visit-conversion-rate.png)

* アクティビティがライブになった後で最適化目標が売上高からコンバージョンに変更されたアクティビティもサポートされません。

* [!UICONTROL Personalization Insights] レポートは、 [!UICONTROL Primary Goal] が [!UICONTROL Report Metric] 」ドロップダウンリストから選択できます。

* [!UICONTROL Personalization Insights] レポートは、 [デフォルト環境](/help/main/administrating-target/hosts.md) のみ。

* [!UICONTROL Personalization Insights] レポートは、 [!UICONTROL Live] のステータスと、少なくとも 15 日間アクティブ化され、トラフィックを受け取っていること。

## パーソナライゼーションインサイトレポートの概要 {#section_B47CD4A50FEB43D587F9FACD9FFD6D9D}

の目標 [!UICONTROL Personalization Insights] レポートは、 [!UICONTROL Target] AP および AT アクティビティの背後にあるパーソナライゼーションモデルは、訪問者トラフィックをパーソナライズします。 The [ランダムフォレストアルゴリズム](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) は、 [!DNL Target] パーソナライゼーションモデル。

これは、 [!UICONTROL Personalization Insights] レポートは、 [!DNL Target] パーソナライゼーションモデルは、どの訪問者をどのコンテンツに送信するかを決定し、 [!UICONTROL Personalization Insights] レポートは、AP または AT アクティビティによって提供されるすべてのトラフィックのサブセグメントのみを反映します。 具体的に言うと、これら 2 つのレポートは、パーソナライゼーションモデルを使用したすべてのトラフィックを反映します。言い換えれば、 [!UICONTROL Personalization Insights] レポートでは、制御トラフィックや、勝者モデル全体で提供されるトラフィックは考慮されません。

2 [!UICONTROL Personalization Insights] 次のレポートを使用できます。

| レポート | 詳細 |
|--- |--- |
| [!UICONTROL Automated Segments] | AP／AT アクティビティでのオファーやエクスペリエンスへの反応は、訪問者によって異なります。このレポートは、 [!DNL Target] パーソナライゼーションモデルがアクティビティのオファー/エクスペリエンスに応答しました。 |
| [!UICONTROL Important Attributes] | 異なるアクティビティでは、モデルによるパーソナライゼーションの決定にとって重要な属性も多かれ少なかれ異なります。このレポートは、モデルに影響を及ぼした上位の属性とそれら属性の相対的重要性を示します。 |

## パーソナライゼーションインサイトでの属性の解釈 {#section_B5C45E723EC941BDA2A7A642EEB30E4D}

には 2 種類の属性が表示されます。 [!UICONTROL Personalization Insights] AP または自動ターゲットモデルで使用されるレポート：

* **Target が自動的に収集する属性：** [!DNL Target] は、基本データセットを使用して、パーソナライゼーションインサイトに反映される AP および AT アクティビティのパーソナライゼーションアルゴリズムを構築します。 詳しくは、 [Target のパーソナライゼーションアルゴリズムのデータ収集](/help/main/c-activities/t-automated-personalization/ap-data.md) データタイプ、属性の例およびそれらの [!UICONTROL Personalization Insights] 命名規則を使用します。 これらの属性は考慮されますが、個々のアクティビティのモデルでは、最終モデルでこれらの属性のすべてが使用されるわけではないことに注意してください。
* **Target に渡される属性：** 詳しくは、 [Target のパーソナライゼーションアルゴリズムのデータのアップロード](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md).

[!DNL Target] には、追加のデータをに渡す方法が多数用意されています。 [!DNL Target] AP および AT アクティビティのパーソナライゼーションアルゴリズムの構築に使用するベースデータセットをエンリッチメントするには：

| データタイプ | 説明 | データタイプの命名規則 |
|--- |--- |--- |
| プロファイル属性（プロファイルスクリプト、プロファイル更新 API、ページ内プロファイル属性など） | Target のユーザープロファイルに追加したすべての情報。<br>この情報は、プロファイルスクリプトや、プロファイル更新 API を使用してアップロードされた情報、「profile」というプレフィックスが付いた in-mbox プロファイルパラメーターから取得できます。 | `Custom - Profile - [parameter name]` |
| ページパラメーター（mbox パラメーター） | ページコードを介して直接渡される名前と値のペアで、今後の使用のために訪問者のプロファイルに保管されることはありません。 | `Custom - Mbox Parameter - [parameter name]` |
| 顧客属性 | 顧客属性を利用すると、FTP を介して訪問者のプロファイルデータを Experience Cloud にアップロードできます。アップロード後は、データを Adobe Analytics と Adobe Target で利用できます。 | `Custom - Customer Attributes - [parameter name]` |
| 共有オーディエンス（Adobe Audience Manager または Adobe Analytics） | Adobe Audience Manager または Adobe Analytics で作成され、Target と共有されているオーディエンス。 | `Custom - Experience Cloud Segment - [segment name]` |
| 共有オーディエンス (Adobe Experience Platform/リアルタイム CDP) | Adobe Experience Platform/リアルタイム CDP を通じて作成され、宛先を介して Target と共有されるオーディエンス。 | `Custom - Adobe Experience Platform Segment - [segment name]` |
| 共有属性 (Adobe Experience Platform/リアルタイム CDP) | Adobe Experience Platform/Real-time CDP を通じて作成され、宛先を介して Target と共有される属性。 この機能は現在ベータ版です。 | `Custom - Adobe Experience Platform Attribute - [attribute name]]` |
| アクティビティ内レポート用オーディエンス／セグメント | 「目標と指標」の設定中に AP または自動ターゲットアクティビティで定義されたオーディエンス。 | `Custom - Reporting Segment - [segment name]` |

## よくある質問

に関するよくある質問のリスト [!UICONTROL Automated Personalization] (AP) および [!UICONTROL Auto-Target] [!UICONTROL Insights] レポート。

### のデータの長さ [!UICONTROL Automated Personalization] (AP) および [!UICONTROL Auto-Target] モデルは保持されます。

[!UICONTROL Automated Personalization] (AP) および [!UICONTROL Auto-Target] モデルは、アクティビティの過去 45 日間のユーザー行動（ユーザープロファイル、インプレッションイベントおよびコンバージョンイベント）に基づいてトレーニングされます。

[!UICONTROL Automated Personalization] (AP) および [!UICONTROL Auto-Target] モデルは、ユーザーの行動、トレーニングレコード、モデルの決定データを 90 日間保持し、 [!UICONTROL Insights] レポート。 90 日が経過すると、トレーニングレコードとモデルの決定は破棄されます。 [!UICONTROL Automated Personalization] (AP) および [!UICONTROL Auto-Target] モデルでは、2 年間、レポート目的で、集計されたエクスペリエンス/オファーレベルのインプレッションおよびコンバージョンのデータも保持されます。 このデータは集計レベルのデータのみで、個人レベルのプロファイルデータは含まれません。

## トレーニングビデオ：パーソナライゼーションインサイトレポートの使用 ![チュートリアルバッジ](/help/main/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/25601/)

詳しくは、 [Adobe Targetでのパーソナライゼーションインサイトレポートの使用](https://helpx.adobe.com/target/kt/using/personalization-insights-report-feature-video-use.html).

## Adobeブログ

* パート 1: [AI 駆動型パーソナライゼーションのマジックから謎を取り除く](https://theblog.adobe.com/taking-mystery-magic-ai-driven-personalization-part-1/)
* パート 2: [Adobe Targetでのパーソナライゼーションのための AI のカーテンの後ろのプレビュー](https://theblog.adobe.com/a-peek-behind-the-curtain-of-ai-for-personalization-in-adobe-target/)
* パート 3: [MAGIX — AI 駆動型パーソナライゼーションのブラックボックス問題の解決策](https://theblog.adobe.com/magix-the-solution-to-the-black-box-issue-of-ai-driven-personalization/)
