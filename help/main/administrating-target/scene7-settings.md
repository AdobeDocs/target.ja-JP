---
keywords: scene7;dynamic media classic;デジタルアセット管理;アセット;dam;コンテンツライブラリ;画像の置き換え
description: Adobe  [!DNL Target]  を Adobe Dynamic Media Classic（旧称 Scene7）と統合して、コンテンツライブラリでデジタルアセット管理（DAM）を実現する方法を説明します。
title: Dynamic Media Classic（Scene7）統合を設定するにはどうすればよいですか？
feature: Administration & Configuration
role: Admin
exl-id: 315670ca-a4d1-4808-b3ec-f2ac195c281a
TQID: https://experienceleague.adobe.com/LKbjwlGIxrgaU-2i6Ddn1wi-VjsSmpQPAxYkFHRNOYQ
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: da3860b0-d637-47df-bef0-273751180266
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 402
ht-degree: 83%

---

# Dynamic Media Classic（旧称 Scene7）の設定

[!DNL Adobe Target]を[!DNL Adobe Dynamic Media Classic] （旧[!DNL Scene7]）と統合して、[!UICONTROL &#x200B; コンテンツライブラリ &#x200B;]でデジタルアセット管理（DAM）を提供できます。

{{permissions-update}}

>[!NOTE]
>
>[!DNL Target] を [!DNL Dynamic Media Classic] と統合すると、[!DNL Adobe Experience Cloud] アセットフォルダーにアップロードされたアセットを（アクティビティの一部として）配信できるようになります。 この統合によって、[!DNL Dynamic Media Classic] にアップロードされたすべてのアセットにアクセスして、[!DNL Target] アクティビティで配信できるようになるわけではありません。

既に [!DNL Dynamic Media] アカウントをお持ちの場合、既存の資格情報を入力できます。 アカウントをお持ちでない場合、追加費用なしで、使用制限のある [!DNL Dynamic Media Classic] アカウントを [!DNL Adobe] の担当者にリクエストできます。 このアカウントは、[!DNL Target] での使用のみに用途が限定されています。 このサービスは、ワークフローに画像の入れ替え機能が必要なお客様向けのものです。

<!-- 
>[!NOTE]
>
>A restricted-use, free [!DNL Dynamic Media Classic] account for [!DNL Adobe Target] is no longer supported for new customers or new users. Existing sign-in credentials work as usual. 
-->

この設定が設定されていない場合は、アクティビティ作成ワークフロー内の[!UICONTROL &#x200B; スワップ画像オファー] オプションは使用できません。 この設定を設定した後、画像オファーをスワップ/変更するオプションは、[Visual Experience Composer （VEC）とForm-Based Experience Composer &#x200B;](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D)の両方で使用できます。 以降は、[!DNL Adobe Experience Cloud] からアップロードした画像を含んだ画像オファーを  [!DNL Target] アクティビティで利用できます。

アクティビティの作成中に、オファーやカスタムコードで公開画像 URL を直接参照したい場合は、各自の Web サーバーに画像を展開し、コードで独自の URL を使用する必要があります。 [!DNL Experience Cloud] にアップロードされた画像の公開済み URL を取得して、直接使用したり、[!DNL Target] を使用するターゲティングワークフロー以外で使用したりすることはできません。 契約内容にあるように、この機能は許可されません。

[!DNL Dynamic Media] 内の画像のストレージ URL と最終公開 URL は異なります。画像のストレージリンクを使用してオファーを&#x200B;*作成しないでください*。作成すると、配信が機能しません。 アドビのヘルプドキュメントに記載されているとおりに、画像オファーの機能を使用する必要があります。

[!DNL Dynamic Media Classic]（[!DNL Scene7]）と統合するには、次の情報を指定する必要があります。

1. **[!UICONTROL 管理]** > **[!UICONTROL Scene7設定]**&#x200B;をクリックします。

1. 以下の [!DNL Dynamic Media Classic] アカウント情報を指定します。

   **地域：**&#x200B;[!DNL Dynamic Media] アカウントの地域は、北米、ヨーロッパ、アジアです。

   **アドホックフォルダー：**&#x200B;ターゲットフォルダーの外部に存在し [!DNL Dynamic Media] に手動でアップロードされるコンテンツの場所。

   **メールアドレス：**&#x200B;[!DNL Dynamic Media Classic]（[!DNL Scene7]）へのログインに使用するメールアドレス

   **パスワード：**&#x200B;[!DNL Dynamic Media Classic]（[!DNL Scene7]）へのログインに使用するパスワード

1. [**[!UICONTROL 送信]**] をクリックします。
