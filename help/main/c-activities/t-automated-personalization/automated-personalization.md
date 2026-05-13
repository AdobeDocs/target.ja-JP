---
keywords: 自動パーソナライゼーション；アプリ；オーディエンス；アンサンブル；ランダムフォレスト；マルチアームドバンディット；トンプソンサンプリング；マシンラーニング；機械学習
description: 高度な機械学習を使用して、各訪問者に対する様々なオファーのバリエーションを一致させる [!DNL Adobe Target] の[!UICONTROL Automated Personalization] （AP）アクティビティの使用方法について説明します。
title: '[!UICONTROL Automated Personalization] （AP） アクティビティとは何ですか？'
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Automated Personalization
exl-id: 3654dce4-0d6c-42a3-8be7-e081ec478075
TQID: https://experienceleague.adobe.com/BBtKgNRTlqNFFoAjr1LQkhHyZeAlXG2h8D7bsndh4kQ
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
subfeature_v2:
  - id: fff07a91-d479-45f4-ae95-9762e79b1b7c
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: c4147b6e-073b-4d3c-9ab1-d60f2f4434ef
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 1003
ht-degree: 40%

---

# [!UICONTROL Automated Personalization] （AP）

[!DNL Adobe Target]の[!UICONTROL Automated Personalization] （AP）アクティビティは、オファーまたはメッセージを組み合わせ、高度な機械学習を使用して、個々の顧客プロファイルに基づいて各訪問者に異なるオファーのバリエーションを一致させ、コンテンツをパーソナライズし、向上を促進します。

