---
keywords: recommendations デザイン;デザインの作成;デザインのコピー
description: デザインによって、レコメンデーションがページに表示される方法が定義されます。
title: デザインの作成
feature: Recommendations
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '995'
ht-degree: 32%

---


# ![PREMIUM](/help/assets/premium.png) デザインの作成{#create-a-design}

デザインによって、レコメンデーションがページに表示される方法が定義されます。

[!UICONTROL Recommendations] のデザイン作成には、デフォルトのデザインを使用するか、カスタムデザインを作成することができます。**[!UICONTROL Recommendations>デザイン]**&#x200B;画面には、デフォルトのデザインカードと、アカウントで作成されたすべてのデザインが表示されます。

デザインを操作する際は、次の情報に注意してください。

* レコメンデーションデザインは、デフォルトのデザインを使用して作成することも、カスタムデザインを作成することもできます。
* デフォルトのデザインは編集または削除できません。
* カスタムデザインは、編集、コピー、または削除できます。
* デフォルトのデザインに基づいてデザインを作成するには、まずデザインをコピーしてから、そのコピーを編集する必要があります。

次の図は、デフォルトの1 x 4の設計を示しています。

![1 x 4デフォルトデザイン](/help/c-recommendations/c-design-overview/assets/default-design.png)

次の図に、カスタムデザインを示します。

![カスタムデザイン](/help/c-recommendations/c-design-overview/assets/custom-design.png)

デザインは、アクティビティ作成プロセス中に、Visual Experience Composer(VEC)内またはアクティビティ作成以外のデザインライブラリから作成できます。 以下の節では、ライブラリからデザインを作成していることを前提としていますが、手順は似ています。

## デザインの作成

デフォルトのデザインに基づいてデザインを作成することも、カスタムデザインを作成することもできます。

### デフォルトのデザインに基づくデザインの作成

1. **[!UICONTROL Recommendations]**/**[!UICONTROL デザイン]**&#x200B;をクリックして、[!UICONTROL デザイン]ライブラリを表示します。

   ![デザインライブラリ](/help/c-recommendations/c-design-overview/assets/design-library.png)

1. 作成するデザインのカードの上にマウスを移動し、**[!UICONTROL コピー]**&#x200B;アイコンをクリックします。

   ![](assets/Card_CopyDesign.png)

   [!UICONTROL デザインを作成]ダイアログボックスが表示されます。

   ![](assets/createDesign.png)

1. **[!UICONTROL 情報]**&#x200B;パネルで、デザインカードに表示する&#x200B;**[!UICONTROL コンテンツ名]**&#x200B;とオプションのプレビュー画像を追加します。

   デフォルトのデザインを使用する場合、デザイン名と「コピー」が「**[!UICONTROL コンテンツ名]**」フィールドに表示されます。 名前は編集できます。デザインカードに表示する画像を選択することもできます。

1. （条件付き）必要に応じて、デザイン&#x200B;**[!UICONTROL コード]**&#x200B;を編集します。

   レコメンデーションデザインには、オープンソースの Velocity デザイン言語が使用されています。Velocityに関する情報は、[https://velocity.apache.org](https://velocity.apache.org)および[Velocity](/help/c-recommendations/c-design-overview/customizing-a-template.md)を使用したデザインのカスタマイズで確認できます。

   デザインは HTML または HTML 以外にすることができます。デフォルトで、HTML デザインは`<div>`タグでラップされ、Web 環境でのクリック追跡が可能です。HTML 以外のデザインは、Web 環境ではない環境用のもので、クリック追跡ができません。[!UICONTROL HTMLデザイン]の切り替えを「オフ」位置にスライドさせ、HTML以外のコードを使用します。

   >[!NOTE]
   >
   >デザインで参照できるエンティティの最大数は、ハードコードまたはループ経由で、99です。

1. 「**[!UICONTROL 保存]**」をクリックします。

### カスタムデザインの作成

1. **[!UICONTROL Recommendations]**/**[!UICONTROL デザイン]**&#x200B;をクリックして、[!UICONTROL デザイン]ライブラリを表示します。

1. 「**[!UICONTROL デザインを作成]**」をクリックします。

   既存のデザインを基に新しいカスタムデザインを作成する場合は、目的のデザインにマウスを移動し、[!UICONTROL コピー]アイコンをクリックします。 その後、コピーを編集して、新しいカスタムデザインを作成できます。

1. 追加&#x200B;**[!UICONTROL コンテンツ名]**&#x200B;とオプションのプレビュー画像。

1. （条件付き）必要に応じて、デザイン&#x200B;**[!UICONTROL コード]**&#x200B;を編集します。

   詳細については、上記の手順4の情報を参照してください。

1. 「**[!UICONTROL 保存]**」をクリックします。

## デザインの編集、コピー、削除

デフォルトのデザインは編集またはコピーできません。デフォルトのデザインのみコピーできます。

[!UICONTROL デザイン]ライブラリ内の目的のデザインの上にマウスポインターを置き、次のうち該当するアイコンをクリックします。編集、コピー、または削除を行います。

