---
keywords: FAQ;よくある質問;Analytics for Target;A4T;上昇率;アドホック;Report Builder;信頼性
description: Analytics for  [!DNL Target]  （A4T）使用時の上昇率と信頼性に関する質問への回答を示します。 A4T では、 [!DNL Target]  アクティビティに Analytics のレポート機能を使用できます。
title: A4T での上昇率と信頼性に関する情報はどこで確認できますか？
feature: Analytics for Target (A4T)
exl-id: 42fd179b-944a-4a0a-b299-85ea4a7ea244
source-git-commit: aff96eca1380f4274dba0c1567f6e41d42f4b5ab
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 16%

---

# 上昇率と信頼性 - A4T FAQ

このトピックには、[!DNL Adobe Analytics] を [!DNL Adobe Target] （A4T）のレポートソースとして使用する場合の上昇率と信頼性に関するよくある質問に対する回答が含まれています。

## A4T でオフライン計算を実行することはできますか？ {#section_55B5B750E17D414CAECBEECE27B15D81}

+++回答
A4T に対してオフラインの計算を実行できますが、[!DNL Analytics] でのデータの書き出しに関する手順が必要です。 詳しくは、[A/Bn テストでの統計計算 ](/help/main/c-reports/statistical-methodology/statistical-calculations.md) を参照してください。

+++

## 上昇率はどのように計算されますか？ {#section_8CAE788EED5646C4B1D64A0D22070734}

+++回答
上昇率は、コントロールページの結果と成功したテストバリアントの間のパーセント差です。

+++

## 信頼性はどのように計算されますか？ {#section_97DB24D833E742988318CA65DA65DAD9}

+++回答
信頼水準は、t 検定から `p-value` が計算される確率（パーセントで表す）で、`1 - p-value` と等しくなります。 [A/Bn テストでの統計計算 ](/help/main/c-reports/statistical-methodology/statistical-calculations.md) を参照してください。

+++

## 計算指標で上昇率および信頼性が表示できないのはなぜですか？ {#lift-confidence}

+++回答
計算指標は、現在、リフト関数と信頼性関数ではサポートされていません。 Analytics は、指標を訪問者レベルではなく集計レベルで計算します。 特に、信頼性は、訪問者レベルの計算です。

計算されない（標準）イベントは、上昇率と信頼性でサポートされます。 それらは lift 関数の分子になります。分子は計算自体ではいけません。 分母は、標準化指標（インプレッション数、訪問回数、訪問者）です。 標準イベントの例としては、注文、売上高、アクティビティのコンバージョン、カスタムイベント 1 ～ 1000 などがあります。 会話率（注文数/訪問者）や RPV （売上高/訪問者）などの一般的な最適化指標は、上昇率と信頼性でサポートされます。

サポートされていない指標やユースケースの例を次に示します。

* 平均注文額（訪問者あたりの売上高/注文）。 分子が計算指標であるため、AOV はサポートされていません。 代わりに、AOV に影響を与える 2 つの指標（訪問者あたりの売上高とコンバージョン率）を考慮することをお勧めします。
* 標準イベントの合計である計算指標。 例えば、10 個の異なるリードフォームを 10 個の異なるイベントにトラッキングし、それらを追加して合計リード送信数を取得できます。 これらのイベントをトラッキングするには、Analytics で 1 つのリード送信イベントを実装し、eVarを使用してリードフォームのタイプを収集することをお勧めします。 この方法を使用すると、必要な変数が少なくなり、リフト関数と信頼性関数で単一のリード送信指標を使用できるようになります。

+++

## A4T は、信頼性の計算をどのように扱いますか？ {#section_66115EAF1BA34F7A8FCED7B08DA4F99C}

+++回答
[!DNL Adobe Analytics] は、すべての指標を非バイナリとして扱うので、通常の t 検定でのバイナリ指標の使用とは異なる方法で信頼性/p 値を計算します。 特に、A4T で使用される計算では、各ユーザーに対して連続的な指標結果（各ユーザーに対して 1 や 0 だけでなく）を持つことができるので、各エクスペリエンスの平方偏差（または関連して、標準偏差）を適切に計算する必要があります。 極端な注文は考慮されません。 また、信頼性計算では、複数のオファーに対してボンフェローニ補正が適用されません。

+++

## 上昇率および信頼性は Ad Hoc および Report Builder で機能しますか？そのままでは機能しない場合、自分自身で機能させることはできますか？ {#section_D8BB69AE700B4C5CB5FD28DB51F9A4E9}

+++回答
上昇率と信頼性はアドホックまたはReport Builderでは機能せず、連続変数に対して自分で計算することはできません。 バイナリ指標を手動で計算することは可能です。
+++
