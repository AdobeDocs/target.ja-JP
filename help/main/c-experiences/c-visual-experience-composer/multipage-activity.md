---
keywords: 複数ページ;遍歴のテスト;複数ページアクティビティ
description: Adobeで複数ページのアクティビティを作成する方法を説明します。こ  [!DNL Target]  により、各ページに固有のデザインを使用して、複数ページにわたるストーリーを作成できます。
title: 複数ページアクティビティの作成方法
feature: Visual Experience Composer (VEC)
exl-id: d000cc73-4729-4ce0-ab30-756dd3ca8545
source-git-commit: f968ec45f015fa0b195007f5790b9efb743c8b65
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 54%

---

# 複数ページアクティビティ

[!DNL Adobe Target] の複数ページアクティビティを使用すると、各ページに固有のデザインで、複数ページにわたるストーリーを作成できます。

例えば、特定の金額を超える買い物をした顧客に対して送料を無料にするオファーをテストできます。そのオファーをランディングページ、カテゴリページおよび特定の商品のページに表示しますが、ページのタイプに応じて異なる場所に異なるサイズで表示します。ホームページには目立つようにオファーを表示し、他の関連ページには小さく表示してオファーを強化できます。

また、複数ページアクティビティを使用して、デスクトップおよびノンレスポンシブモバイルサイト用の異なるレイアウトを定義できます。サイトに、[!DNL m.mysite.com] ではなく [!DNL `www.mysite.com`] のような個別のモバイルサイトがある場合は、[ 複数ページアクティビティ ](/help/main/c-experiences/c-visual-experience-composer/multipage-activity.md#concept_277E096063E14813AC5D8EDFA1D2ED48) を作成し、[!DNL m.mysite.com] を個別のページとして追加してから、モバイル編集を適用して、同じエクスペリエンスでデスクトップバージョンとモバイルバージョンに適切な変更を加える必要があります。 レスポンシブモバイルサイトでは、[モバイルエクスペリエンスの編集](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md#concept_8E45527C4ABC41D59AA3553BEDC76FA5)を使用します。

>[!NOTE]
>
>複数ページアクティビティは、同じオファーを複数のページで異なる外観で表示するアクティビティのためのものです。すべてのページでオファーを同じ外観で表示する場合は、[テンプレートテスト](/help/main/c-experiences/c-visual-experience-composer/temtest.md#task_2539D51A18044F82B0D9895636546781)のほうがより効率的です。

複数ページテストでは、各ページにテンプレートルールを指定できます。例えば、複数ページテストでカテゴリページにテンプレートルールを適用することで、ホームページおよびすべてのカテゴリページで複数ページテストを実行できます。[ 類似のページに同じエクスペリエンスを含める ](/help/main/c-experiences/c-visual-experience-composer/temtest.md#task_2539D51A18044F82B0D9895636546781) を参照してください。

テストにページを追加するには：

1. **[!UICONTROL Configure]** アイコン（![ 設定アイコン ](/help/main/assets/icons/Setting.svg)）をクリックします。
1. **[!UICONTROL Add Additional Pages]** をクリックします。

   画面の左側に [!UICONTROL Pages] ペインが表示されます。

1. ページを指定し、デフォルトのページを設定します。

   「**[!UICONTROL Add Page]**」（![ 追加アイコン ](/help/main/assets/icons/Add.svg)）をクリックしてページを追加し、ページ名と URL を指定して「**[!UICONTROL Save]**」をクリックします。

1. [!UICONTROL Visual Experience Composer] を使用して、各ページでのオファーの外観をデザインします。
