---
keywords: プロモーション；フロントプロモーション；バックプロモーション；プロモーションタイプ；アイテムのリスト；属性によるプロモーション；コレクションのプロモーション
description: Adobe [!DNL Target] Recommendations デザインで、プロモーションされたアイテムを追加し、その配置を制御する方法について説明します。 静的なプロモーションおよび動的なプロモーションを追加できます。
title: レコメンデーションデザインにプロモーションを追加するにはどうすればよいですか？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
exl-id: bd5e5e12-a712-4c4c-9cf8-6b0f4834067b
TQID: https://experienceleague.adobe.com/tAfKOzwjnUJgypDh-4LdVukNlTVwMS4UkvcNmCaCV0E
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 709
ht-degree: 44%

---

# プロモーションの追加

プロモーションされたアイテムを追加し、[!DNL Adobe Target Recommendations] デザインでの配置を制御します。 静的なプロモーションおよび動的なプロモーションを追加できます。

>[!IMPORTANT]
>
>静的および動的な除外ルールは、マーケティングに役立つ便利な機能です。 詳細、例、ユースケースのシナリオについては、[動的および静的インクルージョンルールの使用](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F)を参照してください。

[!DNL Recommendations] アクティビティを作成するときは、[!DNL Recommendations] デザインにプロモーション項目を含めることができます。 プロモーションは、デザインの使用可能なスロットを使用し、条件の結果およびバックアップレコメンデーションよりも優先されます。 例えば、デザインに 6 つのスロットがあり、そのうち 2 つをプロモーションに使用した場合、条件に基づいてレコメンデーションされる項目に 4 つのスロットを使用できます。

プロモーションは、アクティビティの条件で推奨された項目に対して重複排除されるので、特定の項目が 1 つのレコメンデーショントレイに 2 回表示されることはありません。

特定の項目をプロモーションしたり、動的に項目をプロモーションしたり、属性に基づいて項目をプロモーションすることができます。また、コレクションをプロモーションすることもできます。

[!DNL Target]UI![&#128279;](assets/add_promotion_toggles.png)の[!UICONTROL &#x200B; フロントプロモーション &#x200B;]および[!UICONTROL &#x200B; バックプロモーション &#x200B;] オプション

>[!NOTE]
>
>プロモーションを使用すると、CSV の構造と出力が変更されます。 この変更により、電子メールなど、CSV に関連する外部プロセスが影響を受ける可能性があります。

1. **[!UICONTROL オプション]** ページで、**[!UICONTROL フロントプロモーション]**&#x200B;または&#x200B;**[!UICONTROL バックプロモーション]** トグルをクリックします。

   次の図は、「オン」位置の[!UICONTROL &#x200B; フロントプロモーション &#x200B;] トグルを示しています。

   ![「プロモーション - 前」オプションを追加](/help/main/c-recommendations/t-create-recs-activity/assets/add_promotion_front.png)

   条件の結果の前と&#x200B;**&#x200B;後のどちらにもプロモーションを挿入できます。

1. プロモーション項目に使用するデザインスロットの数を設定します。

   [!DNL Recommendations] デザインによりますが、最大で 20 個のスロットを使用できます。 使用した各スロットは、条件に基づいて返されたレコメンデーションには使用できません。

1. プロモーション項目の開始日と終了日を設定します。

   開始日を設定しない場合、プロモーションはすぐに開始されます。 終了日を設定しない場合、プロモーションは無期限に実行されます。

1. **[!UICONTROL プロモーションタイプ]**&#x200B;を選択します。

   * **[!UICONTROL 項目のリスト]**&#x200B;を選択し、昇格する特定の項目の`entity.id`値をコンマで区切って入力します。

   * 「**[!UICONTROL 属性別にプロモート]**」を選択し、プロモーションする項目の属性を定義するルールを追加します。

     [!UICONTROL 属性によるプロモーション &#x200B;]を選択すると、動的な一致を作成できます。 詳しくは、[動的および静的インクルージョンルールの使用](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F)を参照してください。

   * 「**[!UICONTROL コレクションをプロモート]**」を選択し、プロモーションする項目のコレクションを選択します。

     プロモーションに使用する新しいコレクションを作成できます。 詳しくは、[&#x200B; コレクションの作成](/help/main/c-recommendations/c-products/collections.md#task_1256DFF6842141FCAADD9E1428EF7F08)を参照してください。

   **[!UICONTROL プロモーションタイプ]**&#x200B;として&#x200B;**[!UICONTROL アイテムのリスト]**&#x200B;を選択した場合、必要に応じて「**[!UICONTROL アイテムの順序をランダム化]**」チェックボックスを選択できます。

   [!UICONTROL &#x200B; アイテムのリスト &#x200B;]のデフォルトの並べ替え順序は、[!DNL Target] UIまたはAPIで入力した順序に基づいています。 リストに、プロモーション用に設定したスロット数を超えるアイテムが含まれる場合、[!UICONTROL &#x200B; アイテムの順序をランダム化] オプションは、デザインに表示されるプロモーションされたアイテムをランダム化します。 このオプションを選択すると、テンプレート内のプロモーションに対して有効なアイテムが、各ヒットに設定されたプロモーションセット全体から[!DNL Target]個ランダムに選択されます。

   エンティティに`entity.value`属性がない場合（たとえば、製品を販売していない場合）、公開日など、`entity.value`属性に数値を渡すことができます。 この場合、最新の公開日に基づいて、昇格された項目を降順で昇格させることができます。 `entity.value`属性はdouble タイプです。文字列は受け付けません。

   **[!UICONTROL 属性で昇格]**&#x200B;または&#x200B;**[!UICONTROL コレクションを昇格]** オプションを選択した場合、注文をランダム化するオプションは適用されません。

   [!UICONTROL 属性で昇格]または[!UICONTROL &#x200B; コレクションを昇格] オプションを使用して特定のアイテムを昇格する場合、アイテムが表示されるデフォルトの順序は、降順の`entity.value`属性に基づきます。

   次の表に、これらのオプションの違いを示します。

   | プロモーションタイプ | デフォルトの並べ替え | バックアップの並べ替え | 動的フィルターオプション |
   | --- | --- | --- | --- |
   | [!UICONTROL 項目のリスト &#x200B;] | Target UI/APIに入力された順序 | ランダム（UI/APIで選択した場合） | × |
   | [!UICONTROL 属性によるプロモーション &#x200B;] | `entity.value` （降順） | ランダム化なし | ○ |
   | [!UICONTROL &#x200B; コレクションのプロモーション &#x200B;] | `entity.value` （降順） | ランダム化なし | × |

1. 「**[!UICONTROL 保存]**」をクリックします。

プロモーションはアクティビティのすべてのエクスペリエンスに適用されます。
