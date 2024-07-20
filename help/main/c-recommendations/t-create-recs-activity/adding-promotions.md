---
keywords: プロモーション；フロントプロモーション；バックプロモーション；プロモーションタイプ；項目のリスト；属性別に昇格；コレクションを昇格
description: プロモーション対象のアイテムを追加し、Adobeの  [!DNL Target] Recommendations デザインでの配置を制御する方法について説明します。 静的なプロモーションおよび動的なプロモーションを追加できます。
title: Recommendations デザインでプロモーションを追加するにはどうすればよいですか？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
exl-id: bd5e5e12-a712-4c4c-9cf8-6b0f4834067b
source-git-commit: 07062b7df75300bd7558a24da5121df454520e42
workflow-type: tm+mt
source-wordcount: '637'
ht-degree: 42%

---

# プロモーションの追加

プロモーション対象のアイテムを追加し、[!DNL Adobe Target Recommendations] デザインでの配置を制御します。 静的なプロモーションおよび動的なプロモーションを追加できます。

>[!IMPORTANT]
>
>静的および動的な除外ルールは、マーケティングに役立つ便利な機能です。詳細、例およびユースケースシナリオについては、[ 動的および静的インクルージョンルールの使用 ](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F) を参照してください。

[!DNL Recommendations] アクティビティを作成するときは、[!DNL Recommendations] デザインにプロモーション項目を含めることができます。プロモーションは、デザインの使用可能なスロットを使用し、条件の結果およびバックアップレコメンデーションよりも優先されます。例えば、デザインに 6 つのスロットがあり、そのうち 2 つをプロモーションに使用した場合、条件に基づいてレコメンデーションされる項目に 4 つのスロットを使用できます。

プロモーションは、アクティビティの条件で推奨された項目に対して重複排除されるので、特定の項目が 1 つのレコメンデーショントレイに 2 回表示されることはありません。

特定の項目をプロモーションしたり、動的に項目をプロモーションしたり、属性に基づいて項目をプロモーションすることができます。また、コレクションをプロモーションすることもできます。

[!DNL Target] UI の ![[!UICONTROL Front Promotion] および [!UICONTROL Back Promotion] オプション ](assets/add_promotion_toggles.png)

>[!NOTE]
>
>プロモーションを使用すると、CSV の構造と出力が変更されます。この変更により、電子メールなど、CSV に関連する外部プロセスが影響を受ける可能性があります。

1. **[!UICONTROL Options]** ページで、「**[!UICONTROL Front Promotion]**」または「**[!UICONTROL Back Promotion]**」の切り替えスイッチをクリックします。

   次の図は、「オン」の位置にある「[!UICONTROL Front Promotion]」トグル切り替えスイッチを示しています。

   ![「プロモーション - 前」オプションを追加](/help/main/c-recommendations/t-create-recs-activity/assets/add_promotion_front.png)

   条件の結果の前と&#x200B;**&#x200B;後のどちらにもプロモーションを挿入できます。

1. プロモーション項目に使用するデザインスロットの数を設定します。

   [!DNL Recommendations] デザインによりますが、最大で 20 個のスロットを使用できます。使用した各スロットは、条件に基づいて返されたレコメンデーションには使用できません。

1. プロモーション項目の開始日と終了日を設定します。

   開始日を設定しない場合、プロモーションはすぐに開始されます。終了日を設定しない場合、プロモーションは無期限に実行されます。

1. **[!UICONTROL Promotion Type]** を選択します。

   * 「**[!UICONTROL List of items]**」を選択し、昇格させる特定の項目の `entity.id` 値をコンマで区切って入力します。

   * 「**[!UICONTROL Promote by attribute]**」を選択してルールを追加し、昇格させる項目の属性を定義します。

     [!UICONTROL Promote by Attribute] を選択すると、動的一致を作成できます。 詳しくは、[ 動的および静的インクルージョンルールの使用 ](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F) を参照してください。

   * 「**[!UICONTROL Promote a collection]**」を選択し、昇格させる項目のコレクションを選択します。

     プロモーションに使用する新しいコレクションを作成できます。詳しくは、[ コレクションの作成 ](/help/main/c-recommendations/c-products/collections.md#task_1256DFF6842141FCAADD9E1428EF7F08) を参照してください。

   **[!UICONTROL Promotion Type]** として **[!UICONTROL List of Items]** を選択した場合は、必要に応じて「**[!UICONTROL Randomize Item Order]**」チェックボックスを選択できます。

   [!UICONTROL List of Items] のデフォルトの並べ替え順は、[!DNL Target] UI または API で入力した順序に基づいています。 リストに、プロモーション用に設定したスロット数よりも多くの項目が含まれている場合、[[!UICONTROL Randomize Item Order]] オプションを選択すると、デザインに表示されるプロモーションされた項目がランダムに表示されます。 このオプションを選択する [!DNL Target]、各ヒットに設定されたプロモーション全体から、テンプレートでプロモーションが有効になっている項目がランダムに選択されます。

   エンティティに `entity.value` 属性がない場合（製品を販売していない場合など）は、公開日などの数値を `entity.value` 属性に渡すことができます。 この場合、昇格されたアイテムは、最新の公開日を基準として、降順で昇格させることができます。 `entity.value` 属性の型は double です。文字列は受け付けられません。

   「**[!UICONTROL Promote by Attribute]**」または「**[!UICONTROL Promote a Collection]**」オプションを選択した場合、順序をランダム化するオプションは適用されません。

   [!UICONTROL Promote by Attribute] または [!UICONTROL Promote a Collection] オプションを使用して特定の項目を昇格させる場合、項目が表示されるデフォルトの順序は、`entity.value` 属性に基づいて、降順で示されます。

   次の表に、これらのオプションの違いを示します。

   | プロモーションのタイプ | デフォルトの並べ替え | バックアップの並べ替え | 動的フィルターオプション |
   | --- | --- | --- | --- |
   | [!UICONTROL List of Items] | Target UI/API で入力された順序 | ランダム（UI/API 経由で選択した場合） | × |
   | [!UICONTROL Promote by Attribute] | `entity.value` （降順） | ランダム化なし | ○ |
   | [!UICONTROL Promote a Collection] | `entity.value` （降順） | ランダム化なし | × |

1. **[!UICONTROL Save]** をクリックします。

プロモーションはアクティビティのすべてのエクスペリエンスに適用されます。
