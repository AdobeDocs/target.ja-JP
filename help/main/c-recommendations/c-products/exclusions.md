---
keywords: 除外
description: Adobeで除外を作成する方法を説明します [!DNL Target] Recommendationsを使用して、訪問者に商品やコンテンツがレコメンデーションされるのを防ぎます。
title: Recommendations Activities での除外の使用方法を教えてください。
feature: Recommendations
exl-id: e41487c7-6d47-4958-8e4b-616a2ad56b3c
source-git-commit: 1383088bb2f6be0432e6f140400d8723048c8530
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 44%

---

# 除外

での除外の作成 [!DNL Adobe Target Recommendations] 訪問者に商品やコンテンツがレコメンデーションされるのを防ぐ。 除外は、訪問者にレコメンデーションすべきでない、製品またはコンテンツのサブセットです。

除外は、アカウント全体で使用できます。 コレクションとは異なり、コレクションでは、作成時に各エクスペリエンスに特定のコレクションを指定します [!UICONTROL Recommendations] アクティビティ、除外は、アカウント全体のすべてのアクティビティに適用されます。 アクティビティの作成時に除外グループを割り当てるオプションはありません。

除外を使用する場合の例を次に示します。

* 廃止された製品
* 秋/冬のカタログは、オンラインで表示する必要がある唯一のカタログになりました。 夏のカタログの品目は、購入できなくなりました。
* ほとんどのページや画面でレコメンデーションに適していない可能性のある品目（アダルト商品、NC-17 映画など）
* 不完全なメタデータフィールドを持つ製品（サムネール、価格、その他の重要なメタデータが欠落）
* レコメンデーションすべきでない製品（SKU がシステムに存在しても購入可能な品目ではない場合や、実際に何かを注文せずに購入をシミュレートする QA チームの偽の SKU である場合など）

>[!IMPORTANT]
>
>除外ルールは、すべての環境にグローバルに適用されます。
>
>静的および動的な除外ルールは、マーケティングに役立つ便利な機能です。詳細な情報、例、および使用例については、[動的および静的インクルージョンルールの使用](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F)を参照してください。

## 除外の作成

1. **[!UICONTROL Recommendations]**／**[!UICONTROL 除外]**&#x200B;をクリックして、既存の除外のリストを表示します。

   ![exclusions_list 画像](assets/exclusions_list.png)

   [!UICONTROL 除外]リストビューで各除外について報告される「項目数」は、現在設定されているデフォルトの Recommendations [ホストグループ](/help/main/administrating-target/hosts.md)（環境）内でその除外のルールに一致する製品の数です。デフォルトのホストグループを変更するには、[設定](https://experienceleague.corp.adobe.com/docs/target-dev/developer/recommendations.html?lang=ja)を参照してください。{target=_blank}

1. 「**[!UICONTROL 除外を作成]**」をクリックします。

1. （条件付き）除外の作成（または更新）時に、環境を&#x200B;**[!UICONTROL 環境]**&#x200B;フィルターから選択して、その環境の除外のコンテンツをプレビューします。デフォルトでは、デフォルトのホストグループの結果が表示されます。

   ![除外を作成](/help/main/c-recommendations/c-products/assets/CreateExclusion.png)

1. 除外の&#x200B;**[!UICONTROL 名前]**&#x200B;を入力し、オプションで説明を入力します。

1. ルールビルダーを使用して除外を作成します。

   ルールリストでパラメーターを選択して、オペレーターを選択してから、1 つ以上の値を入力して製品を特定します。複数の値はコンマで区切ります。

1. 「**[!UICONTROL 保存]**」をクリックします。

## 詳細検索を使用した除外の作成

また、 [!UICONTROL 詳細検索] の [カタログ検索](/help/main/c-recommendations/c-products/catalog-search.md#save-as) ページ ( [!UICONTROL Recommendations] > [!UICONTROL カタログ検索] > [!UICONTROL 詳細検索]) をクリックします。

![名前を付けて保存ダイアログ](/help/main/c-recommendations/c-products/assets/save-as.png)

「ID／次を含む」などを使用した検索を作成したら、[!UICONTROL 名前を付けて保存]／[!UICONTROL 除外]をクリックします。

>[!IMPORTANT]
>
>この [!UICONTROL 詳細検索] 機能では大文字と小文字が区別されません。ただし、配信時に返される製品は、大文字と小文字を区別した検索に基づいています。 この違いが混乱を招くこともあります。詳細検索機能による結果を基にして除外を作成する際は、大文字と小文字の区別を考慮してください。例えば、最初に「Holiday」と検索すると、「Holiday」または「holiday」を含む結果が返されます。その後、「holiday」を含む商品を除外することを目的とした除外を作成すると、「holiday」を含む商品のみが除外されます。「Holiday」を含む商品は除外されません。

## 除外の編集、コピー、削除

リスト内の目的の除外の上にマウスポインターを置いて、次に適切なアイコンをクリックします。編集、コピー、削除を行います。

![除外のアイコンにマウスポインターを置く](/help/main/c-recommendations/c-products/assets/hover-exclusions.png)

既存の除外をコピーして、重複する除外を作成し、それを変更できます。 これにより、手間をかけずに同様の除外を作成できます。

除外は、アカウント全体で使用できることに注意してください。 除外を削除する前に、必ずこの点を考慮してください。 削除した除外は復元できません。

## トレーニングビデオ：Recommendationsでのコレクションと除外の作成(7:05) ![チュートリアルバッジ](/help/main/assets/tutorial.png)

このビデオには、次の情報が含まれています。

* コレクションの作成
* 除外の作成

>[!VIDEO](https://video.tv.adobe.com/v/27689)
