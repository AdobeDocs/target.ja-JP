---
keywords: automated personalization;ap；オーディエンス；アンサンブル；ランダムフォレスト；マルチアームバンディット；トンプソンサンプリング；ml；機械学習
description: 高度な機械学習を使用して各訪問者にマッチするオファーの様々 [!UICONTROL Automated Personalization] バリエーションを見つける、での  [!DNL Adobe Target]  （AP）アクティビティの使用方法を説明します。
title: '[!UICONTROL Automated Personalization] （AP）アクティビティとは'
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Automated Personalization
exl-id: 3654dce4-0d6c-42a3-8be7-e081ec478075
source-git-commit: d5b24f298ae405d57c2ba639082cbe99c4e358fd
workflow-type: tm+mt
source-wordcount: '931'
ht-degree: 33%

---

# [!UICONTROL Automated Personalization] （AP）

[!UICONTROL Automated Personalization] の [!DNL Adobe Target] （AP）アクティビティは、オファーやメッセージを組み合わせ、高度な機械学習を使用して、個々の顧客プロファイルに基づいて各訪問者に異なるオファーのバリエーションを照合し、コンテンツをパーソナライズして上昇率を高めます。

>[!NOTE]
>
>[!UICONTROL Automated Personalization] は、[!DNL Target Premium] ソリューションの一部として利用できます。 この機能は、[!DNL Target Premium] ライセンスのない [!DNL Target Standard] では使用できません。このライセンスで提供される高度な機能について詳しくは、[Target Premium](/help/main/c-intro/intro.md#premium) を参照してください。

[!UICONTROL Auto-Target] と同様、[!UICONTROL Automated Personalization] は主要なデータサイエンスアンサンブル手法である [ ランダムフォレストアルゴリズム ](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) を主なパーソナライゼーションアルゴリズムとして使用して、訪問者に表示する最適なエクスペリエンスを決定します。 テストの発見フェーズでは [!UICONTROL Automated Personalization] が役立つ場合があります。 また、多様な訪問者をターゲット設定する際に、機械学習で最も効果的なコンテンツを決定する場合にも便利です。時間の経過とともに、アルゴリズムは最も効果的なコンテンツを予測し、目標を達成する可能性が最も高いコンテンツを表示できるようになります。

[!UICONTROL Automated Personalization] との違いについて詳 [!UICONTROL Auto-Target] くは、[ 自動ターゲット ](/help/main/c-activities/auto-target/auto-target-to-optimize.md#section_BA4D83BE40F14A96BE7CBC7C7CF2A8FB) を参照してください。

マーケターは、サイトに 1 つのファイルを実装します。このファイルを使用すれば、任意のコンテンツを指定してクリックし、[!UICONTROL Visual Experience Composer] （VEC）を使用してその領域の追加のコンテンツオプションを視覚的に作成して選択できます。 その後は、アルゴリズムが各訪問者に関して持っているすべての行動データに基づいて、コンテンツのどの要素を配信するかをそれぞれのケースで自動的に判断し、パーソナライズしたエクスペリエンスを提供します。[!UICONTROL Automated Personalization] れは訪問者行動の変更に適応できるので、設定された終了日なしで実行して、進行中の上昇率とパーソナライゼーションを提供できます。 このモードは、「常時稼動」と呼ばれることもあります。 テストを実行し、結果を分析し、それを踏まえて推奨結果を配信するという、標準的な A/B アクティビティの結果を実装する標準的な演算順序を踏まなくても、最適化による改善を具現化できます。

[!UICONTROL Automated Personalization] について説明するときに役立つ用語を次に示します。

| 用語 | 定義 |
|---|---|
| マルチアームバンディット | マルチアームバンディット最適化アプローチでは、調査学習とその学習の活用のバランスを取ります。 |
| ランダムフォレスト | 最先端の機械学習アプローチ。 データサイエンスの用語では、訪問者および訪問の属性に基づいて多くのデシジョンツリーを構築することで機能する、アンサンブル分類または回帰手法です。 |
| トンプソンサンプリング | トンプソンサンプリングの目的は、全体的に最良の（パーソナライズされていない）エクスペリエンスを最小限の「コスト」で特定することです。トンプソンサンプリングでは、2 つのエクスペリエンスに統計的な差異がない場合でも、必ず勝者が選定されます。詳しくは、[トンプソンサンプリング](https://en.wikipedia.org/wiki/Thompson_sampling)を参照してください。 |

[!UICONTROL Automated Personalization] を使用する際は、次の詳細を考慮してください。

## [!UICONTROL Automated Personalization] は、ランダムフォレストアルゴリズムを使用してパーソナライズします

ランダムフォレストは、最先端の機械学習アプローチです。 データサイエンスの用語では、訪問者および訪問の属性に基づいて多くのデシジョンツリーを構築することで機能する、アンサンブル分類または回帰手法です。 [!DNL Target] 内では、ランダムフォレストを使用して、各特定の訪問者について、コンバージョンの可能性が最も高い（または訪問あたりの売上高が最も高い）エクスペリエンスを判断します。 例えば、Chromeを使用する訪問者はゴールドロイヤルティメンバーで、火曜日にサイトにアクセスした場合は、エクスペリエンス A でコンバージョンされる可能性が高くなります。ニューヨークの訪問者は、エクスペリエンス B でコンバージョンされる可能性が高くなります。[!DNL Target] のランダムフォレストについて詳しくは、[ ランダムフォレストアルゴリズム ](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) を参照してください。

## パーソナライゼーションモデルは、訪問ごとに最適化されます

* アルゴリズムは、訪問者のコンバージョンの可能性（またはコンバージョンからの推定売上高）を予測して、最適なエクスペリエンスを提供します。
* 訪問者は、コントロール母集団に属している場合を除き、既存セッションの終了時に新しいエクスペリエンスを利用できます。 訪問者がコントロール母集団に属している場合、訪問者が最初の訪問で表示されるエクスペリエンスは、その後の訪問で表示されるエクスペリエンスと同じです。
* 表示されるエクスペリエンスは、視覚的な一貫性を維持するためにセッション内で変更されることはありません。

## パーソナライゼーションモデルは、訪問者の行動の変化に適応します

* マルチアームバンディットは、アクティビティの全期間を通じて学習を継続し、以前に学習したトレンドの過剰利用を防ぐために、モデルが常にわずかなトラフィックを「費やす」ことを保証します。
* 基になるモデルは、最新の訪問者行動データを使用して 24 時間ごとに再構築され、常に変化する訪問者の環境設定を使用して [!DNL Target] るようにします。
* アルゴリズムによって個々の訪問者の勝者エクスペリエンスを特定できなかった場合は、総合的なパフォーマンスが最も高いエクスペリエンスを表示する方式に自動的に切り替わります。その間もパーソナライズされた勝者の特定は続行されます。最もパフォーマンスが高いエクスペリエンスは、[トンプソンサンプリング](https://en.wikipedia.org/wiki/Thompson_sampling)によって割り出されます。

## モデルは、1 つの目標指標を継続的に最適化します

* この指標は、コンバージョンベースまたは収益ベース（具体的には [!UICONTROL Revenue per Visitor]）の場合があります。

## [!DNL Target] は、訪問者に関する情報を自動的に収集してパーソナライゼーションモデルを構築します

* [!UICONTROL Auto-Target] および [!UICONTROL Automated Personalization] で使用される属性について詳しくは、[Automated Personalization Data Collection](/help/main/c-activities/t-automated-personalization/ap-data.md) を参照してください。

## [!DNL Target] では、すべての共有オーディエンス [!DNL Adobe Experience Cloud] 自動的に使用してパーソナライゼーションモデルを構築します

* モデルにオーディエンスを追加するために、特別な作業を行う必要はありません。 [!DNL Experience Cloud Audiences] と [!DNL Target] を併用する方法について詳しくは、「[Experience Cloud オーディエンス](/help/main/c-integrating-target-with-mac/mmp.md)」を参照してください。

## マーケターは、オフラインデータ、傾向スコア、その他のカスタムデータをアップロードして、パーソナライゼーションモデルを構築できます

CRM 情報や顧客チャーンの傾向スコアなどのオフラインデータは、パーソナライゼーションモデルを構築する際に非常に役立つ可能性があります。 [!UICONTROL Automated Personalization] （AP）および [!UICONTROL Auto-Target] のパーソナライゼーションアルゴリズムでデータを入力する方法はいくつかあります。

* [mbox パラメーター](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=ja){target=_blank}
* [プロファイルパラメーター](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=ja){target=_blank}
* [プロファイル更新のためのサーバー側 API](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=ja){target=_blank}

[!UICONTROL Automated Personalization] および [!UICONTROL Auto-Target] パーソナライゼーションアルゴリズムによって自動的に収集および使用されるデータについて詳しくは、[Automated Personalizationのデータ収集 ](/help/main/c-activities/t-automated-personalization/ap-data.md) を参照してください。

## トレーニングビデオ：アクティビティのタイプ

このビデオでは、[!DNL Target] で利用できるアクティビティのタイプについて説明しています。[!UICONTROL Automated Personalization] については 5:55 から説明します。

* [!DNL Adobe Target] に含まれるアクティビティタイプの説明
* 目標達成に適したアクティビティタイプの選択
* すべてのアクティビティタイプを対象とする、ガイド付き 3 ステップワークフローの説明

>[!VIDEO](https://video.tv.adobe.com/v/17386)
