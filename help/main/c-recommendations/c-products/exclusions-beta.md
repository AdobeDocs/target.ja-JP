---
keywords: 除外
description: で除外を作成して、製品やコンテンツが訪問者  [!DNL Target Recommendations]  推奨されないようにする方法を説明します。
title: 除外を [!UICONTROL Recommendations] アクティビティで使用する方法
feature: Recommendations
hide: true
hidefromtoc: true
source-git-commit: 31cf23a52c331eabad0e5f6423eeeca84df87625
workflow-type: tm+mt
source-wordcount: '513'
ht-degree: 18%

---

# 除外

[!DNL Adobe Target Recommendations] で除外を作成して、製品やコンテンツが訪問者に推奨されないようにします。 除外とは、訪問者に推奨すべきでない製品またはコンテンツのサブセットです。

除外は、アカウント全体で利用できます。 [!UICONTROL Recommendations] アクティビティを作成する際にエクスペリエンスごとに特定のコレクションを指定するコレクションとは異なり、除外はアカウント全体のすべてのアクティビティに適用されます。 アクティビティの作成時に除外グループを割り当てるオプションはありません。

除外を使用する時間の例を次に示します。

* 生産中止品です。
* 現在、秋冬カタログは、オンラインで公開する唯一のカタログとなっています。 サマーカタログの商品は購入できなくなりました。
* 多くのページや画面で推奨するのに適さないアイテム（アダルトグッズ、NC-17 動画など）。
* メタデータフィールドが不完全な製品（サムネール、価格、その他の重要なメタデータが欠落）
* 推奨されるべきではない製品（SKU がシステム内に存在しているかもしれませんが、購入可能な項目ではありません。 または、QA チームが実際に何かを注文せずに購入をシミュレートするための偽の SKU である場合もあります（その他）。

>[!IMPORTANT]
>
>除外ルールはすべての [ 環境 ](/help/main/administrating-target/environments.md) にグローバルに適用されます。
>
>静的および動的な除外ルールは、マーケティングに役立つ便利な機能です。詳細な情報、例、および使用例については、[動的および静的インクルージョンルールの使用](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F)を参照してください。

## 除外の作成

1. **[!UICONTROL Recommendations]** > **[!UICONTROL Exclusions]** をクリックして、既存の除外のリストを表示します。

   ![exclusions_list image](assets/exclusions-list.png)

   [!UICONTROL Exclusions] のリスト表示の各除外について報告された「Number of Items」は、設定されたデフォルトのRecommendations [host group](/help/main/administrating-target/hosts.md) （environment）内でその除外のルールに一致する商品の数です。 デフォルトのホストグループを変更する方法については、*Adobe Target開発者ガイド* の [ 計画と実装  [!DNL Recommendations]](https://experienceleague.adobe.com/en/docs/target-dev/developer/recommendations){target=_blank} を参照してください。

1. [!UICONTROL Filter] （条件付き）除外アイコンをクリックし、除外の作成（または更新）時に目的の [ 環境 ](/help/main/administrating-target/environments.md) を **[!UICONTROL Environment]** ドロップダウンリストから選択して、その環境での除外のコンテンツをプレビューします。 デフォルトでは、デフォルトのホストグループの結果が表示されます。

   ![除外を作成](/help/main/c-recommendations/c-products/assets/choose-environment.png)

1. **[!UICONTROL Create Exclusion]** をクリックします。

   ![ 除外を作成ダイアログボックス ](/help/main/c-recommendations/c-products/assets/create-exclusion.png)

1. 除外 **[!UICONTROL Name]** を入力し、オプションで説明を入力します。

1. ルールビルダーを使用して除外を作成します。

   ルールリストでパラメーターを選択して、オペレーターを選択してから、1 つ以上の値を入力して製品を特定します。複数の値はコンマで区切ります。

1. **[!UICONTROL Create]** をクリックします。

<!-- ## Create an exclusion using Advanced Search

You can also create exclusions using [!UICONTROL Advanced Search] on the [Catalog Search](/help/main/c-recommendations/c-products/catalog-search.md#save-as) page ( [!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]). 

![Save as dialog](/help/main/c-recommendations/c-products/assets/save-as.png)

After creating a search using "id > contains," for example, you can then click [!UICONTROL Save As] > [!UICONTROL Exclusion].

>[!IMPORTANT]
>
>The [!UICONTROL Advanced Search] functionality is case-insensitive; however, products returned at the time of delivery are based on case-sensitive search. This mismatch might lead to confusion. Ensure that you consider case-sensitivity when you create exclusions based on results using the Advanced Search functionality. For example, if you perform a search for "Holiday," that initial search lists results containing "Holiday" and "holiday." If you then create an exclusion with the intent to exclude products containing "holiday," only products containing "holiday" are excluded. Products containing "Holiday" are not excluded. -->

## 除外の編集、コピー、削除

リスト内の目的の除外の横にある **省略記号** アイコンをクリックし、適切なアイコン（編集、コピー、削除）をクリックします。

![ オプション：編集、コピー、削除 ](/help/main/c-recommendations/c-products/assets/edit-copy-delete.png)

既存の除外をコピーして重複する除外を作成し、それを変更できます。 このオプションを使用すると、同様の除外を少ない労力で作成できます。

除外は、アカウント全体で利用できることに注意してください。 除外を削除する前に、次の点に注意してください。 削除した除外は復元できません。

## トレーニングビデオ：Recommendationsでコレクションと除外を作成（7:05） ![ チュートリアルバッジ ](/help/main/assets/tutorial.png)

このビデオには、次の情報が含まれています。

* コレクションの作成
* 除外の作成

>[!VIDEO](https://video.tv.adobe.com/v/27689)