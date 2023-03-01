---
keywords: 自動パーソナライゼーション；ap；オーディエンス；アンサンブル；ランダムフォレスト；マルチアームバンディット；トンプソンサンプリング；ml；機械学習
description: AdobeでのAutomated Personalization(AP) アクティビティの使用方法を説明します [!DNL Target] 高度な機械学習を使用して、各訪問者に異なるオファーのバリエーションを一致させる
title: Automated Personalization(AP) アクティビティとは
feature: Automated Personalization
exl-id: 3654dce4-0d6c-42a3-8be7-e081ec478075
source-git-commit: 3ac61272ee1ccd72a8670966f181e7798cbe9f76
workflow-type: tm+mt
source-wordcount: '1049'
ht-degree: 89%

---

# ![プレミアム](/help/main/assets/premium.png) Automated Personalization(AP)

[!UICONTROL Automated Personalization] (AP) アクティビティ [!DNL Adobe Target] オファーやメッセージを組み合わせ、高度な機械学習を使用して個々の顧客プロファイルに基づいて様々なオファーのバリエーションを各訪問者に一致させ、コンテンツをパーソナライズして上昇率を高めます。

>[!NOTE]
>
>[!UICONTROL Automated Personalization] は、[!DNL Target Premium] ソリューションの一部として利用できます。[!DNL Target Premium] ライセンスがない場合、[!DNL Target Standard] には含まれません。[!DNL Target Premium] ライセンスをお持ちの場合、[!DNL Adobe Experience Cloud] 内の [!DNL Target Standard] カードが [!DNL Target Premium] カードに置き換わります。

[!UICONTROL 自動ターゲット]と同様に、[!UICONTROL Automated Personalization] でも、先進のデータサイエンスアンサンブル手法であるランダムフォレストアルゴリズムを主要パーソナライゼーションアルゴリズムとして使用し、訪問者に表示する最適なエクスペリエンスを決定します。[!UICONTROL Automated Personalization は、テストの検出フェーズで重要になります。]また、多様な訪問者をターゲット設定する際に、機械学習で最も効果的なコンテンツを決定する場合にも便利です。時間の経過とともに、アルゴリズムは最も効果的なコンテンツを予測し、目標を達成する可能性が最も高いコンテンツを表示できるようになります。

方法の詳細を見るには [!UICONTROL Automated Personalization] 次と異なる [!UICONTROL 自動ターゲット]を参照してください。 [自動ターゲット](/help/main/c-activities/auto-target/auto-target-to-optimize.md).

ファイルをサイトに実装することで、任意のコンテンツをクリックできるようになり、そこから、VEC（[!UICONTROL Visual Experience Composer]）を使用して、その領域の追加のコンテンツオプションを視覚的に作成および選択できるようになります。その後は、アルゴリズムが各訪問者に関して持っているすべての行動データに基づいて、コンテンツのどの要素を配信するかをそれぞれのケースで自動的に判断し、パーソナライズしたエクスペリエンスを提供します。[!UICONTROL Automated Personalization] は、訪問者の行動の変化に対応できるので、終了日の設定がなくても実行でき、継続的な改善やパーソナライゼーションができます。これは、「常時稼動」モードとも呼ばれます。テストを実行し、結果を分析し、それを踏まえて推奨結果を配信するという、標準的な A/B アクティビティの結果を実装する標準的な演算順序を踏まなくても、最適化による改善を具現化できます。

[!UICONTROL Automated Personalization] について説明する際に、次の用語が役立ちます。

