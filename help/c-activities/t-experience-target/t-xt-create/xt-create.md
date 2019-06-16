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
source-git-commit: c6085fae6428cb837eed6eadd778140687348817

---


# エクスペリエンスのターゲット設定アクティビティの作成{#create-an-experience-targeting-activity}

[!UICONTROL Visual Experience Composer] （VEC）を使用して、Target対応ページで [!UICONTROL エクスペリエンスターゲット設定] （XT）アクティビティを作成し、ページの一部を変更 [!DNL Adobe Target]します。

エクスペリエンスのターゲット設定（XT）では、マーケティング担当者が定義した一連のルールや条件を基にして、特定のオーディエンスにコンテンツを配信します。

エクスペリエンスターゲット設定（ [地域ターゲティング](/help/c-target/c-audiences/c-target-rules/geo.md)を含む）は、特定のオーディエンスに特定のエクスペリエンスまたはコンテンツをターゲット設定するルールを定義するのに便利です。アクティビティで複数のルールを定義して、様々なオーディエンスに異なるコンテンツのバリエーションを提供します。

エクスペリエンスのターゲット設定、ユースケースシナリオ、トレーニングビデオについて詳しくは [、エクスペリエンスのターゲット設定](/help/c-activities/t-experience-target/experience-target.md)を参照してください。

**XTアクティビティを作成するには:**

1. 「[!UICONTROL アクティビティ]」リストで、「**[!UICONTROL アクティビティを作成**]／**[!UICONTROL エクスペリエンスのターゲット設定]**」の順に選択します。

   ![アクティビティを作成/エクスペリエンスのターゲット設定](/help/c-activities/t-experience-target/t-xt-create/assets/xt_select-1.png)

   >[!NOTE]
   >
   >利用可能なアクティビティタイプは、Target アカウントによって異なります。一部のアクティビティタイプがリストに表示されない可能性があります。例えば、 [!UICONTROL 自動パーソナライゼーション] は [Target Premium機能](/help/c-intro/intro.md#premium)です。
   >
   >使用可能な様々なアクティビティタイプ [!DNL Target] とその違いについて詳しくは [、アクティビティ](../../../c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)を参照してください。必要なアクティビティのタイプを決定するには [、Targetアクティビティのタイプ](/help/c-activities/target-activities-guide.md) を参照してください。

1. 必要に応じて **[!UICONTROL 、「ビジュアル（デフォルト）]**」を選択します。

   ![エクスペリエンスターゲット設定アクティビティの作成ダイアログボックス](/help/c-activities/t-experience-target/t-xt-create/assets/form_url-new.png)

   フォームベースの Experience Composer を使用する場合、「[!UICONTROL フォーム]」を選択します。詳しくは [、フォームベースのExperience Composer](/help/c-experiences/form-experience-composer.md) を参照してください。

   >[!NOTE]
   >
   >VECおよびフォームベースのExperience Composerに加えて、Targetは単一ページアプリケーションVECおよびVEC forモバイルアプリを提供します。様々なコンポーザーについて詳しくは [、エクスペリエンスとオファー](/help/c-experiences/experiences.md)を参照してください。
   >
   >問題がある VEC のトラブルシューティング情報については、[Visual Experience Composer のトラブルシューティング](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)を参照してください。
   >
   >前述の図の [!UICONTROL 「勤務先を選択」] オプションは [、Target Premium](/help/c-intro/intro.md) 機能です。このオプションが表示されない場合、組織にTarget Standardライセンスがあります。

1. （条件付き） Target Premiumのお客様の場合は、ワークスペース [を選択](/help/administrating-target/c-user-management/property-channel/property-channel.md)します。

1. [アクティビティURLを指定](../../../c-activities/t-experience-target/t-xt-create/xt-activity-url.md#concept_D28549AAA0A14E3BB5F05F32BE8ABC90)し、「 **[!UICONTROL 次へ]**」をクリックします。

   アカウントにデフォルトのURLが [設定されている場合、](/help/administrating-target/r-target-account-preferences/target-account-preferences.md)そのURLはデフォルトで表示されます。必要に応じて、デフォルトのURLから別のURLに変更できます。

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

   手順については、エクスペリエンスの追加を参照 [](/help/c-activities/t-experience-target/t-xt-create/xt-add-experience.md)してください。

1. アクティビティの[目標と設定](../../../c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)を指定します。