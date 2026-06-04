---
keywords: 除外
description: ' [!DNL Target Recommendations] で除外を作成して、製品またはコンテンツが訪問者に推奨されないようにする方法を説明します。'
title: '[!UICONTROL Recommendations]のアクティビティで除外を使用するにはどうすればよいですか？'
feature: Recommendations
exl-id: e41487c7-6d47-4958-8e4b-616a2ad56b3c
TQID: https://experienceleague.adobe.com/6-PWkqq5eXAwyLcGGbSqSZmFdJa85yU3x7FPNEt8-2o
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 16fb7a1902ea76cab56a93fa141a32a3c6bc4467
workflow-type: tm+mt
source-wordcount: 527
ht-degree: 13%

---

# 除外

[!DNL Adobe Target Recommendations]に除外を作成して、製品またはコンテンツが訪問者に推奨されないようにします。 除外とは、訪問者に推奨すべきではない製品やコンテンツのサブセットのことです。

除外は、アカウント全体で使用できます。 [!UICONTROL Recommendations] アクティビティを作成する際に、エクスペリエンスごとに特定のコレクションを指定するコレクションとは異なり、除外はアカウントのすべてのアクティビティに適用されます。 アクティビティの作成中に除外グループを割り当てるオプションはありません。

除外の使用例には、次のようなものがあります。

* 廃止された製品。
* 秋と冬のカタログは、オンラインで表示する必要がある唯一のカタログです。 夏のカタログの商品は購入できなくなりました。
* ほとんどのページやスクリーン（アダルト製品、NC-17映画など）で推奨するのが不適切な可能性があるアイテム。
* 不完全なメタデータフィールド（サムネール、価格、その他の重要なメタデータが含まれていない）を持つ製品。
* 推奨すべきでない商品（SKUがシステム内に存在し、購入可能な商品ではない可能性がある）。 あるいは、実際に何かを注文することなく購入をシミュレートすることは、QA チームにとって偽のSKUかもしれません）。

>[!IMPORTANT]
>
>除外ルールは、すべての[環境](/help/main/administrating-target/environments.md)にグローバルに適用されます。
>
>静的および動的な除外ルールは、マーケティングに役立つ便利な機能です。 詳細な情報、例、および使用例については、[動的および静的インクルージョンルールの使用](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F)を参照してください。

## 除外の作成

1. **[!UICONTROL Recommendations]** > **[!UICONTROL Exclusions]**&#x200B;をクリックして、既存の除外のリストを表示します。

   [!UICONTROL Exclusions] リストビューで各除外について報告された「項目数」は、設定されたデフォルトのRecommendations [&#x200B; ホストグループ &#x200B;](/help/main/administrating-target/hosts.md) （環境）内の、その除外のルールに一致する製品の数です。 デフォルトのホストグループを変更する方法について詳しくは、*Adobe Target開発者ガイド*&#x200B;の[計画と実装 [!DNL Recommendations]](https://experienceleague.adobe.com/en/docs/target-dev/developer/recommendations){target=_blank}を参照してください。

1. （条件付き）除外を作成（または更新）する際に、**[!UICONTROL フィルターを表示]** アイコン （![&#x200B; フィルターを表示アイコン &#x200B;](/help/main/assets/icons/Filter.svg)）をクリックし、**[!UICONTROL 環境]** ドロップダウンリストから目的の[環境](/help/main/administrating-target/environments.md)を選択して、その環境の除外の内容をプレビューします。 デフォルトでは、デフォルトのホストグループの結果が表示されます。

1. 「**[!UICONTROL 除外を作成]**」をクリックします。

1. 除外&#x200B;**[!UICONTROL 名前]**&#x200B;を入力し、オプションの説明を入力します。

1. ルールビルダーを使用して除外を作成します。

   [!UICONTROL &#x200B; ルール &#x200B;] リストでパラメーターを選択し、演算子を選択してから、1つ以上の値を入力して製品を識別します。 複数の値はコンマで区切ります。

1. 「**[!UICONTROL 作成]**」をクリックします。

<!--
## Create an exclusion using Advanced Search

You can also create exclusions using [!UICONTROL Advanced Search] on the [Catalog Search](/help/main/c-recommendations/c-products/catalog-search.md#save-as) page ( [!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]). 

![Save as dialog](/help/main/c-recommendations/c-products/assets/save-as.png)

After creating a search using "id > contains," for example, you can then click [!UICONTROL Save As] > [!UICONTROL Exclusion].

>[!IMPORTANT]
>
>The [!UICONTROL Advanced Search] functionality is case-insensitive; however, products returned at the time of delivery are based on case-sensitive search. This mismatch might lead to confusion. Ensure that you consider case-sensitivity when you create exclusions based on results using the Advanced Search functionality. For example, if you perform a search for "Holiday," that initial search lists results containing "Holiday" and "holiday." If you then create an exclusion with the intent to exclude products containing "holiday," only products containing "holiday" are excluded. Products containing "Holiday" are not excluded.
-->

## 除外の編集、コピー、削除

リスト内の目的の除外の横にあるその他のアクション アイコン（![その他のアクション アイコン &#x200B;](/help/main/assets/icons/MoreSmallList.svg)）をクリックし、適切なアイコン（[!UICONTROL 編集]、[!UICONTROL &#x200B; コピー]、または[!UICONTROL 削除]）をクリックします。

既存の除外をコピーして重複した除外を作成し、変更することができます。 このオプションを使用すると、より少ない労力で同様の除外を作成できます。

除外は、アカウント全体で使用できます。 除外を削除する前に、この注意事項を考慮してください。 削除された除外は復元できません。

## トレーニングビデオ：レコメンデーションでコレクションと除外を作成する（7:05） ![&#x200B; チュートリアルバッジ &#x200B;](/help/main/assets/tutorial.png)

このビデオには、次の情報が含まれています。

* コレクションの作成
* 除外の作成

>[!VIDEO](https://video.tv.adobe.com/v/27689)
