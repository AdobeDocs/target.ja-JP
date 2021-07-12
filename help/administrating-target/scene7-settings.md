---
keywords: scene7;dynamic media classic；デジタルアセット管理；アセット；dam；コンテンツライブラリ；画像の置き換え
description: Adobe [!DNL Target] をAdobeDynamic Media Classic(旧称Scene7)と統合して、コンテンツライブラリでデジタルアセット管理(DAM)を提供する方法について説明します。
title: Dynamic Media Classic(Scene7)統合の設定方法を教えてください。
feature: 管理と設定
role: Admin
exl-id: 315670ca-a4d1-4808-b3ec-f2ac195c281a
source-git-commit: be7b5478006af231aae2b78e4a8c0066e3cb4a5b
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 24%

---

# Dynamic Media Classic(旧称Scene7)の設定

[!DNL Adobe Target] を(旧称 [!DNL Adobe Dynamic Media Classic] )と統合し [!DNL Scene7]て、コンテンツライブラリでDigital Asset Management(DAM)を提供 [!UICONTROL できます]。

>[!NOTE]
>
>[!DNL Target]を[!DNL Dynamic Media Classic]と統合すると、[!DNL Adobe Experience Cloud]アセットフォルダーにアップロードされたアセットを（アクティビティの一部として）配信できるようになります。 この統合により、[!DNL Dynamic Media Classic]にアップロードされたすべてのアセットにアクセスして、[!DNL Target]アクティビティで配信できるようになるわけではありません。

既に[!DNL Dynamic Media]アカウントを持っている場合は、既存の資格情報を指定できます。 アカウントをお持ちでない場合は、[!DNL Adobe]担当者に追加料金なしで、使用制限のある[!DNL Dynamic Media Classic]アカウントをリクエストできます。 このアカウントは、[!DNL Target]での使用に制限された目的でのみ使用できます。 このサービスは、ワークフローに画像の入れ替え機能が必要なお客様向けのものです。

<!-- 
>[!NOTE]
>
>A restricted-use, free [!DNL Dynamic Media Classic] account for [!DNL Adobe Target] is no longer supported for new customers or new users. Existing sign-in credentials work as usual. 
-->

この設定が設定されていない場合、アクティビティ作成ワークフロー内の「[!UICONTROL 画像を入れ替えオファー]」オプションは使用できません。 この機能が設定されたら、画像オファーを交換／変更するオプションを     [Visual Experience Composer とフォームベースの Experience Composer](/help/c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D) の両方で利用できます。その後、[!DNL Adobe Experience Cloud]からアップロードされた画像を含む画像オファーを[!DNL Target]アクティビティで使用して活用できます。

アクティビティの作成中に、オファーやカスタムコードで公開画像 URL を直接参照したい場合は、各自の Web サーバーに画像を展開し、コードで独自の URL を使用する必要があります。[!DNL Experience Cloud]にアップロードされた画像の公開済みURLを取得して、[!DNL Target]を使用して直接または外部のターゲティングワークフローを使用する方法はありません。 契約内容にあるように、この機能は許可されません。

ストレージURLと[!DNL Dynamic Media]からの画像の最終公開URLは異なるので、画像のストレージリンクを使用してオファーを&#x200B;*NOT*&#x200B;で作成する必要があります。この場合、配信は機能しません。 アドビのヘルプドキュメントで説明されているように、画像オファー機能を使用する必要があります。

[!DNL Dynamic Media Classic]([!DNL Scene7])と統合するには、次の情報を指定する必要があります。

1. **[!UICONTROL 管理]** / **[!UICONTROL Scene7設定]**&#x200B;をクリックします。

   ![Scene7ページ](/help/administrating-target/assets/scene7.png)

1. 次の[!DNL Dynamic Media Classic]アカウント情報を指定します。

   **地域：**[!DNL Dynamic Media] アカウントの地域は、北米、ヨーロッパ、アジアです。

   **アドホックフォルダー：** ターゲットフォルダーの外部に存在し、に手動でアップロードされるコンテンツの場所 [!DNL Dynamic Media]。

   **電子メールアドレス：** ( [!DNL Dynamic Media Classic] )へのログインに使用する電[!DNL Scene7]子メールアドレス。

   **パスワード：** ( [!DNL Dynamic Media Classic] )へのログインに使用する[!DNL Scene7]パスワード。

1. 「**[!UICONTROL 送信]**」をクリックします。
