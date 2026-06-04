---
keywords: json オファー；json オファーの作成
description: '[!UICONTROL &#x200B; フォームベースのExperience Composer]で使用するJSON オファーを作成する方法について説明します。'
title: JSON オファーを作成するにはどうすればよいですか？
feature: Experiences and Offers
exl-id: 793665a4-4cd6-458f-8225-ba23e503a115
TQID: https://experienceleague.adobe.com/BI7N44iK4Ce2xOiz1vgh4O9efGZFAvK83RsL1368ItU
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
  - id: f7c7de77-382f-4f48-8b36-61a170f06d3d
subfeature_v2:
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 506
ht-degree: 23%

---

# JSON オファーの作成

[!DNL Adobe Target]の[!UICONTROL &#x200B; オファーライブラリ &#x200B;]でJSON オファーを作成し、[!UICONTROL &#x200B; フォームベースのExperience Composer]で使用します。

JSON オファーをフォームベースのアクティビティで使用すると、SPA フレームワークまたはサーバーサイド統合で使用するためにJSON形式でオファーを送信するために[!DNL Target]決定が必要なユースケースを有効にできます。

## JSONの考慮事項

JSON オファーを使用する際は次の点を考慮してください。

* JSON オファーは現在、[!UICONTROL A/B テスト &#x200B;]、[!UICONTROL Automated Personalization] （AP）、[!UICONTROL &#x200B; エクスペリエンスのターゲット設定] （XT）アクティビティでのみ使用できます。
* JSON オファーは、[&#x200B; フォームベースのアクティビティ &#x200B;](/help/main/c-experiences/form-experience-composer.md)でのみ使用できます。
* JSON オファーは、[Server Side APIとMobile Node.js、Java、.NET、およびPython SDK](https://experienceleague.adobe.com/en/docs/target-dev/developer/server-side/server-side-overview){target=_blank}を使用している場合に直接取得できます。
* ブラウザーでは、JSON オファーは、`setJson` アクションを使用してアクションをフィルタリングすることにより、at.js 1.2.3 （以降）および[getOffer （） &#x200B;](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/adobe-target-getoffer){target=_blank}を使用してのみ取得できます。
* JSON オファーは、文字列ではなくネイティブの JSON オブジェクトとして配信されます。 これらのオブジェクトを利用する際に、オブジェクトを文字列として処理し、JSON オブジェクトに変換する必要はなくなりました。
* JSON オファーはビジュアルオファーではないので、他のオファー（HTML オファーなど）とは異なり自動的に適用されることはありません。 開発者は、[getOffer （） &#x200B;](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/adobe-target-getoffer){target=_blank}を使用してオファーを明示的に取得するコードを記述する必要があります。

## JSON オファーの作成 {#section_BB9C72D59DEA4EFB97A906AE7569AD7A}

1. 「**[!UICONTROL オファー]**」 > 「**[!UICONTROL コードオファー]**」をクリックします。
1. 「**[!UICONTROL オファーを作成]**」 > 「**[!UICONTROL JSON オファー]**」をクリックします。
1. オファー名を入力します。
1. （条件付き）プレミアムアカウント [&#128279;](/help/main/c-intro/intro.md#premium) [!DNL Target] をお持ちの場合は、目的の[&#x200B; ワークスペース &#x200B;](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#workspace)を選択します。
1. （条件付き）目的のプロファイル属性を選択します。
1. 「**[!UICONTROL コード]**」ボックスに JSON コードを入力するか貼り付けます。
1. 「**[!UICONTROL 作成]**」をクリックします。

## JSONの例 {#section_A54F7BB2B55D4B7ABCD5002E0C72D8C9}

JSON オファーは、[&#x200B; フォームベースのExperience Composer](/help/main/c-experiences/form-experience-composer.md)を使用して作成されたアクティビティでのみサポートされます。 現在、JSON オファーを使用できる唯一の方法は、ダイレクト API/SDK呼び出しです。

次に例を示します。

![JSON オファーダイアログボックスを作成](/help/main/c-experiences/c-manage-content/assets/json-example.png)

success コールバックに渡すアクションは、オブジェクトの配列です。 1つのJSON オファーがある場合、次のコンテンツが含まれています。

```json
{ 
  "demo": {"a": 1, "b": 2} 
}
```

アクション配列には、次の構造があります。

```json
[ 
 { 
   action: "setJson", 
   content: [{ 
     "demo": {"a": 1, "b": 2} 
   }] 
 }  
]
```

JSON オファーを抽出するには、アクションを繰り返し、`setJson` アクションを使用してアクションを見つけ、コンテンツ配列を繰り返します。

## ユースケース {#section_85B07907B51A43239C8E3498EF58B1E5}

次の JSON オファーが Web ページに配信されるとします。

```json
{ 
    "_id": "5a65d24d8fafc966921e9169", 
    "index": 0, 
    "guid": "7c006504-c6f7-468d-a46f-f72531ea454c", 
    "isActive": true, 
    "balance": "$2,075.06", 
    "picture": "https://placehold.it/32x32", 
    "tags": [ 
      "esse", 
      "commodo", 
      "excepteur"
    ], 
    "friends": [ 
      { 
        "id": 0, 
        "name": "Carla Lyons" 
      }, 
      { 
        "id": 1, 
        "name": "Ollie Mooney" 
      } 
    ], 
    "greeting": "Hello, Stephenson Fernandez! You have 4 unread messages.", 
    "favoriteFruit": "strawberry" 
} 
  
```

次のコードは、「greeting」属性にアクセスする方法を示しています。

```json
adobe.target.getOffer({   
  "mbox": "name_of_mbox", 
  "params": {}, 
  "success": function(offer) {           
        console.log(offer[0].content[0].greeting); 
  },   
  "error": function(status, error) {           
      console.log('Error', status, error); 
  } 
});
```

## Real-time CDP プロファイル属性を使用したJSON オファーの例

Real-time CDP プロファイル属性は、[!DNL Target]と共有して、HTMLおよびJSON オファーで使用できます。

詳しくは、[Real-time CDP プロファイル属性を [!DNL Target]](/help/main/c-integrating-target-with-mac/integrating-with-rtcdp.md#rtcdp-profile-attributes)と共有するを参照してください。

## JSON オファータイプによるオファーのフィルタリング {#section_52533555BCE6420C8A95EB4EB8907BDE}

**[!UICONTROL フィルターを表示]** アイコン （![&#x200B; フィルターを表示](/help/main/assets/icons/Filter.svg)）をクリックし、**[!UICONTROL JSON オファー]** チェックボックスを選択することで、JSON オファータイプで[!UICONTROL &#x200B; オファー] ライブラリをフィルタリングできます。
