---
keywords: 除外
description: で除外を作成する方法を説明します [!DNL Target Recommendations] 製品やコンテンツが訪問者に推薦されるのを防ぐ。
title: で除外を使用する方法 [!UICONTROL Recommendations] 活動？
feature: Recommendations
hide: true
hidefromtoc: true
source-git-commit: b6eaf89ef71ea3448584dcdadc926c45dba77504
workflow-type: tm+mt
source-wordcount: '630'
ht-degree: 26%

---

# 除外

での除外の作成 [!DNL Adobe Target Recommendations] 製品やコンテンツが訪問者に推薦されるのを防ぐ。 除外とは、訪問者に推奨すべきでない製品またはコンテンツのサブセットです。

除外は、アカウント全体で利用できます。 コレクションとは異なり、コレクションの作成時にエクスペリエンスごとに特定のコレクションを指定します。 [!UICONTROL Recommendations] アクティビティ、除外は、アカウント全体のすべてのアクティビティに適用されます。 アクティビティの作成時に除外グループを割り当てるオプションはありません。

除外を使用する時間の例を次に示します。

* 生産中止品です。
* 現在、秋冬カタログは、オンラインで公開する唯一のカタログとなっています。 サマーカタログの商品は購入できなくなりました。
* 多くのページや画面で推奨するのに適さないアイテム（アダルトグッズ、NC-17 動画など）。
* メタデータフィールドが不完全な製品（サムネール、価格、その他の重要なメタデータが欠落）
* 推奨されるべきではない製品（SKU がシステム内に存在しているかもしれませんが、購入可能な項目ではありません。 または、QA チームが実際に何かを注文せずに購入をシミュレートするための偽の SKU である場合もあります（その他）。

>[!IMPORTANT]
>
>除外ルールはすべてのユーザーにグローバルに適用されます [環境](/help/main/administrating-target/environments.md).
>
>静的および動的な除外ルールは、マーケティングに役立つ便利な機能です。詳細な情報、例、および使用例については、[動的および静的インクルージョンルールの使用](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F)を参照してください。

## 除外の作成

1. クリック **[!UICONTROL Recommendations]** > **[!UICONTROL Exclusions]** 既存の除外のリストを表示します。

   ![exclusions_list 画像](assets/exclusions-list.png)

   で除外ごとに報告される「項目数」 [!UICONTROL Exclusions] リスト表示は、設定されたデフォルトのRecommendations内で、その除外のルールに一致する製品の数です [ホスト グループ](/help/main/administrating-target/hosts.md) （環境）。 参照： [プランと実装 [!DNL Recommendations]](https://experienceleague.adobe.com/en/docs/target-dev/developer/recommendations){target=_blank} が含まれる *Adobe Target開発者ガイド* デフォルトホストグループの変更方法については、を参照してください。

1. （条件付き）をクリック [!UICONTROL Filter] アイコンをクリックしてから、目的のを選択します [0.9511122](/help/main/administrating-target/environments.md) から **[!UICONTROL Environment]** 除外を作成（または更新）するときにドロップダウンリストを使用して、その環境での除外の内容をプレビューできます。 デフォルトでは、デフォルトのホストグループの結果が表示されます。

   ![除外を作成](/help/main/c-recommendations/c-products/assets/choose-environment.png)

1. **[!UICONTROL Create Exclusion]** をクリックします。

   ![除外を作成ダイアログボックス](/help/main/c-recommendations/c-products/assets/create-exclusion.png)

1. 除外を入力 **[!UICONTROL Name]** オプションで説明を入力します。

1. ルールビルダーを使用して除外を作成します。

   ルールリストでパラメーターを選択して、オペレーターを選択してから、1 つ以上の値を入力して製品を特定します。複数の値はコンマで区切ります。

1. **[!UICONTROL Create]** をクリックします。

## 詳細検索を使用した除外の作成

以下を使用して除外を作成することもできます。 [!UICONTROL Advanced Search] 日 [カタログ検索](/help/main/c-recommendations/c-products/catalog-search.md#save-as) ページ （ [!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]）に設定します。

![ダイアログとして保存](/help/main/c-recommendations/c-products/assets/save-as.png)

例えば、「id > 次を含む」を使用して検索を作成した後、 [!UICONTROL Save As] > [!UICONTROL Exclusion].

>[!IMPORTANT]
>
>この [!UICONTROL Advanced Search] 機能では大文字と小文字が区別されません。ただし、配信時に返される製品は大文字と小文字を区別した検索に基づいています。 この違いが混乱を招くこともあります。詳細検索機能による結果を基にして除外を作成する際は、大文字と小文字の区別を考慮してください。例えば、最初に「Holiday」と検索すると、「Holiday」または「holiday」を含む結果が返されます。その後、「holiday」を含む商品を除外することを目的とした除外を作成すると、「holiday」を含む商品のみが除外されます。「Holiday」を含む商品は除外されません。

## 除外の編集、コピー、削除

「」をクリックします **省略記号** アイコン リスト内の目的の除外の横にある、適切なアイコン（編集、コピー、削除）をクリックします。

![オプション：編集、コピー、削除](/help/main/c-recommendations/c-products/assets/edit-copy-delete.png)

既存の除外をコピーして重複する除外を作成し、それを変更できます。 このオプションを使用すると、同様の除外を少ない労力で作成できます。

除外は、アカウント全体で利用できることに注意してください。 除外を削除する前に、次の点に注意してください。 削除した除外は復元できません。

## トレーニングビデオ：Recommendationsでコレクションと除外を作成（7:05） ![チュートリアルバッジ](/help/main/assets/tutorial.png)

このビデオには、次の情報が含まれています。

* コレクションの作成
* 除外の作成

>[!VIDEO](https://video.tv.adobe.com/v/27689)