---
keywords: 管理;承認者の役割;承認者
description: 最初のタスクのAdobe [!DNL Target] 管理者は、Adobe Experience Cloudへの招待メールを受け取った後に、を実行する必要があります。
title: Target の管理の基本を学ぶには、どこから始めればよいですか？
feature: Administration & Configuration
role: Admin
exl-id: b60236da-20ae-4bab-b261-6a33d2f70e23
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '406'
ht-degree: 82%

---

# 管理者の最初の手順

この記事では、最初の手順について説明します [!DNL Adobe Target] 管理者は、 [!DNL Adobe Experience Cloud].

## への招待 [!DNL Target] {#task_3E0817630774431983FAA3D2CB2E75BD}

[!DNL Adobe Admin Console] のシステム管理者は、参加させたいひとを招待することで [!DNL Target] にユーザーとして追加する必要があります。次に、システム管理者が、1 つ以上の役割用のグループに追加する必要があります。これらの作業は、共に [Adobe Admin Console](https://adminconsole.adobe.com) で実行されます。

詳しくは、 [Experience Cloudユーザーと製品を管理する](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html) 内 *Experience Cloudとコアサービスのヘルプ*.

システム管理者がこれらの手順を実行すると、招待の電子メールが送信されます。

## 招待の受諾 {#task_24FE66659E634B24AB61DB8497772E17}

[!DNL Adobe Experience Cloud] への招待メールを受け取ったら、招待を受諾し、ログインして、エンドユーザー使用許諾契約（EULA）に同意します。

1. [!DNL Adobe Experience Cloud] への招待を受諾します。
1. Adobe ID をまだ持っていない場合は、作成するよう求められます。 

   Adobe ID を持っている場合は、その Adobe ID が認識され、サインインするよう求められます。
1. 利用条件に同意します。
1. ここまでおこなった操作のまとめを確認し、「**[!UICONTROL Experience Cloud を続行]**」をクリックします。
1. Adobe Experience Cloud にログインし、「**[!UICONTROL アカウントにリンク]**」をクリックします。

   >[!NOTE]
   >
   >アカウントをリンクしないと、[!DNL Target] にアクセスできません。

   リンクページにすべての Experience Cloud 製品が表示されます。「`Link Target`」をクリックし、Target のユーザー名とパスワードを入力して、Target Standard にアクセスします。
1. 「**[!UICONTROL Experience Cloud を続行]**」をクリックします。

   この時点では、リンクできる権限を持ったグループはまだ設定されていません。
1. 必要に応じて、[!DNL Adobe Experience Cloud] の紹介ビデオを見ます。
1. 新しい権限と製品へのアクセスを確認するために、[!DNL Adobe Experience Cloud] からログアウトし、再びログインします。
1. 次の手順である[承認者の役割の割り当て](/help/main/administrating-target/start-target.md#task_15CAA437A71444E2932B333D5E66A3C7)に進みます。

## 承認者の役割の割り当て {#task_15CAA437A71444E2932B333D5E66A3C7}

[!DNL Adobe Experience Cloud] への招待を受諾してログインしたら、自分の [!DNL Experience Cloud] アカウントに Target が追加されていることを確認し、自分自身に [!DNL Target] の[!UICONTROL 承認者]の役割を割り当てます。

お客様の組織が [Target Standard](/help/main/c-intro/intro.md#section_ACD5EFF17AAB4E979CBEFA0145CCD905) ライセンスを所有している場合、*ユーザー*&#x200B;の[役割および権限の指定](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions)を参照してください。

お客様の組織が [Target Premium](/help/main/c-intro/intro.md#premium) ライセンスを所有している場合、*エンタープライズ権限の設定*&#x200B;の[手順 6：役割および権限の指定](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md#section_8C425E43E5DD4111BBFC734A2B7ABC80)を参照してください。

次の手順では、Target Standard および Target Premium でユーザーを設定します。詳しくは、[ユーザー管理](/help/main/administrating-target/c-user-management/user-management.md)を参照してください。
