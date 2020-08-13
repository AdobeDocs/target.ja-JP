---
keywords: api;apis;admin api;delivery api;reporting api;profile api
description: 管理API、配信API、レポートAPI、プロファイルAPIなど、Adobe TargetAPIに関する情報です。
title: Adobe TargetAPIの概要
feature: api
topic: APIs
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 1%

---


# Adobe TargetAPIの概要

[!DNL Adobe Target] APIはタイプに従ってグループ化できます。

| APIタイプ | 何が可能か | ダウンロードリンク | その他の役立つリンク |
| --- | --- | --- |--- |
| 管理者 | アクティビティ、オーディエンス、オファー、およびその他のオブジェクト（エンティティ、基準、設計などを含む）を作成、変更、削除します。 [!DNL Recommendations] APIは管理APIの一種です。) [!DNL Recommendations] | <UL><li>[ターゲット管理APIポストマンコレクション](https://developers.adobetarget.com/api/#admin-postman-collection)</li><li>[RecommendationsAPIポストマンコレクション](https://developers.adobetarget.com/api/recommendations/#section/Postman)</li></ul> | [](https://docs.adobe.com/content/help/en/target-learn/recommendations-api-tutorial/recs-api-overview.html) Adobe TargetTutorialsでのRecommendationsAPIの使用 ** |
| 配信 | エンドユーザーに対して配信を行うた [!DNL Target] めに、最適化され、パーソナライズされたコンテンツを取得します。 | [ターゲット配信API Postmanコレクション](https://developers.adobetarget.com/api/delivery-api/#section/Getting-Started/Postman-Collection) |  |
| レポート | アクティビティ結果とその他のレポート結果を書き出します。 | レポートAPIは、 [ターゲット管理API Postmanコレクションに含まれています](https://developers.adobetarget.com/api/#admin-postman-collection)。 |  |
| プロファイル | Adobe Targetに保存されているユーザプロファイルを取得して変更します。 | [ターゲットプロファイルAPI Postmanコレクション](https://developers.adobetarget.com/api/#profiles) |  |

>[!NOTE]
>
>管理API（APIを含む）と [!DNL Target] 配信APIには、次のような重要な違いがあり [!DNL Recommendations][!DNL Target] ます。
>
>* 管理APIを使用すると、 [!DNL Target] UIで設定できる様々な設定を行うこ [!DNL Target] とができます。 管理者APIは認証が必要です。
   >
   >
* 配信APIを使用して、コンテンツを取得できます。 配信APIには認証は必要ありません。
>
>
管理APIを使用するには、まずAdobeI/Oを使用して認証を設定する必要があります。 [!DNL Target] 詳しくは、「 [Adobe TargetTutorialsでの認証の](https://docs.adobe.com/content/help/en/target-learn/tutorials/apis/configure-io-target-integration.html) 設定 *」を参照してください*。
