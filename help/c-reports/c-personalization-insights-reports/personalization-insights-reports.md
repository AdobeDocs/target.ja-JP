---
description: Automated Personalization（AP）および自動ターゲット（AT）アクティビティのユーザーは、自動セグメントレポートと重要な属性レポートの 2 つの特殊なレポートを使用できます。
keywords: ターゲット設定;AP レポート;Automated Personalization レポート;自動ターゲット;自動的なターゲット;自動ターゲットレポート;自動的なターゲットのレポート;パーソナライゼーション;インサイト;自動セグメント;FAQ;よくある質問;重要な属性
seo-description: Automated Personalization（AP）および自動ターゲット（AT）アクティビティのユーザーは、自動セグメントレポートと重要な属性レポートの 2 つの特殊なレポートを使用できます。
seo-title: パーソナライゼーションインサイトレポート
solution: 'Target '
title: パーソナライゼーションインサイトレポート
title-outputclass: premium
uuid: 2507a7a6-d229-412a-a992-5777b45c80e7
badge: premium
translation-type: tm+mt
source-git-commit: c0d0ae6bcd401777169e74b93a4fb18f1a9b24dc

---


# ![PREMIUM](/help/assets/premium.png) パーソナライゼーションインサイトレポート{#personalization-insights-reports}

Automated Personalization（AP）および自動ターゲット（AT）アクティビティのユーザーは、自動セグメントレポートと重要な属性レポートの 2 つの特殊なレポートを使用できます。

>[!NOTE]
>
>AP および AT アクティビティは、[!DNL Target Premium] ソリューションの一部です。これらは、[!DNL Target Premium] ライセンスのない [!DNL Target Standard] には付属していません。
>
>パーソナライゼーションインサイトレポートは、コンバージョン最適化目標を使用する AP および AT アクティビティについてのみ使用できます。アクティビティがライブになった後で最適化目標が売上高からコンバージョンに変更されたアクティビティもサポートされません。
>
>パーソナライゼーションインサイトレポートは、[デフォルト環境](../../administrating-target/hosts.md)でのみサポートされています。
>
>パーソナライゼーションインサイトレポートは、ライブステータスにあるアクティビティに対してのみ生成され、少なくとも15日間アクティブ化および受信されたアクティビティに対してのみ生成されます。

## パーソナライゼーションインサイトレポートの概要 {#section_B47CD4A50FEB43D587F9FACD9FFD6D9D}

[!UICONTROL パーソナライゼーションインサイト]レポートの目標は、AP および AT アクティビティの背後にある Target パーソナライゼーションモデルで訪問者トラフィックがどのようにパーソナライズされるかを詳細に示すことです。[ランダムフォレストアルゴリズム](/help/c-activities/t-automated-personalization/algo-random-forest.md)は、Target のパーソナライゼーションモデルの基礎となるものです。

パーソナライゼーションインサイトレポートの目標は、どの訪問者にどのようなコンテンツを表示するかが Target のパーソナライゼーションモデルでどう決定されたかを理解することです。そのため、パーソナライゼーションインサイトレポートでは、AP または AT アクティビティで提供されたすべてのトラフィックのサブセグメントだけを反映します。具体的に言うと、これら 2 つのレポートは、パーソナライゼーションモデルを使用したすべてのトラフィックを反映します。つまり、パーソナライゼーションインサイトレポートでは、制御トラフィックや、勝者モデル全体で提供されるトラフィックは考慮されません。

2つのパーソナライゼーションインサイトレポートを利用できます。

| レポート | 詳細 |
|--- |--- |
| 自動セグメント | AP／AT アクティビティでのオファーやエクスペリエンスへの反応は、訪問者によって異なります。このレポートは、Target のパーソナライゼーションモデルで定義された様々な自動セグメントがアクティビティのオファー／エクスペリエンスにどう反応しているかを示します。 |
| 重要な属性 | 異なるアクティビティでは、モデルによるパーソナライゼーションの決定にとって重要な属性も多かれ少なかれ異なります。このレポートは、モデルに影響を及ぼした上位の属性とそれら属性の相対的重要性を示します。 |

## パーソナライゼーションインサイトでの属性の解釈 {#section_B5C45E723EC941BDA2A7A642EEB30E4D}

[!UICONTROL パーソナライゼーションインサイト]レポートで表される属性のうち、AP モデルまたは自動ターゲットモデルで使用されるものは、次の 2 種類です。

* **Target で自動的に収集される属性：** Target では基本データセットを使用して、パーソナライゼーションインサイトに反映される AP アクティビティおよび AT アクティビティのパーソナライゼーションアルゴリズムを構築します。データ型、属性の例、[!UICONTROL パーソナライゼーションインサイト]の命名規則について詳しくは、[Target のパーソナライゼーションアルゴリズムのデータ収集](../../c-activities/t-automated-personalization/ap-data.md#reference_255BD3DE7AD04DC9B766E0BC78961058)を参照してください。これらの属性は考慮はされますが、個々のアクティビティの最終モデルでは、これらの属性がすべて使用されるとは限らないことに注意してください。
* **Target に渡される属性：**[Target のパーソナライゼーションアルゴリズムのデータのアップロード](../../c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md#concept_85EA505B37E54514A1C8AB91553FEED6)を参照してください。

Target に追加データを渡して、AP および AT アクティビティのパーソナライゼーションアルゴリズムの構築に使用する基本データセットを拡充する方法が次のようにたくさんあります。

| データタイプ | 説明 | データタイプの命名規則 |
|--- |--- |--- |
| プロファイル属性（プロファイルスクリプト、プロファイル更新 API、ページ内プロファイル属性など） | Target のユーザープロファイルに追加したすべての情報。<br>この情報は、プロファイルスクリプトや、プロファイル更新 API を使用してアップロードされた情報、「profile」というプレフィックスが付いた in-mbox プロファイルパラメーターから取得できます。 | `Custom - Profile - [parameter name]` |
| ページパラメーター（「mbox パラメーター」） | ページコードを介して直接渡される名前と値のペアで、今後の使用のために訪問者のプロファイルに保管されることはありません。 | `Custom - Mbox Parameter - [parameter name]` |
| 顧客属性 | 顧客属性を利用すると、FTP を介して訪問者のプロファイルデータを Experience Cloud にアップロードできます。アップロード後は、データを Adobe Analytics と Adobe Target で利用できます。 | `Custom - Customer Attributes - [parameter name]` |
| 共有オーディエンス（Adobe Audience Manager または Adobe Analytics） | Adobe Audience Manager または Adobe Analytics で作成され、Target と共有されているオーディエンス。 | `Custom - Experience Cloud Segment - [segment name]` |
| アクティビティ内レポート用オーディエンス／セグメント | 「目標と指標」の設定中に AP または自動ターゲットアクティビティで定義されたオーディエンス。 | `Custom - Reporting Segment - [segment name]` |

## トレーニングビデオ：パーソナライゼーションインサイトレポートの使用

>[!VIDEO](https://video.tv.adobe.com/v/25601/?captions=jpn)

詳しくは、Adobe Targetのパーソナライゼーションインサイトレポート [の使用](https://helpx.adobe.com/target/kt/using/personalization-insights-report-feature-video-use.html)を参照してください。
