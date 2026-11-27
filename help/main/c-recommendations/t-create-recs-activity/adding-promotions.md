---
keywords: プロモーション；フロントプロモーション；バックプロモーション；プロモーションタイプ；アイテムのリスト；属性によるプロモーション；コレクションのプロモーション
description: Adobe [!DNL Target] Recommendations デザインで、プロモーションされたアイテムを追加し、その配置を制御する方法について説明します。 静的なプロモーションおよび動的なプロモーションを追加できます。
title: レコメンデーションデザインにプロモーションを追加するにはどうすればよいですか？
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
exl-id: bd5e5e12-a712-4c4c-9cf8-6b0f4834067b
TQID: 'https://experienceleague.adobe.com/tAfKOzwjnUJgypDh-4LdVukNlTVwMS4UkvcNmCaCV0E'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '695'
ht-degree: 6%
---
# プロモーションの追加 {#add-promotions}

>[!BEGINSHADEBOX]

**このページ：**&#x200B;では、プロモートされたアイテムを[!DNL Recommendations] デザインに追加する方法と、それらの並べ替え順序の決定方法について説明します。

>[!ENDSHADEBOX]

プロモーションでは、条件で推奨されるアイテムに加えて、特定のアイテムを[!DNL Recommendations] デザインに配置します。 設計で使用可能なスロットを使用し、基準の結果とバックアップの推奨事項よりも優先されます。 例えば、デザインに6つのスロットがあり、そのうちの2つがプロモーションに使用されている場合、基準に基づいて推奨されるアイテムには4つのスロットが残ります。

プロモーションは、アクティビティの基準で推奨されるアイテムに対して重複排除されるので、特定のアイテムが1つのレコメンデーショントレイに2回表示されることはありません。

![&#x200B; フロントプロモーションとバックプロモーションの切り替えをオフにしたプロモーションダイアログの変更](assets/add_promotion_toggles.png)

>[!NOTE]
>
>プロモーションを使用すると、CSV構造と出力が変更されます。 これらの変更は、電子メールなど、CSVを含むあらゆる外部プロセスに影響を与える可能性があります。

## プロモーションを追加 {#add-promotion}

プロモーションでは、プロモーションするアイテム、使用するデザインスロットの数、表示する期間を定義します。

1. **[!UICONTROL オプション]** ページで、**[!UICONTROL フロントプロモーション]**&#x200B;または&#x200B;**[!UICONTROL バックプロモーション]** トグルをクリックします。

   次の図は、「オン」位置の&#x200B;**[!UICONTROL フロントプロモーション]** トグルを示しています。 プロモーションは、条件の結果の前と後の両方に挿入できます。

   ![&#x200B; フロントプロモーショントグルをオンにしてプロモーションダイアログを変更し、デザインスロット数、スケジュール数、プロモーションタイプのオプションを表示](/help/main/c-recommendations/t-create-recs-activity/assets/add_promotion_front.png)

1. プロモートされたアイテムに使用するデザインスロットの数&#x200B;**[!UICONTROL 個]**&#x200B;を設定します。

   [!DNL Recommendations]のデザインに応じて、最大20個のスロットを使用できます。 使用されている各スロットは、条件に基づいて返される推奨事項に使用できなくなります。

1. プロモ – ションされたアイテムの&#x200B;**開始**&#x200B;日と&#x200B;**終了**&#x200B;日を設定します。

   開始日が設定されていない場合、プロモーションはすぐに開始されます。 終了日が設定されていない場合、プロモーションは無期限に実行されます。

1. **[!UICONTROL プロモーションタイプ]**&#x200B;を選択します。

   * **[!UICONTROL 項目のリスト]**：昇格する項目の`entity.id`値をコンマで区切って入力します。
   * **[!UICONTROL 属性で昇格]**：昇格する項目の属性を定義するルールを追加します。 このオプションを使用すると、静的ルールと動的ルールを使用して動的に一致させることができます。 詳細、例、ユースケースのシナリオについては、[動的および静的インクルージョンルールの使用](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#inclusion-rules)を参照してください。
   * **[!UICONTROL コレクションを昇格]**：昇格するアイテムのコレクションを選択します。 プロモーション用に新しいコレクションを作成できます。 [&#x200B; コレクションの作成](/help/main/c-recommendations/c-products/collections.md#task_1256DFF6842141FCAADD9E1428EF7F08)を参照してください。

   プロモーションタイプは、プロモートされたアイテムの並べ替え順序も決定します。 [&#x200B; プロモーションタイプと並べ替え順序](#promotion-sort-order)を参照してください。

   ![&#x200B; プロモーションタイプのオプションがハイライト表示されたプロモーションダイアログの変更：項目のリスト、属性によるプロモート、コレクションのプロモート &#x200B;](/help/main/c-recommendations/t-create-recs-activity/assets/promotion_type.png)

1. 「**[!UICONTROL Save]**」をクリックします。

プロモーションはアクティビティのすべてのエクスペリエンスに適用されます。

## プロモーションの種類と並べ替え順序 {#promotion-sort-order}

次の表に示すように、プロモーションされたアイテムの並べ替え順序は、プロモーションタイプによって異なります。

| プロモーションタイプ | デフォルトの並べ替え | バックアップの並べ替え | 動的フィルターオプション |
| --- | --- | --- | --- |
| **[!UICONTROL 項目のリスト]** | [!DNL Target] UIまたはAPIで注文が入力されました | ランダム（UIまたはAPIで選択した場合） | いいえ |
| **[!UICONTROL 属性によるプロモーション]** | `entity.value` （降順） | ランダム化なし | ○ |
| **[!UICONTROL コレクションのプロモーション]** | `entity.value` （降順） | ランダム化なし | × |

* **[!UICONTROL 項目のリスト]**: デフォルトの並べ替え順序は、[!DNL Target] UIまたはAPIで入力された順序です。 このタイプには、**[!UICONTROL 項目注文をランダム化]** チェックボックスが用意されています。 リストにプロモーション用に設定されたスロット数を超えるアイテムが含まれる場合、このオプションは、デザインに表示されるプロモーションされたアイテムをランダム化します。 各ヒットで、[!DNL Target]は、テンプレート内のプロモーションに対して有効なアイテムをプロモーションセット全体からランダムに選択します。
* **[!UICONTROL 属性で昇格]**&#x200B;および&#x200B;**[!UICONTROL コレクションを昇格]**: デフォルトの順序は、`entity.value`属性に基づいています（降順）。 注文のランダム化は適用できません。

エンティティに`entity.value`属性がない場合（例えば、ビジネスが製品を販売していない場合）、公開日などの数値を`entity.value`属性に渡すことができます。 昇格されたアイテムは、最新の公開日に降順で並べられます。 `entity.value`属性はdouble タイプで、文字列を受け付けません。
