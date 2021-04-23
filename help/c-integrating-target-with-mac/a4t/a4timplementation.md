---
keywords: A4T;Adobe Analytics;Analytics ベースのアクティビティ;Analytics レポートスイート;レポートスイート;Analytics Target 統合;レポートスイートの設定
description: ' [!DNL Target] (A4T) in your Adobe [!DNL Target] およびAdobe Analyticsの各ソリューションに対してAnalyticsを実装するために必要な手順に従います。'
title: Analytics for [!DNL Target] (A4T)の実装方法
feature: Analytics for Target（A4T）
exl-id: b5269b9e-01ef-449a-bb03-3dcc2cd68af7
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '881'
ht-degree: 28%

---

# [!DNL Target]の導入の分析

[!DNL Adobe Analytics]を[!DNL Adobe Target]のレポートソースとして実装する場合(A4T)には、いくつかの手順が必要です。

## 導入手順{#section_73961BAD5BB4430A95E073DE5C026277}

次の節では、この統合をサイトに導入するために必要な手順について説明します。

## 手順1:Analyticsとターゲットのプロビジョニングのリクエスト

[!DNL Analytics]を[!DNL Target]のレポートソースとして実装した後、[!DNL Analytics]と[!DNL Target]のプロビジョニングを行う必要があります。 [プロビジョニングの依頼にはこのフォームを使用します](http://www.adobe.com/go/audiences)。

## 手順 2： ユーザー権限を設定します。

[!DNL Target]で[!DNL Analytics]ベースのアクティビティを作成するには、ユーザーアカウントの要件が満たされている必要があります。 [ユーザー権限の要件](/help/c-integrating-target-with-mac/a4t/account-reqs.md)を参照してください。

## 手順 3： Experience Cloud 訪問者 ID サービスを導入します。

訪問者 ID サービスによって、[!DNL Adobe Experience Cloud] ソリューション全体でユーザーを特定することができます。Experience Cloud訪問者IDの必要なバージョンを実装するか、そのバージョンに移行します。 詳しくは、[実装する前に](/help/c-integrating-target-with-mac/a4t/before-implement.md)の「導入に必要な条件」を参照してください。

*Experience Cloud訪問者IDサービス*&#x200B;のドキュメントで、[ターゲット用のExperience CloudIDサービスの実装](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-target.html)を参照してください。

## 手順 4： AppMeasurement for JavaScript または s_code を更新します。

appMeasurement.jsの必要なバージョンを実装するか、そのバージョンに移行します。 詳しくは、[実装する前に](/help/c-integrating-target-with-mac/a4t/before-implement.md)の「導入に必要な条件」を参照してください。

新しい導入方法については、『*Analytics導入ガイド*』の「[JavaScript導入の概要](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html)」を参照してください。

移行の場合は、『*Analytics導入ガイド*』の「[JavaScript版AppMeasurement](https://experienceleague.adobe.com/docs/analytics/implementation/js/migrate-from-hcode.html)への移行」を参照してください。

## 手順5:at.jsのダウンロードと更新

実稼動アカウントを使用して、必要なバージョンのat.jsを実装するか、そのバージョンに移行します。 コードの修正は必要ありません。

詳しくは、[実装する前に](/help/c-integrating-target-with-mac/a4t/before-implement.md)の「導入に必要な条件」を参照してください。

## 手順6:at.jsのホスト

以前にat.jsをデプロイしている場合は、既存のファイルを最新バージョンに置き換えることができます。 詳しくは、[実装する前に](/help/c-integrating-target-with-mac/a4t/before-implement.md)の「導入に必要な条件」を参照してください。

配置していない場合は、最新のファイルを Visitor ID サービスおよび AppMeasurement for JavaScript のファイルとともにホストします。これらのファイルは、サイトのすべてのページからアクセス可能な Web サーバーでホストする必要があります。これらのファイルへのパスを、次の手順で使用します。

## 手順7:すべてのサイトページでat.jsを参照{#step7}

各ページのタグ内に次のコードを追加して、VisitorAPI.jsの下にat.jsを含めます。

at.js の場合：

```javascript
<script language="JavaScript" type="text/javascript"
src="http://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/at.js"></script>
```

VisitorAPI.jsは、at.jsの前に読み込む必要があります。 既存のat.jsまたはmbox.jsファイルを更新する場合は、読み込み順序を確認してください。

導入の観点から、[!DNL Target]と[!DNL Analytics]の統合のデフォルト設定は、ページから渡されたSDIDを使用して、バックエンドで[!DNL Target]と[!DNL Analytics]のリクエストを自動的に結合します。

[!DNL Target]に関連する解析データを、レポートのためにいつ、どのように[!DNL Analytics]に送信するかを制御できます。 [!DNL Target]と[!DNL Analytics]オプトインをSDID経由で自動的に結合しないデフォルト設定を使用する場合は、**window.targetGlobalSettings**&#x200B;を介して、**analyticsLogging = client_side**&#x200B;を設定します。 注意：2.1 未満のバージョンでは、この方法をサポートしていません。

次に例を示します。

```javascript
window.targetGlobalSettings = {
  analyticsLogging: "client_side"
};
```

この設定はグローバルな効果を持ちます。つまり、at.jsによるすべての呼び出しに&#x200B;**analyticsLogging:[!DNL Target]リクエスト内で送信される&quot;client_side&quot;**。また、リクエストごとにanalyticsペイロードが返されます。 このオプションを設定すると、返されるペイロードの形式は次のようになります。

```javascript
"analytics": {
   "payload": {
      "pe": "tnt",
      "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
   }
}
```

ペイロードは、[Data Insertion API](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html)を介してAnalyticsに転送できます。 自動配分と自動ターゲットアクティビティの場合は、sessionIdも転送する必要があります。 詳しくは、*Adobe TargetSDK*&#x200B;ガイドの[ターゲット用のAnalytics(A4T)レポート](https://adobetarget-sdks.gitbook.io/docs/integration-with-experience-cloud/analytics-for-target-a4t-reporting)を参照してください。

グローバル設定が不要で、よりオンデマンドの方法をお勧めする場合は、**analyticsLogging:&quot;client_side&quot;**。 [](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md)Analyticsペイロードはこの呼び出しに対してのみ返され、[!DNL Target]バックエンドはペイロードを[!DNL Analytics]に転送しません。 このアプローチを追跡すると、at.js [!DNL Target]リクエストはすべてデフォルトでペイロードを返しますが、必要で指定された場合にのみ返します。

次に例を示します。

```javascript
adobe.target.getOffers({
      request: {
        experienceCloud: {
          analytics: {
            logging: "client_side"
          }
        },
        prefetch: {
          mboxes: [{
            index: 0,
            name: "a1-serverside-xt"
          }]
        }
      }
    })
    .then(console.log)
```

この呼び出しは、分析ペイロードを抽出できる応答を呼び出します。

応答は以下のようになります。

```javascript
{
  "prefetch": {
    "mboxes": [{
      "index": 0,
      "name": "a1-serverside-xt",
      "options": [{
        "content": "<img src=\"http://s7d2.scene7.com/is/image/TargetAdobeTargetMobile/L4242-xt-usa?tm=1490025518668&fit=constrain&hei=491&wid=980&fmt=png-alpha\"/>",
        "type": "html",
        "eventToken": "n/K05qdH0MxsiyH4gX05/2qipfsIHvVzTQxHolz2IpSCnQ9Y9OaLL2gsdrWQTvE54PwSz67rmXWmSnkXpSSS2Q==",
        "responseTokens": {
          "profile.memberlevel": "0",
          "geo.city": "bucharest",
          "activity.id": "167169",
          "experience.name": "USA Experience",
          "geo.country": "romania"
        }
      }],
      "analytics": {
        "payload": {
          "pe": "tnt",
          "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
        }
      }
    }]
  }
}
```

次に、ペイロードは[Data Insertion API](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html)を介して[!DNL Analytics]に転送できます。

## 手順 8：実装を検証します。{#step8}

JavaScript ライブラリを更新した後でページをロードして、 呼び出しの `mboxMCSDID`[!DNL Target] パラメーター値が ページビュー呼び出しの `sdid`[!DNL Analytics] パラメーター値と一致していることを確認します。

呼び出しの順序が必ずしも予測可能とは限らない場合、これらの値がシングルページアプリ(SPA)で一致することを確認することが特に重要です。

**注意：A4T** が正しく機能するには、これらの値の一致が必要です。

## 手順 9： （オプション）以前の統合コードを削除します。

Adobeでは、導入を簡素化し、システム間の不一致を解消する必要をなくすため、以前の統合を削除することをお勧めします。 以前のSCからT&amp;Tへの統合用に展開したコード（`mboxLoadSCPlugin`を含む）はすべて削除できます。

## 手順 10： Analytics を Target のレポートソースとして使用するためのオプションを有効にします。

[!DNL Target]で、**[!UICONTROL 管理/Visual Experience Composer]**&#x200B;をクリックし、「**[!UICONTROL アクティビティごとに選択]**」または「**[!UICONTROL Adobe Analytics]**」を選択して、オプションを有効にします。

* **[!UICONTROL 「アクティビティごとに選択」を選択すると、各アクティビティの作成時に か かを選択できます。]**[!DNL Target][!DNL Analytics]
* **[!UICONTROL 「Adobe 」を選択すると、作成したすべてのアクティビティのレポートソースが Analytics に設定されます。]**[!DNL Analytics]
