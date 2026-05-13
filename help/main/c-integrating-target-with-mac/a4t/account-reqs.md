---
keywords: レポートソースとしてのAnalytics;a4t;A4T；要件
description: Analytics for [!DNL Target]  （A4T）を使用して、Adobe [!DNL Target] でAdobe Analytics ベースのアクティビティを作成するために必要なユーザーアカウント要件を設定する方法について説明します。
title: A4Tに必要なユーザー権限の要件はどれですか？
feature: Analytics for Target (A4T)
solution: Target,Analytics
exl-id: f56fc525-92da-4814-86c1-18b3a2765f37
TQID: https://experienceleague.adobe.com/SGNIoARqe3yN4WvKF4JPIp0t0JCMiSgj--zrjt-ZXJQ
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3aid: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c93393a4-e558-47e1-992e-c91ed4d480ce
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 298
ht-degree: 37%

---

# ユーザー権限の要件

（A4T）で [!DNL Adobe Analytics]のベースとなるアクティビティ[!DNL Adobe Target] を作成するためのユーザーアカウント要件に関する情報です。

[!DNL Analytics]アクティビティを定義するときは、レポートスイートを選択する前に、 [!DNL Analytics]ユーザーアカウントと[!DNL Target]ユーザーアカウントの両方が必要になります。

次の節の説明に従って、ユーザーアカウントを設定する必要があります。

## Adobe Experience Cloud {#section_3931A2FAD38F4A4FA92CC77B92AF3F0D}

[!DNL Adobe Experience Cloud] [Admin Console](https://adminconsole.adobe.com)で次のタスクを実行します。

### ソリューションアカウントを Adobe ID にリンクします。

あなたの[!DNL Analytics]および[!DNL Target]のユーザーアカウントは Adobe ID にリンクされている必要があります。

詳しくは、[組織とアカウントリンク ](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=en)を参照してください。

### Experience Cloud グループのメンバーシップを設定します。

あなたは[!DNL Analytics] と [!DNL Target]にアクセスできる 1 つ以上の[!DNL Experience Cloud]グループのメンバーでなければなりません。

詳しくは、[Experience Cloud ユーザーと製品の管理](https://experienceleague.adobe.com/ja/docs/core-services/interface/administration/admin-tool-experience-cloud)を参照してください。

## Adobe Analytics {#section_8F404FDE9A634534AB0AA4CB3075582B}

特定のレポートスイートでA4Tを使用するには、そのレポートスイートにアクセスし、[!DNL Web Services Access] グループへのアクセス権を付与する必要があります。

1. **[!UICONTROL Admin Console]**&#x200B;で、[!DNL Analytics]製品プロファイルをクリックし、「**[!UICONTROL Permissions]**」タブをクリックします。

   次に、プロファイルがアクセスできるレポートスイートを確認できます。

1. [!DNL Target]でアクセス権を持つレポートスイートが、自分が属している製品プロファイルにリストされているレポートスイートのいずれかであることを確認します。

   次の図は、すべてのレポートスイートにアクセスできる製品プロファイルの例です。

   ![Admin Console権限タブ ](/help/main/c-integrating-target-with-mac/a4t/assets/permissions-tab.png)

1. [!UICONTROL Web Services Access] グループへのアクセスを構成します。

   [!DNL Target]のレポートソースとして[!DNL Analytics]を使用するには、[!DNL Analytics]の[!UICONTROL Web Services Access] グループへのアクセスが必要です。


## アドビ [!DNL Target] {#section_26BA212D8D40443E9EE2AB327091425C}

追加の権限は必要ありません。
