---
keywords: 自動パーソナライゼーション；アプリ；オーディエンス；アンサンブル；ランダムフォレスト；マルチアームドバンディット；トンプソンサンプリング；マシンラーニング；機械学習
description: 高度な機械学習を使用して、各訪問者に対する様々なオファーのバリエーションを一致させる[!DNL Adobe Target]の[!UICONTROL Automated Personalization] （AP）アクティビティの使用方法について説明します。
title: '[!UICONTROL Automated Personalization] （AP）アクティビティとは何ですか？'
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Automated Personalization
exl-id: 3654dce4-0d6c-42a3-8be7-e081ec478075
TQID: 'https://experienceleague.adobe.com/BBtKgNRTlqNFFoAjr1LQkhHyZeAlXG2h8D7bsndh4kQ'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: fff07a91-d479-45f4-ae95-9762e79b1b7c
    internal-label: Shared audiences
  - id: f0055dd2-93f3-4ac8-9abc-d69d4ed2d977
    internal-label: Automated personalization
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c4147b6e-073b-4d3c-9ab1-d60f2f4434ef
    internal-label: Behavioral data
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
    internal-label: Machine learning
source-git-commit: ddd4fa83540294ee229b87f041bc2245ba9a3464
workflow-type: tm+mt
source-wordcount: '906'
ht-degree: 25%
---
# [!UICONTROL Automated Personalization]（AP） {#automated-personalization-overview}

>[!BEGINSHADEBOX]

**このページ：**&#x200B;では、**[!UICONTROL Automated Personalization]** アクティビティが各訪問者に対するオファーのバリエーションと一致する方法と、それを使用する際に考慮すべき点について説明します。

>[!ENDSHADEBOX]

>[!NOTE]
>
>**[!UICONTROL Automated Personalization]**&#x200B;は、[!DNL Target Premium] ソリューションの一部として利用できます。 この機能は、[!DNL Target Premium] ライセンスのない [!DNL Target Standard] では使用できません。 このライセンスで提供される高度な機能について詳しくは、[Target Premium](/help/main/c-intro/intro.md#premium) を参照してください。

**[!UICONTROL Automated Personalization]** （AP）のアクティビティは、[!DNL Adobe Target]でオファーまたはメッセージを組み合わせ、高度な機械学習を使用して、個々の顧客プロファイルに基づいて各訪問者に異なるオファーのバリエーションを一致させ、コンテンツをパーソナライズし、向上を促進します。

マーケターはサイトに1つのファイルを実装し、任意のコンテンツをポイントしてクリックし、**[!UICONTROL Visual Experience Composer]** （VEC）を使用して、その領域の追加のコンテンツオプションを視覚的に作成できます。 次に、アルゴリズムは、システムがその訪問者に関して保持しているあらゆる行動データにもとづいて、各訪問者に配信するコンテンツを自動的に決定します。

**[!UICONTROL Automated Personalization]**&#x200B;は訪問者の行動の変化に適応するので、終了日を設定せずに実行して、継続的なリフトとパーソナライズを提供できます。 このモードは「常時オン」と呼ばれることもあります。 マーケターは、リフトを認識する前にテストを実行して結果を分析し、勝者を配信する必要はありません。 **[!UICONTROL Automated Personalization]**&#x200B;は、テストの検出フェーズや、多様な訪問者をターゲットにする場合にも役立ちます。 **[!UICONTROL 自動ターゲット]**&#x200B;との違いについて詳しくは、[自動ターゲット ](/help/main/c-activities/auto-target/auto-target-to-optimize.md#section_BA4D83BE40F14A96BE7CBC7C7CF2A8FB)を参照してください。

次の用語は、**[!UICONTROL Automated Personalization]**&#x200B;について説明する際に役立ちます。

