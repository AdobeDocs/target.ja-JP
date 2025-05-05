---
keywords: 除外
description: Adobe [!DNL Target] Recommendationsで除外を作成して、商品やコンテンツが訪問者にレコメンデーションされないようにする方法を説明します。
title: Recommendations アクティビティで除外を使用する方法
feature: Recommendations
exl-id: e41487c7-6d47-4958-8e4b-616a2ad56b3c
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '598'
ht-degree: 28%

---

# 除外

[!DNL Adobe Target Recommendations] で除外を作成して、製品やコンテンツが訪問者に推奨されないようにします。 除外とは、訪問者に推奨すべきでない製品またはコンテンツのサブセットです。

除外は、アカウント全体で利用できます。 [!UICONTROL Recommendations] アクティビティを作成する際にエクスペリエンスごとに特定のコレクションを指定するコレクションとは異なり、除外はアカウント全体のすべてのアクティビティに適用されます。 アクティビティの作成時に除外グループを割り当てるオプションはありません。

除外を使用する時間の例を次に示します。

* 生産中止品
* オンラインで公開すべきカタログは、秋冬カタログのみです。 サマーカタログの商品は購入できなくなりました。
* ほとんどのページ/画面で推奨するのに適さないアイテム（アダルトプロダクト、NC-17 動画など）
* メタデータフィールドが不完全な製品（サムネール、価格、その他の重要なメタデータが欠落）
* 推奨すべきでない製品（システム内に何らかの SKU が存在しても、購入可能な項目ではない場合や、QA チームが実際に何かを注文せずに購入をシミュレートするための偽 SKU である場合など）

>[!IMPORTANT]
>
>除外ルールはすべての環境にグローバルに適用されます。
>
>静的および動的な除外ルールは、マーケティングに役立つ便利な機能です。詳細な情報、例、および使用例については、[動的および静的インクルージョンルールの使用](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F)を参照してください。

## 除外の作成

1. **[!UICONTROL Recommendations]** > **[!UICONTROL Exclusions]** をクリックして、既存の除外のリストを表示します。

   ![exclusions_list image](assets/exclusions_list.png)

   [!UICONTROL Exclusions] のリスト表示の各除外について報告された「Number of Items」は、設定されたデフォルトのRecommendations [host group](/help/main/administrating-target/hosts.md) （environment）内でその除外のルールに一致する商品の数です。 デフォルトのホストグループを変更するには、[ 設定 ](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html?lang=ja){target=_blank} を参照してください。

1. **[!UICONTROL Create Exclusion]** をクリックします。

1. （条件付き）除外を作成（または更新）する際に、**[!UICONTROL Environment]** フィルターから環境を選択して、その環境の除外のコンテンツをプレビューします。 デフォルトでは、デフォルトのホストグループの結果が表示されます。

   ![除外を作成](/help/main/c-recommendations/c-products/assets/CreateExclusion.png)

1. 除外 **[!UICONTROL Name]** を入力し、オプションで説明を入力します。

1. ルールビルダーを使用して除外を作成します。

   ルールリストでパラメーターを選択して、オペレーターを選択してから、1 つ以上の値を入力して製品を特定します。複数の値はコンマで区切ります。

1. **[!UICONTROL Save]** をクリックします。

## 詳細検索を使用した除外の作成

[ カタログ検索 ](/help/main/c-recommendations/c-products/catalog-search.md#save-as) ページ（[!UICONTROL Recommendations]/[!UICONTROL Catalog Search]/[!UICONTROL Advanced Search]）の [!UICONTROL Advanced Search] を使用して除外を作成することもできます。

![ 名前を付けて保存ダイアログ ](/help/main/c-recommendations/c-products/assets/save-as.png)

例えば、「id > 次を含む」を使用して検索を作成したら、[!UICONTROL Save As] > [!UICONTROL Exclusion] をクリックできます。

>[!IMPORTANT]
>
>[!UICONTROL Advanced Search] の機能では、大文字と小文字が区別されません。ただし、配信時に返される製品は、大文字と小文字を区別した検索に基づいています。 この違いが混乱を招くこともあります。詳細検索機能による結果を基にして除外を作成する際は、大文字と小文字の区別を考慮してください。例えば、最初に「Holiday」と検索すると、「Holiday」または「holiday」を含む結果が返されます。その後、「holiday」を含む商品を除外することを目的とした除外を作成すると、「holiday」を含む商品のみが除外されます。「Holiday」を含む商品は除外されません。

## 除外の編集、コピー、削除

リスト内の目的の除外にポインタを合わせ、適切なアイコン（編集、コピー、削除）をクリックします。

![ 除外に対するホバーアイコン ](/help/main/c-recommendations/c-products/assets/hover-exclusions.png)

既存の除外をコピーして重複する除外を作成し、それを変更できます。 これにより、少ない労力で同様の除外を作成できます。

除外は、アカウント全体で利用できることに注意してください。 除外を削除する前に、このことを考慮してください。 削除した除外は復元できません。

## トレーニングビデオ：Recommendationsでコレクションと除外を作成（7:05） ![ チュートリアルバッジ ](/help/main/assets/tutorial.png)

このビデオには、次の情報が含まれています。

* コレクションの作成
* 除外の作成

>[!VIDEO](https://video.tv.adobe.com/v/27689)
