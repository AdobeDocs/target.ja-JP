---
keywords: mvt；多変量テスト；オファー；組み合わせ
description: Adobe [!DNL Target]の[!UICONTROL Visual Experience Composer] （VEC）を使用して、[!UICONTROL 多変量テスト &#x200B;] （MVT）に含めるオファーを作成する方法を説明します。
title: '[!UICONTROL 多変量テスト &#x200B;] （MVT）で組み合わせを作成するにはどうすればよいですか？'
feature: Multivariate Tests
exl-id: 8b5883de-de76-403d-ae20-c933a8665555
TQID: 'https://experienceleague.adobe.com/3vxuP07ZViE1etmmvBdYVHIOrtZqRZfL3nE5RMHo9rU'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: b934e7cf-c07f-5a64-924b-3c9da8413e3d
    internal-label: Multivariate Tests
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 0ae6991a6a86854bd64a632070a1fcbe544cc606
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 29%
---
# 組み合わせの作成 {#create-combinations}

>[!BEGINSHADEBOX]

**このページ：**&#x200B;では、**[!UICONTROL 多変量テスト]**&#x200B;の組み合わせを構成する画像とHTML オファーを作成する方法について説明します。

>[!ENDSHADEBOX]

**[!UICONTROL 多変量テスト]** （MVT）では、すべての場所に複数のオファーが含まれ、場所のオファーの組み合わせごとに1つのエクスペリエンスが提供されます。 [!DNL Adobe Target]の&#x200B;**[!UICONTROL Visual Experience Composer]** （VEC）を使用して、テストに含めるオファーを作成します。

VEC を使用したオファーの作成および編集について詳しくは、[Visual Experience Composer オプション](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)を参照してください。

>[!NOTE]
>
>ページ上のオブジェクトを選択する際に、**[!UICONTROL 選択範囲を拡大]**&#x200B;をクリックすると、最初に選択した要素に加えて親エレメントを選択できます。 親要素を選択しているときは、その要素のすべての子が自動的に選択されます。 選択の拡張は繰り返し実行できます。
>
>また、[DOM パス](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#dom-path)を使用して要素をナビゲートすることもできます。

## 画像オファー {#image-offers}

複数の画像オファーを特定の場所でテストして、どの画像が最も効果が高いかを判断します。

1. ページ上の画像をクリックし、**[!UICONTROL 画像オファーの変更]**&#x200B;を選択します。

   ![画像オファーメニューの変更](../assets/multivariate-1.png)

1. **[!UICONTROL 画像オファー]** ダイアログボックスで、テストに含めるすべての画像を選択し、**[!UICONTROL 追加]**&#x200B;をクリックします。

   ![画像オファーメニューの変更](../assets/multivariate-3.png)

各画像は、その場所での別々のエクスペリエンスになります。

## HTML オファー {#html-offers}

複数の HTML オファーを特定の場所でテストして、どのオファーが最も効果が高いかを判断します。

1. ページ上のHTML オファーをクリックし、**[!UICONTROL HTML オファーの変更]**&#x200B;をクリックします。

   ![HTML オファーメニューの変更](../assets/multivariate-2.png)

1. HTML オファーを選択し、「**[!UICONTROL オファーを作成]**」、「**[!UICONTROL HTML オファー]**」の順にクリックします。

   ![HTML オファーメニューの変更](../assets/multivariate-4.png)

1. オファーに名前を付け、HTML オファーのコードを入力または貼り付け、**[!UICONTROL 作成]**&#x200B;をクリックします。

   追加のHTML オファーを含める場合は、この手順を繰り返します。

1. 「**[!UICONTROL Save]**」をクリックします。

各 HTML オファーは、その場所での別々のエクスペリエンスになります。

含める組み合わせの数と、テストを開始する前にそれらを確認する方法に関する推奨事項については、[多変量テストのベストプラクティス &#x200B;](/help/main/c-activities/c-multivariate-testing/best-practices.md#create)を参照してください。
