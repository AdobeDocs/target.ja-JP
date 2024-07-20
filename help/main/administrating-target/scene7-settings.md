---
keywords: scene7;dynamic media classic;デジタルアセット管理;アセット;dam;コンテンツライブラリ;画像の置き換え
description: Adobe  [!DNL Target]  を Adobe Dynamic Media Classic（旧称 Scene7）と統合して、コンテンツライブラリでデジタルアセット管理（DAM）を実現する方法を説明します。
title: Dynamic Media Classic（Scene7）統合を設定するにはどうすればよいですか？
feature: Administration & Configuration
role: Admin
exl-id: 315670ca-a4d1-4808-b3ec-f2ac195c281a
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 85%

---

# Dynamic Media Classic（旧称 Scene7）の設定

[!DNL Adobe Target] を [!DNL Adobe Dynamic Media Classic] （旧称 [!DNL Scene7]）と統合して、[!UICONTROL Content Library] でデジタルアセット管理（DAM）を実現できます。

>[!NOTE]
>
>[!DNL Target] を [!DNL Dynamic Media Classic] と統合すると、[!DNL Adobe Experience Cloud] アセットフォルダーにアップロードされたアセットを（アクティビティの一部として）配信できるようになります。この統合によって、[!DNL Dynamic Media Classic] にアップロードされたすべてのアセットにアクセスして、[!DNL Target] アクティビティで配信できるようになるわけではありません。

既に [!DNL Dynamic Media] アカウントをお持ちの場合、既存の資格情報を入力できます。アカウントをお持ちでない場合、追加費用なしで、使用制限のある [!DNL Dynamic Media Classic] アカウントを [!DNL Adobe] の担当者にリクエストできます。このアカウントは、[!DNL Target] での使用のみに用途が限定されています。このサービスは、ワークフローに画像の入れ替え機能が必要なお客様向けのものです。

<!-- 
>[!NOTE]
>
>A restricted-use, free [!DNL Dynamic Media Classic] account for [!DNL Adobe Target] is no longer supported for new customers or new users. Existing sign-in credentials work as usual. 
-->

この機能が設定されていない場合は、アクティビティ作成ワークフロー内で [!UICONTROL Swap Image offer] のオプションを利用することはできません。 この設定が完了すると、画像オファーを入れ替える/変更するオプションが [Visual Experience Composer （VEC）とフォームベースの Experience Composer](/help/main/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D) の両方で使用できるようになります。 以降は、[!DNL Adobe Experience Cloud] からアップロードした画像を含んだ画像オファーを  [!DNL Target] アクティビティで利用できます。

アクティビティの作成中に、オファーやカスタムコードで公開画像 URL を直接参照したい場合は、各自の Web サーバーに画像を展開し、コードで独自の URL を使用する必要があります。[!DNL Experience Cloud] にアップロードされた画像の公開済み URL を取得して、直接使用したり、[!DNL Target] を使用するターゲティングワークフロー以外で使用したりすることはできません。契約内容にあるように、この機能は許可されません。

[!DNL Dynamic Media] 内の画像のストレージ URL と最終公開 URL は異なります。画像のストレージリンクを使用してオファーを&#x200B;*作成しないでください*。作成すると、配信が機能しません。アドビのヘルプドキュメントに記載されているとおりに、画像オファーの機能を使用する必要があります。

[!DNL Dynamic Media Classic]（[!DNL Scene7]）と統合するには、次の情報を指定する必要があります。

1. **[!UICONTROL Administration]**／**[!UICONTROL Scene7 Configuration]**&#x200B;をクリックします。

   ![Scene7 ページ](/help/main/administrating-target/assets/scene7.png)

1. 以下の [!DNL Dynamic Media Classic] アカウント情報を指定します。

   **地域：**[!DNL Dynamic Media] アカウントの地域は、北米、ヨーロッパ、アジアです。

   **アドホックフォルダー：**&#x200B;ターゲットフォルダーの外部に存在し [!DNL Dynamic Media] に手動でアップロードされるコンテンツの場所。

   **メールアドレス：**[!DNL Dynamic Media Classic]（[!DNL Scene7]）へのログインに使用するメールアドレス

   **パスワード：**[!DNL Dynamic Media Classic]（[!DNL Scene7]）へのログインに使用するパスワード

1. **[!UICONTROL Submit]** をクリックします。
