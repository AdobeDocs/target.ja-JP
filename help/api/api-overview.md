---
keywords: api;api;api;admin api;配信api;レポートapi;プロファイルapi
description: 管理API、配信API、レポートAPI、プロファイルAPIを含むAdobe TargetAPIを探します。
title: ターゲットAPIおよびSDKドキュメントはどこで入手できますか？
feature: APIs/SDKs
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 1%

---


# Adobe TargetAPIの概要

[!DNL Adobe Target] APIは、次のタイプに従ってグループ化できます。管理API、配信API、レポートAPI、プロファイルAPI

| APIタイプ | 何が可能か | ダウンロードリンク | その他の役立つリンク |
| --- | --- | --- |--- |
| 管理者 | アクティビティ、オーディエンス、オファー、およびその他のオブジェクト（[!DNL Recommendations]エンティティ、条件、デザインなど）を作成、変更、削除します。 [!DNL Recommendations] APIは管理APIの一種です。) | <UL><li>[ターゲット管理APIポストマンコレクション](https://developers.adobetarget.com/api/#admin-postman-collection)</li><li>[RecommendationsAPIポストマンコレクション](https://developers.adobetarget.com/api/recommendations/#section/Postman)</li></ul> | [](https://experienceleague.adobe.com/docs/target-learn/recommendations-api-tutorial/recs-api-overview.html) Adobe TargetTutorialsでRecommendations *APIを使用* |
| 配信 | エンドユーザーに配信するために、最適化され、パーソナライズされたコンテンツを[!DNL Target]から取得します。 | [ターゲット配信API Postmanコレクション](https://developers.adobetarget.com/api/delivery-api/#section/Getting-Started/Postman-Collection) |  |
| レポート | アクティビティ結果とその他のレポート結果を書き出します。 | レポートAPIは、[ターゲット管理APIポストマンコレクション](https://developers.adobetarget.com/api/#admin-postman-collection)に含まれています。 |  |
| プロファイル | Adobe Targetに保存されているユーザプロファイルを取得して変更します。 | [ターゲットプロファイルAPI Postmanコレクション](https://developers.adobetarget.com/api/#profiles) |  |

>[!NOTE]
>
>[!DNL Target]管理API（[!DNL Recommendations] APIを含む）と[!DNL Target]配信APIには、次のような重要な違いがあります。
>
>* 管理APIを使用すると、[!DNL Target] UIでも設定できる[!DNL Target]の様々な要素を設定できます。 管理者APIは認証が必要です。
   >
   >
* 配信APIを使用して、コンテンツを取得できます。 配信APIには認証は必要ありません。
>
>
[!DNL Target]管理APIを使用するには、まずAdobe I/Oを使用して認証を設定する必要があります。詳しくは、*Adobe TargetTutorials*&#x200B;の[認証を設定](https://experienceleague.adobe.com/docs/target-learn/tutorials/apis/configure-io-target-integration.html)を参照してください。
