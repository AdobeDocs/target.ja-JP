---
keywords: Overview and Reference
description: Target を Adobe Campaign と共に使用して、電子メールコンテンツを最適化します。
title: Target と Adobe Campaign の統合
feature: null
topic: Standard
uuid: 1a5b70e6-d501-4b52-bec8-4ae2c419d331
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 51%

---


# Target と Adobe Campaign の統合{#integrate-target-with-adobe-campaign}

Use [!DNL Target] with [!DNL Adobe Campaign] to optimize email content.

To optimize your email content--for example, to display different offers for male and female recipients--you can create a redirect offer in [!DNL Target], then use [!DNL Adobe Campaign] to manage the email offers.

電子メールを開いた際に、統合が実施されます。When the customer opens the email, a call is made to [!DNL Target] and a dynamic version of the content appears. コンテンツは、すべてのブラウザーでサポートされる静的な画像で構成されます。[!DNL Target] は、オーディエンスまたはセッションレベルでオファーに対する反応を追跡し、そのデータは、 のレポートで利用できます。[!DNL Target]

Target は、次のデータを追跡できます。

* ユーザーエージェント
* IP アドレス
* 地理的な場所
* Target で訪問者の ID に関連付けられたセグメント（法的な承認を必要とします）
* Data from [!DNL Campaign] Datamart

いくつかの制限があります。

* 使用できるのは画像のみなので、コンテンツはパーソナライズできません。
* Tracking is not consolidated in [!DNL Adobe Campaign].
* 統一されたユーザーエクスペリエンスはありません。

   You must use both [!DNL Target] and [!DNL Campaign] to set up different parts of the integration:

   *  の rawbox およびエクスペリエンス[!DNL Target]
   >[!NOTE]
   >
   >rawboxおよびを使用する場合は、「ターゲットに対してmbox呼び出しを送信する権限を持つホストを指定する許可リストの [!DNL Target]作成」の重要なセキュリティに関する通知を参照してください [](/help/administrating-target/hosts.md#allowlist)。

   * The delivery in [!DNL Campaign]



## 始める前に {#section_FF19BF1BCA064260930BF6C141313B0E}

Before you use [!DNL Adobe Campaign] to set up your targeted email offers, set up the following in [!DNL Target]:

* Two or more [!DNL Target] redirect offers

   See [Create redirect offer](/help/c-experiences/c-manage-content/offer-redirect.md).
* 各オファーのエクスペリエンスと目的の[成功指標](/help/c-activities/r-success-metrics/success-metrics.md)を含む Target アクティビティ

   [URL にリダイレクト](/help/c-experiences/c-visual-experience-composer/redirect-offer.md)を参照してください。

Start the activity in [!DNL Target] before setting up the [!DNL Campaign] portion of the integration.

## Adobe Campaign 電子メールに Target オファーを含める {#section_B201BBE27A704E18AF0D553F35695837}

1. Create an email in [!DNL Adobe Campaign].
1. 電子メールのプロパティで、**[!UICONTROL 含める]**／**[!UICONTROL Adobe Target によって提供される動的画像]**&#x200B;をクリックします。
1. 共有アセットからデフォルト画像を選択します。
1. 場所（rawbox）を指定します。
1. 受信者の性別など、その他の決定パラメーターを追加します。
1. 各オファーに少なくとも 1 人の受信者を選択して（この場合、男性および女性）、電子メールをプレビューします。
1. In [!DNL Campaign], define the [!DNL Target] Edge server you are using to control the activity and the name of the tenant.
1. Specify the external account used for the [!DNL Adobe Experience Cloud] so you can access the resources in the [!DNL Experience Cloud].

For more information, refer to the [!DNL Adobe Campaign] documentation.
