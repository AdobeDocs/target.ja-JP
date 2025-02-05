---
keywords: テンプレートテスト;テンプレート;類似のページと同じエクスペリエンス;テンプレートテスト
description: Adobe [!DNL Target] Visual Experience Composer （VEC）を使用して、同様に構造化された複数のページや、同じテンプレート要素を含む複数のページに同じエクスペリエンスを含める方法を説明します。
title: 類似のページに同じエクスペリエンスを組み込むことはできますか？
feature: Experiences and Offers
exl-id: 4ea95794-496c-4eff-96ec-8a9d1f732c4a
source-git-commit: be9996c4dce0a3135a39fcbf0608b57b6e742ac3
workflow-type: tm+mt
source-wordcount: '517'
ht-degree: 24%

---

# 類似のページに同じエクスペリエンスを組み込む

[!DNL Adobe Target] のページテンプレートを使用してページに構造を提供するか、ページに類似の要素が含まれている場合は、類似した構造のページ要素またはドメイン全体でのバリエーションをテストします。

正しく機能させるには、構造が類似しているページや、すべてのページで構造が同じテンプレート要素を含むページでこの機能を使用する必要があります。

>[!IMPORTANT]
>
>この機能を使用して、異なる類似ページ間で要素を変更すると、予期しない結果が生じる可能性があります。

例えば、この機能を使用して次のような操作を実行できます。

* 要素を並べ替えたり、削除したりして、グローバルナビゲーションバーをテストします。
* 特定のページテンプレートを使用するすべての製品ページから、アイテムを削除します。
* すべての製品ページにバナーを追加します。
* 記事テンプレートのレイアウトの変更

変更要素を含むページを指定するか、サイトまたはドメイン全体に変更を適用できます。

1. [ アクティビティ ](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03) の説明に従って、アクティビティを作成または編集します。

1. エクスペリエンスが表示されるページを指定するには、[!UICONTROL Visual Experience Composer] （VEC）で「[!UICONTROL Configure]」アイコン（![ 設定アイコン ](/help/main/assets/icons/Setting.svg)）をクリックし、「**[!UICONTROL Page Delivery]**」を選択します。

1. 「**[!UICONTROL Add Rule]**」をクリックして、エクスペリエンスを追加するページの条件を指定します。

1. ページの範囲を指定します。ページの範囲は、次のいずれかの方法で指定します。

   * [!UICONTROL URL] （[!DNL Target] による URL の評価方法について詳しくは、[ ターゲットとオーディエンスに関する FAQ](/help/main/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md) を参照してください）。
   * [!UICONTROL Domain]
   * [!UICONTROL Path]
   * [!UICONTROL Hash (#) Fragment] （#記号に続く URL の部分をターゲットにします）
   * [!UICONTROL Query]
   * [!UICONTROL Custom]

1. 演算子を選択します。

   演算子は、演算子の後ろに指定された項目がどのようにページ範囲を規定するかを指定するものです。使用可能な演算子は次のとおりです。

   * [!UICONTROL Contains]
   * [!UICONTROL Does not contain]
   * [!UICONTROL Is (case sensitive)]
   * [!UICONTROL Is not]
   * [!UICONTROL Starts with]
   * [!UICONTROL Ends with]

1. ドメインや、ページ名に含まれる文字列など、エクスペリエンスを追加する場所を定義する文字列を入力します。

   例えば、「**[!UICONTROL Domain]**」と「**[!UICONTROL Is (case sensitive)]**」を選択した場合、エクスペリエンスをすべてのページに追加するドメインを入力します。

   複数の項目を指定することができます。

   >[!IMPORTANT]
   >
   >複数の項目が OR ロジックを使用しています。つまり、リスト内の 1 つの項目によって条件が true になります。

1. 必要に応じて、「**[!UICONTROL Add Rule]**」をクリックして前の手順を繰り返し、追加の基準を入力します。

   複数の条件は AND のロジックで連結されます。指定 [!DNL Target] た条件に一致するすべてのページにエクスペリエンスが追加されます。

>[!IMPORTANT]
>
> ページが期待どおりに表示 [!DNL Target] れるかどうかを確認することはできないので、この機能を使用して影響を受けるページを公開する前にテストすることは、常に重要なプラクティスです。

## 使用例

サイトでテンプレートルールを使用する方法については、次のユースケースを確認してください。

### ドメイン全体で同じアクティビティをレンダリングする

次のユースケースでは、テンプレートルールを使用して、ドメイン全体で同じアクティビティをレンダリングすることを検討してください。

* グローバルヘッダーまたはグローバルフッターを組み込むには
* グローバルバナー（COVID-19 のお知らせなど）を含める
* グローバルな送料無料プロモを組み込むには

1. [ アクティビティ ](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03) の説明に従って、アクティビティを作成または編集します。

1. エクスペリエンスが表示されるドメインを指定するには、エクスペリ [!UICONTROL Visual Experience Composer] ンスで [!UICONTROL Configure] 定アイコン（![ 設定アイコン ](/help/main/assets/icons/Setting.svg)）をクリックし、「**[!UICONTROL Page Delivery]**」を選択します。

1. **[!UICONTROL Add Rule]**／**[!UICONTROL Domain]**&#x200B;をクリックします。

1. **[!UICONTROL Choose evaluator]** ドロップダウンから「**[!UICONTROL Contains]**」を選択し、ドメインを指定します。
