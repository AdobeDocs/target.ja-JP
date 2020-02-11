---
keywords: recommendations design;create design;copy design
description: デザインによって、レコメンデーションがページに表示される方法が定義されます。
title: デザインの作成
uuid: 812258e0-8d28-4ef3-b745-45ed694fcabe
translation-type: tm+mt
source-git-commit: 65a4fd0d05ad065c9291a83dc0b3066451f7373e

---


# ![PREMIUM](/help/assets/premium.png) デザインの作成{#create-a-design}

デザインによって、レコメンデーションがページに表示される方法が定義されます。

[!UICONTROL Recommendations] のデザイン作成には、デフォルトのデザインを使用するか、カスタムデザインを作成することができます。**[!UICONTROL レコメンデーション／デザイン]**&#x200B;スクリーンには、デフォルトデザインカードと過去に作成したすべてのデザインが表示されます。デフォルトのデザインの編集や削除はできません。

1. **[!UICONTROL レコメンデーション／デザイン]**&#x200B;画面で、作成するデザインのカードの上にマウスを移動します。

   ![](assets/Card_CopyDesign.png)

1. 既存のデザインをコピーおよび編集する場合は、**[!UICONTROL コピー]**&#x200B;アイコンをクリックします。

   または

   カスタムデザインを作成するには、**[!UICONTROL レコメンデーション／デザイン]**&#x200B;スクリーン上で「**[!UICONTROL デザインを作成]**」をクリックします。

   ![](assets/createDesign.png)

1. 「**[!UICONTROL コンテンツ名]**」を追加します。

   デフォルトデザインを使用した場合には、デザイン名と「コピー」が「**[!UICONTROL コンテンツ名]**」フィールドに表示されます。名前は編集できます。1.（オプション）デザインカード上に表示する画像をクリックして選択します。
1. デザインの&#x200B;**[!UICONTROL コード]**&#x200B;を編集します。

   レコメンデーションデザインには、オープンソースの Velocity デザイン言語が使用されています。Velocity について詳しくは、[](https://velocity.apache.org)https://velocity.apache.org を参照してください。

   デザインは HTML または HTML 以外にすることができます。デフォルトで、HTML デザインは <div> タグでラップされ、Web 環境でのクリック追跡が可能です。HTML 以外のデザインは、Web 環境ではない環境用のもので、クリック追跡ができません。

   >[!NOTE]
   >
   >デザインで参照できるエンティティの最大数は、ハードコーディングでもループ経由でも 99 です。

1. 「**[!UICONTROL 保存]**」をクリックします。

## Training video: Create custom designs in Recommendations (3:20) ![Overview badge](/help/assets/overview.png)

このビデオには、次の情報が含まれています。

* カスタムデザインの作成
* デザインでの表示変数の参照方法の説明

>[!VIDEO](https://video.tv.adobe.com/v/27687)
