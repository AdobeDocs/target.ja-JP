---
keywords: 複数ページ;遍歴のテスト;複数ページアクティビティ
description: Adobe [!DNL Target]で複数ページのアクティビティを作成する方法を説明します。複数ページにわたってストーリーを作成し、各ページに固有のデザインを作成できます。
title: マルチページアクティビティの作成方法
feature: Visual Experience Composer (VEC)
exl-id: d000cc73-4729-4ce0-ab30-756dd3ca8545
TQID: 'https://experienceleague.adobe.com/ZFqgbNp-sLF-ahG-uXKvWY0XPcxO0oZScGkpNX8hDHY'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c18d9e03-ac7d-4811-9c92-3e92ddc70ade
    internal-label: Mobile experience
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 13%
---
# 複数ページアクティビティ {#multipage-activity}

>[!BEGINSHADEBOX]

**このページ：**&#x200B;では、複数ページのアクティビティを使用して、各ページに固有のデザインを持つ複数ページにわたるストーリーを作成する方法を説明します。

>[!ENDSHADEBOX]

[!DNL Adobe Target]のマルチページアクティビティでは、各ページに固有のデザインを持つ、複数ページにわたるストーリーが作成されます。

たとえば、一定額を超える購入をした場合の送料無料オファーをテストすることができます。 オファーは、ランディングページ、カテゴリーページ、特定の製品ページに、サイズが異なり、各ページタイプで異なる場所に表示されます。 ホームページに目立つオファーを表示し、他の関連ページに小さなオファーを配置して強化することができます。

マルチページアクティビティは、デスクトップとレスポンシブ以外のモバイルサイトに対して異なるレイアウトを定義することもできます。 サイトに[!DNL `www.mysite.com`]ではなく[!DNL m.mysite.com]などの個別のモバイルサイトがある場合は、マルチページアクティビティを作成し、[!DNL m.mysite.com]を個別のページとして追加してから、モバイル編集を適用して、デスクトップ版とモバイル版を同じエクスペリエンスで適切に変更します。 レスポンシブモバイルサイトでは、[モバイルエクスペリエンスの編集](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md)を使用します。

>[!NOTE]
>
>複数ページアクティビティは、同じオファーを複数のページで異なる外観で表示するアクティビティのためのものです。 すべてのページでオファーを同じ外観で表示する場合は、[テンプレートテスト](/help/main/c-experiences/c-visual-experience-composer/temtest.md#similar-pages)のほうがより効率的です。

テンプレートルールは、マルチページテストの各ページに対して指定できます。 例えば、マルチページテストでは、マルチページテストのカテゴリページにテンプレートルールを適用することで、ホームページとすべてのカテゴリページにわたってテストを実行できます。 [類似ページに同じエクスペリエンスを含める](/help/main/c-experiences/c-visual-experience-composer/temtest.md#similar-pages)を参照してください。

## ページをアクティビティに追加 {#add-pages}

アクティビティに追加されたページごとに、オファーの独自のデザインを設定できます。

1. **[!UICONTROL 設定]** アイコン（![設定アイコン &#x200B;](/help/main/assets/icons/Setting.svg)）をクリックします。

1. 「**[!UICONTROL 追加ページを追加]**」をクリックします。

   画面の左側に&#x200B;**[!UICONTROL ページ]** ペインが表示されます。

   ![&#x200B; アイコンの設定](assets/vec_edit_4.png)

1. ページを指定し、デフォルトページを設定します。

   **[!UICONTROL ページを追加]** （![&#x200B; アイコンを追加](/help/main/assets/icons/Add.svg)）をクリックして追加ページを追加し、ページ名とURLを指定して、**[!UICONTROL 保存]**&#x200B;をクリックします。

1. [!UICONTROL Visual Experience Composer]を使用して、各ページでのオファーの表示方法をデザインします。
