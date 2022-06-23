---
keywords: リモートオファー;リモートオファーの作成
description: Adobeで JSON オファーを作成する方法を説明します [!DNL Target] フォームベースの Experience Composer で使用する場合。 JSON オファーは、SPAフレームワークまたはサーバー側統合に役立ちます。
title: JSON オファーの作成方法
feature: Experiences and Offers
exl-id: 793665a4-4cd6-458f-8225-ba23e503a115
source-git-commit: a0a20b99a76ba0346f00e3841a345e916ffde8ea
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 49%

---

# JSON オファーの作成

で JSON オファーを作成 [!UICONTROL オファーライブラリ] in [!DNL Adobe Target] ( [!UICONTROL フォームベースの Experience Composer].

JSON オファーは、フォームベースのアクティビティで使用できるので、 [!DNL Target]SPAフレームワークまたはサーバー側統合での使用のために、オファーを JSON 形式で送信するには、の判定が必要です。

## JSON の考慮事項

JSON オファーを使用する際は次の点を考慮してください。

* JSON オファーは現在、 [!UICONTROL A/B テスト] および [!UICONTROL エクスペリエンスのターゲット設定] (XT) アクティビティ
* JSON オファーは、 [フォームベースのアクティビティ](/help/main/c-experiences/form-experience-composer.md) のみ。
* JSON オファーは、サーバー側 API、Mobile SDK または NodeJS SDK を使用している場合は直接取得できます。
* ブラウザーでは、JSON オファーは、at.js 1.2.3 以降と [getOffer()](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-getoffer/){target=_blank} を `setJson` アクション。
* JSON オファーは、文字列ではなくネイティブの JSON オブジェクトとして配信されます。これらのオブジェクトを利用する際に、オブジェクトを文字列として処理し、JSON オブジェクトに変換する必要はなくなりました。
* JSON オファーはビジュアルオファーではないので、他のオファー（HTML オファーなど）とは異なり自動的に適用されることはありません。開発者は[getOffer()](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-getoffer/) を使用して、オファーを明示的に取得するコードを作成する必要があります。

## JSON オファーの作成 {#section_BB9C72D59DEA4EFB97A906AE7569AD7A}

1. クリック **[!UICONTROL オファー]** > **[!UICONTROL コードオファー]**.

   ![オファー/「コードオファー」タブ](/help/main/c-experiences/c-manage-content/assets/code-offers-tab.png)

1. **[!UICONTROL 作成]**／**[!UICONTROL JSON オファー]**&#x200B;をクリックします。

   ![](assets/offer-json.png)

1. オファー名を入力します。
1. 「**[!UICONTROL コード]**」ボックスに JSON コードを入力するか貼り付けます。
1. 「**[!UICONTROL 保存]**」をクリックします。

## JSON の例 {#section_A54F7BB2B55D4B7ABCD5002E0C72D8C9}

JSON オファーは、 [フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md). 現時点で JSON オファーを使用できる方法は、直接の API 呼び出しのみとなっています。

次に例を示します。

```json
adobe.target.getOffer({ 
  mbox: "some-mbox", 
  success: function(actions) { 
    console.log('Success', actions); 
  }, 
  error: function(status, error) { 
    console.log('Error', status, error); 
  } 
});
```

success コールバックに渡すアクションは、オブジェクトの配列です。次のコンテンツを含む単一の JSON オファーがあるとします。

```json
{ 
  "demo": {"a": 1, "b": 2} 
}
```

アクション配列は次のような構成になります。

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

JSON オファーを抽出するには、アクションを繰り返し処理し、 `setJson` アクションを実行し、コンテンツ配列を繰り返し処理します。

## 使用例 {#section_85B07907B51A43239C8E3498EF58B1E5}

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
      "excepteur", 
    ], 
    "friends": [ 
      { 
        "id": 0, 
        "name": "Carla Lyons" 
      }, 
      { 
        "id": 1, 
        "name": "Ollie Mooney" 
      }, 
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

## JSON オファータイプによるオファーのフィルタリング {#section_52533555BCE6420C8A95EB4EB8907BDE}

次の項目をフィルターできます。 [!UICONTROL オファー] ライブラリを JSON オファータイプ別に作成する場合は、 **[!UICONTROL タイプ]** 」ドロップダウンリストから、 **[!UICONTROL JSON]** チェックボックス。

![](assets/offer-json-filter.png)
