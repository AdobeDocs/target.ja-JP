---
description: Target Standard を Adobe Dynamic Media Classic（以前の Scene7）と統合して、コンテンツライブラリで Digital Asset Management（DAM）を実行できます。
title: Dynamic Media Classic の統合 構成統合
subtopic: Getting Started
topic: Standard
uuid: 4b06a3ed-0e87-4e49-874f-2e479324f81c
translation-type: tm+mt
source-git-commit: 3edb13b196240bb1918fc66edcc653936e32d3ef
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 32%

---


# Scene7の設定 {#scene-settings}

Target can be integrated with [!DNL Adobe Dynamic Media Classic] (formerly [!DNL Scene7]) to provide Digital Asset Management (DAM) in the Content Library.

>[!NOTE]
>
>Integrating [!DNL Target] with [!DNL Dynamic Media Classic] enables delivery of assets (as part of activities) uploaded to the [!DNL Adobe Experience Cloud] assets folder. This integration does not enable access to all assets uploaded in [!DNL Dynamic Media Classic] for delivery in [!DNL Target] activities.

If you already have a [!DNL Dynamic Media] account, you can supply your existing credentials. If you do not have an account, you can request a restricted-use [!DNL Dynamic Media Classic] account at no additional charge from your [!DNL Adobe] representative. This account can be used for purposes restricted for use in [!DNL Target] only. このサービスは、ワークフローに画像の入れ替え機能が必要なお客様向けのものです。

If this setting is not configured, the [!UICONTROL Swap Image offer] option within the activity creation workflow is not available. この機能が設定されたら、画像オファーを交換／変更するオプションを     [Visual Experience Composer とフォームベースの Experience Composer](../c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D) の両方で利用できます。You can then leverage image offers with images that have been uploaded from the [!DNL Adobe Experience Cloud] for use in [!DNL Target] activities.

アクティビティの作成中に、オファーやカスタムコードで公開画像 URL を直接参照したい場合は、各自の Web サーバーに画像を展開し、コードで独自の URL を使用する必要があります。There is no way to obtain the published URL of an image uploaded into the [!DNL Experience Cloud] to consume directly or outside of targeting workflows using [!DNL Target]. 契約内容にあるように、この機能は許可されません。

Note that the storage URL and the final publish URLs of images from [!DNL Dynamic Media] are different and one must *NOT* create offers using the storage link of images as delivery will not work in such cases. ヘルプドキュメントで説明されているように、画像オファー機能を使用する必要があります。

( [!DNL Dynamic Media Classic] )と統合するに[!DNL Scene7]は、次の情報を指定する必要があります。

1. **[!UICONTROL 管理]** / **[!UICONTROL Scene7設定をクリックします]**。

   ![Scene7ページ](/help/administrating-target/assets/scene7.png)

1. Specify the following [!DNL Dynamic Media Classic] account information:

   **地域：**[!DNL Dynamic Media] アカウントの地域は、北米、ヨーロッパ、アジアです。

   **アドホックフォルダー：** ターゲットフォルダーの外部にあり、に手動でアップロードされるコンテンツの場所 [!DNL Dynamic Media]。

   **電子メールアドレス：** ( [!DNL Dynamic Media Classic] )へのログインに使用する電子メールアドレス[!DNL Scene7]。

   **パスワード：** ( [!DNL Dynamic Media Classic] )へのログインに使用するパスワード[!DNL Scene7]。

1. 「**[!UICONTROL 送信]**」をクリックします。
