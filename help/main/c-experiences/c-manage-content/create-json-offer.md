---
keywords: json オファー；json オファーの作成
description: '[!UICONTROL Form-Based Experience Composer] で使用する JSON オファーを作成する方法を説明します。'
title: JSON オファーを作成するには
feature: Experiences and Offers
exl-id: 793665a4-4cd6-458f-8225-ba23e503a115
source-git-commit: e8201198dc6ac36e803153d5c6b345a30716204a
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 25%

---

# JSON オファーの作成

[!UICONTROL Offer Library] で使用する JSON オファーを [!DNL Adobe Target] の [!UICONTROL Form-Based Experience Composer] で作成します。

JSON オファーをフォームベースのアクティビティで使用すると、SPA フレームワークまたはサーバーサイド統合で使用するために JSON 形式のオファーを送信する際に [!DNL Target] ーザー決定が必要になるユースケースを可能にできます。

## JSON の考慮事項

JSON オファーを使用する際は次の点を考慮してください。

* JSON オファーは現在、[!UICONTROL A/B Test]、[!UICONTROL Automated Personalization] （AP）および [!UICONTROL Experience Targeting] （XT）アクティビティでのみ使用できます。
* JSON オファーは、[ フォームベースのアクティビティ ](/help/main/c-experiences/form-experience-composer.md) でのみ使用できます。
* JSON オファーは、[ サーバーサイド API および Mobile Node.js、Java、.NET、Python SDK](https://experienceleague.adobe.com/en/docs/target-dev/developer/server-side/server-side-overview){target=_blank} を使用している場合に直接取得できます。
* ブラウザーでは、JSON オファーは、at.js 1.2.3 （またはそれ以降）経由でのみ取得でき、[ アクションを使用してアクションをフィルタリングすることで ](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/adobe-target-getoffer){target=_blank}getOffer （） `setJson` を使用できます。
* JSON オファーは、文字列ではなくネイティブの JSON オブジェクトとして配信されます。これらのオブジェクトを利用する際に、オブジェクトを文字列として処理し、JSON オブジェクトに変換する必要はなくなりました。
* JSON オファーはビジュアルオファーではないので、他のオファー（HTML オファーなど）とは異なり自動的に適用されることはありません。開発者は、[getOffer （） ](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/adobe-target-getoffer){target=_blank} を使用してオファーを明示的に取得するコードを記述する必要があります。

## JSON オファーの作成 {#section_BB9C72D59DEA4EFB97A906AE7569AD7A}

1. **[!UICONTROL Offers]**／**[!UICONTROL Code Offers]**&#x200B;をクリックします。
1. **[!UICONTROL Create Offer]**／**[!UICONTROL JSON Offer]**&#x200B;をクリックします。
1. オファー名を入力します。
1. （条件付き） [[!DNL Target] Premium アカウント ](/help/main/c-intro/intro.md#premium) をお持ちの場合は、目的の [ ワークスペース ](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#workspace) を選択します。
1. （条件付き）目的のプロファイル属性を選択します。
1. **[!UICONTROL Code]** ボックスに JSON コードを入力または貼り付けます。
1. **[!UICONTROL Create]** をクリックします。

## JSON の例 {#section_A54F7BB2B55D4B7ABCD5002E0C72D8C9}

JSON オファーは、[ フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md) を使用して作成されたアクティビティでのみサポートされます。 現在、JSON オファーを使用できるのは、API またはSDKの直接呼び出しを介してのみです。

次に例を示します。

![JSON オファーを作成ダイアログボックス ](/help/main/c-experiences/c-manage-content/assets/json-example.png)

success コールバックに渡すアクションは、オブジェクトの配列です。1 つの JSON オファーがあり、そこに次のコンテンツがあるとします。

```json
{ 
  "demo": {"a": 1, "b": 2} 
}
```

アクション配列の構造は次のとおりです。

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

JSON オファーを抽出するには、アクションを反復処理し、`setJson` アクションを含むアクションを見つけて、コンテンツ配列を反復処理します。

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

## Real-time CDP プロファイル属性を使用した JSON オファーの例

Real-time CDP プロファイル属性は、HTML オファーと JSON オファーで使用するために [!DNL Target] と共有できます。

詳しくは、[Real-time CDP プロファイル属性の  [!DNL Target]](/help/main/c-integrating-target-with-mac/integrating-with-rtcdp.md#rtcdp-profile-attributes) との共有を参照してください。

## JSON オファータイプによるオファーのフィルタリング {#section_52533555BCE6420C8A95EB4EB8907BDE}

[!UICONTROL Offers] のアイコン（**[!UICONTROL Show filters]** フィルターを表示アイコン ![）をクリックし、「](/help/main/assets/icons/Filter.svg)」チェックボックスを選択すると、JSON オファータイプで **[!UICONTROL JSON Offers]** ライブラリをフィルタリングできます。
