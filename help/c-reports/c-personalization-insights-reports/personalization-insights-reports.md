---
keywords: Targeting;AP reports;automated personalization reports;auto-target;auto target;auto target report;auto-target report;personalization;insights;automated segments;faq;frequently asked questions;important attributes
description: Automated Personalization（AP）および自動ターゲット（AT）アクティビティのユーザーは、自動セグメントレポートと重要な属性レポートの 2 つの特殊なレポートを使用できます。
title: パーソナライゼーションインサイトレポート
feature: null
uuid: 2507a7a6-d229-412a-a992-5777b45c80e7
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '716'
ht-degree: 68%

---


# ![PREMIUM](/help/assets/premium.png) パーソナライゼーションインサイトレポート{#personalization-insights-reports}

[!UICONTROL Automated Personalization]（AP）および自動ターゲット（AT）アクティビティのユーザーは、[!UICONTROL 自動セグメント]レポートと重要な属性レポートの 2 つの特殊なレポートを使用できます。

>[!NOTE]
>
>個人用設定インサイトレポートを使用する場合は、以下の点を考慮してください。
>
>* AP および AT アクティビティは、[!DNL Target Premium] ソリューションの一部です。これらは、[!DNL Target Premium] ライセンスのない [!DNL Target Standard] には付属していません。
   >
   >
* [!UICONTROL パーソナライゼーションインサイトレポートは、コンバージョン最適化目標を使用する AP および AT アクティビティについてのみ使用できます。]アクティビティがライブになった後で最適化目標が売上高からコンバージョンに変更されたアクティビティもサポートされません。
   >
   >
* [!UICONTROL [個人設定インサイト] ]レポートは、[ [!UICONTROL レポート指標]ドロップダウンリストから[] プライマリ目標]が選択されている場合にのみ使用できます。
   >
   >
* パーソナライゼーションインサイトレポートは、[デフォルト環境](../../administrating-target/hosts.md)でのみサポートされています。
   >
   >
* [!UICONTROL 個人用設定インサイト] レポートは、  ライブステータスで、アクティブ化され、15日以上トラフィックを受け取っているアクティビティに対してのみ生成されます。


## パーソナライゼーションインサイトレポートの概要 {#section_B47CD4A50FEB43D587F9FACD9FFD6D9D}

[!UICONTROL パーソナライゼーションインサイト]レポートの目標は、AP および AT アクティビティの背後にある Target パーソナライゼーションモデルで訪問者トラフィックがどのようにパーソナライズされるかを詳細に示すことです。The [Random Forest algorithm](/help/c-activities/t-automated-personalization/algo-random-forest.md) is the basis for the [!DNL Target] personalization models.

Because the goal of the [!UICONTROL Personalization Insights] reports is to understand how the [!DNL Target] personalization models decided to send which visitor to what piece(s) of content, the [!UICONTROL Personalization Insights] reports reflect only a sub-segment of all the traffic served by your AP or AT activity. 具体的に言うと、これら 2 つのレポートは、パーソナライゼーションモデルを使用したすべてのトラフィックを反映します。つまり、[!UICONTROL パーソナライゼーションインサイト]レポートでは、制御トラフィックや、勝者モデル全体で提供されるトラフィックは考慮されません。

次の2つの [!UICONTROL パーソナライゼーションインサイト] レポートを使用できます。

| レポート | 詳細 |
|--- |--- |
| [!UICONTROL 自動セグメント] | AP／AT アクティビティでのオファーやエクスペリエンスへの反応は、訪問者によって異なります。This report shows how different automated segments defined by the [!DNL Target] personalization models responded to the offers/experiences in the activity. |
| [!UICONTROL 重要な属性] | 異なるアクティビティでは、モデルによるパーソナライゼーションの決定にとって重要な属性も多かれ少なかれ異なります。このレポートは、モデルに影響を及ぼした上位の属性とそれら属性の相対的重要性を示します。 |

