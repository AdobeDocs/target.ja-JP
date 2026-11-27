---
keywords: ターゲティング；コリジョン；競合
description: Adobe Targetでアクティビティを正しく設定することで、同じページでのコンテンツ配信の競合を防ぎます。
title: アクティビティの競合を回避するにはどうすればよいですか？
feature: Visual Experience Composer (VEC)
exl-id: 1af90dd1-69c9-41ec-8785-095dcc557b32
TQID: 'https://experienceleague.adobe.com/R6cwp4KnoYPO9Wxr47HswtBX6jKPJ0i-UGdtA1ZHawU'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 18%
---
# アクティビティの衝突 {#activity-collisions}

>[!BEGINSHADEBOX]

**このページ：** 「**[!UICONTROL 衝突]**」タブを使用して、同じページにコンテンツを配信する可能性のあるアクティビティを検索する方法を説明します。

>[!ENDSHADEBOX]

アクティビティの衝突は、複数のアクティビティが同じページにコンテンツを配信するよう設定されているときに発生します。 アクティビティの衝突が発生した場合、予想されるコンテンツがページに表示されない可能性があります。

[!DNL Adobe Target]の&#x200B;**[!UICONTROL アクティビティの概要]** ページの&#x200B;**[!UICONTROL 衝突]** タブには、サイト上のアクティビティの衝突が一覧表示され、アクティビティに潜在的な衝突が含まれているかどうかが表示されます。 **[!UICONTROL コリジョン]**&#x200B;のリストは、次の操作に役立ちます。

* 新しいアクティビティを設定する前に、テストがページ上で既に実行されているかどうかを識別します
* コンテンツが期待どおりに表示されない場合に、アクティビティのトラブルシューティングをおこなうことができます。

## 「Collisions」タブにアクセスします {#access-collisions}

**[!UICONTROL アクティビティ]**&#x200B;をクリックし、リストから目的のアクティビティをクリックしてから、**[!UICONTROL 衝突]** メニューにアクセスします。

![ アイコンの設定](assets/collisions_1.png)

各アクティビティのオーディエンスのターゲット設定にかかわらず、同じ URL のすべてのアクティビティが一覧表示されます。 このタブには、衝突している可能性のあるアクティビティが一覧表示されます。 衝突によって期待したエクスペリエンスが表示されない場合は、アクティビティを編集します。

## コリジョン リストを読む {#collisions-list}

**[!UICONTROL 衝突]** リストには、mboxが使用され、同じURLを使用する[!DNL Target]個のシナリオが表示されます。 衝突が発生する可能性がある場合、リストにはアクティビティ URL、衝突が発生する可能性のあるmbox名、およびそれらの両方の条件に一致するアクティビティが表示されます。 複数の mbox がある場合は、すべての mbox が一覧表示されます。

このリストには、潜在的な衝突のステータスと優先度のほか、他の情報も表示されます。 ステータスと優先度は、衝突が発生する可能性を判断するのに役立ちます。 衝突する可能性のある2つのアクティビティ：

* 1つのアクティビティが現在アクティブでない場合、衝突は発生しません。 衝突は、非アクティブなアクティビティがアクティブになった場合にのみ可能です。
* 同じ優先度と同じオーディエンスを持つ2つのライブアクティビティ間で衝突が発生する可能性がある場合、衝突が発生します。 優先度またはステータスは、衝突を防ぐために変更できます。
* オーディエンスが異なる場合、特定の訪問者が複数のオーディエンスに属している可能性があるため、衝突する可能性があります。
