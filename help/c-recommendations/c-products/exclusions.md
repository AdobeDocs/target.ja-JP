---
description: 除外リストを作成すると、品目がレコメンデーションされないようにできます。
keywords: 除外
seo-description: Adobe Targetで除外リストを作成して、品目のレコメンデーションを防ぎます。
seo-title: Adobe Targetの除外
solution: 'Target '
title: 除外
topic: Premium
uuid: 1970846e-37d8-4b69-a0d9-ff45bb840bef
translation-type: tm+mt
source-git-commit: 12953606c44d4545e5f9a65e6473fc172bb9ca73

---


# 除外{#exclusions}

除外リストを作成すると、品目がレコメンデーションされないようにできます。

>[!IMPORTANT]
>
>静的および動的な除外ルールは、マーケティングに役立つ便利な機能です。詳細な情報、例、および使用例については、[動的および静的インクルージョンルールの使用](../../c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F)を参照してください。

**除外を作成するには:**

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

## アドバンス検索を使用した除外の作成

カタログ検索ページの詳細検索（[!UICONTROL レコメンデーション]／[!UICONTROL カタログ検索]／[!UICONTROL 詳細検索]）を使用して、除外を作成することもできます。

[名前を付けて保存](/help/c-recommendations/c-products/assets/save-as.png)

「ID／次を含む」などを使用した検索を作成したら、[!UICONTROL 名前を付けて保存]／[!UICONTROL 除外]をクリックします。詳しくは [、カタログ検索](/help/c-recommendations/c-products/catalog-search.md)を参照してください。

>[!IMPORTANT]
>
>詳細検索機能では大文字と小文字は区別されません。ただし、配信時に返される商品は、大文字と小文字が区別される検索に基づきます。この違いが混乱を招くこともあります。詳細検索機能による結果を基にして除外を作成する際は、大文字と小文字の区別を考慮してください。例えば、最初に「Holiday」と検索すると、「Holiday」または「holiday」を含む結果が返されます。その後、「holiday」を含む商品を除外することを目的とした除外を作成すると、「holiday」を含む商品のみが除外されます。「Holiday」を含む商品は除外されません。

## トレーニングビデオ:Recommendationsでのコレクションと除外の作成（7:05）

このビデオには、次の情報が含まれています。

* コレクションの作成
* 除外の作成

>[!VIDEO](https://video.tv.adobe.com/v/27689?captions=jpn)