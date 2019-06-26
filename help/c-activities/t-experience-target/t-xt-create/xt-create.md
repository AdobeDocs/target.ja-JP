---
description: Visual Experience Composer を使用すると、Target を有効にしたページ上にエクスペリエンスのターゲット設定アクティビティを作成し、Target 内でページの一部を変更することができます。
seo-description: Visual Experience Composerを使用して、Target対応ページでエクスペリエンスターゲット設定（XT）アクティビティを作成し、Adobe Target内でページの一部を変更します。
seo-title: エクスペリエンスのターゲット設定アクティビティの作成
solution: 'Target '
subtopic: 多変量分析テスト
title: エクスペリエンスのターゲット設定アクティビティの作成
topic: Standard
uuid: 6299982b-b1ba-4dd0-9c69-36a76680a3e1
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# エクスペリエンスのターゲット設定アクティビティの作成{#create-an-experience-targeting-activity}

[!UICONTROL Visual Experience Composer] （VEC）を使用して、Target対応ページで [!UICONTROL エクスペリエンスターゲット設定] （XT）アクティビティを作成し、ページの一部を変更 [!DNL Adobe Target]します。

エクスペリエンスのターゲット設定（XT）では、マーケティング担当者が定義した一連のルールや条件を基にして、特定のオーディエンスにコンテンツを配信します。

Experience Targeting, including [geo-targeting](/help/c-target/c-audiences/c-target-rules/geo.md), is valuable for defining rules that target a specific experience or content to a particular audience. アクティビティで複数のルールを定義して、様々なオーディエンスに異なるコンテンツのバリエーションを提供します。

For more information about Experience Targeting, a use-case scenario, and training videos, see [Experience Targeting](/help/c-activities/t-experience-target/experience-target.md).

**XTアクティビティを作成するには:**

1. 「[!UICONTROL アクティビティ]」リストで、「**[!UICONTROL アクティビティを作成**]／**[!UICONTROL エクスペリエンスのターゲット設定]**」の順に選択します。

   ![アクティビティを作成/エクスペリエンスのターゲット設定](/help/c-activities/t-experience-target/t-xt-create/assets/xt_select-1.png)

   >[!NOTE]
   >
   >利用可能なアクティビティタイプは、Target アカウントによって異なります。一部のアクティビティタイプがリストに表示されない可能性があります。For example, [!UICONTROL Automated Personalization] is a [Target Premium feature](/help/c-intro/intro.md#premium).
   >
   >For more information about the various activity types available in [!DNL Target] and their differences, see [Activities](../../../c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03). See [Target Activity types](/help/c-activities/target-activities-guide.md) to help you decide which activity type best suites your needs.

1. Select **[!UICONTROL Visual (Default)]**, if necessary.

   ![エクスペリエンスターゲット設定アクティビティの作成ダイアログボックス](/help/c-activities/t-experience-target/t-xt-create/assets/form_url-new.png)

   フォームベースの Experience Composer を使用する場合、「[!UICONTROL フォーム]」を選択します。See [Form-Based Experience Composer](/help/c-experiences/form-experience-composer.md) for more information.

   >[!NOTE]
   >
   >VECおよびフォームベースのExperience Composerに加えて、Targetは単一ページアプリケーションVECおよびVEC forモバイルアプリを提供します。For more information about the various composers, see [Experiences and Offers](/help/c-experiences/experiences.md).
   >
   >問題がある VEC のトラブルシューティング情報については、[Visual Experience Composer のトラブルシューティング](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)を参照してください。
   >
   >The [!UICONTROL Choose Workplace] option in the preceding illustration is a [Target Premium](/help/c-intro/intro.md) feature. このオプションが表示されない場合、組織にTarget Standardライセンスがあります。

1. (Conditional) If you are a Target Premium customer, [choose a workspace](/help/administrating-target/c-user-management/property-channel/property-channel.md).

1. [アクティビティURLを指定](../../../c-activities/t-experience-target/t-xt-create/xt-activity-url.md#concept_D28549AAA0A14E3BB5F05F32BE8ABC90)し、「 **[!UICONTROL 次へ]**」をクリックします。

   If your account is [configured with a default URL](/help/administrating-target/r-target-account-preferences/target-account-preferences.md), that URL appears by default. 必要に応じて、デフォルトのURLから別のURLに変更できます。

   VECが開き、URLで指定されたページが表示されます。

   ![VEC内のエクスペリエンスターゲット設定アクティビティ](/help/c-activities/t-experience-target/t-xt-create/assets/xt-in-vec.png)

1. 用意されている領域に、アクティビティの名前を入力します。

   ![名前フィールド](/help/c-activities/t-experience-target/t-xt-create/assets/xt_name-new.png)

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

1. 差異オーディエンスをターゲットにした新しいエクスペリエンスを作成します。

   For step-by-step instructions, see [Add experience](/help/c-activities/t-experience-target/t-xt-create/xt-add-experience.md).

1. アクティビティの[目標と設定](../../../c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)を指定します。