## パーソナライゼーションインサイトでの属性の解釈 {#section_B5C45E723EC941BDA2A7A642EEB30E4D}

[!UICONTROL パーソナライゼーションインサイト]レポートで表される属性のうち、AP モデルまたは自動ターゲットモデルで使用されるものは、次の 2 種類です。

* **で自動的に収集される属性：**[!DNL Target]Target では基本データセットを使用して、パーソナライゼーションインサイトに反映される AP アクティビティおよび AT アクティビティのパーソナライゼーションアルゴリズムを構築します。データ型、属性の例、[!UICONTROL パーソナライゼーションインサイト]の命名規則について詳しくは、[Target のパーソナライゼーションアルゴリズムのデータ収集](../../c-activities/t-automated-personalization/ap-data.md#reference_255BD3DE7AD04DC9B766E0BC78961058)を参照してください。これらの属性は考慮はされますが、個々のアクティビティの最終モデルでは、これらの属性がすべて使用されるとは限らないことに注意してください。
* **Target に渡される属性：**[Target のパーソナライゼーションアルゴリズムのデータのアップロード](../../c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md#concept_85EA505B37E54514A1C8AB91553FEED6)を参照してください。

[!DNL Target] には、APおよびATアクティビティでパーソナライゼーションアルゴリズムを構築する際に使用するベースデータセット [!DNL Target] を拡張するために、追加のデータをに渡す様々な方法が用意されています。

| データタイプ | 説明 | データタイプの命名規則 |
|--- |--- |--- |
| プロファイル属性（プロファイルスクリプト、プロファイル更新 API、ページ内プロファイル属性など） | Target のユーザープロファイルに追加したすべての情報。<br>この情報は、プロファイルスクリプトや、プロファイル更新 API を使用してアップロードされた情報、「profile」というプレフィックスが付いた in-mbox プロファイルパラメーターから取得できます。 | `Custom - Profile - [parameter name]` |
| ページパラメーター（「mbox パラメーター」） | ページコードを介して直接渡される名前と値のペアで、今後の使用のために訪問者のプロファイルに保管されることはありません。 | `Custom - Mbox Parameter - [parameter name]` |
| 顧客属性 | 顧客属性を利用すると、FTP を介して訪問者のプロファイルデータを Experience Cloud にアップロードできます。アップロード後は、データを Adobe Analytics と Adobe Target で利用できます。 | `Custom - Customer Attributes - [parameter name]` |
| 共有オーディエンス（Adobe Audience Manager または Adobe Analytics） | Adobe Audience Manager または Adobe Analytics で作成され、Target と共有されているオーディエンス。 | `Custom - Experience Cloud Segment - [segment name]` |
| アクティビティ内レポート用オーディエンス／セグメント | 「目標と指標」の設定中に AP または自動ターゲットアクティビティで定義されたオーディエンス。 | `Custom - Reporting Segment - [segment name]` |

## トレーニングビデオ：パーソナライゼーションインサイトレポートの使用 ![チュートリアルバッジ](/help/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/25601/)

詳しくは、「Adobe Targetでのパーソナライゼーションインサイトレポートの [使用](https://helpx.adobe.com/target/kt/using/personalization-insights-report-feature-video-use.html)」を参照してください。

## Adobeブログ

* パート1: [AI主導のパーソナライゼーションの魔法による謎の解き明かし](https://theblog.adobe.com/taking-mystery-magic-ai-driven-personalization-part-1/)
* パート2: [Adobe Targetでパーソナライゼーションを実現するAIの幕の後ろを覗く](https://theblog.adobe.com/a-peek-behind-the-curtain-of-ai-for-personalization-in-adobe-target/)
* パート3: [MAGIX — AIに基づくパーソナライゼーションのブラックボックス号の解決策](https://theblog.adobe.com/magix-the-solution-to-the-black-box-issue-of-ai-driven-personalization/)
