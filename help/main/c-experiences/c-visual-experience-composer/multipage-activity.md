---
keywords: 複数ページ;遍歴のテスト;複数ページアクティビティ
description: Adobeで複数ページのアクティビティを作成する方法を説明します  [!DNL Target]  各ページに固有のデザインを使用して、複数ページにわたるストーリーを作成できます。
title: 複数ページアクティビティの作成方法
feature: Visual Experience Composer (VEC)
exl-id: d000cc73-4729-4ce0-ab30-756dd3ca8545
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 68%

---

# 複数ページアクティビティ

[!DNL Adobe Target] の複数ページアクティビティを使用すると、各ページに固有のデザインで、複数ページにわたるストーリーを作成できます。

例えば、特定の金額を超える買い物をした顧客に対して送料を無料にするオファーをテストできます。そのオファーをランディングページ、カテゴリページおよび特定の商品のページに表示しますが、ページのタイプに応じて異なる場所に異なるサイズで表示します。ホームページには目立つようにオファーを表示し、他の関連ページには小さく表示してオファーを強化できます。

また、複数ページアクティビティを使用して、デスクトップおよびノンレスポンシブモバイルサイト用の異なるレイアウトを定義できます。サイトに、[!DNL `www.mysite.com`] ではなく [!DNL m.mysite.com] のような個別のモバイルサイトがある場合は、[ 複数ページアクティビティ ](/help/main/c-experiences/c-visual-experience-composer/multipage-activity.md#concept_277E096063E14813AC5D8EDFA1D2ED48) を作成し、[!DNL m.mysite.com] を個別のページとして追加してから、モバイル編集を適用して、同じエクスペリエンスでデスクトップバージョンとモバイルバージョンに適切な変更を加える必要があります。 レスポンシブモバイルサイトでは、[モバイルエクスペリエンスの編集](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md#concept_8E45527C4ABC41D59AA3553BEDC76FA5)を使用します。

>[!NOTE]
>
>複数ページアクティビティは、同じオファーを複数のページで異なる外観で表示するアクティビティのためのものです。すべてのページでオファーを同じ外観で表示する場合は、[テンプレートテスト](/help/main/c-experiences/c-visual-experience-composer/temtest.md#task_2539D51A18044F82B0D9895636546781)のほうがより効率的です。

複数ページテストでは、各ページにテンプレートルールを指定できます。例えば、複数ページテストでカテゴリページにテンプレートルールを適用することで、ホームページおよびすべてのカテゴリページで複数ページテストを実行できます。[ 類似のページに同じエクスペリエンスを含める ](/help/main/c-experiences/c-visual-experience-composer/temtest.md#task_2539D51A18044F82B0D9895636546781) を参照してください。

テストにページを追加するには：

1. **[!UICONTROL Configure]** 歯車アイコンをクリックします。
1. **[!UICONTROL Add Additional Pages]** をクリックします。

   画面の左側に、ナビゲーションバーが表示されます。

   ![multipage_nav 画像 ](assets/multipage_nav.png)

1. このナビゲーションバーを使用してページを指定し、デフォルトページを設定します。

   「**[!UICONTROL Add Page]**」をクリックして、ページを追加します。

   縦並びの省略記号アイコンをクリックして、アクションメニューを表示します。

   ![multipage_menu 画像 ](assets/multipage_menu.png)

   このメニューを使用して、ページの名前変更、複数ページアクティビティからのリダイレクトテストの実行、ページの削除をおこないます。

1. Visual Experience Composer を使用して、各ページでのオファーの外観をデザインします。
