---
keywords: 自動パーソナライゼーション；ap；オーディエンス；アンサンブル；ランダムフォレスト；マルチアームバンディット；トンプソンサンプリング；ml；機械学習
description: 使用方法を学ぶ [!UICONTROL Automated Personalization] (AP) アクティビティ [!DNL Adobe Target] 高度な機械学習を使用して、各訪問者に異なるオファーのバリエーションを一致させる
title: とは [!UICONTROL Automated Personalization] (AP) アクティビティ
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Automated Personalization
exl-id: 3654dce4-0d6c-42a3-8be7-e081ec478075
source-git-commit: d5b24f298ae405d57c2ba639082cbe99c4e358fd
workflow-type: tm+mt
source-wordcount: '1010'
ht-degree: 47%

---

# [!UICONTROL Automated Personalization]（AP）

[!UICONTROL Automated Personalization] (AP) アクティビティ [!DNL Adobe Target] オファーやメッセージを組み合わせ、高度な機械学習を使用して、個々の顧客プロファイルに基づいて様々なオファーのバリエーションを各訪問者に一致させ、コンテンツをパーソナライズして上昇率を高めます。

>[!NOTE]
>
>[!UICONTROL Automated Personalization] は、[!DNL Target Premium] ソリューションの一部として利用できます。この機能は、[!DNL Target Premium] ライセンスのない [!DNL Target Standard] では使用できません。このライセンスで提供される高度な機能について詳しくは、[Target Premium](/help/main/c-intro/intro.md#premium) を参照してください。

同様に [!UICONTROL 自動ターゲット], [!UICONTROL Automated Personalization] はを使用します [ランダムフォレストアルゴリズム](/help/main/c-activities/t-automated-personalization/algo-random-forest.md)：主要なデータサイエンスアンサンブル手法で、訪問者に表示する最適なエクスペリエンスを決定する主なパーソナライゼーションアルゴリズムとして使用されます。 [!UICONTROL Automated Personalization は、テストの検出フェーズで重要になります。]また、多様な訪問者をターゲット設定する際に、機械学習で最も効果的なコンテンツを決定する場合にも便利です。時間の経過とともに、アルゴリズムは最も効果的なコンテンツを予測し、目標を達成する可能性が最も高いコンテンツを表示できるようになります。

方法の詳細を見るには [!UICONTROL Automated Personalization] 次と異なる [!UICONTROL 自動ターゲット]を参照してください。 [自動ターゲット](/help/main/c-activities/auto-target/auto-target-to-optimize.md#section_BA4D83BE40F14A96BE7CBC7C7CF2A8FB).

ファイルをサイトに実装すると、任意のコンテンツをクリックでき、その領域の追加のコンテンツオプションを [!UICONTROL Visual Experience Composer] (VEC) を参照してください。 その後は、アルゴリズムが各訪問者に関して持っているすべての行動データに基づいて、コンテンツのどの要素を配信するかをそれぞれのケースで自動的に判断し、パーソナライズしたエクスペリエンスを提供します。[!UICONTROL Automated Personalization] は、訪問者の行動の変化に対応できるので、終了日の設定がなくても実行でき、継続的な改善やパーソナライゼーションができます。このモードは、「常時稼動」とも呼ばれます。 テストを実行し、結果を分析し、それを踏まえて推奨結果を配信するという、標準的な A/B アクティビティの結果を実装する標準的な演算順序を踏まなくても、最適化による改善を具現化できます。

[!UICONTROL Automated Personalization] について説明する際に、次の用語が役立ちます。

| 用語 | 定義 |
|---|---|
| マルチアームバンディット | マルチアームバンディット最適化アプローチでは、調査学習とその学習の活用のバランスを取ります。 |
| ランダムフォレスト | 最先端の機械学習アプローチです。 データサイエンスの用語では、訪問者と訪問の属性に基づいて多数のデシジョンツリーを構築することで機能するアンサンブル分類または回帰手法です。 |
| トンプソンサンプリング | トンプソンサンプリングの目的は、全体的に最良の（パーソナライズされていない）エクスペリエンスを最小限の「コスト」で特定することです。トンプソンサンプリングでは、2 つのエクスペリエンスに統計的な差異がない場合でも、必ず勝者が選定されます。詳しくは、[トンプソンサンプリング](https://en.wikipedia.org/wiki/Thompson_sampling)を参照してください。 |

[!UICONTROL Automated Personalization] を利用する際は、次の点を考慮してください。

## [!UICONTROL Automated Personalization] は、ランダムフォレストアルゴリズムを使用してパーソナライズします

ランダムフォレストは、優れた機械学習アプローチです。 データサイエンスの用語では、訪問者と訪問の属性に基づいて多数のデシジョンツリーを構築することで機能するアンサンブル分類または回帰手法です。 [!DNL Target] 内部では、ランダムフォレストを使用して、コンバージョンの可能性が最も高い（または訪問あたりの売上高が最も高い）と予想されるエクスペリエンスを特定の訪問者ごとに決定します。例えば、Chrome を使用する訪問者は金ロイヤリティメンバーで、Tuesdays でサイトにアクセスした訪問者はエクスペリエンス A でコンバートする可能性が高くなります。ニューヨークからの訪問者はエクスペリエンス B でコンバートする可能性が高くなります。でのランダムフォレストの詳細 [!DNL Target]を参照してください。 [ランダムフォレストアルゴリズム](/help/main/c-activities/t-automated-personalization/algo-random-forest.md).

## 訪問ごとにパーソナライゼーションモデルが最適化されます

* アルゴリズムは、訪問者のコンバージョンの可能性（またはコンバージョンによる推定売上高）を予測して、最高のエクスペリエンスを提供します。
* 訪問者は、コントロール母集団に属している場合を除き、既存のセッションの終了時に新しいエクスペリエンスの対象となります。 訪問者がコントロール母集団に属する場合、最初の訪問時に訪問者が表示するエクスペリエンスは、その後の訪問で表示されるエクスペリエンスと同じです。
* 表示されるエクスペリエンスは、視覚的な一貫性を維持するために、セッション内で変更されません。

## パーソナライゼーションモデルは、訪問者の行動の変化に適応します

* マルチアームバンディットを使用すると、モデルは常にトラフィックのごく一部を「消費」してアクティビティの全期間にわたって学習を継続し、以前に学習したトレンドの過度の活用を防ぐことができます。
* を確実におこなうために、24 時間ごとに訪問者の最新の行動データを使用して基になるモデルが再構築されます。 [!DNL Target] は常に訪問者の設定を変更して使用しています。
* アルゴリズムによって個々の訪問者の勝者エクスペリエンスを特定できなかった場合は、総合的なパフォーマンスが最も高いエクスペリエンスを表示する方式に自動的に切り替わります。その間もパーソナライズされた勝者の特定は続行されます。最もパフォーマンスが高いエクスペリエンスは、[トンプソンサンプリング](https://en.wikipedia.org/wiki/Thompson_sampling)によって割り出されます。

## 単一の目標指標に合わせてモデルが絶えず最適化されます

* この指標には、コンバージョンベースと売上高ベース（具体的には、[!UICONTROL 訪問者 1 人あたりの売上高]）があります。

## [!DNL Target] パーソナライゼーションモデルを構築するために、訪問者に関する情報を自動的に収集します

* [!UICONTROL 自動ターゲット] および [!UICONTROL Automated Personalization] で使用される属性について詳しくは、「[Automated Personalizationのデータ収集](/help/main/c-activities/t-automated-personalization/ap-data.md)」を参照してください。

## [!DNL Target] 自動的にすべてを使用 [!DNL Adobe Experience Cloud] 共有オーディエンスを使用してパーソナライゼーションモデルを構築

* オーディエンスをモデルに追加するために特別な作業をおこなう必要はありません。 [!DNL Experience Cloud Audiences] と [!DNL Target] を併用する方法について詳しくは、「[Experience Cloud オーディエンス](/help/main/c-integrating-target-with-mac/mmp.md)」を参照してください。

## パーソナライゼーションモデルを構築するために、オフラインデータや傾向スコアなどのカスタムデータをアップロードできます

CRM 情報や顧客のチャーン傾向スコアなどのオフラインデータは、パーソナライゼーションモデルを構築する際に非常に重要になる可能性があります。 [!UICONTROL Automated Personalization]（AP）および [!UICONTROL 自動ターゲット] のパーソナライゼーションアルゴリズムにデータを入力する方法はいくつかあります。

* [mbox パラメーター](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html){target=_blank}
* [プロファイルパラメーター](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html){target=_blank}
* [プロファイル更新のためのサーバー側 API](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html){target=_blank}

自動的に収集され、[!UICONTROL Automated Personalization] および[!UICONTROL 自動ターゲット]のパーソナライゼーションアルゴリズムで使用されるデータについて詳しくは、「[Automated Personalization のデータ収集](/help/main/c-activities/t-automated-personalization/ap-data.md)」を参照してください。

## トレーニングビデオ：アクティビティのタイプ

このビデオでは、[!DNL Target] で利用できるアクティビティのタイプについて説明しています。[!UICONTROL Automated Personalization に関する説明は 5:55 から始まります。]

* [!DNL Adobe Target] に含まれるアクティビティのタイプの説明
* 目標達成に適したアクティビティタイプの選択
* すべてのアクティビティタイプを対象とする、ガイド付き 3 ステップワークフローの説明

>[!VIDEO](https://video.tv.adobe.com/v/17386)