>[!NOTE]
>
>[!UICONTROL Automated Personalization]は[!DNL Target Premium] ソリューションの一部として利用できます。 この機能は、[!DNL Target Premium] ライセンスのない [!DNL Target Standard] では使用できません。 このライセンスで提供される高度な機能について詳しくは、[Target Premium](/help/main/c-intro/intro.md#premium) を参照してください。

[!UICONTROL Auto-Target]と同様に、[!UICONTROL Automated Personalization]では、主要なデータサイエンス アンサンブル手法である[&#x200B; ランダムフォレスト アルゴリズム &#x200B;](/help/main/c-activities/t-automated-personalization/algo-random-forest.md)を主なパーソナライゼーションアルゴリズムとして使用して、訪問者に最適なエクスペリエンスを決定しています。 [!UICONTROL Automated Personalization]は、テストの検出フェーズで役立ちます。 また、多様な訪問者をターゲティングする際に、機械学習で最も効果的なコンテンツを決定する場合にも便利です。 時間の経過とともに、アルゴリズムは最も効果的なコンテンツを予測し、目標を達成する可能性が最も高いコンテンツを表示できるようになります。

[!UICONTROL Automated Personalization]と[!UICONTROL Auto-Target]の違いについて詳しくは、[自動ターゲット &#x200B;](/help/main/c-activities/auto-target/auto-target-to-optimize.md#section_BA4D83BE40F14A96BE7CBC7C7CF2A8FB)を参照してください。

マーケターはサイトに1つのファイルを実装し、任意のコンテンツをポイントしてクリックし、[!UICONTROL Visual Experience Composer] （VEC）を使用して、その領域の追加のコンテンツオプションを視覚的に作成および選択できます。 その後は、アルゴリズムが各訪問者に関して持っているすべての行動データに基づいて、コンテンツのどの要素を配信するかをそれぞれのケースで自動的に判断し、パーソナライズしたエクスペリエンスを提供します。 [!UICONTROL Automated Personalization]は訪問者の行動の変化に適応できるため、終了日を設定せずに実行して、継続的なリフトとパーソナライゼーションを提供できます。 このモードは「常時オン」と呼ばれることもあります。 テストを実行し、結果を分析し、それを踏まえて推奨結果を配信するという、標準的な A/B アクティビティの結果を実装する標準的な演算順序を踏まなくても、最適化による改善を具現化できます。

[!UICONTROL Automated Personalization] について説明するときに役立つ用語を次に示します。

| 用語 | 定義 |
|---|---|
| マルチアームバンディット | マルチアームバンディット最適化アプローチでは、調査学習とその学習の活用のバランスを取ります。 |
| ランダムフォレスト | AI時代のデータ戦略。 データサイエンスの用語では、訪問者と訪問属性に基づいて多くの決定木を構築することで機能するアンサンブル分類または回帰方法です。 |
| トンプソンサンプリング | トンプソンサンプリングの目的は、全体的に最良の（パーソナライズされていない）エクスペリエンスを最小限の「コスト」で特定することです。 トンプソンサンプリングでは、2 つのエクスペリエンスに統計的な差異がない場合でも、必ず勝者が選定されます。 詳しくは、[トンプソンサンプリング](https://en.wikipedia.org/wiki/Thompson_sampling)を参照してください。 |

[!UICONTROL Automated Personalization]を使用する場合は、次の詳細を検討してください。

## [!UICONTROL Automated Personalization]は、ランダム フォレスト アルゴリズムを使用してパーソナライズします

Random Forestは主要なマシンラーニングアプローチです。 データサイエンスの用語では、訪問者と訪問属性に基づいて多くの決定木を構築することで機能するアンサンブル分類または回帰方法です。 [!DNL Target] 内部では、ランダムフォレストを使用して、コンバージョンの可能性が最も高い（または訪問あたりの売上高が最も高い）と予想されるエクスペリエンスを特定の訪問者ごとに決定します。 たとえば、Chromeを利用し、ゴールドロイヤルティの会員で、火曜日にサイトにアクセスした訪問者は、エクスペリエンス Aでコンバージョンする可能性が高くなります。ニューヨークの訪問者は、エクスペリエンス Bでコンバージョンする可能性が高くなります。[!DNL Target]のランダム フォレストについて詳しくは、[&#x200B; ランダム フォレスト アルゴリズム &#x200B;](/help/main/c-activities/t-automated-personalization/algo-random-forest.md)を参照してください。

## パーソナライゼーションモデルは、各訪問に最適化されます

* このアルゴリズムは、訪問者がコンバージョンに至る可能性（またはコンバージョンによる推定売上）を予測し、最適なエクスペリエンスを提供します。
* 訪問者がコントロールグループに属していない限り、訪問者は既存のセッションの終了時に新しいエクスペリエンスの対象となります。 訪問者がコントロール グループ内にある場合、訪問者が最初の訪問で見たエクスペリエンスは、その後の訪問で見たエクスペリエンスと同じです。
* 提示されたエクスペリエンスは、視覚的な一貫性を維持するためにセッション内で変更されません。

## パーソナライゼーションモデルは、訪問者の行動の変化に適応します

* マルチアームバンディットは、モデルがアクティビティのライフタイムを通じて学習を継続し、以前に学習したトレンドの過度な悪用を防ぐために、常に小さなトラフィックを「費やす」ことを保証します。
* 基になるモデルは、最新の訪問者行動データを使用して24時間ごとに再構築され、[!DNL Target]が常に変化する訪問者の環境設定を使用していることを確認します。
* アルゴリズムによって個々の訪問者の勝者エクスペリエンスを特定できなかった場合は、総合的なパフォーマンスが最も高いエクスペリエンスを表示する方式に自動的に切り替わります。その間もパーソナライズされた勝者の特定は続行されます。 最もパフォーマンスが高いエクスペリエンスは、[トンプソンサンプリング](https://en.wikipedia.org/wiki/Thompson_sampling)によって割り出されます。

## このモデルは、単一の目標指標を継続的に最適化します

* この指標は、コンバージョンベースまたは収益ベース（具体的には[!UICONTROL Revenue per Visitor]）です。

## [!DNL Target]は、パーソナライゼーション モデルを構築するために訪問者に関する情報を自動的に収集します

* [!UICONTROL Auto-Target]および[!UICONTROL Automated Personalization]で使用される属性について詳しくは、[Automated Personalization Data Collection](/help/main/c-activities/t-automated-personalization/ap-data.md)を参照してください。

## [!DNL Target]は、すべての[!DNL Adobe Experience Cloud]共有オーディエンスを自動的に使用してパーソナライゼーションモデルを構築します

* モデルにオーディエンスを追加するために特別な何もする必要はありません。 [!DNL Experience Cloud Audiences] と [!DNL Target] を併用する方法について詳しくは、「[Experience Cloud オーディエンス](/help/main/c-integrating-target-with-mac/mmp.md)」を参照してください。

## マーケターは、オフラインデータ、傾向スコア、その他のカスタムデータをアップロードして、パーソナライゼーションモデルを構築できます

CRM情報や顧客解約傾向スコアなどのオフラインデータは、パーソナライゼーションモデルを構築する際に非常に価値があります。 [!UICONTROL Automated Personalization] （AP）および[!UICONTROL Auto-Target]個のパーソナライゼーションアルゴリズムにデータを入力するには、いくつかの方法があります。

* [mbox パラメーター](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=ja){target=_blank}
* [プロファイルパラメーター](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=ja){target=_blank}
* [プロファイル更新のためのサーバー側 API](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=ja){target=_blank}

[!UICONTROL Automated Personalization]および[!UICONTROL Auto-Target]個のパーソナライゼーションアルゴリズムによって自動的に収集および使用されるデータについて詳しくは、[Automated Personalization Data Collection](/help/main/c-activities/t-automated-personalization/ap-data.md)を参照してください。

## トレーニングビデオ：アクティビティのタイプ

このビデオでは、[!DNL Target] で利用できるアクティビティのタイプについて説明しています。 [!UICONTROL Automated Personalization]は5:55から議論されています。

* [!DNL Adobe Target] に含まれるアクティビティタイプの説明
* 目標達成に適したアクティビティタイプの選択
* すべてのアクティビティタイプを対象とする、ガイド付き 3 ステップワークフローの説明

>[!VIDEO](https://video.tv.adobe.com/v/30014?captions=jpn)
