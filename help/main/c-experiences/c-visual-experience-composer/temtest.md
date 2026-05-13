---
keywords: テンプレートテスト;テンプレート;類似のページと同じエクスペリエンス;テンプレートテスト
description: Adobe [!DNL Target] Visual Experience Composer （VEC）を使用して、同じ構造の複数のページ、または同じテンプレート要素を含む複数のページに同じエクスペリエンスを含める方法を説明します。
title: 同様のページに同じエクスペリエンスを含めることはできますか？
feature: Experiences and Offers
exl-id: 4ea95794-496c-4eff-96ec-8a9d1f732c4a
TQID: https://experienceleague.adobe.com/zk7U6g7gk7XkpWsEFQbwuCm7xbpIb1lCaZefxjn-39g
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 518
ht-degree: 24%

---

# 類似のページに同じエクスペリエンスを組み込む

[!DNL Adobe Target]でページテンプレートを使用して、ページに構造を提供するか、ページに類似した要素が含まれている場合は、類似した構造化ページ要素またはドメイン全体でバリエーションをテストします。

この機能を正しく機能させるには、構造が類似しているページや、すべてのページで同じ構造のテンプレート要素が含まれているページで使用する必要があります。

>[!IMPORTANT]
>
>この機能を使用して、異なるページ間で要素を変更すると、予期しない結果が発生する可能性があります。

例えば、この機能を使用して次のような操作を実行できます。

* 要素を並べ替えたり、削除したりして、グローバルナビゲーションバーをテストします。
* 特定のページテンプレートを使用するすべての製品ページから、アイテムを削除します。
* すべての製品ページにバナーを追加します。
* 記事テンプレートのレイアウトの変更

変更要素を含むページを指定するか、サイトまたはドメイン全体に変更を適用できます。

1. 「[ アクティビティ ](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)」の説明に従って、アクティビティを作成または編集します。

1. エクスペリエンスが表示されるページを指定するには、[!UICONTROL Visual Experience Composer] （VEC）で[!UICONTROL Configure] アイコン（![設定アイコン ](/help/main/assets/icons/Setting.svg)）をクリックし、**[!UICONTROL Page Delivery]**&#x200B;を選択します。

1. 「**[!UICONTROL Add Rule]**」をクリックし、エクスペリエンスを追加するページの条件を指定します。

1. ページの範囲を指定します。 ページの範囲は、次のいずれかの方法で指定します。

   * [!UICONTROL URL] （[!DNL Target]がURLを評価する方法について詳しくは、[ ターゲットとオーディエンスに関するFAQ](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md)を参照してください）。
   * [!UICONTROL Domain]
   * [!UICONTROL Path]
   * [!UICONTROL Hash (#) Fragment] （#記号に続くURLの部分をターゲットにします）
   * [!UICONTROL Query]
   * [!UICONTROL Custom]

1. 演算子を選択します。

   演算子は、演算子の後ろに指定された項目がどのようにページ範囲を規定するかを指定するものです。 使用可能な演算子は次のとおりです。

   * [!UICONTROL Contains]
   * [!UICONTROL Does not contain]
   * [!UICONTROL Is (case sensitive)]
   * [!UICONTROL Is not]
   * [!UICONTROL Starts with]
   * [!UICONTROL Ends with]

1. ドメインや、ページ名に含まれる文字列など、エクスペリエンスを追加する場所を定義する文字列を入力します。

   例えば、**[!UICONTROL Domain]**&#x200B;と&#x200B;**[!UICONTROL Is (case sensitive)]**&#x200B;を選択した場合は、エクスペリエンスをすべてのページに追加するドメインを入力します。

   複数の項目を指定することができます。

   >[!IMPORTANT]
   >
   >複数の項目はOR ロジックを使用します。つまり、リスト内の単一の項目が条件をtrueにします。

1. 必要に応じて、**[!UICONTROL Add Rule]**&#x200B;をクリックし、前の手順で手順を繰り返して、追加の条件を入力します。

   複数の条件は AND のロジックで連結されます。 [!DNL Target]は、指定された条件に一致するすべてのページにエクスペリエンスを追加します。

>[!IMPORTANT]
>
> [!DNL Target]はページを確認して、期待どおりに表示できるかどうかを確認できません。そのため、この機能を使用して影響を受けるページを公開する前にテストする場合は、常に重要な手順です。

## ユースケース

サイトでテンプレートルールを使用する方法については、次のユースケースを確認してください。

### ドメイン全体で同じアクティビティをレンダリングします

次のユースケースでは、テンプレートルールを使用して、ドメイン全体で同じアクティビティをレンダリングすることをお勧めします。

* グローバルヘッダーまたはフッターを含めるには
* グローバルバナー（COVID-19の発表など）を含めるには
* グローバルな送料無料プロモーションを含めるには

1. 「[ アクティビティ ](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)」の説明に従って、アクティビティを作成または編集します。

1. エクスペリエンスが表示されるドメインを指定するには、[!UICONTROL Visual Experience Composer]で[!UICONTROL Configure] アイコン（![設定アイコン ](/help/main/assets/icons/Setting.svg)）をクリックし、**[!UICONTROL Page Delivery]**&#x200B;を選択します。

1. **[!UICONTROL Add Rule]**／**[!UICONTROL Domain]**&#x200B;をクリックします。

1. 「**[!UICONTROL Choose evaluator]**」ドロップダウンから「**[!UICONTROL Contains]**」を選択し、ドメインを指定します。
