---
keywords: オーディエンス;オーディエンスの選択;オーディエンスの選択;セレクター
description: オーディエンス条件に基づいて、Adobe [!DNL Target] アクティビティに参加するサイト訪問者を定義します。
title: '[!DNL Target] A/B アクティビティでオーディエンスを選択する方法を教えてください。'
feature: A/B Tests
exl-id: 281ae227-c593-4b71-ad12-865430b332be
TQID: 'https://experienceleague.adobe.com/7W8BrRxk4mKlYlgGb-GSOuc0kRMRWBvSochz9STYrTs'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ab2570eb-4844-49aa-8334-e91a345525e5
    internal-label: A/B Tests
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 4876228feee28031373f7e0abe62a66b05b15274
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 2%
---
# オーディエンスの選択 {#select-audience}

>[!BEGINSHADEBOX]

**このページ：**&#x200B;では、A/B アクティビティのオーディエンスを選択、作成、結合、表示、編集、コピーする方法と、含める訪問者の割合を設定する方法について説明します。

>[!ENDSHADEBOX]

オーディエンスは、どの適格な訪問者を[!DNL Adobe Target] アクティビティに入力するかを決定します。

アクティビティを作成する[の3つの部分で構成されるガイド付きワークフローの&#x200B;**[!UICONTROL ターゲティング]** ステップには、オーディエンスとそのトラフィック率の割り当て、トラフィック配分方法の選択、アクティビティの各エクスペリエンスのトラフィック配分の指定の手順を示すフロー図が表示されます。](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)

![A/B テストのターゲティング手順](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new-ui.png)

フロー図のすべてのオプションについて詳しくは、[A/B テストアクティビティの作成](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)を参照してください。

## アクティビティのオーディエンスの選択

オーディエンスは、アクティビティの閲覧者を制御します。 オーディエンスに一致する訪問者のみが入力でき、その訪問者のシェアを決定します。 デフォルトでは、アクティビティはすべての訪問者をターゲットにします。

1. 「**[!UICONTROL すべての訪問者]**」コントロールをクリックして、アクティビティ用の別のオーディエンスを選択します。

   **[!UICONTROL すべての訪問者]**&#x200B;がデフォルトのオーディエンスです。 特定のオーディエンスターゲティングを使用しないA/B テストの場合は、デフォルトを維持します。 別のオーディエンスを選択すると、その名前が一番左のコントロールに表示されます。

1. **[!UICONTROL 置換] アイコン** （![置換アイコン &#x200B;](/help/main/assets/icons/Retweet.svg)）をクリックします。

   ![](../../assets/audience_activity.png)

1. **[!UICONTROL オーディエンスを追加]** ダイアログボックスで、**[!UICONTROL オーディエンスライブラリ]**&#x200B;から選択したオーディエンスを参照するか、アクティビティのみのオーディエンスを作成できます。

   **[!UICONTROL オーディエンスライブラリ]**&#x200B;には、以前に定義されたオーディエンスが含まれています。これには、[!DNL Target]の一部として事前に構築された一般的なオーディエンスも含まれます。

   ![](../../assets/audience_activity_2.png)

1. オーディエンスの横にある&#x200B;**[!UICONTROL 情報]** アイコン （![情報アイコン &#x200B;](/help/main/assets/icons/InfoOutline.svg)）をクリックして、そのオーディエンスのソースと属性を含む詳細を表示します。

   ![](../../assets/audience_activity_3.png)

   「**[!UICONTROL 詳細を表示]**」をクリックして、オーディエンスに関する詳細を表示することもできます。

1. （条件付き）複数のオーディエンスを組み合わせるオーディエンスを作成するには、**[!UICONTROL オーディエンスを組み合わせる]**&#x200B;から[をクリックします](/help/main/c-target/combining-multiple-audiences.md)。

   +++ 新しいオーディエンスを作成する手順

   まだ&#x200B;**[!UICONTROL オーディエンスライブラリ]**&#x200B;にない新しいオーディエンスを作成するには、**[!UICONTROL オーディエンスの作成]**&#x200B;をクリックし、オーディエンスを定義してから、**[!UICONTROL 完了]**&#x200B;をクリックします。

   [create-audience ワークフロー](/help/main/c-target/c-audiences/audiences.md)中に、次のオプションから選択できます。

   * **[!UICONTROL オーディエンスライブラリ]**: **[!UICONTROL オーディエンスライブラリ]**&#x200B;に保存され、他のアクティビティで再利用できるオンデマンドオーディエンスを作成します。
   * **[!UICONTROL このアクティビティのみ]**: **[!UICONTROL オーディエンスライブラリ]**&#x200B;に保存されていない[&#x200B; アクティビティ固有のオーディエンス &#x200B;](/help/main/c-target/creating-activity-only-audience.md)を作成し、現在のアクティビティでのみ使用できます。

   +++

1. オーディエンスを編集またはコピーするには、目的のオーディエンスの横にある&#x200B;**[!UICONTROL その他のアクション]** アイコン （![その他のアクション アイコン &#x200B;](/help/main/assets/icons/More.svg)）をクリックします。

1. オーディエンスを選択したら、「**[!UICONTROL オーディエンスを割り当て]**」をクリックします。

1. 右側のペインで「**[!UICONTROL 訪問者の割合]**」をクリックし、アクティビティに含める対象となる訪問者の割合を指定します。

1. オーディエンスに問題がなければ、**[!UICONTROL 次へ]**&#x200B;をクリックして、3段階のガイド付きワークフローの3番目のステップに移動します。

>[!NOTE]
>
>**[!UICONTROL Audience]** リストを開くと、読み込まれたオーディエンスはバックグラウンドで自動的に読み込まれ、読み込まれたオーディエンスが10分以上経過しています。
