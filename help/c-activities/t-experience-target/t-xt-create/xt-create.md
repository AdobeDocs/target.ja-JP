---
description: Visual Experience Composer を使用すると、Target を有効にしたページ上にエクスペリエンスのターゲット設定（XT）アクティビティを作成し、Adobe Target 内でページの一部を変更できます。
title: エクスペリエンスのターゲット設定アクティビティの作成
subtopic: Multivariate Test
topic: Standard
uuid: 6299982b-b1ba-4dd0-9c69-36a76680a3e1
translation-type: tm+mt
source-git-commit: fdf75402a0283c3189952fb74997d4ab536d5098
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 100%

---


# エクスペリエンスのターゲット設定アクティビティの作成{#create-an-experience-targeting-activity}

[!UICONTROL Visual Experience Composer]（VEC）を使用すると、Target を有効にしたページ上に[!UICONTROL エクスペリエンスのターゲット設定]（XT）アクティビティを作成し、[!DNL Adobe Target] 内でページの一部を変更することができます。

エクスペリエンスのターゲット設定（XT）では、マーケティング担当者が定義した一連のルールや条件を基にして、特定のオーディエンスにコンテンツを配信します。

エクスペリエンスのターゲット設定（[ジオターゲティング](/help/c-target/c-audiences/c-target-rules/geo.md)を含む）は、特定のオーディエンスに特定のエクスペリエンスまたはコンテンツをターゲット設定するルールを定義する際に有効です。アクティビティで複数のルールを定義して、様々なオーディエンスに異なるコンテンツのバリエーションを提供します。

エクスペリエンスターゲット設定、使用例のシナリオおよびトレーニングビデオについて詳しくは、[エクスペリエンスのターゲット設定](/help/c-activities/t-experience-target/experience-target.md)を参照してください。

**XT アクティビティを作成するには：**

1. 「[!UICONTROL アクティビティ]」リストで、**[!UICONTROL アクティビティを作成]**／**[!UICONTROL エクスペリエンスのターゲット設定]**&#x200B;を選択します。

   ![アクティビティを作成／エクスペリエンスのターゲット設定](/help/c-activities/t-experience-target/t-xt-create/assets/xt_select-1.png)

   >[!NOTE]
   >
   >利用可能なアクティビティタイプは、Target アカウントによって異なります。一部のアクティビティタイプがリストに表示されない可能性があります。例えば、[!UICONTROL 自動パーソナライゼーション]は、[Target Premium 機能](/help/c-intro/intro.md#premium)です。
   >
   >[!DNL Target] で使用できる様々なアクティビティタイプおよびその違いについて詳しくは、[アクティビティ](../../../c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)を参照してください。ニーズに最も適したアクティビティタイプを決定するのに役立つ情報については、[Target アクティビティタイプ](/help/c-activities/target-activities-guide.md)を参照してください。

1. 必要に応じて、「**[!UICONTROL ビジュアル (デフォルト)]**」を選択します。

   ![エクスペリエンスのターゲット設定アクティビティを作成ダイアログボックス](/help/c-activities/t-experience-target/t-xt-create/assets/form_url-new.png)

   フォームベースの Experience Composer を使用する場合、「[!UICONTROL フォーム]」を選択します。詳しくは、[フォームベースの Experience Composer](/help/c-experiences/form-experience-composer.md) を参照してください。

   >[!NOTE]
   >
   >VEC およびフォームベースの Experience Composer に加えて、Target はシングルページアプリケーション VEC およびモバイルアプリ向け VEC を提供します。様々なコンポーザーについて詳しくは、[エクスペリエンスとオファー](/help/c-experiences/experiences.md)を参照してください。
   >
   >問題がある VEC のトラブルシューティング情報については、[Visual Experience Composer のトラブルシューティング](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)を参照してください。
   >
   >前述の図の「[!UICONTROL ワークスペースを選択]」オプションは、[Target Premium](/help/c-intro/intro.md) の機能です。このオプションが表示されない場合、お客様の組織は Target Standard ライセンスを所有しています。]

1. （条件付き）Target Premium のお客様の場合、[ワークスペースを選択](/help/administrating-target/c-user-management/property-channel/property-channel.md)します。

1. [アクティビティ URL](../../../c-activities/t-experience-target/t-xt-create/xt-activity-url.md#concept_D28549AAA0A14E3BB5F05F32BE8ABC90) を指定してから、「**[!UICONTROL 次へ]**」をクリックします。

   アカウントに[デフォルトの URL が設定されている](/help/administrating-target/visual-experience-composer-set-up.md)場合は、その URL がデフォルトで表示されます。必要に応じて、デフォルトの URL を別の URL に変更できます。

   VEC が開き、URL で指定したページが表示されます。

   ![VEC 内のエクスペリエンスのターゲット設定アクティビティ](/help/c-activities/t-experience-target/t-xt-create/assets/xt-in-vec.png)

1. 用意されている領域に、アクティビティの名前を入力します。

   ![「名前」フィールド](/help/c-activities/t-experience-target/t-xt-create/assets/xt_name-new.png)

   次の文字はアクティビティ名として入力できません。

   | 文字 | 説明 |
   |--- |--- |
   | `/` | フォワードスラッシュ |
   | `?` | 疑問符 |
   | `#` | 番号記号 |
   | `:` | コロン |
   | `=` | イコール |
   | `+` | プラス |
   | `-` | マイナス |
   | `@` | アットマーク |

1. 別のオーディエンスをターゲットにした新しいエクスペリエンスを作成します。

   手順については、[エクスペリエンスの追加](/help/c-activities/t-experience-target/t-xt-create/xt-add-experience.md)を参照してください。

1. アクティビティの[目標と設定](../../../c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)を指定します。