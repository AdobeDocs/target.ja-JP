---
keywords: プロモーション；プロモーション — 前；プロモーション — 後；プロモーションタイプ；項目のリスト；属性別にプロモート；コレクションをプロモート
description: プロモーション項目を追加し、Adobe内での配置を制御する方法を説明します [!DNL Target] Recommendationsのデザイン。 静的なプロモーションおよび動的なプロモーションを追加できます。
title: Recommendations Designs にプロモーションを追加する方法を教えてください。
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: bd5e5e12-a712-4c4c-9cf8-6b0f4834067b
source-git-commit: 07062b7df75300bd7558a24da5121df454520e42
workflow-type: tm+mt
source-wordcount: '687'
ht-degree: 50%

---

# プロモーションの追加

プロモーション項目を追加して、[!DNL Adobe Target Recommendations] デザインでの配置を制御します。静的なプロモーションおよび動的なプロモーションを追加できます。

>[!IMPORTANT]
>
>静的および動的な除外ルールは、マーケティングに役立つ便利な機能です。詳細な情報、例、および使用例については、 [動的および静的インクルージョンルールの使用](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F).

[!DNL Recommendations] アクティビティを作成するときは、[!DNL Recommendations] デザインにプロモーション項目を含めることができます。プロモーションは、デザインの使用可能なスロットを使用し、条件の結果およびバックアップレコメンデーションよりも優先されます。例えば、デザインに 6 つのスロットがあり、そのうち 2 つをプロモーションに使用した場合、条件に基づいてレコメンデーションされる項目に 4 つのスロットを使用できます。

プロモーションは、アクティビティの条件で推奨された項目に対して重複排除されるので、特定の項目が 1 つのレコメンデーショントレイに 2 回表示されることはありません。

特定の項目をプロモーションしたり、動的に項目をプロモーションしたり、属性に基づいて項目をプロモーションすることができます。また、コレクションをプロモーションすることもできます。

![[!UICONTROL プロモーション — 前] および [!UICONTROL プロモーション — 後] オプション [!DNL Target] UI](assets/add_promotion_toggles.png)

>[!NOTE]
>
>プロモーションを使用すると、CSV の構造と出力が変更されます。この変更により、電子メールなど、CSV に関連する外部プロセスが影響を受ける可能性があります。

1. **[!UICONTROL オプション]**&#x200B;ページで、「**[!UICONTROL プロモーション - 前]**」または「**[!UICONTROL プロモーション - 後]**」をクリックします。

   以下の図に、「[!UICONTROL プロモーション - 前]」が「オン」の状態を示します。

   ![「プロモーション - 前」オプションを追加](/help/main/c-recommendations/t-create-recs-activity/assets/add_promotion_front.png)

   条件の結果の前と&#x200B;**&#x200B;後のどちらにもプロモーションを挿入できます。

1. プロモーション項目に使用するデザインスロットの数を設定します。

   [!DNL Recommendations] デザインによりますが、最大で 20 個のスロットを使用できます。使用した各スロットは、条件に基づいて返されたレコメンデーションには使用できません。

1. プロモーション項目の開始日と終了日を設定します。

   開始日を設定しない場合、プロモーションはすぐに開始されます。終了日を設定しない場合、プロモーションは無期限に実行されます。

1. 「**[!UICONTROL プロモーションタイプ]**」を選択します。

   * 「**[!UICONTROL 項目のリスト]**」を選択し、プロモーションする特定の項目の `entity.id` 値をコンマで区切って入力します。

   * 「**[!UICONTROL 属性別にプロモート]**」を選択し、プロモーションする項目の属性を定義するルールを追加します。

      次を選択した場合、 [!UICONTROL 属性別にプロモート]を使用すると、動的な一致を作成できます。 詳しくは、 [動的および静的インクルージョンルールの使用](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F).

   * 「**[!UICONTROL コレクションをプロモート]**」を選択し、プロモーションする項目のコレクションを選択します。

      プロモーションに使用する新しいコレクションを作成できます。詳しくは、 [コレクションの作成](/help/main/c-recommendations/c-products/collections.md#task_1256DFF6842141FCAADD9E1428EF7F08) を参照してください。
   次を選択した場合： **[!UICONTROL 項目のリスト]** を **[!UICONTROL プロモーションタイプ]**&#x200B;を選択した場合、 **[!UICONTROL 項目の順序をランダム化]** 」チェックボックスをオンにします。

   のデフォルトの並べ替え順 [!UICONTROL 項目のリスト] が [!DNL Target] UI または API。 リストに、プロモーション用に設定したスロット数より多くの項目が含まれている場合、 [!UICONTROL 項目の順序をランダム化] オプションは、デザインに表示されるプロモーション項目をランダム化します。 このオプションを選択すると、次の結果になります。 [!DNL Target] 各ヒットで設定されたプロモーション全体から、テンプレートでプロモーションが有効な項目をランダムに選択する。

   エンティティに `entity.value` 属性（製品を販売していない場合など）は、 `entity.value` 属性（公開日など）。 この場合、最新の公開日に基づいて、昇格済みの項目を降順で昇格させることができます。 この `entity.value` 属性の型は double です。文字列は受け入れられません。

   選択した **[!UICONTROL 属性別にプロモート]** または **[!UICONTROL コレクションを昇格]** 」オプションを使用する場合、順序をランダム化するオプションは適用されません。

   を使用して特定の項目を昇格させる場合 [!UICONTROL 属性別にプロモート] または [!UICONTROL コレクションを昇格] オプションを指定した場合、デフォルトの表示順序は `entity.value` 属性。降順の数値順で指定します。

   次の表に、これらのオプションの違いを示します。

   | プロモーションタイプ | デフォルトの並べ替え | バックアップの並べ替え | 動的フィルターオプション |
   | --- | --- | --- | --- |
   | [!UICONTROL 項目のリスト] | Target UI/API で入力された注文 | ランダム（UI/API 経由で選択された場合） | × |
   | [!UICONTROL 属性別にプロモート] | `entity.value` （降順） | ランダム化なし | ○ |
   | [!UICONTROL コレクションを昇格] | `entity.value` （降順） | ランダム化なし | × |

1. 「**[!UICONTROL 保存]**」をクリックします。

プロモーションはアクティビティのすべてのエクスペリエンスに適用されます。
