---
keywords: recommendations デザイン;デザインの作成;デザインのコピー
description: Adobe [!DNL Target] Recommendationsのデザインは、デフォルトのデザインを使用するか、ページのレイアウトに最適に合うようにカスタムデザインを作成します。
title: Recommendationsでデザインを作成する方法を教えてください。
feature: Recommendations
exl-id: 0f10ee9d-7210-4e02-9342-e4f85cf46e8c
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '1029'
ht-degree: 32%

---

# ![PREMIUM](/help/main/assets/premium.png) デザインの作成

デザインによって、レコメンデーションがページに表示される方法が定義されます。

[!UICONTROL Recommendations] のデザイン作成には、デフォルトのデザインを使用するか、カスタムデザインを作成することができます。この **[!UICONTROL Recommendations /デザイン]** 画面には、デフォルトのデザインカードと、アカウントで作成されたすべてのデザインが表示されます。

デザインを操作する際は、次の情報に留意してください。

* レコメンデーションデザインは、デフォルトのデザインを使用して作成することも、カスタムデザインを作成することもできます。
* デフォルトのデザインを編集または削除することはできません。
* カスタムデザインは、編集、コピー、削除できます。
* デフォルトのデザインに基づいてデザインを作成するには、まずデザインをコピーしてから、コピーを編集する必要があります。

次の図は、デフォルトの 1 x 4 のデザインを示しています。

![1 x 4 デフォルトデザイン](/help/main/c-recommendations/c-design-overview/assets/default-design.png)

この図は、カスタムデザインを示しています。

![カスタムデザイン](/help/main/c-recommendations/c-design-overview/assets/custom-design.png)

デザインは、アクティビティ作成プロセス中に Visual Experience Composer(VEC) 内から、またはアクティビティ作成以外のデザインライブラリから作成できます。 以降の節では、ライブラリからデザインを作成すると仮定していますが、手順は似ています。

## デザインの作成

デフォルトのデザインに基づいてデザインを作成することも、カスタムデザインを作成することもできます。

### デフォルトのデザインに基づくデザインの作成

1. クリック **[!UICONTROL Recommendations]** > **[!UICONTROL デザイン]** 表示する [!UICONTROL デザイン] ライブラリ。

   ![デザインライブラリ](/help/main/c-recommendations/c-design-overview/assets/design-library.png)

1. 作成するデザインのカードの上にマウスを移動し、 **[!UICONTROL コピー]** アイコン

   ![Card_CopyDesign の画像](assets/Card_CopyDesign.png)

   この [!UICONTROL デザインを作成] ダイアログボックスが表示されます。

   ![createDesign 画像](assets/createDesign.png)

1. 内 **[!UICONTROL 情報]** パネル、追加する **[!UICONTROL コンテンツ名]** デザインカードに表示するプレビュー画像（オプション）

   デフォルトのデザインを使用すると、デザイン名と「コピー」が **[!UICONTROL コンテンツ名]** フィールドに入力します。 名前は編集できます。デザインカードに表示する画像を選択することもできます。

