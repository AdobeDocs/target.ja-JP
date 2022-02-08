---
keywords: テンプレートテスト;テンプレート;類似のページと同じエクスペリエンス;テンプレートテスト
description: Adobe [!DNL Target] Visual Experience Composer(VEC) を使用して、同じ構造の複数のページに同じエクスペリエンスを組み込むか、同じテンプレート要素を含めます。
title: 類似のページに同じエクスペリエンスを組み込むことはできますか？
feature: Experiences and Offers
exl-id: 4ea95794-496c-4eff-96ec-8a9d1f732c4a
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '617'
ht-degree: 46%

---

# 類似のページに同じエクスペリエンスを組み込む

でのページテンプレートの使用 [!DNL Adobe Target] ページの構造を指定する場合、またはページに類似の要素が含まれている場合は、同様に構造化されたページ要素内やドメイン全体のバリエーションをテストする場合に使用します。

この機能を正しく機能させるには、構造が同じページまたはすべてのページで同じ構造を持つテンプレート要素を含むページで使用する必要があります。

>[!IMPORTANT]
>
>この機能を使用して構造の似ていないページの要素を変更すると、予期しない結果が発生する可能性が高くなります。

例えば、この機能を使用して次のような操作を実行できます。

* 要素を並べ替えたり、削除したりして、グローバルナビゲーションバーをテストします。
* 特定のページテンプレートを使用するすべての製品ページから、アイテムを削除します。
* すべての製品ページにバナーを追加します。
* 記事テンプレートのレイアウトを変更します。

要素の変更を含むページを指定することも、サイトやドメイン全体に変更を適用することもできます。

1. アクティビティの作成または編集 ( [アクティビティ](/help/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03).

1. エクスペリエンスが表示されるページを [!UICONTROL Visual Experience Composer] (VEC) 歯車アイコンをクリックし、 **[!UICONTROL ページ配信]**.

   ![歯車アイコン/ページ配信](/help/c-experiences/c-visual-experience-composer/assets/icon-gear.png)

1. 「**[!UICONTROL テンプレートルールを追加]**」をクリックし、エクスペリエンスを追加するページの条件を指定します。

1. ページの範囲を指定します。ページの範囲は、次のいずれかの方法で指定します。

   * URL (For more information about how Target evaluates URLs, see [Targets and audiences FAQ](/help/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md).)
   * ドメイン
   * パス
   * ハッシュ (#) フラグメント（#記号に続く URL の部分をターゲットにします）。
   * クエリ
   * パラメーター

1. 演算子を選択します。

   演算子は、演算子の後ろに指定された項目がどのようにページ範囲を規定するかを指定するものです。Available operators include:

   * 次を含む
   * 次を含まない
   * 等しい (大文字と小文字を区別)
   * 次とまったく一致しない
   * 次の語句で始まる
   * 次の語句で終わる

1. ドメインや、ページ名に含まれる文字列など、エクスペリエンスを追加する場所を定義する文字列を入力します。

   例えば、「**[!UICONTROL ドメイン]**」および「**[!UICONTROL 等しい (大文字と小文字を区別)]**」を選択した場合は、すべてのページにエクスペリエンスを追加するドメインを入力します。

   複数の項目を指定することができます。

   >[!IMPORTANT]
   >
   >Multiple items use OR logic, meaning that any single item in the list makes the condition true.

1. 必要に応じて、「 **[!UICONTROL テンプレートルールを追加]** 上記の手順を繰り返します。

   複数の条件は AND のロジックで連結されます。[!DNL Target] では、指定した条件に一致するすべてのページにエクスペリエンスが追加されます。

>[!IMPORTANT]
>
> [!DNL Target] では、ページが想定どおりに表示されるかどうかを自動的には確認できません。そのため、この機能を使用する場合は、ページを公開する前に、該当するページをテストしておくことが重要です。

## 使用例

サイトでテンプレートルールを使用する方法については、次の使用例を確認してください。

### ドメイン全体で同じアクティビティをレンダリングする

You might consider using template rules to render the same activity across your entire domain for the following use cases:

* グローバルヘッダーまたはフッターを含めるには
* グローバルバナーを含める（COVID-19 のお知らせなど）
* グローバルな送料無料プロモーションを含めるには

1. アクティビティの作成または編集 ( [アクティビティ](/help/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03).

1. エクスペリエンスが表示されるドメインを指定するには、Visual Experience Composer で歯車アイコンをクリックし、 **[!UICONTROL ページ配信]**.

1. クリック **[!UICONTROL テンプレートルールを追加]** > **[!UICONTROL ドメイン]**.

1. 次の **[!UICONTROL 評価基準を選択]** ドロップダウンで、「 **[!UICONTROL 次を含む]**、ドメインを指定します。

   ![ドメインに含む](/help/c-experiences/c-visual-experience-composer/assets/domain-template-rule.png)

## Training video: Visual Experience Composer (2 of 2) (7:29) ![Tutorial badge](/help/assets/tutorial.png)

* エクスペリエンスの名前の変更と複製
* リダイレクトエクスペリエンスの作成
* 単一の URL または URL のグループに対するアクティビティのターゲット化
* 複数ページのアクティビティの作成
* レスポンシブ Web サイト用のエクスペリエンスのプレビューおよび構築
* オーバーレイを使用した要素のタイプのハイライト

>[!VIDEO](https://video.tv.adobe.com/v/17401)
