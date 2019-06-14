---
description: Visual Experience Composer を使用すると、Target を有効にしたページ上にエクスペリエンスのターゲット設定アクティビティを作成し、Target 内でページの一部を変更することができます。
seo-description: Visual Experience Composerを使用して、Target対応のページにエクスペリエンスのターゲット設定アクティビティを作成し、Adobe Target内でページの一部を変更します。
seo-title: エクスペリエンスのターゲット設定アクティビティの作成
solution: 'Target '
subtopic: 多変量分析テスト
title: エクスペリエンスのターゲット設定アクティビティの作成
topic: Standard
uuid: 6299982b-b1ba-4dd0-9c69-36a76680a3e1
translation-type: tm+mt
source-git-commit: 5eb79fcd0407e0da841048bcd0a1b64393490fcf

---


# エクスペリエンスのターゲット設定アクティビティの作成{#create-an-experience-targeting-activity}

[!UICONTROL Visual Experience Composer] （VEC）を使用して、Target対応ページで [!UICONTROL エクスペリエンスターゲット設定] （XT）アクティビティを作成し、ページの一部を変更 [!DNL Adobe Target]します。

1. 「[!UICONTROL アクティビティ]」リストで、「**[!UICONTROL アクティビティを作成**]／**[!UICONTROL エクスペリエンスのターゲット設定]**」の順に選択します。

   ![アクティビティを作成/エクスペリエンスのターゲット設定](/help/c-activities/t-experience-target/t-xt-create/assets/xt_select-1.png)

   >[!NOTE]
   >
   >利用可能なアクティビティタイプは、Target アカウントによって異なります。一部のアクティビティタイプがリストに表示されない可能性があります。例えば、自動パーソナライゼーションは [Target Premium機能](/help/c-intro/intro.md#premium)です。

   アクティビティのタイプについて詳しくは [、アクティビティ](../../../c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03) および [Targetアクティビティのタイプ](/help/c-activities/target-activities-guide.md)を参照してください。

1. 必要に応じて **[!UICONTROL 、「ビジュアル（デフォルト）]**」を選択します。

   ![エクスペリエンスターゲット設定アクティビティの作成ダイアログボックス](/help/c-activities/t-experience-target/t-xt-create/assets/form_url-new.png)

   フォームベースの Experience Composer を使用したい場合は、そちらのオプションを選択します。詳しくは、[フォームベースの Experience Composer](https://marketing.adobe.com/resources/help/en_US/target/target/t_form_experience_composer.html) を参照してください。

   >[!NOTE]
   >
   >VECおよびフォームベースのExperience Composerに加えて、Targetは単一ページアプリケーションVECおよびVEC forモバイルアプリを提供します。様々なコンポーザーについて詳しくは [、エクスペリエンスとオファー](/help/c-experiences/experiences.md)を参照してください。

   問題がある VEC のトラブルシューティング情報については、[Visual Experience Composer のトラブルシューティング](../../../c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md#reference_77743144F10143A3A89D56E116D296E4)を参照してください。

1. [アクティビティURLを指定](../../../c-activities/t-experience-target/t-xt-create/xt-activity-url.md#concept_D28549AAA0A14E3BB5F05F32BE8ABC90)し、「 **[!UICONTROL 次へ]**」をクリックします。

   アカウントにデフォルトの URL が設定されている場合は、その URL がデフォルトで表示されます。デフォルトの URL を別の URL に変更できます。

   Visual Experience Composer が表示され、URL で指定したページが表示されます。

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

1. 新しいエクスペリエンスを作成します（ページ上の要素の変更）。

   手順については、エクスペリエンスの追加を参照 [](/help/c-activities/t-experience-target/t-xt-create/xt-add-experience.md)してください。

   デフォルトでは、バナーの回転など JavaScript を含む要素については、Visual Experience Composer で変更できません。このような要素を Visual Experience Composer を使用して変更するには、JavaScript を無効にします。

   ページ上の要素にマウスカーソルを重ねると、その要素が強調表示されます。ハイライトされている要素は、VECを使用して変更できます。エクスペリエンスを変更するために要素上で実行できるアクションのリストについては [、Visual Experience Composerのオプション](/help/c-experiences/c-visual-experience-composer/viztarget-options.md)を参照してください。

   Target Classic（旧称 Test&amp;Target）を使用してページに mbox を作成していた場合は、mbox 名を表示する要素として mbox が表示され、他の要素と同様に修正することができます。

1. アクティビティの[目標と設定](../../../c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)を指定します。