![デザインにカーソルを合わせたときのアイコン](/help/c-recommendations/c-design-overview/assets/hover-icons-design.png)

既存のデザインをコピーして重複デザインを作成し、その後変更できます。 これにより、手間をかけずに類似したデザインを作成できます。

デザインはアカウント全体で使用できることに注意してください。 デザインを削除する前に、この点を考慮してください。 削除したデザインは元に戻せません。

## JSON の例 {#section_75BFB2537CFF4FBD9B560F59EB32C8DD}

次の例は、フォームベースのエディターを使用してアクティビティを設定する場合に、JSON応答を返す方法を示しています。

1. デザインライブラリ内またはフォームベースのワークフロー内からデザインを作成します。 Visual Experience Composer(VEC)ワークフロー内でこれを行う場合は、HTMLデザイン以外を作成することはできません。HTMLデザインは、クリック追跡のために`<div>`にラップされます。

1. 「HTML デザイン」オプションがオフになっていることを確認します。

   ![](assets/html_design_toggle.png)

1. 次のコードは、デザインに貼り付けることができる内容の例です。

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

1. このデザインを使用するフォームベースの[!DNL Recommendations]アクティビティを設定します。

   1. **[!UICONTROL アクティビティ]**&#x200B;ページに移動します。
   1. **[!UICONTROL アクティビティを作成]**／**[!UICONTROL レコメンデーション]**&#x200B;をクリックします。
   1. 「**[!UICONTROL Experience Composer]**&#x200B;を選択」で「**[!UICONTROL フォーム]**」を選択し、「**[!UICONTROL 次へ]**」をクリックします。
   1. 「場所」で &quot;Sample_Recs_Response&quot; というテキストを入力します。
   1. 「**[!UICONTROL デフォルトコンテンツ]**」で、下矢印、「**[!UICONTROL レコメンデーションの追加]**」の順にクリックします。
   1. 「ページタイプ」を選択します。これにより、次の画面の最初のフィルタリングが決まります。
   1. 条件カードを選択し、「**[!UICONTROL 次へ]**」をクリックします。
   1. 前の手順で作成したデザインを選択し、「**[!UICONTROL 次へ]**」をクリックします。
   1. 設定プロセスを完了します。
   1. 「**[!UICONTROL 非アクティブ]**」の横にある右矢印をクリックし、「**[!UICONTROL アクティブ化]**」を選択します。

1. アクティビティを設定してアクティブ化したら、クリーンな JSON 応答を返すサンプルのリクエストを設定できます。

   アクティビティを保存した時点から、[!DNL Target]は、選択した条件の設定をサポートするモデルを構築する必要があります。 要素の数によっては、構築に時間がかかる場合もあります。モデルの構築が完了すると結果が表示されます。

   次に例を示します。

   ```
   https://[YOUR_CLIENT_CODE].tt.omtrdc.net/m2/YOUR_CLIENT_CODE/ubox/raw?mbox=[YOUR_MBOX_NAME]&mboxContentType=text/html&mboxXDomain=disabled&entity.id=[ENTITY_ID]&mboxHost=rawbox_sample&at_property=[AT_PROPERTY_TOKEN]&mboxNoRedirect=true&mboxPC=1234-4321&mboxSession=9876-7000
   ```

   where

   | パラメーター | 値 |
   |--- |--- |
   | `[YOUR_CLIENT_CODE]` | ターゲットクライアントコード(/help/target/products.html#recs設定/RecommendationsAPIトークン/クライアントコードで利用可能) |
   | `[YOUR_MBOX_NAME]` | フォームベースのRecommendationsの「場所」セクションで選択した名前（この場合はSample_Recs_Response）。 |
   | `[ENTITY_ID` | カタログ内の項目の `entity.id` です。 |
   | `[AT_PROPERTY_TOKEN]` | （オプション）アクティビティの設定時にプロパティ（Enterprise 権限の一部）を選択した場合は追加します。 |

アルゴリズムを実行して結果が得られたら、応答は次のようになります。

![](assets/json_recommendation.png){width=&quot;575px&quot;}

## その他のJSONオブジェクトのヒントとテクニック{#section_C305673C68944749969DB239E3221DC2}

次の構文でデザインを設定することで、シンプルなコンマ区切りの項目リストを返すこともできます。

```
entity1.id, $entity2.id, $entity3.id, $entity4.id, $entity5.id, 
```

応答でその他の情報を送信することもできます。次のコードファイルはより複雑なサンプルで、エンティティ ID と関連するスロット（順序）以外に様々な情報を返します。この設計例では、アクティビティの詳細、ターゲットプロファイルの詳細（該当する場合）、および返された項目に関連付けられた他の`entity.attributes`も返します。

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

## トレーニングビデオ：Recommendationsでカスタムデザインを作成する(3:20)![概要バッジ](/help/assets/overview.png)

このビデオには、次の情報が含まれています。

* カスタムデザインの作成
* デザインでの表示変数の参照方法の説明

>[!VIDEO](https://video.tv.adobe.com/v/27687)
