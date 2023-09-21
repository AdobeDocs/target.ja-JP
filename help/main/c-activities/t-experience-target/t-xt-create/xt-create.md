---
keywords: エクスペリエンスのターゲット設定；xt；作成
description: の使用方法を学ぶ [!UICONTROL Visual Experience Composer] (VEC) [!DNL Adobe Target] を作成するには、 [!UICONTROL エクスペリエンスのターゲット設定] (XT) アクティビティ
title: 作成方法 [!UICONTROL エクスペリエンスのターゲット設定] 活動？
feature: Experience Targeting
exl-id: fc7fc37f-40bf-4947-a4d0-e51fa09b6c56
source-git-commit: 4faafcef38d02674072d8b20ae03d3e2ef2115d6
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 51%

---

# の作成 [!UICONTROL エクスペリエンスのターゲット設定] (XT) アクティビティ

以下を使用します。 [!UICONTROL Visual Experience Composer] (VEC) を使用して [!UICONTROL エクスペリエンスのターゲット設定] (XT) アクティビティ [!DNL Target] — 有効なページと、 [!DNL Adobe Target].

[!UICONTROL エクスペリエンスのターゲット設定]（XT）では、マーケターが定義した一連のルールや条件を基にして、特定のオーディエンスにコンテンツを配信します。

エクスペリエンスのターゲット設定（[ジオターゲティング](/help/main/c-target/c-audiences/c-target-rules/geo.md)を含む）は、特定のオーディエンスに特定のエクスペリエンスまたはコンテンツをターゲット設定するルールを定義する際に有効です。アクティビティで複数のルールを定義して、様々なオーディエンスに異なるコンテンツのバリエーションを提供します。

詳しくは、 [!UICONTROL エクスペリエンスのターゲット設定]、使用例のシナリオおよびトレーニングビデオについては、 [エクスペリエンスのターゲット設定](/help/main/c-activities/t-experience-target/experience-target.md).

**次の手順で、 [!UICONTROL エクスペリエンスのターゲット設定] アクティビティ：**

1. 「[!UICONTROL アクティビティ]」リストで、**[!UICONTROL アクティビティを作成]**／**[!UICONTROL エクスペリエンスのターゲット設定]**&#x200B;を選択します。

   ![アクティビティを作成／エクスペリエンスのターゲット設定](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_select-1.png)

   >[!NOTE]
   >
   >利用可能なアクティビティタイプは、[!DNL Target] アカウントによって異なります。一部のアクティビティタイプがリストに表示されない可能性があります。例えば、[!UICONTROL Automated Personalization]は、[Target Premium 機能](/help/main/c-intro/intro.md#premium)です。
   >
   >[!DNL Target] で使用できる様々なアクティビティタイプおよびその違いについて詳しくは、[アクティビティ](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)を参照してください。ニーズに最も適したアクティビティタイプを決定するのに役立つ情報については、[Target アクティビティタイプ](/help/main/c-activities/target-activities-guide.md)を参照してください。

1. 必要に応じて、「**[!UICONTROL ビジュアル (デフォルト)]**」を選択します。

   を使用したい場合は、 [フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md)を選択します。 [!UICONTROL フォーム].

   >[!NOTE]
   >
   >VEC および [!UICONTROL フォームベースの Experience Composer], [!DNL Target] は、シングルページアプリケーション VEC を提供します。 様々なコンポーザーについて詳しくは、[エクスペリエンスとオファー](/help/main/c-experiences/experiences.md)を参照してください。
   >
   >VEC のトラブルシューティングについて詳しくは、 [Visual Experience Composer のトラブルシューティング](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

1. （条件付き） [!DNL Target Premium] 顧客 [ワークスペースの選択](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

   The [!UICONTROL 職場を選択] オプションは [Target Premium](/help/main/c-intro/intro.md) 機能。 組織が [!DNL Target Standard] ライセンスを使用してください（このオプションが表示されない場合）。

1. [アクティビティ URL](/help/main/c-activities/t-experience-target/t-xt-create/xt-activity-url.md#concept_D28549AAA0A14E3BB5F05F32BE8ABC90) を指定してから、「**[!UICONTROL 作成]**」をクリックします。

   アカウントに[デフォルトの URL が設定されている](/help/main/administrating-target/visual-experience-composer-set-up.md)場合は、その URL がデフォルトで表示されます。必要に応じて、デフォルトの URL を別の URL に変更できます。

   VEC が開き、URL で指定したページが表示されます。

   ![VEC 内のエクスペリエンスのターゲット設定アクティビティ](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt-in-vec.png)

1. 用意されている領域に、アクティビティの名前を入力します。

   ![「名前」フィールド](/help/main/c-activities/t-experience-target/t-xt-create/assets/xt_name-new.png)

   アクティビティ名の先頭に次の文字を使用することはできません。

   | 文字 | 説明 |
   |--- |--- |
   | `=` | イコール |
   | `+` | プラス |
   | `-` | マイナス |
   | `@` | アットマーク |

   アクティビティ名に次の文字シーケンスを含めることはできません。

   | 文字シーケンス | 説明 |
   |--- |--- |
   | ;= | セミコロン、等しい |
   | ;+ | セミコロン、プラス |
   | ;- | セミコロン、マイナス |
   | ;@ | セミコロン、アットマーク |
   | ,= | コンマ、等しい |
   | ,+ | コンマ、プラス |
   | ,- | コンマ、マイナス |
   | ,@ | コンマ、アットマーク |
   | `[`&quot; | 開き角括弧、二重引用符 |
   | &quot;`]` | 二重引用符、閉じ角括弧 |

1. 別のオーディエンスをターゲットにした新しいエクスペリエンスを作成します。

   手順については、[エクスペリエンスの追加](/help/main/c-activities/t-experience-target/t-xt-create/xt-add-experience.md)を参照してください。

1. アクティビティの[目標と設定](/help/main/c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)を指定します。
