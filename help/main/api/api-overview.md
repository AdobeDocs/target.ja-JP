---
keywords: API;API；管理 API；配信 API；レポート API；プロファイル API
description: 検索Adobe [!DNL Target] API（管理 API、配信 API、レポート API、プロファイル API を含む）
title: 入手方法 [!DNL Target] API および SDK のドキュメント
feature: APIs/SDKs
role: Developer
exl-id: 2a0232cc-9a6a-42f4-afb6-4b3e2b13939c
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 1%

---

# Adobe [!DNL Target] API の概要

[!DNL Adobe Target] API は、次のタイプに従ってグループ化できます。管理 API、配信 API、レポート API、プロファイル API。

| API タイプ | 機能 | ダウンロードリンク | その他の役立つリンク |
| --- | --- | --- |--- |
| 管理者 | アクティビティ、オーディエンス、オファーおよびその他のオブジェクト ( [!DNL Recommendations] エンティティ、条件、デザインなど。 この [!DNL Recommendations] API は管理 API の一種です。) | <UL><li>[Target 管理 API Postman コレクション](https://developers.adobetarget.com/api/#admin-postman-collection)</li><li>[Recommendations API Postman コレクション](https://developers.adobetarget.com/api/recommendations/#section/Postman)</li></ul> | [Recommendations API の使用](https://experienceleague.adobe.com/docs/target-learn/recommendations-api-tutorial/recs-api-overview.html) in *Adobe TargetTutorials* |
| 配信 | 次の場所から最適化され、パーソナライズされたコンテンツを取得 [!DNL Target] エンドユーザーに配信するために使用します。 | [Target 配信 API Postman コレクション](https://developers.adobetarget.com/api/delivery-api/#section/Getting-Started/Postman-Collection) |  |
| レポート | アクティビティの結果と他のレポート結果をエクスポートします。 | レポート API は [Target 管理 API Postman コレクション](https://developers.adobetarget.com/api/#admin-postman-collection). |  |
| プロファイル | Adobe Targetに保存されているユーザープロファイルを取得して変更します。 | [Target プロファイル API Postman コレクション](https://developers.adobetarget.com/api/#profiles) |  |

>[!NOTE]
>
>～間には重要な区別がある [!DNL Target] 管理 API( [!DNL Recommendations] API) および [!DNL Target] 配信 API:
>
>* 管理 API を使用すると、 [!DNL Target] これは、 [!DNL Target] UI 管理 API には認証が必要です。
>
>* Delivery API を使用すると、コンテンツを取得できます。 配信 API には認証は必要ありません。
>
>使用する [!DNL Target] 管理 API を使用する場合、最初に認証を使用して認証を設定する必要があります。Adobe I/O詳しくは、 [認証の設定](https://experienceleague.adobe.com/docs/target-learn/tutorials/apis/configure-io-target-integration.html) in *Adobe TargetTutorials*.
