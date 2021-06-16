---
keywords: ターゲット設定;AP レポート;Automated Personalization レポート;自動ターゲット;自動的なターゲット;自動ターゲットレポート;自動的なターゲットのレポート;パーソナライゼーション;インサイト;自動セグメント;FAQ;よくある質問;重要な属性
description: Automated Personalization(AP)および自動ターゲット(AT)アクティビティ用の専用レポートの使用方法（自動セグメントと重要な属性）について説明します。
title: パーソナライゼーションインサイトレポートの使用方法
feature: レポート
exl-id: 89295d95-f179-4277-ae63-453350e1bba8
source-git-commit: c0eae79da63e2f269f603b4d9fd2a5a1170e2687
workflow-type: tm+mt
source-wordcount: '862'
ht-degree: 56%

---

# ![PREMIUM](/help/assets/premium.png) パーソナライゼーションインサイトレポート

[!UICONTROL Automated Personalization]（AP）および自動ターゲット（AT）アクティビティのユーザーは、[!UICONTROL 自動セグメント]レポートと重要な属性レポートの 2 つの特殊なレポートを使用できます。

>[!NOTE]
>
>パーソナライゼーションインサイトレポートを使用する際は、次の点を考慮してください。
>
>* AP および AT アクティビティは、[!DNL Target Premium] ソリューションの一部です。これらは、[!DNL Target Premium] ライセンスのない [!DNL Target Standard] には付属していません。
   >
   >
* [!UICONTROL パーソナライゼーションインサイトレポートは、コンバージョン最適化目標を使用する AP および AT アクティビティについてのみ使用できます。]アクティビティがライブになった後で最適化目標が売上高からコンバージョンに変更されたアクティビティもサポートされません。
   >
   >
* [!UICONTROL パーソナライ] ゼーションインサイトレポートは、レポート指標ドロップダウンリストから  プライマリGoalisが選択された場合に  のみ使用できます。
   >
   >
* パーソナライゼーションインサイトレポートは、[デフォルト環境](/help/administrating-target/hosts.md)でのみサポートされています。
   >
   >
* [!UICONTROL パーソナ] ライゼーションインサイトレポートは、Livestatusに属し、アクティブ化さ  れ、15日以上トラフィックを受け取ったアクティビティに対してのみ生成されます。


## パーソナライゼーションインサイトレポートの概要 {#section_B47CD4A50FEB43D587F9FACD9FFD6D9D}

[!UICONTROL パーソナライゼーションインサイト]レポートの目標は、AP および AT アクティビティの背後にある Target パーソナライゼーションモデルで訪問者トラフィックがどのようにパーソナライズされるかを詳細に示すことです。[ランダムフォレストアルゴリズム](/help/c-activities/t-automated-personalization/algo-random-forest.md)は、[!DNL Target]パーソナライゼーションモデルの基礎となります。

[!UICONTROL パーソナライゼーションインサイト]レポートの目標は、 [!DNL Target]パーソナライゼーションモデルがどの訪問者をコンテンツの一部に送信するかを把握することです。 [!UICONTROL パーソナライゼーションインサイト]レポートは、APまたはATアクティビティが提供するすべてのトラフィックのサブセグメントのみを反映します。 具体的に言うと、これら 2 つのレポートは、パーソナライゼーションモデルを使用したすべてのトラフィックを反映します。つまり、[!UICONTROL パーソナライゼーションインサイト]レポートでは、制御トラフィックや、勝者モデル全体で提供されるトラフィックは考慮されません。

2つの[!UICONTROL パーソナライゼーションインサイト]レポートを使用できます。

| レポート | 詳細 |
|--- |--- |
| [!UICONTROL 自動セグメント] | AP／AT アクティビティでのオファーやエクスペリエンスへの反応は、訪問者によって異なります。このレポートは、[!DNL Target]パーソナライゼーションモデルで定義された様々な自動セグメントが、アクティビティのオファー/エクスペリエンスにどのように反応したかを示します。 |
| [!UICONTROL 重要な属性] | 異なるアクティビティでは、モデルによるパーソナライゼーションの決定にとって重要な属性も多かれ少なかれ異なります。このレポートは、モデルに影響を及ぼした上位の属性とそれら属性の相対的重要性を示します。 |

## パーソナライゼーションインサイトでの属性の解釈 {#section_B5C45E723EC941BDA2A7A642EEB30E4D}

[!UICONTROL パーソナライゼーションインサイト]レポートで表される属性のうち、AP モデルまたは自動ターゲットモデルで使用されるものは、次の 2 種類です。

