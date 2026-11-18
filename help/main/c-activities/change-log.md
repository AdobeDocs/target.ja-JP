---
keywords: アクティビティの変更ログ；変更ログ
description: Adobe [!DNL Target]のアクティビティの変更ログにアクセスして、アクティビティを変更したユーザーと変更がいつ発生したかの記録を表示します。
title: アクティビティの変更ログを表示するにはどうすればよいですか？
feature: Activities
exl-id: 72a901c1-4fba-4044-b72b-393cab56b936
TQID: 'https://experienceleague.adobe.com/YmadzVwbj4Hy1bk3Q7a0hp9oZ7-lSgl12ImQaEsiDwU'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: 6efa6b7a-8062-5c41-aef4-b4853cc306ae
    internal-label: Activities
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
source-git-commit: 8c6f23b495228ab930e6649aa2f9e6dae506cae2
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 10%
---
# アクティビティの変更ログ {#change-log}

>[!BEGINSHADEBOX]

**このページ：** アクティビティに対して実行されたアクション、実行したユーザー、およびいつ実行したかを表示する方法を説明します。

>[!ENDSHADEBOX]

[!DNL Adobe Target] **[!UICONTROL 変更ログ]**&#x200B;には、変更された内容、変更を加えたユーザー、変更が発生した日時など、アクティビティに対して実行されたアクションが記録されます。 アクティビティの履歴が明確になり、リアルタイムのインサイト用に&#x200B;**[!UICONTROL 変更ログ]** ページが入力されます。

**[!UICONTROL Change Log]** ページにアクセスするには：

1. 「**[!UICONTROL アクティビティ]**」をクリックし、リスト内のアクティビティをクリックします。
1. 左側のパネルで「**[!UICONTROL Change Log]**」をクリックします。

   このページには、実行されたアクション、アクションの日付、およびアクティビティが作成、更新、アクティブ化、非アクティブ化されるたびに実行したユーザーが一覧表示されます。 アクティビティで使用したカスタムターゲットとオファーに関する変更も一覧表示されます。

   ![&#x200B; ログメニューの変更](assets/change_logs.png)

1. アクションを昇順または降順で一覧表示するには、**[!UICONTROL 日付]**&#x200B;列ヘッダーをクリックします。

1. ステータスの変更を確認するには、ページを更新します。

## Target監査ログ API

* [リビジョン：最終作成者の名前と変更後のタイムスタンプで監査ログを取得します](https://developer.adobe.com/target/administer/admin-api/#tag/Revisions){target=_blank}
* [アクティビティの変更ログのリスト](https://developer.adobe.com/target/administer/admin-api/#tag/Activities/operation/getChangelog){target=_blank}
