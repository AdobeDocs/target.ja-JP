---
keywords: 管理;承認者の役割;承認者
description: ' [!DNL Adobe Experience Cloud] への招待をメールで受け取った後、管理者が取るべき最初のタスク  [!DNL Adobe Target]  タスクを実行します。'
title: ' [!DNL Target] の管理を開始するにはどうすればよいですか？'
feature: Administration & Configuration
role: Admin
exl-id: b60236da-20ae-4bab-b261-6a33d2f70e23
source-git-commit: d40c25f75103327e749ad864b17df926cb323be0
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 40%

---

# 管理者の最初の手順

この記事には、管理者が [!DNL Adobe Experience Cloud] ーザーへの招待メールを受信した後に実行す [!DNL Adobe Target] 最初の手順が含まれています。

## [!DNL Target] に招待される {#task_3E0817630774431983FAA3D2CB2E75BD}

[!DNL Adobe Admin Console] のシステム管理者が、あなたを招待して参加 [!DNL Target] せるユーザーとして追加する必要があります。 システム管理者は、ユーザーを 1 つ以上の役割固有のグループに追加する必要があります。 これらのタスクは両方とも、[Adobe Admin Console](https://adminconsole.adobe.com) で実行されます。

詳しくは、*Experience Cloudおよびコアサービスのヘルプ [Experience Cloudユーザーと製品の管理 ](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html) を参照してくだ* い。

システム管理者がこれらの手順を実行すると、招待メールが届きます。

## 招待の受諾 {#task_24FE66659E634B24AB61DB8497772E17}

[!DNL Adobe Experience Cloud] への招待を受け取ったら、招待を受け入れ、ログインして、[!UICONTROL End User License Agreement] （EULA）に同意します。

1. [!DNL Adobe Experience Cloud] への招待を受諾します。
1. Adobe ID をまだ持っていない場合は、作成するよう求められます。 

   Adobe IDを使用している場合は、Adobe IDが認識され、ログインするように求められます。
1. [!UICONTROL Terms of Use] を承認します。
1. これまでに行った作業の概要を確認し、「**[!UICONTROL Continue to Experience Cloud]**」をクリックします。
1. [!DNL Adobe Experience Cloud] にログインし、「**[!UICONTROL Link Account]**」をクリックします。

   >[!NOTE]
   >
   >アカウントをリンクしないと、[!DNL Target] にアクセスできません。

   すべて [!UICONTROL Experience Cloud] 製品がリンクページに表示されます。 `Link Target` をクリックし、[!DNL Target] のユーザー名とパスワードを入力して [!DNL Target] にアクセスします。
1. **[!UICONTROL Continue to Experience Cloud]** をクリックします。

   この時点では、リンクできる権限を持ったグループはまだ設定されていません。
1. 必要に応じて、[!DNL Adobe Experience Cloud] の紹介ビデオを見ます。
1. 新しい権限と製品へのアクセスを確認するために、[!DNL Adobe Experience Cloud] からログアウトし、再びログインします。
1. 次の手順である[承認者の役割の割り当て](/help/main/administrating-target/start-target.md#task_15CAA437A71444E2932B333D5E66A3C7)に進みます。

## 承認者の役割の割り当て {#task_15CAA437A71444E2932B333D5E66A3C7}

[!DNL Adobe Experience Cloud] への招待を承諾してログインしたら、[!DNL Target] が [!DNL Experience Cloud] アカウントに追加されたことを確認してから、[!DNL Target] の [!UICONTROL Approver] ロールを自分に割り当てます。

お客様の組織が [Target Standard](/help/main/c-intro/intro.md#section_ACD5EFF17AAB4E979CBEFA0145CCD905) ライセンスを所有している場合、*ユーザー*&#x200B;の[役割および権限の指定](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions)を参照してください。

お客様の組織が [Target Premium](/help/main/c-intro/intro.md#premium) ライセンスを所有している場合、*エンタープライズ権限の設定*&#x200B;の[手順 6：役割および権限の指定](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md#section_8C425E43E5DD4111BBFC734A2B7ABC80)を参照してください。

次の手順は、[!DNL Target Standard] と [!DNL Target Premium] でユーザーを設定することです。 詳しくは、[ユーザー管理](/help/main/administrating-target/c-user-management/user-management.md)を参照してください。

>[!IMPORTANT]
>
>[!DNL Adobe Admin Console] の [!UICONTROL Product Admin] 権限または [!UICONTROL System Admin] 権限を持つユーザーは、[!DNL Target] の役割に関係なく、[!DNL Target] の [!UICONTROL Administration] ページのすべての設定を編集または変更できます。[!DNL Adobe Admin Console] で [!UICONTROL Product Admin] 権限または [!UICONTROL System Admin] 権限を持たないユーザーは、これらの変更を行うために特定の [!DNL Target] の役割が必要です。