* **で自動的に収集される属性：**[!DNL Target]Target では基本データセットを使用して、パーソナライゼーションインサイトに反映される AP アクティビティおよび AT アクティビティのパーソナライゼーションアルゴリズムを構築します。データ型、属性の例、[!UICONTROL パーソナライゼーションインサイト]の命名規則について詳しくは、[Target のパーソナライゼーションアルゴリズムのデータ収集](/help/c-activities/t-automated-personalization/ap-data.md)を参照してください。これらの属性は考慮はされますが、個々のアクティビティの最終モデルでは、これらの属性がすべて使用されるとは限らないことに注意してください。
* **Target に渡される属性：**[Target のパーソナライゼーションアルゴリズムのデータのアップロード](/help/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md)を参照してください。

[!DNL Target] には、追加のデータをに渡して、APおよびATアクティビティでのパーソナライゼ [!DNL Target] ーションアルゴリズムの構築に使用するベースデータセットをエンリッチメントする方法が多数用意されています。

| データタイプ | 説明 | データタイプの命名規則 |
|--- |--- |--- |
| プロファイル属性（プロファイルスクリプト、プロファイル更新 API、ページ内プロファイル属性など） | Target のユーザープロファイルに追加したすべての情報。<br>この情報は、プロファイルスクリプトや、プロファイル更新 API を使用してアップロードされた情報、「profile」というプレフィックスが付いた in-mbox プロファイルパラメーターから取得できます。 | `Custom - Profile - [parameter name]` |
| ページパラメーター（「mbox パラメーター」） | ページコードを介して直接渡される名前と値のペアで、今後の使用のために訪問者のプロファイルに保管されることはありません。 | `Custom - Mbox Parameter - [parameter name]` |
| 顧客属性 | 顧客属性を利用すると、FTP を介して訪問者のプロファイルデータを Experience Cloud にアップロードできます。アップロード後は、データを Adobe Analytics と Adobe Target で利用できます。 | `Custom - Customer Attributes - [parameter name]` |
| 共有オーディエンス（Adobe Audience Manager または Adobe Analytics） | Adobe Audience Manager または Adobe Analytics で作成され、Target と共有されているオーディエンス。 | `Custom - Experience Cloud Segment - [segment name]` |
| アクティビティ内レポート用オーディエンス／セグメント | 「目標と指標」の設定中に AP または自動ターゲットアクティビティで定義されたオーディエンス。 | `Custom - Reporting Segment - [segment name]` |

## よくある質問

[!UICONTROL Automated Personalization](AP)および[!UICONTROL 自動ターゲット] [!UICONTROL インサイト]レポートに関するよくある質問のリストです。

### [!UICONTROL Automated Personalization](AP)および[!UICONTROL 自動ターゲット]モデルのデータは、どの程度の期間保持されますか？

[!UICONTROL Automated Personalization] (AP)および自動ターゲッ  トモデルは、アクティビティの過去45日間のユーザー行動（ユーザープロファイル、インプレッションイベントおよびコンバージョンイベント）に関するトレーニングを受けます。

[!UICONTROL Automated Personalization] (AP)および [!UICONTROL 自動ターゲッ] トモデルは、ユーザーの行動、トレーニングレコード、モデル決定データを90日間保持し、インサイトレポートを生成  します。90日後、トレーニングレコードとモデルの決定は破棄されます。 [!UICONTROL Automated Personalization] (AP)および自動ターゲット [!UICONTROL モデルで] も、2年間、レポート目的で、エクスペリエンス/オファーレベルのインプレッションおよびコンバージョンデータの集計が保持されます。このデータは集計レベルのデータのみで、個人レベルのプロファイルデータは含まれません。

## トレーニングビデオ：パーソナライゼーションインサイトレポート![チュートリアルバッジ](/help/assets/tutorial.png)の使用

>[!VIDEO](https://video.tv.adobe.com/v/25601/)

詳しくは、Adobe Target](https://helpx.adobe.com/target/kt/using/personalization-insights-report-feature-video-use.html)でのパーソナライゼーションインサイトレポートの使用[を参照してください。

## Adobeブログ

* パート1:[AI主導のパーソナライゼーションの魔法から謎を取り除く](https://theblog.adobe.com/taking-mystery-magic-ai-driven-personalization-part-1/)
* パート2:[Adobe TargetのパーソナライゼーションのためのAIの幕の後ろののぞき](https://theblog.adobe.com/a-peek-behind-the-curtain-of-ai-for-personalization-in-adobe-target/)
* パート3:[MAGIX — AI駆動型パーソナライゼーションのブラックボックス問題の解決策](https://theblog.adobe.com/magix-the-solution-to-the-black-box-issue-of-ai-driven-personalization/)
