---
keywords: template testing;template;same experience on similar pages;template test
description: Adobe Targetのページテンプレートを使用して、ページの構造を作成したり、ページに類似の要素が含まれる場合は、類似の構造を持つページ要素のバリエーションをテストしたりします。
title: Adobe Targetを使用して、類似のページに同じエクスペリエンスを組み込む
feature: experiences
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '608'
ht-degree: 45%

---


# 類似のページに同じエクスペリエンスを組み込む

ページに構造を提供す [!DNL Adobe Target] る場合、またはページに類似の要素が含まれる場合は、でページテンプレートを使用して、同様に構造化されたページ要素内またはドメイン全体のバリエーションをテストします。

正しく機能させるには、この機能を、構造が似ているページ、または構造が同じテンプレート要素を含むページですべてのページで使用する必要があります。

>[!IMPORTANT]
>
>この機能を使用して構造の似ていないページの要素を変更すると、予期しない結果が発生する可能性が高くなります。

例えば、この機能を使用して次のような操作を実行できます。

* 要素を並べ替えたり、削除したりして、グローバルナビゲーションバーをテストします。
* 特定のページテンプレートを使用するすべての製品ページから、アイテムを削除します。
* すべての製品ページにバナーを追加します。
* 記事テンプレートのレイアウトを変更します。

要素の変更を含むページを指定するか、サイトまたはドメイン全体に変更を適用できます。

1. [アクティビティの説明に従って、アクティビティを作成または編集します](/help/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)。

1. To specify the pages where the experience will appear, in the [!UICONTROL Visual Experience Composer] (VEC) click the gear icon, then select **[!UICONTROL Page Delivery]**.

   ![歯車アイコン/ページ配信](/help/c-experiences/c-visual-experience-composer/assets/icon-gear.png)

1. 「**[!UICONTROL テンプレートルールを追加]**」をクリックし、エクスペリエンスを追加するページの条件を指定します。

1. ページの範囲を指定します。ページの範囲は、次のいずれかの方法で指定します。

   * URL (ターゲットがURLを評価する方法について詳しくは、 [ターゲットとオーディエンスに関するFAQ](/help/c-target/c-troubleshooting-targets-and-audiences/troubleshooting-targets-and-audiences.md))。
   * ドメイン
   * パス
   * ハッシュ(#)フラグメント(#記号に続くURLの部分をターゲット)
   * クエリ
   * パラメーター

1. 演算子を選択します。

   演算子は、演算子の後ろに指定された項目がどのようにページ範囲を規定するかを指定するものです。次の演算子を使用できます。

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
   >複数の項目でORロジックが使用されます。つまり、リスト内の任意の項目が条件を満たすと見なされます。

1. If desired, enter additional criteria by clicking **[!UICONTROL Add Template Rule]** and repeating the procedure in the previous steps.

   複数の条件は AND のロジックで連結されます。[!DNL Target] では、指定した条件に一致するすべてのページにエクスペリエンスが追加されます。

>[!IMPORTANT]
>
> [!DNL Target] では、ページが想定どおりに表示されるかどうかを自動的には確認できません。そのため、この機能を使用する場合は、ページを公開する前に、該当するページをテストしておくことが重要です。

## 使用例

サイトでテンプレートルールを使用する方法について、次の使用例を確認します。

### ドメイン全体で同じアクティビティをレンダリングする

テンプレートルールを使用して、次のような使用例で、ドメイン全体に同じアクティビティをレンダリングすることを検討できます。

* グローバルヘッダーまたはグローバルフッターを含めるには
* グローバルバナーを含めるには（例えば、COVID-19のお知らせ）
* グローバルな無料配送プロモーションを含めるには

1. [アクティビティの説明に従って、アクティビティを作成または編集します](/help/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)。

1. To specify the domain where the experience will appear, in the Visual Experience Composer click the gear icon, then select **[!UICONTROL Page Delivery]**.

1. テン **[!UICONTROL プレートルール]** / **[!UICONTROL ドメイン]**&#x200B;をクリックします。

1. 「評価基準を **[!UICONTROL 選択]** 」ドロップダウンから「 **[!UICONTROL 次を含む」を選択し]**、ドメインを指定します。

   ![ドメインに次を含む](/help/c-experiences/c-visual-experience-composer/assets/domain-template-rule.png)

## Training video: Visual Experience Composer (2 of 2) (7:29) ![Tutorial badge](/help/assets/tutorial.png)

* エクスペリエンスの名前の変更と複製
* リダイレクトエクスペリエンスの作成
* 単一の URL または URL のグループに対するアクティビティのターゲット化
* 複数ページのアクティビティの作成
* レスポンシブ Web サイト用のエクスペリエンスのプレビューおよび構築
* オーバーレイを使用した要素のタイプのハイライト

>[!VIDEO](https://video.tv.adobe.com/v/17401)