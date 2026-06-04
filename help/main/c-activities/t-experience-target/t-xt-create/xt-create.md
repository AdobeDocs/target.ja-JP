---
keywords: エクスペリエンスのターゲット設定；xt；作成
description: ' [!DNL Adobe Target] の[!UICONTROL Visual Experience Composer] （VEC）を使用して、[!UICONTROL Experience Targeting] （XT）アクティビティを作成する方法を説明します。'
title: '[!UICONTROL  エクスペリエンスのターゲット設定] アクティビティを作成するにはどうすればよいですか？'
feature: Experience Targeting
exl-id: fc7fc37f-40bf-4947-a4d0-e51fa09b6c56
TQID: https://experienceleague.adobe.com/RKSF7zTO3lb4hs1VaJuTUR9v8AnOlCjHkp-whqBIcKo
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: c1579802-ddd4-4214-8a91-97b2066abe11id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 443
ht-degree: 30%

---

# [!UICONTROL  エクスペリエンスのターゲット設定] （XT） アクティビティの作成

[!UICONTROL Visual Experience Composer] （VEC）を使用して、[!DNL Target]対応ページで[!UICONTROL Experience Targeting] （XT）アクティビティを作成し、[!DNL Adobe Target]内のページの一部を変更します。

[!UICONTROL  エクスペリエンスのターゲット設定] （XT）は、マーケターが定義した一連のルールと条件に基づいて、特定のオーディエンスにコンテンツを配信します。

[地域ターゲット ](/help/main/c-target/c-audiences/c-target-rules/geo.md)を含む[!UICONTROL  エクスペリエンスターゲティング ]は、特定のエクスペリエンスまたはコンテンツを特定のオーディエンスにターゲットするルールを定義する場合に役立ちます。 アクティビティで複数のルールを定義して、様々なオーディエンスに異なるコンテンツのバリエーションを提供します。

[!UICONTROL  エクスペリエンスのターゲット設定]、ユースケース シナリオ、およびトレーニング ビデオについて詳しくは、[ エクスペリエンスのターゲット設定](/help/main/c-activities/t-experience-target/experience-target.md)を参照してください。

**エクスペリエンスのターゲット設定] アクティビティ [!UICONTROL を作成するには：**

1. [!UICONTROL  アクティビティ ] リストから、**[!UICONTROL アクティビティの作成]** > **[!UICONTROL エクスペリエンスのターゲット設定]**&#x200B;をクリックします。

   >[!NOTE]
   >
   >利用可能なアクティビティタイプは、[!DNL Target] アカウントによって異なります。 一部のアクティビティタイプがリストに表示されない可能性があります。 例えば、[!UICONTROL Automated Personalization]は[Target Premium機能](/help/main/c-intro/intro.md#premium)です。
   >
   >[!DNL Target] で使用できる様々なアクティビティタイプおよびその違いについて詳しくは、[アクティビティ](/help/main/c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03)を参照してください。 ニーズに最も適したアクティビティタイプを決定するのに役立つ情報については、[Target アクティビティタイプ](/help/main/c-activities/target-activities-guide.md)を参照してください。

1. 必要に応じて、**[!UICONTROL Visual]**&#x200B;を選択します。

   [ フォームベースのExperience Composer](/help/main/c-experiences/form-experience-composer.md)を使用する場合は、[!UICONTROL Form]を選択します。

   >[!NOTE]
   >
   >VECおよび[!UICONTROL  フォームベースのExperience Composer]に加えて、[!DNL Target]はシングルページアプリケーション VECを提供しています。 様々なコンポーザーについて詳しくは、[エクスペリエンスとオファー](/help/main/c-experiences/experiences.md)を参照してください。
   >
   >VECに関するトラブルシューティング情報については、[Visual Experience Composerのトラブルシューティング ](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md)を参照してください。

1. （条件付き）お客様が[!DNL Target Premium]のお客様の場合、[ ワークスペースを選択](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)。

   「[!UICONTROL 職場を選択]」オプションは、[Target Premium](/help/main/c-intro/intro.md)機能です。 このオプションが表示されない場合、組織に[!DNL Target Standard] ライセンスがある場合。

1. [ アクティビティ URL](/help/main/c-activities/t-experience-target/t-xt-create/xt-activity-url.md#concept_D28549AAA0A14E3BB5F05F32BE8ABC90)を指定し、**[!UICONTROL 作成]**&#x200B;をクリックします。

   アカウントに[デフォルトの URL が設定されている](/help/main/administrating-target/visual-experience-composer-set-up.md)場合は、その URL がデフォルトで表示されます。 必要に応じて、デフォルトの URL を別の URL に変更できます。

   VEC が開き、URL で指定したページが表示されます。

1. アクティビティに名前を付けるには、「[!UICONTROL 名称未設定のアクティビティ ]」の横にある&#x200B;**[!UICONTROL 編集]** アイコン （![編集アイコン ](/help/main/assets/icons/Edit.svg)）をクリックし、アクティビティのわかりやすい名前を指定して、**[!UICONTROL 保存]**&#x200B;をクリックします。

   アクティビティ名の先頭に次の文字を使用することはできません：

   | 文字 | 説明 |
   |--- |--- |
   | `=` | イコール |
   | `+` | プラス |
   | `-` | マイナス |
   | `@` | アットマーク |

   アクティビティ名に次の文字シーケンスを含めることはできません。

   | 文字シーケンス | 説明 |
   |--- |--- |
   | ;= | セミコロン、次に等しい |
   | ;+ | セミコロン、プラス |
   | ;- | セミコロン、マイナス |
   | ;@ | セミコロン、記号 |
   | ,= | コンマ、次に等しい |
   | ,+ | コンマ、プラス |
   | ,- | コンマ、マイナス |
   | ,@ | コンマ、記号 |
   | `[`&quot; | 角括弧を開く、二重引用符 |
   | &quot;`]` | 二重引用符、角括弧を閉じる |

1. さまざまなオーディエンスをターゲットにした新しい体験を構築。

   手順については、[エクスペリエンスの追加](/help/main/c-activities/t-experience-target/t-xt-create/xt-add-experience.md)を参照してください。

1. アクティビティの[目標と設定](/help/main/c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)を指定します。
