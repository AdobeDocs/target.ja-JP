---
keywords: scene7;dynamic media classic;digital asset management;assets;dam;content library;swap image
description: Adobe Targetは、AdobeDynamic Mediaクラシック(旧称Scene7)と統合して、コンテンツライブラリでDigital Asset Management(DAM)を提供できます。
title: Dynamic Mediaクラシック統合設定の統合
feature: Administration & Configuration
translation-type: tm+mt
source-git-commit: 1c5fd1062da5f90f24720fc3deb67f7f3b05aee9
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 25%

---


# Scene7形状

[!DNL Adobe Target] を [!DNL Adobe Dynamic Media Classic] (旧Scene7)と統合して、 [!UICONTROL コンテンツライブラリでDigital Asset Management(DAM)を提供できます]。

>[!NOTE]
>
>[!DNL Target]と[!DNL Dynamic Media Classic]を統合すると、[!DNL Adobe Experience Cloud]アセットフォルダーにアップロードされたアセット(アクティビティの一部として)を配信できます。 この統合では、[!DNL Dynamic Media Classic]にアップロードされたすべてのアセットに対して、[!DNL Target]アクティビティでの配信用にアクセスできるわけではありません。

既に[!DNL Dynamic Media]アカウントをお持ちの場合は、既存の資格情報を指定できます。 アカウントをお持ちでない場合は、[!DNL Adobe]の担当者に無償で[!DNL Dynamic Media Classic]アカウントの使用制限をリクエストできます。 このアカウントは、[!DNL Target]でのみ使用できるよう制限された目的で使用できます。 このサービスは、ワークフローに画像の入れ替え機能が必要なお客様向けのものです。

<!-- 
>[!NOTE]
>
>A restricted-use, free [!DNL Dynamic Media Classic] account for [!DNL Adobe Target] is no longer supported for new customers or new users. Existing sign-in credentials work as usual. 
-->

この設定が設定されていない場合、アクティビティ作成ワークフロー内の「スワップオファー」[!UICONTROL オプションは使用できません。 ]この機能が設定されたら、画像オファーを交換／変更するオプションを     [Visual Experience Composer とフォームベースの Experience Composer](/help/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D) の両方で利用できます。その後、[!DNL Adobe Experience Cloud]からアップロードされた画像を[!DNL Target]アクティビティで使用するために、画像オファーを利用できます。

アクティビティの作成中に、オファーやカスタムコードで公開画像 URL を直接参照したい場合は、各自の Web サーバーに画像を展開し、コードで独自の URL を使用する必要があります。[!DNL Experience Cloud]にアップロードされた画像の公開済みURLを取得して、[!DNL Target]を使用してターゲットワークフローの直接または外部で使用する方法はありません。 契約内容にあるように、この機能は許可されません。

ストレージURLと[!DNL Dynamic Media]からの画像の最終公開URLは異なり、配信は画像のストレージリンクを使用して&#x200B;*NOT*&#x200B;でオファーを作成する必要があるので、このような場合はが機能しません。 ヘルプドキュメントで説明されているように、画像オファー機能を使用する必要があります。

[!DNL Dynamic Media Classic] ([!DNL Scene7])と統合するには、次の情報を指定する必要があります。

1. **[!UICONTROL 管理]**/**[!UICONTROL Scene7構成]**&#x200B;をクリックします。

   ![Scene7ページ](/help/administrating-target/assets/scene7.png)

1. 次の[!DNL Dynamic Media Classic]アカウント情報を指定します。

   **地域：**[!DNL Dynamic Media] アカウントの地域は、北米、ヨーロッパ、アジアです。

   **アドホックフォルダー：** ターゲットフォルダーの外部に存在し、手動でアップロードされるコンテンツの場所 [!DNL Dynamic Media]です。

   **電子メールアドレス：** ログインに使用する電子メールアドレス [!DNL Dynamic Media Classic] ([!DNL Scene7])。

   **パスワード：** ( [!DNL Dynamic Media Classic] )へのログインに使用するパスワード[!DNL Scene7]。

1. 「**[!UICONTROL 送信]**」をクリックします。