1. （条件付き）デザインの編集 **[!UICONTROL コード]**&#x200B;必要に応じて、

   レコメンデーションデザインには、オープンソースの Velocity デザイン言語が使用されています。Velocity に関する情報は、 [https://velocity.apache.org](https://velocity.apache.org) および [Velocity を使用したデザインのカスタマイズ](/help/main/c-recommendations/c-design-overview/customizing-a-template.md).

   デザインは HTML または HTML 以外にすることができます。デフォルトで、HTML デザインは`<div>`タグでラップされ、Web 環境でのクリック追跡が可能です。HTML 以外のデザインは、Web 環境ではない環境用のもので、クリック追跡ができません。スライド [!UICONTROL HTML設計] 「オフ」位置に切り替えて、非HTMLコードを使用します。

   >[!NOTE]
   >
   >デザインで参照できるエンティティの最大数は、ハードコーディングの場合もループの場合も 99 です。

1. 「**[!UICONTROL 保存]**」をクリックします。

### カスタムデザインの作成

1. クリック **[!UICONTROL Recommendations]** > **[!UICONTROL デザイン]** 表示する [!UICONTROL デザイン] ライブラリ。

1. クリック **[!UICONTROL デザインを作成]**.

   新しいカスタムデザインを既存のデザインに基づく場合は、目的のデザインの上にマウスを移動し、 [!UICONTROL コピー] アイコン その後、コピーを編集して新しいカスタムデザインを作成できます。

1. を追加します。 **[!UICONTROL コンテンツ名]** オプションのプレビュー画像。

1. （条件付き）デザインの編集 **[!UICONTROL コード]**&#x200B;必要に応じて、

   詳しくは、上記の手順 4 の情報を参照してください。

1. 「**[!UICONTROL 保存]**」をクリックします。

## デザインの編集、コピー、削除

デフォルトのデザインは編集またはコピーできないことに注意してください。コピーできるのは、デフォルトのデザインのみです。

内の目的のデザインの上にマウスポインターを置きます。 [!UICONTROL デザイン] ライブラリを開き、次の該当するアイコンをクリックします。編集、コピー、削除を行います。

![デザインのアイコンにカーソルを合わせる](/help/main/c-recommendations/c-design-overview/assets/hover-icons-design.png)

既存のデザインをコピーして複製のデザインを作成し、そのデザインを修正することができます。 これにより、手間をかけずに同様のデザインを作成できます。

デザインはアカウント全体で使用できることに注意してください。 デザインを削除する前に、必ずこの点を考慮してください。 削除したデザインは復元できません。

## JSON の例 {#section_75BFB2537CFF4FBD9B560F59EB32C8DD}

次の例は、フォームベースのエディターを使用してアクティビティを設定した場合に、JSON 応答を返す方法を示しています。

1. デザインライブラリ内またはフォームベースのワークフロー内からデザインを作成します。 Visual Experience Composer(VEC) ワークフロー内でこの作業をおこなう場合、HTMLデザイン ( `<div>` クリック追跡のために使用します。

1. 「HTML デザイン」オプションがオフになっていることを確認します。

   ![html_design_toggle image](assets/html_design_toggle.png)

1. 次のコードは、デザインに貼り付けることのできるコードの例です。

   ```javascript
       #* 
       * "Return a simple list of recommended entity ids"   
       *#
   
       {   
         "notes":{   
         "purpose": "Return a simple list of recommended entity ids",   
         "use-case": "Use this approach if you prefer to do a real-time lookup of entity attribute details (such as inventory, price, rating) from another system (such as a CMS, PIM or ecommerce platform)",   
         "version": "01"   
         },   
         "recommendedItems": {   
           "key": "$key.id",   
           "slot-01": "$entity1.id",   
           "slot-02": "$entity2.id",   
           "slot-03": "$entity3.id",   
           "slot-04": "$entity4.id",   
           "slot-05": "$entity5.id",   
           "slot-06": "$entity6.id",   
           "slot-07": "$entity7.id",   
           "slot-08": "$entity8.id",   
           "slot-09": "$entity9.id",   
           "slot-10": "$entity10.id"   
         }   
       }  
   ```

1. フォームベースのセットアップ [!DNL Recommendations] このデザインを使用するアクティビティ。

   1. 次に移動： **[!UICONTROL アクティビティ]** ページ。
   1. **[!UICONTROL アクティビティを作成]**／**[!UICONTROL レコメンデーション]**&#x200B;をクリックします。
   1. の下 **[!UICONTROL Experience Composer を選択]**&#x200B;を選択します。 **[!UICONTROL フォーム]**&#x200B;を選択し、「 **[!UICONTROL 次へ]**.
   1. 「場所」で &quot;Sample_Recs_Response&quot; というテキストを入力します。
   1. 「**[!UICONTROL デフォルトコンテンツ]**」で、下矢印、「**[!UICONTROL レコメンデーションの追加]**」の順にクリックします。
   1. 「ページタイプ」を選択します。これにより、次の画面の最初のフィルタリングが決まります。
   1. 条件カードを選択し、「**[!UICONTROL 次へ]**」をクリックします。
   1. 前の手順で作成したデザインを選択し、「 **[!UICONTROL 次へ]**.
   1. 設定プロセスを完了します。
   1. 「**[!UICONTROL 非アクティブ]**」の横にある右矢印をクリックし、「**[!UICONTROL アクティブ化]**」を選択します。

1. アクティビティを設定してアクティブ化したら、クリーンな JSON 応答を返すサンプルのリクエストを設定できます。

   アクティビティを保存した時点から、 [!DNL Target] は、選択した条件設定をサポートするために、モデルを作成する必要があります。 要素の数によっては、構築に時間がかかる場合もあります。モデルの構築が完了すると結果が表示されます。

   次に例を示します。

   ```
   https://[YOUR_CLIENT_CODE].tt.omtrdc.net/m2/YOUR_CLIENT_CODE/ubox/raw?mbox=[YOUR_MBOX_NAME]&mboxContentType=text/html&mboxXDomain=disabled&entity.id=[ENTITY_ID]&mboxHost=rawbox_sample&at_property=[AT_PROPERTY_TOKEN]&mboxNoRedirect=true&mboxPC=1234-4321&mboxSession=9876-7000
   ```

   where

   | パラメーター | 値 |
   |--- |--- |
   | `[YOUR_CLIENT_CODE]` | Target クライアントコードです (/help/target/products.html#recsSettings/Recommendations API トークン/クライアントコードから入手できます )。 |
   | `[YOUR_MBOX_NAME]` | フォームベースのRecommendationsの「場所」セクションで選択した名前（この場合は Sample_Recs_Response）。 |
   | `[ENTITY_ID` | カタログ内の項目の `entity.id` です。 |
   | `[AT_PROPERTY_TOKEN]` | （オプション）アクティビティの設定時にプロパティ（Enterprise 権限の一部）を選択した場合は追加します。 |

アルゴリズムを実行して結果が得られたら、応答は次のようになります。

![json_recommendation 画像](assets/json_recommendation.png){width=&quot;575px&quot;}

## JSON オブジェクトに関するその他のヒントとテクニック {#section_C305673C68944749969DB239E3221DC2}

次の構文でデザインを設定することで、シンプルなコンマ区切りの項目リストを返すこともできます。

```
entity1.id, $entity2.id, $entity3.id, $entity4.id, $entity5.id, 
```

応答でその他の情報を送信することもできます。次のコードファイルはより複雑なサンプルで、エンティティ ID と関連するスロット（順序）以外に様々な情報を返します。このデザインの例の場合は、アクティビティの詳細、Target プロファイルの詳細（該当する場合）、その他の情報も返されます `entity.attributes` 返される項目に関連付けられています。

```javascript
    {   
     "adobeRecommendations": {   
      "notes": {   
       "purpose": "Return a list of entity ids with their associated entity.attributes",   
       "use-case": "Use this approach to avoid looking up attribute details after receiving a response from Target",   
       "version": "01"   
      },   
      "recommendedItems": {   
       "slot-01": "$entity1.id",   
       "slot-02": "$entity2.id",   
       "slot-03": "$entity3.id",   
       "slot-04": "$entity4.id",   
       "slot-05": "$entity5.id",   
       "slot-06": "$entity6.id",   
       "slot-07": "$entity7.id",   
       "slot-08": "$entity8.id",   
       "slot-09": "$entity9.id",   
       "slot-10": "$entity10.id"   
      },   
      "activityDetails": {   
       "mbox.name": "email-mbox",   
       "campaign.name": "\${campaign.name}",   
       "campaign.id": "\${campaign.id}",   
       "campaign.recipe.name": "\${campaign.recipe.name}",   
       "campaign.recipe.id": "\${campaign.recipe.id}",   
       "offer.name": "\${offer.name}",   
       "offer.id": "\${offer.id}",   
       "criteria.title": "$criteria.title",   
       "algorithm.name": "$algorithm.name",   
       "algorithm.dayCount": "$algorithm.dayCount"   
      },   
      "visitorProfile": {   
       "profile.favorite-category": "\${profile.favorite-category}",   
       "profile.test": "\${profile.test}",   
       "user.endpoint.lastPurchasedEntity": "\${user.endpoint.lastPurchasedEntity}",   
       "user.endpoint.lastViewedEntity": "\${user.endpoint.lastViewedEntity}",   
       "user.endpoint.mostViewedEntity": "\${user.endpoint.mostViewedEntity}",   
       "user.endpoint.categoryAffinity": "\${user.endpoint.categoryAffinity}",   
       "profile.geolocation.city": "\${profile.geolocation.city}",   
       "profile.geolocation.dma": "\${profile.geolocation.dma}",   
       "profile.geolocation.state": "\${profile.geolocation.state}",   
       "profile.geolocation.country": "\${profile.geolocation.country}",   
       "profile.sessionCount": "\${profile.sessionCount}",   
       "profile.averageDaysBetweenVisits": "\${profile.averageDaysBetweenVisits}",   
       "profile.browserTime": "\${profile.browserTime}",   
       "user.activeActivities": "\${user.activeActivities}",   
       "user.pcId": "\${user.pcId}",   
       "user.isFirstSession": "\${user.isFirstSession}",   
       "user.isNewSession": "\${user.isNewSession}",   
       "user.header": "\${user.header}",   
       "user.parameter": "\${user.parameter}"   
      },   
      "recKey": {   
       "recKeyDetails": {   
        "id": "$key.id",   
        "name": "$key.name",   
        "category": "$key.category",   
        "pageUrl": "$key.pageUrl",   
        "thumbnailUrl": "$key.thumbnailUrl"   
       }   
      },   
      "recDetailedResults": {   
       "recEntity1Details": {   
        "id": "$entity1.id",   
        "name": "$entity1.name",   
        "category": "$entity1.category",   
        "pageUrl": "$entity1.pageUrl",   
        "thumbnailUrl": "$entity1.thumbnailUrl"   
       },   
       "recEntity2Details": {   
        "id": "$entity2.id",   
        "name": "$entity2.name",   
        "category": "$entity2.category",   
        "pageUrl": "$entity2.pageUrl",   
        "thumbnailUrl": "$entity2.thumbnailUrl"   
       },   
       "recEntity3Details": {   
        "id": "$entity3.id",   
        "name": "$entity3.name",   
        "category": "$entity3.category",   
        "pageUrl": "$entity3.pageUrl",   
        "thumbnailUrl": "$entity3.thumbnailUrl"   
       },   
       "recEntity4Details": {   
        "id": "$entity4.id",   
        "name": "$entity4.name",   
        "category": "$entity4.category",   
        "pageUrl": "$entity4.pageUrl",   
        "thumbnailUrl": "$entity4.thumbnailUrl"   
       },   
       "recEntity5Details": {   
        "id": "$entity5.id",   
        "name": "$entity5.name",   
        "category": "$entity5.category",   
        "pageUrl": "$entity5.pageUrl",   
        "thumbnailUrl": "$entity5.thumbnailUrl"   
       },   
       "recEntity6Details": {   
        "id": "$entity6.id",   
        "name": "$entity6.name",   
        "category": "$entity6.category",   
        "pageUrl": "$entity6.pageUrl",   
        "thumbnailUrl": "$entity6.thumbnailUrl"   
       },   
       "recEntity7Details": {   
        "id": "$entity7.id",   
        "name": "$entity7.name",   
        "category": "$entity7.category",   
        "pageUrl": "$entity7.pageUrl",   
        "thumbnailUrl": "$entity7.thumbnailUrl"   
       },   
       "recEntity8Details": {   
        "id": "$entity8.id",   
        "name": "$entity8.name",   
        "category": "$entity8.category",   
        "pageUrl": "$entity8.pageUrl",   
        "thumbnailUrl": "$entity8.thumbnailUrl"   
       },   
       "recEntity9Details": {   
        "id": "$entity9.id",   
        "name": "$entity9.name",   
        "category": "$entity9.category",   
        "pageUrl": "$entity9.pageUrl",   
        "thumbnailUrl": "$entity9.thumbnailUrl"   
       },   
       "recEntity10Details": {   
        "id": "$entity10.id",   
        "name": "$entity10.name",   
        "category": "$entity10.category",   
        "pageUrl": "$entity10.pageUrl",   
        "thumbnailUrl": "$entity10.thumbnailUrl"   
       }   
      }   
     }   
    }  
```

## トレーニングビデオ：Recommendations (3:20)でのカスタムデザインの作成 ![概要バッジ](/help/main/assets/overview.png)

このビデオには、次の情報が含まれています。

* カスタムデザインの作成
* デザインでの表示変数の参照方法の説明

>[!VIDEO](https://video.tv.adobe.com/v/27687)
