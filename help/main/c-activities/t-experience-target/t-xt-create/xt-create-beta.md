---
keywords: エクスペリエンスのターゲット設定；xt；作成
description: '[!UICONTROL Visual Experience Composer] （VEC） in を使用して、[!UICONTROL Experience Targeting] （XT）アクティビティを作成する方法を説明します  [!DNL Adobe Target] '
title: '[!UICONTROL Experience Targeting] アクティビティの作成方法'
feature: Experience Targeting
hide: true
hidefromtoc: true
source-git-commit: 269ab2df7538d7e93774e3687bb931c9aaac27b6
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 33%

---

# [!UICONTROL Experience Targeting] （XT）アクティビティの作成

[!UICONTROL Visual Experience Composer] （VEC）を使用して、[!DNL Target] 対応ページに [!UICONTROL Experience Targeting] （XT）アクティビティを作成し、[!DNL Adobe Target] 内のページの一部を変更します。

[!UICONTROL Experience Targeting] （XT）では、マーケターが定義した一連のルールや条件を基にして、特定のオーディエンスにコンテンツを配信します。

[ ジオターゲティング ](/help/main/c-target/c-audiences/c-target-rules/geo.md) を含む [!UICONTROL Experience Targeting] は、特定のオーディエンスに特定のエクスペリエンスまたはコンテンツをターゲット設定するルールを定義する際に有効です。 アクティビティで複数のルールを定義して、様々なオーディエンスに異なるコンテンツのバリエーションを提供します。

[!UICONTROL Experience Targeting]、ユースケースシナリオおよびトレーニングビデオについて詳しくは、[ エクスペリエンスのターゲット設定 ](/help/main/c-activities/t-experience-target/experience-target.md) を参照してください。

**[!UICONTROL Experience Targeting] アクティビティを作成するには：**

1. [!UICONTROL Activities] リストで、**[!UICONTROL Create Activity]**/**[!UICONTROL Experience Targeting]** をクリックします。

   >[!NOTE]
   >
   >利用可能なアクティビティタイプは、[!DNL Target] アカウントによって異なります。一部のアクティビティタイプがリストに表示されない可能性があります。例えば、[!UICONTROL Automated Personalization] は [Target Premium機能 ](/help/main/c-intro/intro.md#premium) です。
   >
   >[!DNL Target] で使用できる様々なアクティビティタイプおよびその違いについて詳しくは、[アクティビティ](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)を参照してください。ニーズに最も適したアクティビティタイプを決定するのに役立つ情報については、[Target アクティビティタイプ](/help/main/c-activities/target-activities-guide.md)を参照してください。

1. 必要に応じて「**[!UICONTROL Visual]**」を選択します。

   [ フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md) を使用する場合は、「[!UICONTROL Form]」を選択します。

   >[!NOTE]
   >
   >VEC と [!UICONTROL Form-Based Experience Composer] に加えて、[!DNL Target] は、シングルページアプリケーション VEC を提供しています。 様々なコンポーザーについて詳しくは、[エクスペリエンスとオファー](/help/main/c-experiences/experiences.md)を参照してください。
   >
   >VEC のトラブルシューティング情報については、[Visual Experience Composer のトラブルシューティング ](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md) を参照してください。

1. （条件付き） [!DNL Target Premium] の顧客の場合は、[ ワークスペースを選択 ](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) します。

   「[!UICONTROL Choose Workplace]」オプションは ](/help/main/c-intro/intro.md)1}Target Premium} 機能です。 [このオプションが表示されない場合、組織が [!DNL Target Standard] ライセンスを保有している場合。

1. [ アクティビティ URL](/help/main/c-activities/t-experience-target/t-xt-create/xt-activity-url.md#concept_D28549AAA0A14E3BB5F05F32BE8ABC90) を指定し、「**[!UICONTROL Create]**」をクリックします。

   アカウントに[デフォルトの URL が設定されている](/help/main/administrating-target/visual-experience-composer-set-up.md)場合は、その URL がデフォルトで表示されます。必要に応じて、デフォルトの URL を別の URL に変更できます。

   VEC が開き、URL で指定したページが表示されます。

1. **[!UICONTROL Rename]** アイコン（名前を変更アイコン ![ をクリックし ](/help/main/assets/icons/MoreSmallListVert.svg) 「名前を **[!UICONTROL Rename]** 更」をクリックしてアクティビティの名前を指定し、「名前を変更」をクリックし **[!UICONTROL Save]** す。

   アクティビティ名は、次の文字で始めることはできません：

   | 文字 | 説明 |
   |--- |--- |
   | `=` | イコール |
   | `+` | プラス |
   | `-` | マイナス |
   | `@` | アットマーク |

   アクティビティ名には、次の文字シーケンスを含めることはできません：

   | 文字シーケンス | 説明 |
   |--- |--- |
   | ;= | セミコロン、次と等しい |
   | ;+ | セミコロン、プラス |
   | ;- | セミコロン マイナス |
   | ;@ | セミコロン、アットサイン |
   | ,= | コンマ、次と等しい |
   | ,+ | コンマ、プラス |
   | ,- | コンマ，マイナス |
   | ,@ | コンマ、アットサイン |
   | `[`&quot; | 左角括弧、二重引用符 |
   | &quot;`]` | 二重引用符、閉じ角括弧 |

1. 様々なオーディエンスをターゲットとした新しいエクスペリエンスを作成します。

   手順については、[エクスペリエンスの追加](/help/main/c-activities/t-experience-target/t-xt-create/xt-add-experience.md)を参照してください。

1. アクティビティの[目標と設定](/help/main/c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)を指定します。