| 用語 | 定義 |
|---|---|
| マルチアームバンディット | 調査学習とその学習の活用のバランスの最適化のためのマルチアームバンディットアプローチです。 |
| ランダムフォレスト | ランダムフォレストは、優れた機械学習手法です。データサイエンス分野においては、訪問者と訪問の属性に基づいて大量のデシジョンツリーを構築することで機能するアンサンブル分類または回帰手法を指します。Target では、個々の訪問者がコンバージョンに至る可能性が最も高い（または訪問あたりの売上高が最も高い）と予想されるエクスペリエンスを決定するためにランダムフォレストが使用されます。Target でのランダムフォレストについて詳しくは、[ランダムフォレストアルゴリズム](/help/main/c-activities/t-automated-personalization/algo-random-forest.md)を参照してください。 |
| トンプソンサンプリング | トンプソンサンプリングの目的は、全体的に最良の（パーソナライズされていない）エクスペリエンスを最小限の「コスト」で特定することです。トンプソンサンプリングでは、2 つのエクスペリエンスに統計的な差異がない場合でも、必ず勝者が選定されます。詳しくは、[トンプソンサンプリング](https://en.wikipedia.org/wiki/Thompson_sampling)を参照してください。 |

[!UICONTROL Automated Personalization] を利用する際は、次の点を考慮してください。

**[!UICONTROL Automated Personalization] では、パーソナライズにランダムフォレストアルゴリズムを利用します。**

ランダムフォレストは、優れた機械学習手法です。データサイエンス分野においては、訪問者と訪問の属性に基づいて大量のデシジョンツリーを構築することで機能するアンサンブル分類または回帰手法を指します。Target では、個々の訪問者がコンバージョンに至る可能性が最も高い（または訪問あたりの売上高が最も高い）と予想されるエクスペリエンスを決定するためにランダムフォレストが使用されます。例えば、ゴールドロイヤルティメンバーであり、Chrome を利用し、火曜日にサイトにアクセスした訪問者はエクスペリエンス A でコンバージョンする確率が高く、ニューヨークからの訪問者はエクスペリエンス B でコンバージョンする確率が高い可能性があります。Target でのランダムフォレストについて詳しくは、[ランダムフォレストアルゴリズム](/help/main/c-activities/t-automated-personalization/algo-random-forest.md)を参照してください。

**パーソナライゼーションモデルは訪問ごとに最適化されます。**

* 最高のエクスペリエンスを提供するために、アルゴリズムによって、訪問者のコンバージョンの確率（またはコンバージョンによる推定売上高）を予測します。
* 訪問者は、既存のセッションの終了時に新しいエクスペリエンスの対象になります（ただし、コントロールグループの訪問者には、最初の訪問とその後の訪問で同じエクスペリエンスが表示されます）。
* セッション内では、ビジュアルの一貫性を維持するために、表示されるエクスペリエンスの変更はおこなわれません。

**訪問者の行動の変化にパーソナライゼーションモデルが対応します。**

* マルチアームバンディットにより、モデルは常にトラフィックのごく一部を利用して、アクティビティの全期間にわたって学習を続け、それまでに学習したトレンドの乱用を防止します。
* Target が変化し続けるユーザーの好みを常に活用できるように、24 時間ごとに訪問者の最新の行動データを使用して基になるモデルを再構築します。
* アルゴリズムによって個々の訪問者の勝者エクスペリエンスを特定できなかった場合は、総合的なパフォーマンスが最も高いエクスペリエンスを表示する方式に自動的に切り替わります。その間もパーソナライズされた勝者の特定は続行されます。最もパフォーマンスが高いエクスペリエンスは、[トンプソンサンプリング](https://en.wikipedia.org/wiki/Thompson_sampling)によって割り出されます。

**単一の目標指標に合わせてモデルが絶えず最適化されます。**

* この指標には、コンバージョンベースと売上高ベース（具体的には、[!UICONTROL 訪問者 1 人あたりの売上高]）があります。

**Target は、パーソナライゼーションモデルを構築するために、訪問者に関する情報を自動的に収集します。**

* [!UICONTROL 自動ターゲット] および [!UICONTROL Automated Personalization] で使用される属性について詳しくは、「[Automated Personalizationのデータ収集](/help/main/c-activities/t-automated-personalization/ap-data.md)」を参照してください。

**Target は、パーソナライゼーションモデルを構築するために、[!DNL Adobe Experience Cloud] のすべての共有オーディエンスを自動的に使用します。**

* オーディエンスをモデルに追加するために何か特別な作業をおこなう必要はありません。[!DNL Experience Cloud Audiences] と [!DNL Target] を併用する方法について詳しくは、「[Experience Cloud オーディエンス](/help/main/c-integrating-target-with-mac/mmp.md)」を参照してください。

**パーソナライゼーションモデルを構築するために、オフラインデータや傾向スコアなどのカスタムデータをアップロードできます。**

CRM 情報や顧客のチャーン傾向スコアなどのオフラインデータは、パーソナライゼーションモデルを構築する際に非常に重要となることがあります。[!UICONTROL Automated Personalization]（AP）および [!UICONTROL 自動ターゲット] のパーソナライゼーションアルゴリズムにデータを入力する方法はいくつかあります。

* [mbox パラメーター](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/methods-to-get-data-into-target/){target=_blank}
* [プロファイルパラメーター](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/methods-to-get-data-into-target/){target=_blank}
* [プロファイル更新のためのサーバー側 API](https://developer.adobe.com/target/before-implement/methods-to-get-data-into-target/methods-to-get-data-into-target/)

自動的に収集され、[!UICONTROL Automated Personalization] および[!UICONTROL 自動ターゲット]のパーソナライゼーションアルゴリズムで使用されるデータについて詳しくは、「[Automated Personalization のデータ収集](/help/main/c-activities/t-automated-personalization/ap-data.md)」を参照してください。

## ![概要バッジ](/help/main/assets/overview.png) トレーニングビデオ：アクティビティタイプ

このビデオでは、[!DNL Target Standard/Premium] で利用できるアクティビティのタイプについて説明しています。[!UICONTROL Automated Personalization に関する説明は 5:55 から始まります。]

* [!DNL Adobe Target] に含まれるアクティビティのタイプの説明
* 目標達成に適したアクティビティタイプの選択
* すべてのアクティビティタイプを対象とする、ガイド付き 3 ステップワークフローの説明

>[!VIDEO](https://video.tv.adobe.com/v/17386)
