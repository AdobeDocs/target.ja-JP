---
keywords: exclusions
description: 除外を作成 [!DNL Adobe Target Recommendations] して、訪問者に商品やコンテンツがレコメンデーションされないようにします。
title: Adobe Target での除外
feature: entities
uuid: 1970846e-37d8-4b69-a0d9-ff45bb840bef
translation-type: tm+mt
source-git-commit: af46453734f4ce185e0cd4282793a800fada8a98
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 55%

---


# 除外{#exclusions}

で除外を作成して、訪問者 [!DNL Adobe Target Recommendations] に商品やコンテンツをレコメンデーションしないようにします。

除外は、訪問者にレコメンデーションしない商品またはコンテンツのサブセットです。 例えば、除外を使用して、廃止されたレコメンデーションや本来の機密性の高いレコメンデーションに商品やコンテンツが表示されないようにできます（コンテンツのレーティングに基づくすべてに適していないレーティングの映画など）。

除外はアカウント全体で使用できます。

>[!IMPORTANT]
>
>静的および動的な除外ルールは、マーケティングに役立つ便利な機能です。詳細な情報、例、および使用例については、[動的および静的インクルージョンルールの使用](../../c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F)を参照してください。

## 除外の作成

1. **[!UICONTROL Recommendations]**／**[!UICONTROL 除外]**&#x200B;をクリックして、既存の除外のリストを表示します。

   ![](assets/exclusions_list.png)

   [!UICONTROL 除外]リストビューで各除外について報告される「項目数」は、現在設定されているデフォルトの Recommendations [ホストグループ](/help/administrating-target/hosts.md)（環境）内でその除外のルールに一致する製品の数です。デフォルトのホストグループを変更するには、[設定](../../c-recommendations/plan-implement.md#concept_C1E1E2351413468692D6C21145EF0B84)を参照してください。

1. 「**[!UICONTROL 除外を作成]**」をクリックします。

1. （条件付き）除外の作成（または更新）時に、環境を&#x200B;**[!UICONTROL 環境]**&#x200B;フィルターから選択して、その環境の除外のコンテンツをプレビューします。デフォルトでは、デフォルトのホストグループの結果が表示されます。

   ![除外を作成](/help/c-recommendations/c-products/assets/CreateExclusion.png)

1. 除外の&#x200B;**[!UICONTROL 名前]**&#x200B;を入力し、オプションで説明を入力します。

1. ルールビルダーを使用して除外を作成します。

   ルールリストでパラメーターを選択して、オペレーターを選択してから、1 つ以上の値を入力して製品を特定します。複数の値はコンマで区切ります。

1. 「**[!UICONTROL 保存]**」をクリックします。

## 詳細検索を使用した除外の作成

You can also create exclusions using [!UICONTROL Advanced Search] on the [Catalog Search](/help/c-recommendations/c-products/catalog-search.md#save-as) page ( [!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]).

![名前を付けて保存ダイアログ](/help/c-recommendations/c-products/assets/save-as.png)

「ID／次を含む」などを使用した検索を作成したら、[!UICONTROL 名前を付けて保存]／[!UICONTROL 除外]をクリックします。

>[!IMPORTANT]
>
>The [!UICONTROL Advanced Search] functionality is case-insensitive; however, products returned at the time of delivery are based on case-sensitive search. この違いが混乱を招くこともあります。詳細検索機能による結果を基にして除外を作成する際は、大文字と小文字の区別を考慮してください。例えば、最初に「Holiday」と検索すると、「Holiday」または「holiday」を含む結果が返されます。その後、「holiday」を含む商品を除外することを目的とした除外を作成すると、「holiday」を含む商品のみが除外されます。「Holiday」を含む商品は除外されません。

## 除外の編集、コピー、削除

リスト内の目的の除外の上にマウスポインターを置き、次のうち該当するアイコンをクリックします。編集、コピー、または削除を行います。

![除外にカーソルを合わせたときのアイコン](/help/c-recommendations/c-products/assets/hover-exclusions.png)

既存の除外をコピーして、重複の除外を作成し、変更できます。 これにより、少ない労力で同様の除外を作成できます。

除外はアカウント全体で使用できることに注意してください。 除外を削除する前に、この点を考慮してください。 削除した除外は復元できません。

## Training video: Create collections and exclusions in Recommendations (7:05) ![Tutorial badge](/help/assets/tutorial.png)

このビデオには、次の情報が含まれています。

* コレクションの作成
* 除外の作成

>[!VIDEO](https://video.tv.adobe.com/v/27689)