| 用語 | 定義 |
|---|---|
| マルチアームバンディット | マルチアームバンディット最適化アプローチでは、調査学習とその学習の活用のバランスを取ります。 |
| ランダムフォレスト | AI時代のデータ戦略。 データサイエンスの用語では、訪問者と訪問属性に基づいて多くの決定木を構築することで機能するアンサンブル分類または回帰方法です。 |
| トンプソンサンプリング | トンプソンサンプリングの目的は、全体的に最良の（パーソナライズされていない）エクスペリエンスを最小限の「コスト」で特定することです。 Thompson Samplingは、2つのエクスペリエンス間に統計的な違いがない場合でも、常に勝者を選びます。 詳しくは、[トンプソンサンプリング](https://en.wikipedia.org/wiki/Thompson_sampling)を参照してください。 |

## パーソナライゼーションモデルの仕組み {#how-ap-works}

**[!UICONTROL Automated Personalization]**&#x200B;は、ランダム フォレスト アルゴリズムを使用してパーソナライズします。 Random Forestは主要なマシンラーニングアプローチです。 データサイエンスの用語では、訪問者と訪問属性に基づいて多くの決定木を構築することで機能するアンサンブル分類または回帰方法です。 [!DNL Target] 内部では、ランダムフォレストを使用して、コンバージョンの可能性が最も高い（または訪問あたりの売上高が最も高い）と予想されるエクスペリエンスを特定の訪問者ごとに決定します。

たとえば、Chromeを利用し、ゴールドロイヤルティの会員で、火曜日にサイトにアクセスした訪問者は、エクスペリエンス Aでコンバージョンする可能性が高くなります。ニューヨークの訪問者は、エクスペリエンス Bでコンバージョンする可能性が高くなります。

[!DNL Target]のランダム フォレストについて詳しくは、[ ランダム フォレスト アルゴリズム ](/help/main/c-activities/t-automated-personalization/algo-random-forest.md)を参照してください。

| 縦横 | 動作の仕組み |
|---|---|
| **各訪問に対する最適化** | このアルゴリズムは、訪問者がコンバージョンに至る可能性（またはコンバージョンによる推定売上）を予測し、最適なエクスペリエンスを提供するのに役立ちます。 訪問者がコントロールグループに属していない場合、訪問者は既存のセッションの終了時に新しいエクスペリエンスの対象となります。 コントロールグループの訪問者は、初回訪問と同じエクスペリエンスを見ます。 エクスペリエンスは、視覚的な一貫性を維持するために、セッション内で変更されません。 |
| **訪問者行動の変化への適応** | マルチアームドバンディットは、アクティビティの全期間を通じて学習を継続し、以前に学習したトレンドの過度な悪用を防ぐために、常にわずかなトラフィックを費やします。 最新の訪問者行動データを使用して、24時間ごとに基本モデルを再構築します。 アルゴリズムが個々の訪問者の勝者エクスペリエンスを判断できない場合は、[ トンプソンサンプリング ](https://en.wikipedia.org/wiki/Thompson_sampling)を使用して見つかった全体的に最もパフォーマンスの高いエクスペリエンスを表示しますが、引き続きパーソナライズされた勝者を探します。 |
| **目標指標** | このモデルは、コンバージョンベースまたは収益ベースの単一の目標指標を継続的に最適化します（具体的には、**[!UICONTROL 訪問あたりの収益]**）。 |
| **データとオーディエンス** | [!DNL Target] では、訪問者に関する情報を自動的に収集して、パーソナライゼーションモデルを構築します。 **[!UICONTROL 自動ターゲット]**&#x200B;および&#x200B;**[!UICONTROL Automated Personalization]**&#x200B;で使用される属性について詳しくは、[Automated Personalization Data Collection](/help/main/c-activities/t-automated-personalization/ap-data.md)を参照してください。 [!DNL Target]は、[!DNL Adobe Experience Cloud]の共有オーディエンスをすべて自動的に使用するので、モデルにオーディエンスを追加するために特定の操作を行う必要はありません。 詳しくは、[Experience Cloud Audiences](/help/main/c-integrating-target-with-mac/mmp.md)を参照してください。 |
| **カスタムデータ** | マーケターは、CRM情報や顧客解約傾向スコアなどのオフラインデータやその他のカスタムデータをアップロードして、パーソナライゼーションモデルを構築することができます。 データは、[mbox パラメーター](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=ja){target=_blank}、[ プロファイルパラメーター](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=ja){target=_blank}、または[ サーバーサイド APIを使用して、プロファイルの更新](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=ja){target=_blank}に入力できます。 |

## トレーニングビデオ：アクティビティのタイプ {#training-video}

このビデオでは、[!DNL Target] で利用できるアクティビティのタイプについて説明しています。 **[!UICONTROL Automated Personalization]**&#x200B;については、5:55以降に説明します。

* [!DNL Adobe Target] に含まれるアクティビティタイプの説明
* 目標達成に適したアクティビティタイプの選択
* すべてのアクティビティタイプを対象とする、ガイド付き 3 ステップワークフローの説明

>[!VIDEO](https://video.tv.adobe.com/v/17386)
