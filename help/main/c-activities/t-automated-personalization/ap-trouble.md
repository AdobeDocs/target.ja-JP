---
keywords: Automated Personalization;ap；トラブルシューティング；モデル；リフト
description: Adobe Targetで[!UICONTROL Automated Personalization] （AP）アクティビティを使用する際に直面する可能性のある潜在的な課題と、推奨される解決策について説明します。
title: '[!UICONTROL Automated Personalization] アクティビティのトラブルシューティング方法を教えてください。'
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Automated Personalization
exl-id: bc23e5db-5b65-44be-be45-c972287a64e7
TQID: 'https://experienceleague.adobe.com/1Qevyq-TiutN1dEZnfC1DDmUgXoHIxtBl-3RMPq-m-0'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: f0055dd2-93f3-4ac8-9abc-d69d4ed2d977
    internal-label: Automated personalization
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 44c6bdd4ab818226e76477782d7e4238b49d5cdc
workflow-type: tm+mt
source-wordcount: '771'
ht-degree: 12%
---
# [!UICONTROL Automated Personalization]のトラブルシューティング {#ap-troubleshooting}

>[!BEGINSHADEBOX]

**このページ：** **[!UICONTROL Automated Personalization]** アクティビティに関する一般的な問題の解決策を見つけます。

>[!ENDSHADEBOX]

活動は必ずしも期待通りに進むとは限らない。 次のリストを使用して、[!UICONTROL Automated Personalization] （AP）アクティビティの一般的な問題の原因を特定し、提案された解決策を適用します。

## モデルとリフト {#models-and-lift}

+++ 私の[!UICONTROL Automated Personalization] アクティビティは、モデルの構築に時間がかかりすぎています

アクティビティの設定に関する複数の選択肢が、モデルの構築に必要な時間に影響します。これには、**[!UICONTROL Automated Personalization]** アクティビティのエクスペリエンス数、サイトへのトラフィック、選択した成功指標などが含まれます。

**解決策：** アクティビティの設定を確認し、モデルの構築スピードを向上させる変更を行えるかどうかを確認します。

* 成功指標が RPV の場合は、コンバージョンに変更することをお勧めします。 コンバージョンアクティビティは、モデルの構築に要するトラフィックが比較的少なくて済みます。 成功指標をRPVからコンバージョンに変更しても、アクティビティデータが失われることはありません。
* セールスファネル上での成功指標とアクティビティのエクスペリエンスの位置が離れていないか確認します。 アクティビティのコンバージョン率が低いほど、モデルを構築するためのトラフィック要件が増加します。コンバージョン数は最小限に抑える必要があるからです。
* アクティビティから除外できるオファーやエクスペリエンスはありますか？ アクティビティ内のエクスペリエンスの数を減らすと、モデルの構築にかかる時間が短縮されます。
* このアクティビティがより成功するトラフィックの高いページはありますか？ アクティビティの場所でのトラフィックとコンバージョンが多ければ多いほど、より迅速なモデルが構築されます。

+++

+++ [!UICONTROL Automated Personalization]のアクティビティで上昇率が生成されませんでした

**[!UICONTROL Automated Personalization]** アクティビティで上昇率を生成するには、いくつかの要素が必要です。

* 訪問者に影響が生じるように、オファーに十分な差異を持たせる必要があります。
* 最適化目標に対する影響度が高い場所にオファーを配置する必要があります。
* 上昇率を検出するため、テストに十分なトラフィックと統計的「検出力」が必要です。
* パーソナライゼーションアルゴリズムが適切に機能する必要があります。

**解決策：**&#x200B;最初に、シンプルでパーソナライズされていないA/B テストを使用して、アクティビティ エクスペリエンスを構成するコンテンツと場所が、全体的な応答率に真に違いをもたらすことを確認することが、最善のアクションです。 サンプルサイズを事前に計算して、合理的な上昇率を確認するのに十分な電力があることを確認し、A/B テストを停止したり変更したりすることなく、固定期間にわたって実行します。 A/B テストの結果で、1つ以上のエクスペリエンスの統計的に有意な上昇率が示された場合、パーソナライズされたアクティビティが成功する可能性が高くなります。 Personalizationは、エクスペリエンスの全体的な応答率に違いがない場合でも機能します。 通常、この問題は、最適化の目標に大きな影響を与えないオファーや場所が、統計的有意性で検出されることに起因します。

+++

## アクティビティの設定とレポート {#setup-and-reporting}

+++ [!UICONTROL Automated Personalization]のアクティビティ URLに、間違ったページにオファーコンテンツが表示されています

**原因：** **[!UICONTROL Automated Personalization]**&#x200B;では、URLとテンプレートのテストルールが[!DNL Target] リクエスト エントリの制約（target-global-mboxなど）に追加され、1回だけ評価されます。 訪問者がアクティビティに適格になった後、リクエストレベルの[!DNL Target]のターゲティングルールは再評価されませんが、ターゲティングオーディエンスは場所ターゲティングルールに追加されます。

**解決策：**&#x200B;必要なテンプレートルールをアクティビティの入力オーディエンスとして追加します。 オーディエンスの評価は、リクエスト（呼び出し）ごとに実施されます。

+++

+++ コンバージョン指標に依存する指標は、コンバージョンに至りません

この動作は想定されています。

**[!UICONTROL Automated Personalization]** アクティビティでは、コンバージョン指標（最適化目標か後目標か）が変換されると、訪問者がエクスペリエンスから解放され、アクティビティが再開されます。

例えば、アクティビティには、コンバージョン指標（C1）と、C1に依存する追加指標（A1）があります。 訪問者が初めてアクティビティにエントリし、C1もA1も変換しなかった場合、成功指標の依存関係によりA1は変換されません。 訪問者がC1を変換してからA1を変換した場合、C1が変換されたときに訪問者が解放されるので、A1はまだ変換されません。

+++

+++ エクスペリエンス URLが期待どおりに機能しない

**解決策：**&#x200B;次のアクションを使用します。

* （ブラウザーのキャッシュが原因で）新しいタブにプレビューが表示されない場合は、2～3回更新してみてください。 リンクをコピーして、新しいブラウザーまたは新しいセッションで開くこともできます。
* コンテンツを変更した場合は、エクスペリエンス URLのリンクを再生成し、新しいリンクをチームメイトと共有します。

+++
